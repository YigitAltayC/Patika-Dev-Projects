# SQL Dersi - Odev 1

- film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.

```SQL
SELECT title, description FROM film;
```
- film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film
WHERE length > 60 AND length < 75;
```

- film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film
WHERE rental_rate = 0.99 AND (replacement_cost = 12.99 OR replacement_cost = 28.99);
```

- customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

```SQL
SELECT last_name FROM customer
WHERE first_name = 'Mary';
```

- film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

```SQL
SELECT * FROM film
WHERE length <= 50 AND (rental_rate != 2.99 OR rental_rate != 4.99)
```

# SQL Dersi - Odev 3



- country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

```SQL
SELECT * FROM country
WHERE country LIKE 'A%a;
```

- country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

```SQL
SELECT * FROM country
WHERE LENGTH(country) >= 6 AND LIKE '%n';
```

- film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

```SQL
SELECT title FROM film
WHERE title LIKE '%T%' or title LIKE '%t%';
```

- film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

```SQL
SELECT * FROM film
WHERE title LIKE 'C%' AND length(title) > 90 AND rental_rate = 2.99;
```

# SQL Odev 4

- film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.

```SQL
SELECT DISTINCT replacement_cost FROM film;
```

- film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?

```SQL
SELECT COUNT(DISTINCT replacement_cost) FROM film;
```

- film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

```SQL
SELECT COUNT(*) 
FROM film 
WHERE title LIKE 'T%' AND rating = 'G';
```

- country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

```SQL
SELECT COUNT(*) 
FROM country 
WHERE LENGTH(country) = 5;
```

- city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?

```SQL
SELECT COUNT(*) 
FROM city 
WHERE city ILIKE '%r';
```

# SQL Odev 5

- film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

```SQL
SELECT * FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5
```

- film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.

```SQL
SELECT * FROM film
WHERE title LIKE '%n'
ORDER BY length ASC
OFFSET 5
LIMIT 5;
```

- customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

```SQL
SELECT * FROM customer
WHERE store_id = 1
ORDER BY last_name ASC
LIMIT 4;
```