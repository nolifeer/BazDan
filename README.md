# Шпора
Вставка данных в таблицу:
INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);

 Выборка данных из таблицы:
SELECT * FROM table_name;

Удаление данных:
DELETE FROM table_name WHERE condition;

Обновление поля во всех записях : update table1 set column1 = new_value 

Обновления поля во всех записях, соответствующих условию : update table1 set column 1 =new_value 

Добавление одной записи : INSERT INTO table (column1, column2) values (value1, value2)

Добавление нескольких записей : INSERT INTO table (column1, column2) values(value11, value12), (value21, value22), ....

Добавление записей из другой таблицы : insert into table (column1, column2) select (col1, col2) from table 2

INSERT INTO orders (id, products, sum) VALUES (6, 4, 8000) = пример добавления еще одного пункта в таблицу.

asc = от меньшего к большему desc = по убыванию

SELECT * FROM users ORDER BY id LIMIT 10 OFFSET 10;

В SQL порядок выполнения логических операторов AND и OR имеет значение и влияет на результат запроса. Вот основные моменты:

- AND имеет более высокий приоритет, чем OR. Это значит, что условия, соединенные с помощью AND, будут обработаны первыми.\
  
- Если вы хотите изменить порядок выполнения, используйте круглые скобки для группировки условий

В этом примере:
- LIMIT 10 означает, что вернётся 10 записей.

- OFFSET 10 пропускает первые 10 записей, начиная выборку с 11-й.

VARCHAR(50) в SQL обозначает тип данных для столбца, который может хранить строковые значения переменной длины. 

- VARCHAR - это тип данных, который позволяет хранить строки. При этом длина строки может варьироваться.

  VARCHAR (65535) - максимум
  
- (50) - это максимальная длина строки, которая может быть сохранена в этом столбце. В данном случае, максимальная длина составляет 50 символов.

  INT в SQL обозначает тип данных, используемый для хранения целых чисел.

  DATE в SQL используется для хранения дат

  Ряд дополнительных типов данных представляют текст неопределенной длины:

TINYTEXT: представляет текст длиной до 255 байт.

TEXT: представляет текст длиной до 65 КБ.

MEDIUMTEXT: представляет текст длиной до 16 МБ

LONGTEXT: представляет текст длиной до 4 ГБ

Числовые типы
TINYINT: представляет целые числа от -128 до 127, занимает 1 байт

BOOL: фактически не представляет отдельный тип, а является лишь псевдонимом для типа TINYINT(1) и может хранить два значения 0 и 1. Однако данный тип может также в качестве значения принимать встроенные константы TRUE (представляет число 1) и FALSE (предоставляет число 0).

Также имеет псевдоним BOOLEAN.

TINYINT UNSIGNED: представляет целые числа от 0 до 255, занимает 1 байт

SMALLINT: представляет целые числа от -32768 до 32767, занимает 2 байтa

SMALLINT UNSIGNED: представляет целые числа от 0 до 65535, занимает 2 байтa

MEDIUMINT: представляет целые числа от -8388608 до 8388607, занимает 3 байта

MEDIUMINT UNSIGNED: представляет целые числа от 0 до 16777215, занимает 3 байта

INT: представляет целые числа от -2147483648 до 2147483647, занимает 4 байта

INT UNSIGNED: представляет целые числа от 0 до 4294967295, занимает 4 байта

BIGINT: представляет целые числа от -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807, занимает 8 байт

BIGINT UNSIGNED: представляет целые числа от 0 до 18 446 744 073 709 551 615, занимает 8 байт

DECIMAL: хранит числа с фиксированной точностью. Данный тип может принимать два параметра precision и scale: DECIMAL(precision, scale).

FLOAT: хранит дробные числа с плавающей точкой одинарной точности от -3.4028 * 1038 до 3.4028 * 1038, занимает 4 байта

Может принимать форму FLOAT(M,D), где M - общее количество цифр, а D - количество цифр после запятой

.
DOUBLE: хранит дробные числа с плавающей точкой двойной точности от -1.7976 * 10308 до 1.7976 * 10308, занимает 8 байт. Также может принимать форму DOUBLE(M,D), где M - общее количество цифр, а D - количество цифр после запятой.


