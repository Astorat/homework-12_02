# Домашнее задание к занятию «Работа с данными (DDL/DML)» - `Щербак С.А.`
   
---

### Задание 1

`Создание учетной записи пользователя, и вывод списка пользователей:`
```
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY '123';
SELECT user, host FROM mysql.user
```
![Screenshot_01_01](https://github.com/Astorat/homework-12_02/blob/main/Screenshots/Screenshot_01_01.png)

`Пользователю предоставлены полные права:`
```
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost' WITH GRANT OPTION;
SELECT * FROM mysql.user WHERE user = 'sys_temp';
```
![Screenshot_01_02](https://github.com/Astorat/homework-12_02/blob/main/Screenshots/Screenshot_01_02.png)

`Подключение под пользователем sys_temp:`
![Screenshot_01_02](https://github.com/Astorat/homework-12_02/blob/main/Screenshots/Screenshot_01_03.png)

`Загрузка БД из файла, и вывод схемы:`
```
mysql -u root -p sakila < D:\sakila-db\sakila-schema.sql
mysql -u root -p sakila < D:\sakila-db\sakila-data.sql
```
![Screenshot_01_02](https://github.com/Astorat/homework-12_02/blob/main/Screenshots/Screenshot_01_04.png)

---

### Задание 2
```
Название таблицы | Название первичного ключа
customer         | customer_id
rental           | rental_id
payment          | payment_id
store            | store_id
staff            | staff_id
address          | address_id
city             | city_id
country          | country_id
inventory        | inventory_id
film             | film_id
language         | language_id
actor            | actor_id
film_actor       | actor_id
film_actor       | film_id
film_text        | cfilm_id
category         | category_id
film_category    | film_id
film_category    | category_id
```

### Задание 3

`Выполнен отзыв прав, у пользователя sys_temp, и выданы права только на чтение БД sakila:`
```
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'sys_temp'@'localhost';
GRANT SELECT ON sakila.* TO 'sys_temp'@'localhost';
SHOW GRANTS FOR 'sys_temp'@'localhost';
```
![Screenshot_01_01](https://github.com/Astorat/homework-12_02/blob/main/Screenshots/Screenshot_01_05.png)


