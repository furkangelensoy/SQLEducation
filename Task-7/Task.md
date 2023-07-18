# Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.
1- Film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.

```Sql

SELECT rating, COUNT(*) FROM film
GROUP BY rating;

```

2- Film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini 
ve karşılık gelen film sayısını sıralayınız.

```Sql

SELECT replacement_cost, COUNT(*) FROM film
GROUP BY replacement_cost
HAVING COUNT(*) > 50;

```

3- Customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayıları nelerdir?

```Sql

SELECT store_id, COUNT(customer_id) FROM customer
GROUP BY store_id;

```

4- City tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id
bilgisini ve şehir sayısını paylaşınız.

```Sql

SELECT country_id, COUNT(city) FROM city
GROUP BY country_id
ORDER BY COUNT(city) DESC;

```
**Output**
```Sql
country_id      count
    44           60
```
