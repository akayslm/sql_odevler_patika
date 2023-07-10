
![patika dev2](https://github.com/akayslm/sql_odevler_patika/assets/73195655/b2d0f14f-19c6-4771-9f28-9f3c0e271c24)
<br>


 # SQL Eğitim Patika 

> #### Bu repo'da [Patika](https://academy.patika.dev/) SQL eğitiminde yapmış olduğum bütün ödevler bulunmaktadır.

<br>

**SQL Ödev 01 | WHERE ve Karşılaştırma & Mantıksal** </br>
**SQL Ödev 02 | BETWEEN - AND Yapısı ve In Operatörü** </br>
**SQL Ödev 03 | LIKE ve ILIKE** </br>
**SQL Ödev 04 | DISTINCT ve COUNT** </br>
**SQL Ödev 05 | LIMIT OFFSET ve ORDER BY** </br>
**SQL Ödev 06 | AGGREGATE Fonksiyonlar** </br>
**SQL Ödev 07 | GROUP BY ve HAVING Fonksiyonları** </br>
**SQL Ödev 08 | Tablo Oluşturma, Veri Ekleme, Silme ve Güncelleme** </br>
**SQL Ödev 09 | INNER JOIN ile Tablo Birleştirme** </br>
**SQL Ödev 10 | LEFT JOIN, RIGHT JOIN, FULL JOIN ile Tablo Birleştirme** </br>
**SQL Ödev 11 | UNION, INTERSECT, EXCEPT** </br>
**SQL Ödev 12 | Sorgu Senaryoları** </br>

<br>

## SQL Ödev 01 | WHERE ve Karşılaştırma & Mantıksal Operatörler 

<br>

1-) <strong>film </strong>tablosunda bulunan <strong>title</strong> ve <strong>description</strong> 
sütunlarındaki verileri sıralayınız.

```

SELECT title, description FROM film;

```

2-) <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük <strong>VE</strong> 75 ten küçük olma koşullarıyla sıralayınız.

```

SELECT * FROM film
WHERE length>60 AND length<75;

```
3-) <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 <strong>VE</strong> replacement_cost 12.99 <strong>VEYA</strong> 28.99 olma koşullarıyla sıralayınız.

```

SELECT * FROM film
WHERE rental_rate=0.99 AND (replacement_cost=12.99 OR replacement_cost=28.99);

```
4-) <strong>customer</strong> tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

```

SELECT first_name, last_name FROM customer
WHERE first_name='Mary';

```
5-) <strong>film</strong> tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

```

SELECT * FROM film
WHERE NOT (length>50 AND (rental_rate = 2.99 OR rental_rate = 4.99));

```
## SQL Ödev 02 | BETWEEN - AND Yapısı ve In Operatörü 

<br>

1-) <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

```

SELECT * FROM film
WHERE replacement_cost BETWEEN 12.99 AND 16.99;

```
2-) <strong>actor</strong> tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

```

SELECT first_name, last_name FROM actor
WHERE first_name IN ('Penelope', 'Nick', 'Ed');

```
3-) <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)
```

SELECT * FROM film
WHERE (rental_rate IN (0.99, 2.99, 4.99) AND replacement_cost IN (12.99, 15.99, 28.99));

```
## SQL Ödev 03 | LIKE ve ILIKE

<br>

1-) <strong>country</strong> tablosunda bulunan <strong>country</strong> sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

```
SELECT country FROM country
WHERE country LIKE 'A%a';
```

2-) <strong>country</strong> tablosunda bulunan <strong>country</strong> sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

```
SELECT country FROM country
WHERE country LIKE '%_____n';
```

3-) <strong>film</strong> tablosunda bulunan <strong>title</strong> sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

```
SELECT title FROM film
WHERE title ILIKE '%T%T%T%T%';
```

4-) <strong>film</strong> tablosunda bulunan tüm sütunlardaki verilerden <strong>title</strong> 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

```
SELECT * FROM film
WHERE title LIKE 'C%' AND length > 90 AND rental_rate = 2.99;
```

## SQL Ödev 04 | DISTINCT ve COUNT

<br>

1-) <strong>film</strong> tablosunda bulunan <strong>replacement_cost</strong> sütununda bulunan birbirinden farklı değerleri sıralayınız.

