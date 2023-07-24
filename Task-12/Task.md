# Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1- Film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?

```Sql

SELECT COUNT (length)
FROM film
WHERE length >
(
SELECT AVG (length) FROM film
);

```

2- Film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?

```Sql

SELECT COUNT (*)
FROM film
WHERE rental_rate =
(
	SELECT MAX (rental_rate) from film
);

```

3- Film tablosunda en düşük rental_rate ve en düşük replacement_cost değerlerine sahip filmleri sıralayınız.

```Sql

SELECT * FROM film
WHERE rental_rate = ANY
(
	SELECT MIN (rental_rate) FROM film
)
AND
replacement_cost = ANY
(
	SELECT MIN(replacement_cost) FROM film
);

```

4- Payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.

```Sql

SELECT customer_id, COUNT(*) AS most_shopping FROM payment
GROUP BY customer_id
ORDER BY most_shopping DESC;

```


