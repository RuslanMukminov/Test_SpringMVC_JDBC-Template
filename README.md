# Проект №1 "Spring MVC. JDBC Template"

### Это один из домашних проектов в рамках курса "Spring - Полный курс" от команды SwiftBook ([ссылка на курс](https://swiftbook.org/courses/438/show_promo)).

В данном задании реализовано веб-приложение для цифрового учета книг в библиотеке, техническое задание - в файле [TZ.md](https://github.com/RuslanMukminov/Test_SpringMVC_JDBC-Template/blob/main/TZ.md).

В качестве базы данных используется PostgreSQL (в программе используется локальное подключение). В БД две таблицы 'Person' и 'Book'
в отношении "One to Many".

Приложение взаимодействует с БД с помощью JDBC Template - что позволяет нам самим писать SQL-запросы.

Представления - страницы HTML - выполнены с помощью шаблонизатора Thymeleaf.

<details>
 <summary>Команда для создания необходимых таблиц в БД:</summary>
 
 ```sql
	CREATE TABLE Person (
		id int GENERATED BY DEFAULT AS IDENTITY PRIMARY KEY,
		full_name varchar(100) NOT NULL UNIQUE,
		year_of_birth int NOT NULL
	);

	CREATE TABLE Book (
		id int GENERATED BY DEFAULT AS IDENTITY PRIMARY KEY,
		title varchar(100) NOT NULL,
		author varchar(100) NOT NULL,
		year int NOT NULL,
		person_id int REFERENCES Person(id) ON DELETE SET NULL
	);
 ```
</details>
 
