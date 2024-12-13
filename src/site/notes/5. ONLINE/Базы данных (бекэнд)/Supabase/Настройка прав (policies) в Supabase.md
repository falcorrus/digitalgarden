---
{"dg-publish":true,"permalink":"/5. ONLINE/Базы данных (бекэнд)/Supabase/Настройка прав (policies) в Supabase/","created":"2024-11-22T12:47:39.188-03:00","updated":"2024-12-13T18:00:08.535-03:00"}
---


## Обучающие видео
Много про RLS (права на строки, на столбцы, MFA/multi-factor auth) [Supabase Is A LOT More POWERFUL Than You Thought! - YouTube](https://www.youtube.com/watch?v=Jipdn8SLwAI)

## Разрешаем только пользоватям, чьё id в таблице users совпадает с uuid_owner в orders
В таблице *order* заводим столбец *uuid_owner*
В таблице *users* нужен столбец *id*
Делаем, что доступ только, если данные в них совпадают

`(EXISTS ( SELECT 1`
`FROM (users u`
`JOIN orders o ON ((u.id = o.uuid_owner)))`
`WHERE (u.id = auth.uid())))`


## Доступ для Админа.
В таблице *users* в столбце *tariff* должно быть *admin*
`(EXISTS ( SELECT 1`
`FROM users`
`WHERE ((users.id = auth.uid()) AND (users.tariff = 'admin'::text))))`


## Все возможные варианты
CREATE TABLE companies (
 id SERIAL PRIMARY KEY,
 name TEXT NOT NULL
);

CREATE TABLE users (
 id UUID PRIMARY KEY,
 email TEXT NOT NULL UNIQUE,
 company_id INTEGER REFERENCES companies(id),
 role TEXT CHECK (role IN ('User', 'Admin')) DEFAULT 'User'
);

CREATE TABLE todos (
 id SERIAL PRIMARY KEY,
 title TEXT NOT NULL,
 description TEXT,
 completed BOOLEAN DEFAULT FALSE,
 company_id INTEGER REFERENCES companies(id),
 user_id UUID REFERENCES users(id),
 created_at TIMESTAMP DEFAULT now() 
 );

INSERT INTO companies (name) VALUES ('Company A'), ('Company B');

ALTER TABLE todos ENABLE ROW LEVEL SECURITY;

CREATE POLICY "Company-based select access"
ON todos
FOR SELECT
USING (
 company_id = (SELECT company_id FROM users WHERE id = auth.uid()) 
);

CREATE POLICY "Company-based insert access"
ON todos
FOR INSERT
WITH CHECK (
 company_id = (SELECT company_id FROM users WHERE id = auth.uid()) 
);

CREATE POLICY "Role-based update access"
 ON todos
 FOR UPDATE
 USING (
 company_id = (SELECT company_id FROM users WHERE id = auth.uid())
 AND (
 user_id = auth.uid() OR
 (SELECT role FROM users WHERE id = auth.uid()) = 'Admin'
 ) 
 )
 WITH CHECK (
 company_id = (SELECT company_id FROM users WHERE id = auth.uid())
 AND (
 user_id = auth.uid() OR
 (SELECT role FROM users WHERE id = auth.uid()) = 'Admin'
 ) 
 );

CREATE POLICY "Role-based delete access"
ON todos
FOR DELETE
USING (
 company_id = (SELECT company_id FROM users WHERE id = auth.uid())
 AND (
 user_id = auth.uid() OR
 (SELECT role FROM users WHERE id = auth.uid()) = 'Admin'
 ) 
);