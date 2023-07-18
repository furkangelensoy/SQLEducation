# Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1- Film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?

```Sql

SELECT AVG(rental_rate) FROM film;

```
**Output:**
````Sql
2.98
````

2- Film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

```Sql

SELECT COUNT(*) FROM film
WHERE title LIKE 'C%';

```
**Output:**
````Sql
92
````

3- Film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

```Sql

SELECT MAX(length) FROM film
WHERE rental_rate = 0.99;

```
**Output:**
````Sql
184
````

4- Film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

```Sql

SELECT COUNT(DISTINCT replacement_cost) FROM film
WHERE length > 150

```
**Output:**
````Sql
21
````
