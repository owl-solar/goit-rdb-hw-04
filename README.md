# goit-rdb-hw-04
Go IT
ДЗ №4: Реляційні бази даних для Data Science (Olist Brazilian E-commerce)

Опис проєкту

Цей репозиторій містить виконання домашнього завдання з теми «Реляційні бази даних для Data Science». Основна мета роботи це розгортання локальної бази даних PostgreSQL (через pgembed у середовищі Google Colab), створення структурованої typed-схеми з обмеженнями (DDL, Constraints, Foreign Keys), виконання просунутих операцій маніпуляції даними (DML, RETURNING, ON CONFLICT), побудова складних JOIN-звітів, агрегацій (GROUP BY, HAVING), а також використання операторів множин (SET OPERATIONS) і віконних функцій (Window Functions).

Джерело датасету та спосіб отримання
Назва датасету: Brazilian E-Commerce Public Dataset by Olist

Охоплення даних: Реальні дані про понад 100 000 замовлень з 2016 по 2018 рік на платформі Olist у Бразилії.

Sample-розмір / Обсяг файлів:
olist_customers_dataset.csv (~99k рядків)
olist_orders_dataset.csv (~99k рядків)
olist_order_items_dataset.csv (~112k рядків)
olist_products_dataset.csv (~32k рядків)
olist_sellers_dataset.csv (~3k рядків)
olist_order_reviews_dataset.csv (~100k рядків)

Інструкція з отримання: Файли автоматично завантажуються безпосередньо у середовище виконання з платформи Kaggle під час першого запуску Jupyter Notebook за допомогою бібліотеки kagglehub.

Технологічний стек
СУБД: PostgreSQL (розгорнута локально через pgembed / pgserver)

Середовище розробки: Google Colab / Jupyter Notebook

Бібліотеки Python:
sqlalchemy, psycopg2-binary, psycopg[binary] — для підключення та виконання SQL-запитів
pandas — для роботи з DataFrame та міграції raw-даних
kagglehub — для автоматичного завантаження датасету


Зміст виконаних завдань у Notebook
Завдання 1 (Setup і typed-схема Olist): Ініціалізація локальної БД, завантаження сирих CSV-файлів, створення реляційної схеми з обмеженнями (PRIMARY KEY, FOREIGN KEY, CHECK, INDEX) та безпечна міграція даних (INSERT ... SELECT).

Завдання 2 (DML-запити з PostgreSQL-фічами):
Створення аудиту алерту для продавців із запізненнями (INSERT ... RETURNING).
Ідемпотентний розрахунок і апсерт рейтингів продавців (INSERT ... ON CONFLICT DO UPDATE).
Масове оновлення прапорців запізнень у замовленнях (UPDATE ... FROM).
Контрольоване очищення застарілих даних (DELETE ... RETURNING).

Завдання 3 (Customer Segments & RFM): Створення дедуплікованого виміру покупців (olist_customer_dim за customer_unique_id), таблиці customer_segments з виробничими обмеженнями та розрахунок RFM-сегментації.

Завдання 4 (JOIN-запити з business-interpretation): Побудова та бізнес-інтерпретація 5 типів об'єднань (INNER JOIN на 4 таблицях, LEFT JOIN з COALESCE, FULL OUTER JOIN, SELF JOIN, Anti-join).

Завдання 5 (GROUP BY, HAVING і агрегати): Агреговані розрахунки виручки та середнього чека (AOV) з фільтрацією груп через HAVING, а також використання STRING_AGG для агрегації списків категорій товарів покупця.

Завдання 6 (Set operations, Window functions & Reflection): Використання операторів множин (UNION, INTERSECT), застосування віконної функції ROW_NUMBER() для пошуку найновіших транзакцій, а також фінальна рефлексія щодо проєкту.

Автор: Мархарита Черкашина (Marharyta Cherkashyna)