Типы для работы с датой и временем
DATE: хранит даты с 1 января 1000 года до 31 деабря 9999 года (c "1000-01-01" до "9999-12-31"). По умолчанию для хранения используется формат yyyy-mm-dd. Занимает 3 байта.

TIME: хранит время от -838:59:59 до 838:59:59. По умолчанию для хранения времени применяется формат "hh:mm:ss". Занимает 3 байта.

DATETIME: объединяет время и дату, диапазон дат и времени - с 1 января 1000 года по 31 декабря 9999 года (с "1000-01-01 00:00:00" до "9999-12-31 23:59:59"). Для хранения по умолчанию используется формат "yyyy-mm-dd hh:mm:ss". Занимает 8 байт

TIMESTAMP: также хранит дату и время, но в другом диапазоне: от "1970-01-01 00:00:01" UTC до "2038-01-19 03:14:07" UTC. Занимает 4 байта

YEAR: хранит год в виде 4 цифр. Диапазон доступных значений от 1901 до 2155. Занимает 1 байт.

Тип Date может принимать даты в различных форматах, однако непосредственно для хранения в самой бд даты приводятся к формату "yyyy-mm-dd". Некоторые из принимаемых форматов:

yyyy-mm-dd - 2018-05-25

yyyy-m-dd - 2018-5-25

yy-m-dd - 18-05-25

В таком формате двузначные числа от 00 до 69 воспринимаются как даты в диапазоне 2000-2069. А числа от 70 до 99 как диапазон чисел 1970 - 1999.

yyyymmdd - 20180525

yyyy.mm.dd - 2018.05.25

Для времени тип Time использует 24-часовой формат. Он может принимать время в различных форматах:

hh:mi - 3:21 (хранимое значение 03:21:00)

hh:mi:ss - 19:21:34

hhmiss - 192134

Примеры значений для типов DATETIME и TIMESTAMP:

2018-05-25 19:21:34
2018-05-25 (хранимое значение 2018-05-25 00:00:00)
Составные типы
ENUM: хранит одно значение из списка допустимых значений. Занимает 1-2 байта

SET: может хранить несколько значений (до 64 значений) из некоторого списка допустимых значений. Занимает 1-8 байт.

Бинарные типы
TINYBLOB: хранит бинарные данные в виде строки длиной до 255 байт.

BLOB: хранит бинарные данные в виде строки длиной до 65 КБ.

MEDIUMBLOB: хранит бинарные данные в виде строки длиной до 16 МБ

LONGBLOB: хранит бинарные данные в виде строки длиной до 4 ГБ

- PRIMARY KEY: Это ограничение, которое обозначает, что столбец является первичным ключом.

- NOT NULL: Это ограничение обозначает, что столбец не может содержать пустые значения (NULL). 

  Первичный ключ (PRIMARY KEY) в SQL — это особое поле в таблице, которое позволяет однозначно идентифицировать каждую запись в ней.  2

Как правило, эти поля используются для хранения уникальных идентификаторов объектов, которые перечислены в таблице, например, это может быть ID клиента или товара

CREATE TABLE users (
id INT(10)UNSIGNED NOT NULL PRIMARY KEY,
first_name VARCHAR (50) NULL,
last_name VARCHAR (50) NULL,
birthday DATE NULL );
INSERT INTO users (id, first_name, last_name, birthday)
VALUES (1,'Дмитрий','Иванов',NULL),
(2,'Анатолий','Белый',NULL),
(3,'Денис','Давыдов','1995-09-08');

Auto_INCREMENT в SQL — это атрибут столбца, который позволяет автоматически увеличивать его значение при добавлении новой строки


# Практическая 1
1) Выберите из таблицы orders все заказы
   
SELECT * FROM orders

![image](https://github.com/user-attachments/assets/b85a30cc-c42c-4e24-bf36-e3fb84c1b15c)



3) Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in

   ![image](https://github.com/user-attachments/assets/1bf95e40-ca77-49ce-8bd4-ff2a2fbf3d7c)

SELECT * FROM orders WHERE STATUS NOT IN ('new')


5) Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new".

   ![image](https://github.com/user-attachments/assets/53dab5dd-d85d-45ce-be2c-65686806aebb)

SELECT * FROM orders WHERE STATUS IN ('new', 'cancelled')


7) Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count). Вывести нужно только номер (id) и сумму (sum) заказа.
   
