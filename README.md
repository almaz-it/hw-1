# hw-1
Домашнее задание 1

Спроектируйте логическую медель данных из >=5 сущностей и реализуйте ее в БД. 

wiki: https://postgrespro.ru/docs/postgresql/15/sql-createtable

пример создания таблиц: 
```
drop table if exists shop;
create table if not exists shop
(
    name    text primary key,
    phone   text,
    address text
);

drop table if exists car;
create table if not exists car
(
    marka     varchar(10) primary key,
    model     varchar(50),
    price     numeric(10, 2) not null,
    count     integer check (count > 0),
    utime     timestamp default current_timestamp,
    udate     date      default current_date,
    is_active boolean   default null,
    shop      text not null references shop(name)
);

insert into car(marka, model, price, count, shop)
values ('ford', 'granta', 600.50, 10, 'tts'),
       ('kia', 'ceed', 700.50, 5, 'tts');

insert into shop(name, phone, address)
values ('tts', '+7000501', 'Kazan');

```

# hw-2
version: нужно создать файл version2.sql c изменениями структуры таблиц
1. измение типов столбцов
2. добавление столбцов
3. добавление ограничений
4. реализовать rollback этих изменений

# hw-3
cju: нужно создать файл version3.sql написать sql запросы: 
1. select используя cte
2. select c join - соединение 
3. select c union [all] - объединение 