```
SELECT DISTINCT replacement_cost FROM film;
```

2-) <strong>film</strong> tablosunda bulunan <strong>replacement_cost</strong> sütununda birbirinden farklı kaç tane veri vardır?

```
SELECT COUNT(DISTINCT replacement_cost) FROM film;
```

3-) <strong>film</strong> tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

```
SELECT COUNT(*) FROM film
WHERE title LIKE 'T%' AND rating = 'G';
```

4-) <strong>country</strong> tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

```
SELECT COUNT(DISTINCT country) FROM country
WHERE country LIKE '_____';
```

5-) <strong>city</strong> tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?

```
SELECT COUNT(DISTINCT city) FROM city
WHERE city ILIKE '%R';
```
## SQL Ödev 05 | LIMIT OFFSET ve ORDER BY

<br>

1-) <strong>film</strong> tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

```
SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5;
```

2-) <strong>film</strong> tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.

```
SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length
OFFSET 5
LIMIT 5;
```

3-) <strong>customer</strong> tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

```
SELECT * FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4;
```

## SQL Ödev 06 | AGGREGATE Fonksiyonlar

<br>

1-) <strong>film</strong> tablosunda bulunan <strong>rental_rate</strong> sütunundaki değerlerin ortalaması nedir?

```
SELECT ROUND(AVG(rental_rate), 2) FROM film;
```

2-) <strong>film</strong> tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

```
SELECT COUNT(*) FROM film 
WHERE title LIKE 'C%';
```

3-) <strong>film</strong> tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

```
SELECT MAX(length) FROM film
WHERE rental_rate = 0.99;
```

4-) <strong>film</strong> tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

```
SELECT COUNT(DISTINCT replacement_cost) FROM film
WHERE length > 150;
```

## SQL Ödev 07 | GROUP BY ve HAVING Fonksiyonları

<br>

1-) <strong>film</strong> tablosunda bulunan filmleri <strong>rating</strong> değerlerine göre gruplayınız.

```
SELECT rating FROM film
GROUP BY rating;
```

2-) <strong>film</strong> tablosunda bulunan filmleri <strong>replacement_cost</strong> sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.

```
SELECT replacement_cost, COUNT(*) FROM film
GROUP BY replacement_cost 
HAVING COUNT(*) > 50;
```

3-) <strong>customer</strong> tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?

```
SELECT store_id, COUNT(*) FROM customer
GROUP BY store_id;
```

4-) <strong>city</strong> tablosunda bulunan şehir verilerini <strong>country_id</strong> sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.

```
SELECT country_id, COUNT(city) FROM city
GROUP BY country_id
ORDER BY COUNT(city) DESC
LIMIT 1;
```
## SQL Ödev 08 | Tablo Oluşturma, Veri Ekleme, Silme ve Güncelleme

<br>

1-) <strong>test</strong> veritabanınızda <strong>employee</strong> isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.

```
CREATE TABLE employee(
	id SERIAL  PRIMARY KEY GENERATED ALWAYS AS IDENTITY,	
	name VARCHAR(50) not null,
	BIRTHDAY date ,
	email VARCHAR(100)
);
```

2-) Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

