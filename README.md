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
  
- (50) - это максимальная длина строки, которая может быть сохранена в этом столбце. В данном случае, максимальная длина составляет 50 символов.

  INT в SQL обозначает тип данных, используемый для хранения целых чисел.

  DATE в SQL используется для хранения дат
  
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














