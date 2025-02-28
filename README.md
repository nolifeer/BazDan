# Шпора
![5312033621076470302](https://github.com/user-attachments/assets/a14a037b-9ed9-48c3-b228-f2ea43876a4f)
# BazDan
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








