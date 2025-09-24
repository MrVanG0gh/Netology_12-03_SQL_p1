# Домашнее задание к занятию "SQL. Часть 1" - `Иншаков Владимир`

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

### Решение 1

```
SELECT DISTINCT a.district AS 'Район' 
FROM address a
WHERE a.district LIKE 'K%a' AND a.district NOT LIKE '% %';
```
![Screenshot_1](https://github.com/MrVanG0gh/Netology_12-03_SQL_p1/blob/main/Screenshots/Screenshot_1.png)

---
### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

### Решение 2

```
SELECT *
FROM payment p
WHERE p.payment_date BETWEEN '2005-06-15' AND '2005-06-18 23:59:59'
AND p.amount > 10;
```
![Screenshot_2](https://github.com/MrVanG0gh/Netology_12-03_SQL_p1/blob/main/Screenshots/Screenshot_2.png)

---

### Задание 3

Получите последние пять аренд фильмов.

### Решение 3

```
SELECT *
FROM sakila.rental r
ORDER BY r.rental_date DESC
LIMIT 5;
```
![Screenshot_3](https://github.com/MrVanG0gh/Netology_12-03_SQL_p1/blob/main/Screenshots/Screenshot_3.png)

---

### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

### Решение 4

```
SELECT REPLACE(LOWER(cus.last_name), 'll', 'pp') AS 'last name', REPLACE(LOWER(cus.first_name), 'll', 'pp') AS 'first name'
FROM sakila.customer AS cus
WHERE cus.first_name LIKE 'Kelly' OR cus.first_name LIKE 'Willie' AND cus.active = 1;
```
![Screenshot_4](https://github.com/MrVanG0gh/Netology_12-03_SQL_p1/blob/main/Screenshots/Screenshot_4_1.png)