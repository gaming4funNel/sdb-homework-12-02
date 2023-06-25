# Домашнее задание к занятию «Работа с данными (DDL/DML)» - Иванов Игорь

### Задание 1
1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp. 

CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY '123qwe!QWE';

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

SELECT User FROM mysql.user;

![mysql](https://github.com/gaming4funNel/sdb-homework-12-02/blob/main/img/mysql1.png)

1.4. Дайте все права для пользователя sys_temp. 

GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'%' WITH GRANT OPTION;

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

SHOW GRANTS FOR 'sys_temp'@'localhost';

![mysql](https://github.com/gaming4funNel/sdb-homework-12-02/blob/main/img/mysql2.png)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос: 
```sql
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

USE sakila
SHOW TABLES;

![mysql](https://github.com/gaming4funNel/sdb-homework-12-02/blob/main/img/mysql4.png)

![mysql](https://github.com/gaming4funNel/sdb-homework-12-02/blob/main/img/mysql3.png)

*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*


### Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)
```
Название таблицы | Название первичного ключа

actor            | actor_id
address          | address_id
category         | category_id
city             | city_id
country          | country_id
customer         | customer_id
film             | film_id
film_actor       | 
film_category    |
film_text        | film_id
inventory        | inventory_id
language         | language_id
payment          | payment_id
rental           | rental_id
staff            | staff_id
store            | store_id

```


## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

### Задание 3*
3.1. Уберите у пользователя sys_temp права на внесение, изменение и удаление данных из базы sakila.

REVOKE ALL PRIVILEGES ON sakila.* FROM 'sys_temp'@'%';

3.2. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*