```
insert into employee (name, email, birthday) values ('Sybil', 'sfice0@usda.gov', '1973/04/21');
insert into employee (name, email, birthday) values ('Keely', 'kmuckley1@blinklist.com', null);
insert into employee (name, email, birthday) values ('Lilith', 'ldensumbe2@ask.com', '1974/11/30');
insert into employee (name, email, birthday) values ('Pavla', 'poats3@howstuffworks.com', '1985/02/26');
insert into employee (name, email, birthday) values ('Dani', 'dballentime4@eventbrite.com', null);
insert into employee (name, email, birthday) values ('Minni', 'mbaltzar5@shutterfly.com', '1930/03/25');
insert into employee (name, email, birthday) values ('Welbie', 'wwillgrass6@wisc.edu', '1933/04/25');
insert into employee (name, email, birthday) values ('Bren', 'bmcpartling7@jigsy.com', '1986/02/06');
insert into employee (name, email, birthday) values ('Kristin', 'kbohea8@mail.ru', '1950/08/03');
insert into employee (name, email, birthday) values ('Angeli', 'atabour9@bing.com', '1924/09/01');
insert into employee (name, email, birthday) values ('Rozina', 'rrainera@4shared.com', null);
insert into employee (name, email, birthday) values ('Sherline', 'schableb@who.int', '1958/12/03');
insert into employee (name, email, birthday) values ('Dane', 'dkindlesidec@epa.gov', null);
insert into employee (name, email, birthday) values ('Vivianna', 'vtoderid@webeden.co.uk', '1915/07/31');
insert into employee (name, email, birthday) values ('Jillian', 'jbrissone@rediff.com', '1901/03/29');
insert into employee (name, email, birthday) values ('Rad', 'rpymf@spiegel.de', '1932/12/20');
insert into employee (name, email, birthday) values ('Shurlock', 'ssmowtong@usnews.com', '1966/07/10');
insert into employee (name, email, birthday) values ('Kerrin', 'kizath@dropbox.com', null);
insert into employee (name, email, birthday) values ('Park', 'pspurieri@google.co.jp', '1953/10/26');
insert into employee (name, email, birthday) values ('Renate', 'rjaquetj@feedburner.com', '1933/07/31');
insert into employee (name, email, birthday) values ('Mufinella', null, '1940/11/16');
insert into employee (name, email, birthday) values ('Merrick', 'mscollardl@sourceforge.net', '1984/07/31');
insert into employee (name, email, birthday) values ('Loella', 'lhillm@sciencedaily.com', '1961/12/30');
insert into employee (name, email, birthday) values ('Holmes', 'hofern@newyorker.com', '1963/09/19');
insert into employee (name, email, birthday) values ('Therese', 'tmccuiso@google.de', '1908/04/10');
insert into employee (name, email, birthday) values ('Xerxes', 'xpollettp@google.cn', '1950/03/10');
insert into employee (name, email, birthday) values ('Stephanus', 'spadrickq@geocities.com', null);
insert into employee (name, email, birthday) values ('Eustacia', 'eshermer@reddit.com', '1970/01/25');
insert into employee (name, email, birthday) values ('Carlin', 'cmuttocks@miitbeian.gov.cn', null);
insert into employee (name, email, birthday) values ('Robenia', 'rwhittletont@samsung.com', null);
insert into employee (name, email, birthday) values ('Caryl', 'cwebburnu@oakley.com', '1928/08/10');
insert into employee (name, email, birthday) values ('Janis', 'jmackneisv@blog.com', '1920/07/15');
insert into employee (name, email, birthday) values ('Gregoor', 'gklaassensw@hugedomains.com', null);
insert into employee (name, email, birthday) values ('Felipa', 'fmcelvoguex@de.vu', null);
insert into employee (name, email, birthday) values ('Heather', null, null);
insert into employee (name, email, birthday) values ('Brynne', 'bcolleckz@google.co.jp', '1969/12/16');
insert into employee (name, email, birthday) values ('Arturo', 'ajandel10@reddit.com', '1989/05/06');
insert into employee (name, email, birthday) values ('Natka', 'nordidge11@prnewswire.com', null);
insert into employee (name, email, birthday) values ('Stacee', 'srosenwasser12@jalbum.net', '1916/05/08');
insert into employee (name, email, birthday) values ('Benedikt', null, '1915/01/20');
insert into employee (name, email, birthday) values ('Florette', 'fchappel14@weebly.com', null);
insert into employee (name, email, birthday) values ('Janeta', 'jandres15@cpanel.net', '1954/03/26');
insert into employee (name, email, birthday) values ('Ernst', 'educarne16@discuz.net', '1986/03/10');
insert into employee (name, email, birthday) values ('Von', 'vtebboth17@seattletimes.com', '1999/12/19');
insert into employee (name, email, birthday) values ('Bev', 'bcasier18@mlb.com', null);
insert into employee (name, email, birthday) values ('Laure', 'lyeldham19@rakuten.co.jp', null);
insert into employee (name, email, birthday) values ('Leonhard', 'lfroggatt1a@technorati.com', '1931/01/09');
insert into employee (name, email, birthday) values ('Kimmie', 'klawden1b@bing.com', '1938/03/18');
insert into employee (name, email, birthday) values ('Krishnah', 'kmaysor1c@cloudflare.com', '1955/09/23');
insert into employee (name, email, birthday) values ('Lynda', 'lside1d@goo.gl', '1915/02/05');
```

