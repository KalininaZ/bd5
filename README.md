# bd5
1.Выберите из таблицы orders 4 самых дорогих заказов за всё время. Данные нужно отсортировать в порядке убывания цены. Отмененные заказы не учитывайте.

SELECT id, user_id, products_count, sum, status FROM orders WHERE status != 'cancelled' ORDER BY sum DESC LIMIT 4;

![image](https://github.com/user-attachments/assets/8cd51852-1d8d-454e-80b5-29b0a252c77b)

2.Выберите из таблицы products название и цены четырех самых дешевых товаров, которые есть на складе.

SELECT name, price FROM products WHERE COUNT > 0 ORDER BY price ASC LIMIT 4;

![image](https://github.com/user-attachments/assets/bd821dfb-3dab-4700-b779-b6682199c182)

3.Выберите из таблицы orders три последних заказа (по дате date) стоимостью от 3200 рублей и выше. Данные отсортируйте по дате в обратном порядке.

SELECT id, user_id, products_count, sum, status, date FROM orders WHERE sum >= 3200 ORDER BY date DESC LIMIT 3;

![image](https://github.com/user-attachments/assets/eb9c0e09-5a5b-4c03-9b59-00c4129291be)

4.Создайте данную таблицу: 
CREATE TABLE products ( id INT UNSIGNED NOT NULL PRIMARY KEY AUTO_INCREMENT, name VARCHAR(255) NOT NULL, count INT NOT NULL DEFAULT 0, price INT NOT NULL );

INSERT INTO products (name, count, price) VALUES ('Стиральная машина', 5, 10000), ('Холодильник', 0, 10000), ('Микроволновка', 3, 4000), ('Пылесос', 2, 4500), ('Вентилятор', 0, 700), ('Телевизор', 7, 31740), ('Тостер', 2, 2500), ('Принтер', 4, 3000), ('Активные колонки', 1, 2900), ('Ноутбук', 4, 36990), ('Посудомоечная машина', 0, 17800), ('Видеорегистратор', 23, 4000), ('Смартфон', 8, 12300), ('Флешка', 4, 1400), ('Блендер', 0, 5500), ('Газовая плита', 5, 11900), ('Клавиатура', 3, 1800);

![image](https://github.com/user-attachments/assets/63971408-313f-43bd-9b8a-62cf163fd3f0)

![image](https://github.com/user-attachments/assets/ba275f36-7bca-4ce1-8ac4-8d19b0a0d22d)

5..Из этой таблицы сделать выборку на основе задания: Сайт выводит товары по 5 штук. Выберите из таблицы products товары, которые пользователи увидят на 3 странице каталога при сортировке в порядке возрастания цены (price).

SELECT id, name, count, price FROM products ORDER BY price ASC LIMIT 5 OFFSET 10;

![image](https://github.com/user-attachments/assets/2801506e-3d0c-4714-80cd-21a6015c0060)