![image](https://github.com/user-attachments/assets/de56a56a-7c6a-42b0-9d07-4df95b99d87c)

SELECT id,sum FROM orders WHERE products_count > 3


# Практическая 2

1) Выберите из таблицы orders 3 самых дешевых заказа за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

![image](https://github.com/user-attachments/assets/12f5e71b-2f89-4f61-b995-deb5cfa40a7d)


SELECT * FROM orders WHERE STATUS != 'cancelled' ORDER BY sum ASC LIMIT 3


2) Выберите из таблицы orders 2 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

![image](https://github.com/user-attachments/assets/28beb440-e205-4cd9-8590-1af4974019c4)

SELECT * FROM orders WHERE STATUS != 'cancelled' ORDER BY SUM desc LIMIT 2


3) Добавьте в таблицу orders данные о новом заказе стоимостью 8000 рублей. В заказе 4 товара (products).

   ![image](https://github.com/user-attachments/assets/98060558-228f-40af-96c8-743e70c3f4d1)

   INSERT INTO orders (id, products, sum) VALUES (6, 4, 8000)

   
4) Добавьте в таблицу products новый товар — «VR-очки», стоимостью 70000 рублей в количестве (count) 2 штук.

   ![image](https://github.com/user-attachments/assets/2b978fa9-ec10-4b00-84cd-8b497cb545c4)

   INSERT INTO products (id,NAME,COUNT,price) VALUE (7, 'VR очки',2,70000)


   5) В таблицу products внесли данные с ошибкой, вместо "PS5" в наименовании написали IMAC. Исправьте ошибку.

      ![image](https://github.com/user-attachments/assets/3a6dace6-ae51-4d75-a46d-5ad10874b347)

      UPDATE products SET NAME='PS5' WHERE NAME='IMAC'


      # Практическая 3

Создайте таблицу users с полем id типа INT и двумя текстовыми полями, которые будут хранить имя (first_name) и фамилию (last_name). Длина имени и фамилии не превышает 50 символов.

Добавьте в таблицу трех пользователей: Дмитрия Иванова, Анатолия Белого и Дениса Давыдова.

![image](https://github.com/user-attachments/assets/0d981754-6f13-41c4-8040-f743fe7c718b)

create table users (id int, first_name varchar (50), last_name varchar(50)); 
insert into users (id, first_name, last_name) values (1, 'Дмитрий', 'Иванов'), (2, 'Анатолий', 'Белый'), (3, 'Денис','Давыдов');

# Таблицы
Создайте таблицу products для хранения информации о товарах в магазине. Выберите оптимальные поля для хранения данных в соответствии с условиями:

id типа INT – только положительные числа;
name – символьный тип до 100 символов;
count – количество товара на складе (до 200 штук);
price – цена в рублях без копеек (не более 1 млн рублей).
Заполните таблицу тремя товарами:

Холодильник, 10 штук, 50 000 рублей.
Стиральная машина, 0 штук, 23 570 рублей.
Утюг, 3 штуки, 7300 рублей

drop table if exists products; = удаление существующий таблицы

CREATE TABLE products
(id INT UNSIGNED, name VARCHAR(100), count TINYINT UNSIGNED, price MEDIUMINT UNSIGNED);
INSERT INTO products 
(id, name, count, price)
VALUES
(1, "Холодильник", 10, 50000),
(2, "Стиральная машина", 0, 23570),
(3, "Утюг", 3, 7300);





Создайте таблицу orders для хранения заказов в магазине. Выберите оптимальные поля для хранения данных в соответствии с условиями:

id – тип INT. Только положительные числа.
product_id – для хранения номера товара. Только положительные числа от 0 до 4294967295.
sale – скидка. Целое положительное число от 0 до 100.
amount – сумма заказа. Денежный тип. Максимальная сумма заказа 999999.99 рублей.
Добавьте три записи так, чтобы получалась таблица

CREATE TABLE orders
(id INT UNSIGNED, products_id INT UNSIGNED, sale TINYINT UNSIGNED, amount decimal(8,2));
INSERT INTO orders 
(id,products_id,sale,amount)
VALUES
(1, 245, 0, 230.5),
(2, 17, 15, 999999.99),
(3, 145677, 21, 1240.00)

drop table if exists products;






Создайте таблицу products для хранения информации о товарах в магазине. Выберите оптимальные поля для хранения данных в соответствии с условиями:

id типа INT – только положительные числа;
name – символьный тип до 100 символов;
count – количество товара на складе (до 200 штук);
price – цена в рублях без копеек (не более 1 млн рублей).
Заполните таблицу тремя товарами:

Холодильник, 10 штук, 50 000 рублей.
Стиральная машина, 0 штук, 23 570 рублей.
Утюг, 3 штуки, 7300 рублей

drop table if exists products;
CREATE TABLE products
(id INT UNSIGNED, name VARCHAR(100), count TINYINT UNSIGNED, price MEDIUMINT UNSIGNED);
INSERT INTO products 
(id, name, count, price)
VALUES
(1, "Холодильник", 10, 50000),
(2, "Стиральная машина", 0, 23570),
(3, "Утюг", 3, 7300);





Создайте таблицу products для хранения информации о товарах в магазине. Выберите оптимальные поля для хранения данных в соответствии с условиями:

id типа INT – только положительные числа;
name – символьный тип до 100 символов;
count – количество товара на складе (до 200 штук);
price – цена в рублях без копеек (не более 1 млн рублей).
Заполните таблицу тремя товарами:

Холодильник, 10 штук, 50 000 рублей.
Стиральная машина, 0 штук, 23 570 рублей.
Утюг, 3 штуки, 7300 рублей


CREATE TABLE products
(id INT UNSIGNED, name VARCHAR(100), count TINYINT UNSIGNED, price MEDIUMINT UNSIGNED);
INSERT INTO products 
(id, name, count, price)
VALUES
(1, "Холодильник", 10, 50000),
(2, "Стиральная машина", 0, 23570),
(3, "Утюг", 3, 7300);






🖼 Создайте таблицу films с информацией о фильмах. Выберете оптимальные поля для хранения данных в соответствии с условиями:

id типа INT, только положительные числа.
name – символьное поле длиной 100.
rating – рейтинг, вещественное число. Принимает положительные значения от 0 до 10.
country – страна фильма. Символьное поле, содержащее ровно 2 символа.
Добавьте в неё 3 записи так, чтобы получалась таблица ниже


CREATE TABLE films (
id INT UNSIGNED,
name VARCHAR (100),
rating FLOAT UNSIGNED,
country VARCHAR (2)
);
INSERT INTO films (id, name, rating, country)
VALUES (1, 'Большая буря', '3.45', 'RU'),
(2, 'Игра', '7.5714', 'US'),
(3, 'Война', '10', 'RU');


# Практическая 4

Создайте таблицу users для хранения информации о пользователях сайта.
В таблице должны быть следующие поля:

id – идентификатор, целое положительное;
email – адрес электронной почты, строка не более 100 символов;
date_joined – дата регистрации (достаточно хранить дату, без времени)
last_activity – дата и время последней активности (с точностью до секунд).

![image](https://github.com/user-attachments/assets/f66cd208-1113-4bb6-8000-98f2f481f81b)

create table users (
id int(10) unsigned,
email varchar (100),
date_joined date,
last_activity datetime
);
insert into users (id, email, date_joined,last_activity)
values
(1,'user1@domain.com', '2014-12-12','2016-04-08 12:34:54'),
(2,'user2@domain.com', '2014-12-12','2017-02-13 11:46:53'),
(3,'user3@domain.com', '2014-12-13','2017-04-04 05:12:07');



Создайте таблицу users для хранения информации о пользователях сайта.
В таблице должны быть следующие поля:

id – идентификатор, целое положительное;
email – адрес электронной почты, строка не более 100 символов;
date_joined – дата регистрации (достаточно хранить дату, без времени)
last_activity – дата и время последней активности (с точностью до секунд).



Create table calendar (
id int unsigned,
user_id int unsigned,
doctor_id int unsigned,
visit_date datetime);
Insert into calendar (id, user_id, doctor_id, visit_date)
Values 
(1, 1914 , 1, '2017-04-08 12:00:00'),
(2, 12, 1, '2017-04-08 12:30:00'),
(3, 4641, 2, '2017-04-09 09:00:00'),
(4, 784, 1,'2017-04-08 13:00:00'),
(5, 15, 2,'2017-04-09 10:00:00')


![image](https://github.com/user-attachments/assets/fa475e73-0844-4c20-b657-2fa3a83f3668)

drop table if exists users;
create table users (
id int (10) ,
first_name varchar (50) ,
last_name varchar (60) ,
bio text
);
INSERT INTO users (id, first_name, last_name, bio)
VALUES
(1,'Антон','Кулик','С отличием окончил 39 лицей.'),
(2,'Сергей','Давыдов',''),
(3,'Дмитрий','Соколов','Профессиональный программист.');



# Практическая 5

1.Выберите из таблицы orders 4 самых дорогих заказов за всё время. Данные нужно отсортировать в порядке убывания цены. Отмененные заказы не учитывайте.

SELECT * FROM orders WHERE status != 'cancelled' ORDER BY sum DESC LIMIT 4;

![image](https://github.com/user-attachments/assets/3ef074f4-57f7-48a8-85ee-5f2eb79330ab)


2. Выберите из таблицы products название и цены четырех самых дешевых товаров, которые есть на складе

SELECT name, price FROM products WHERE count > 0 ORDER BY price ASC LIMIT 4;

![image](https://github.com/user-attachments/assets/2c728f2a-ebb6-43a5-842d-407c48680555)

3.Выберите из таблицы orders три последних заказа (по дате date) стоимостью от 3200 рублей и выше. Данные отсортируйте по дате в обратном порядке.

SELECT *
FROM orders
WHERE sum >= 3200
ORDER BY date DESC
LIMIT 3;

![image](https://github.com/user-attachments/assets/a59de9f0-3450-44d6-9485-06e1abd4865b)



4) Создайте дтаблицу:  ![image](https://github.com/user-attachments/assets/0f599bee-f5f1-4beb-8ab1-9063bc6c89a7)



CREATE TABLE products (
    id INT PRIMARY KEY,
    name VARCHAR(255),
    count INT,
    price DECIMAL(10, 2)
);

INSERT INTO products (id, name, count, price) VALUES
(1, 'Стиральная машина', 5, 10000.00),
(2, 'Холодильник', 0, 10000.00),
(3, 'Микроволновка', 3, 4000.00),
(4, 'Пылесос', 2, 4500.00),
(5, 'Вентилятор', 0, 700.00),
(6, 'Телевизор', 7, 31740.00),
(7, 'Тостер', 2, 2500.00),
(8, 'Принтер', 4, 3000.00),
(9, 'Активные колонки', 1, 2900.00),
(10, 'Ноутбук', 4, 36990.00),
(11, 'Посудомоечная машина', 0, 17800.00),
(12, 'Видеорегистратор', 23, 4000.00),
(13, 'Смартфон', 8, 12300.00),
(14, 'Флешка', 4, 1400.00),
(15, 'Блендер', 0, 5500.00),
(16, 'Газовая плита', 5, 11900.00),
(17, 'Клавиатура', 3, 1800.00);


![image](https://github.com/user-attachments/assets/b2fcf6d7-9400-4d26-b57a-4d36741163bb)



5) Из этой таблицы сделать выборку на основе задания: Сайт выводит товары по 5 штук. Выберите из таблицы products товары, которые пользователи увидят на 3 странице каталога при сортировке в порядке возрастания цены (price).


   SELECT name, price
FROM products
ORDER BY price ASC
LIMIT 5 OFFSET 10;


![image](https://github.com/user-attachments/assets/e21f6586-bb76-49b9-ac52-57a3fb9208c8)


# Практическая 6

1. Создайте таблицу orders для хранения списка заказов: id — идентификатор, целое положительное. user_id — идентификатор пользователя, который оформил заказ. Целое положительное, NULL запрещен. amount — стоимость заказа. Целое положительное число не более 1 млн. NULL запрещен, по умолчанию 0. created — дата и время создания заказа. NULL запрещен. state — статус заказа. Выбор из new, cancelled, in_progress, delivered, completed. Можно выбрать только один вариант. NULL запрещен. По умолчанию должен стоять new. Добавьте 3 записи так, чтобы получалась таблица ниже:

![image](https://github.com/user-attachments/assets/95033d13-5708-465d-ba47-ed5c505a20b7)

CREATE TABLE orders ( id INTEGER PRIMARY KEY AUTO_INCREMENT, user_id INTEGER NOT NULL, amount INTEGER NOT NULL DEFAULT 0, created DATETIME NOT NULL, state ENUM('new', 'cancelled', 'in_progress', 'delivered', 'completed') NOT NULL DEFAULT 'new', CHECK (user_id > 0), CHECK (amount >= 0 AND amount <= 1000000) );

INSERT INTO orders (user_id, amount, created) VALUES (56, 5400, '2018-02-01 17:46:59'); INSERT INTO orders (user_id, amount, created) VALUES (90, 249, '2018-02-01 19:13:04'); INSERT INTO orders (user_id, amount, created) VALUES (78, 2200, '2018-02-01 22:43:09');

SELECT * FROM orders;

![image](https://github.com/user-attachments/assets/855f40ea-fd16-40ce-9f1a-359d107c2409)

2.Создайте таблицу users для хранения списка пользователей сайта: id — идентификатор, целое положительное. first_name — имя, строка до 20 символов. NULL запрещен. last_name — фамилия, строка до 20 символов. NULL запрещен. patronymic — отчество, строка до 20 символов. NULL запрещен, по умолчанию пустая строка. is_active — отметка об активности пользователя. Логическое поле, по умолчанию TRUE. is_superuser — отметка администратора. Логическое поле, по умолчанию FALSE. Добавьте 3 записи так, чтобы получалась таблица 

![image](https://github.com/user-attachments/assets/1c466294-6e84-4f31-bf6c-5c5ecdcbdbc2)

CREATE TABLE users ( id INTEGER PRIMARY KEY AUTO_INCREMENT, first_name VARCHAR(20) NOT NULL, last_name VARCHAR(20) NOT NULL, patronymic VARCHAR(20) NOT NULL DEFAULT '', is_active BOOLEAN NOT NULL DEFAULT TRUE, is_superuser BOOLEAN NOT NULL DEFAULT FALSE, CHECK (LENGTH(first_name) <= 20), CHECK (LENGTH(last_name) <= 20), CHECK (LENGTH(patronymic) <= 20) );

INSERT INTO users (first_name, last_name, patronymic, is_active, is_superuser) VALUES ('Дмитрий', 'Иванов', '', TRUE, FALSE);

INSERT INTO users (first_name, last_name, patronymic, is_active, is_superuser) VALUES ('Анатолий', 'Белый', 'Сергеевич', TRUE, TRUE);

INSERT INTO users (first_name, last_name, is_active, is_superuser) VALUES ('Андрей', 'Крючков', FALSE, FALSE);

SELECT * FROM users;

![image](https://github.com/user-attachments/assets/cabf66ca-02fe-4053-a6a9-642e98839bb8)

3.Создайте таблицу products для хранения товаров в интернет магазине: id — идентификатор, целое положительное. category_id — категория, целое положительное. Может принимать NULL. По умолчанию NULL. name — название, строка до 100 символов. NULL запрещен. count — количество, целое положительное до 255. NULL запрещен, по умолчанию 0. price — цена типа DECIMAL с 10 знаками, 2 из которых выделены для копеек. NULL запрещен, по умолчанию 0.00. Добавьте 3 записи так, чтобы получалась таблица

![image](https://github.com/user-attachments/assets/17b9c46b-51ea-47ed-b960-93aede839f72)

CREATE TABLE products ( id INTEGER PRIMARY KEY AUTO_INCREMENT, category_id INTEGER NULL DEFAULT NULL, name VARCHAR(100) NOT NULL, count TINYINT UNSIGNED NOT NULL DEFAULT 0, price DECIMAL(10, 2) NOT NULL DEFAULT 0.00, CHECK (category_id > 0 OR category_id IS NULL), CHECK (count >= 0 AND count <= 255), CHECK (price >= 0) );

INSERT INTO products (category_id, name, count, price) VALUES (1, 'Кружка', 5, 45.90);

INSERT INTO products (category_id, name, count, price) VALUES (17, 'Фломастеры', 0, 78.00);

INSERT INTO products (name, count, price) VALUES ('Сникерс', 12, 50.80);

SELECT * FROM products;

![image](https://github.com/user-attachments/assets/fa6c57d8-0cd9-4a69-9d6a-2f9815846534)






















