# Домашнее задание к занятию "`SQL. Часть 1`" - `Марченко Вячеслав Игоревич`

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

### Ответ

```
SELECT DISTINCT district
FROM addresses
WHERE district LIKE 'K%' AND district LIKE '%a' AND district NOT LIKE '% %';

```

---

### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.

### Ответ

```
SELECT *
FROM payments
WHERE payment_date BETWEEN '2005-06-15' AND '2005-06-18'
AND amount > 10.00;
```

---

### Задание 3

Получите последние пять аренд фильмов.

### Ответ

```
SELECT *
FROM rentals
ORDER BY rental_date DESC
LIMIT 5;
```

---

### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie.

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

### Ответ

```
SELECT LOWER(REPLACE(first_name, 'll', 'pp')) AS first_name,
       LOWER(REPLACE(last_name, 'll', 'pp')) AS last_name
FROM customers
WHERE (first_name = 'Kelly' OR first_name = 'Willie') AND active = 1;

```