3-) Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.

```
update employee 
set
name =  'mert'
where birthday = '1973-04-21';

update employee 
set
birthday = '2002-10-22'
where birthday = '1938-03-18';

update employee
set 
name = 'victor',
birthday ='2000-01-29'
where id =  10;

update employee
set 
email = 'patika@dev.dev'
where email ='Iside1d@goo.gl';

update employee
set 
email ='patika@patika.dev',
name = 'patika'
where id = 50;
```

4-) Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

```
DELETE FROM employee
WHERE id = 25;

DELETE FROM employee
WHERE name = 'Rossie Dudeney';

DELETE FROM employee
WHERE email = 'tcheales4@stanford.edu';

DELETE FROM employee
WHERE birthday = '1992-10-24';

DELETE FROM employee
WHERE id = 35;
```

## SQL Ödev 09 | INNER JOIN ile Tablo Birleştirme

<br>

1-) <strong>city</strong> tablosu ile <strong>country</strong> tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```
SELECT city, country FROM city
INNER JOIN country ON city.country_id = country.country_id;
```

2-) <strong>customer</strong> tablosu ile <strong>payment</strong> tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```
SELECT payment.payment_id, customer.first_name, customer.last_name FROM payment
INNER JOIN customer ON payment.customer_id = customer.customer_id;
```

3-) <strong>customer</strong> tablosu ile <strong>rental</strong> tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```
SELECT rental.rental_id, customer.first_name, customer.last_name FROM rental
INNER JOIN customer ON rental.customer_id = customer.customer_id;
```

## SQL Ödev 10 | LEFT JOIN, RIGHT JOIN, FULL JOIN ile Tablo Birleştirme

<br>

1-) <strong>city</strong> tablosu ile <strong>country</strong> tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.

```
SELECT city, country FROM city
LEFT JOIN country ON city.country_id = country.country_id;
```

2-) <strong>customer</strong> tablosu ile <strong>payment</strong> tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.

```
SELECT payment.payment_id, customer.first_name, customer.last_name FROM customer
RIGHT JOIN payment ON customer.customer_id = payment.customer_id;
```

3-) <strong>customer</strong> tablosu ile <strong>rental</strong> tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.

```
SELECT rental.rental_id, customer.first_name, customer.last_name FROM customer
FULL JOIN rental ON customer.customer_id = rental.customer_id;
```
## SQL Ödev 11 | UNION, INTERSECT, EXCEPT

<br>

1-) <strong>actor</strong> ve <strong>customer</strong> tablolarında bulunan <strong>first_name</strong> sütunları için tüm verileri sıralayalım.

```
(SELECT first_name FROM actor)
UNION 
(SELECT first_name FROM customer);
```

2-) <strong>actor</strong> ve <strong>customer</strong> tablolarında bulunan <strong>first_name</strong> sütunları için kesişen verileri sıralayalım.

```
(SELECT first_name FROM actor)
INTERSECT
(SELECT first_name FROM customer);
```

3-) <strong>actor</strong> ve <strong>customer</strong> tablolarında bulunan <strong>first_name</strong> sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.

```
(SELECT first_name FROM actor)
EXCEPT
(SELECT first_name FROM customer);
```

4-) İlk 3 sorguyu tekrar eden veriler için de yapalım.

```
(SELECT first_name FROM actor)
UNION ALL
(SELECT first_name FROM customer);

(SELECT first_name FROM actor)
INTERSECT ALL
(SELECT first_name FROM customer);

(SELECT first_name FROM actor)
EXCEPT ALL
(SELECT first_name FROM customer);
```
## SQL Ödev 12 | Sorgu Senaryoları

<br>

1-) <strong>film</strong> tablosunda film uzunluğu <strong>length</strong> sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?

```

```

2-) <strong>film</strong> tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?

```

```

3-) <strong>film</strong> tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.

```

```

4-) <strong>payment</strong> tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.

```

```
