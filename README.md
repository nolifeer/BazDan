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
