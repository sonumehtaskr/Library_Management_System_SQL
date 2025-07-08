
# Library Management System

The Library Management System is a project designed to streamline the administration of library functions. It enables users to borrow books, search for titles, and access detailed information about the library’s collection. By automating these tasks, the system eliminates the need for manual tracking and provides a seamless, user-friendly experience.

## Project Overview

The primary goal of this project is to create a comprehensive system that simplifies the management of books within a library. It features a centralized database containing key details about each book, such as title, price, availability, and quantity. The system improves the process of borrowing books and offers users easy access to the library's resources, making it a modern, efficient alternative to traditional paper-based record-keeping.

## Project Layout

```
├── README.md               <- Project documentation.
├── LMS_query.sql           <- Final SQL query for the project.
├── LMS_schema.sql          <- Database schema for the project.
    
```

---

# Library Management System - Database Schema

## Table: books

The `books` table holds details about the books in the library.

### Columns

| Column Name   | Data Type     | Constraints | Description                                          |
| ------------- | ------------- | ----------- | ---------------------------------------------------- |
| id            | SERIAL        | PRIMARY KEY | Unique ID for each book                              |
| title         | VARCHAR(255)  | NOT NULL    | The book's title                                     |
| author        | VARCHAR(255)  | NOT NULL    | The author of the book                               |
| category      | VARCHAR(255)  | NOT NULL    | The category or genre of the book                    |
| price         | DECIMAL(10,2) | NOT NULL    | Price of the book                                    |
| status        | VARCHAR(255)  | NOT NULL    | The current status (e.g., available, borrowed, sold) |
| total\_copies | INT           | NOT NULL    | Total number of copies available                     |

## Table: customers

The `customers` table tracks information about library members.

### Columns

| Column Name   | Data Type    | Constraints | Description                 |
| ------------- | ------------ | ----------- | --------------------------- |
| id            | SERIAL       | PRIMARY KEY | Unique ID for each customer |
| first\_name   | VARCHAR(255) | NOT NULL    | First name of the customer  |
| last\_name    | VARCHAR(255) | NOT NULL    | Last name of the customer   |
| email         | VARCHAR(255) | NOT NULL    | Customer's email address    |
| phone\_number | VARCHAR(20)  | NOT NULL    | Customer's phone number     |

## Table: issued\_books

The `issued_books` table logs information about books borrowed by customers.

### Columns

| Column Name  | Data Type | Constraints | Description                          |
| ------------ | --------- | ----------- | ------------------------------------ |
| id           | SERIAL    | PRIMARY KEY | Unique ID for the issued book        |
| book\_id     | INT       | NOT NULL    | Foreign key to the `books` table     |
| customer\_id | INT       | NOT NULL    | Foreign key to the `customers` table |
| issue\_date  | DATE      | NOT NULL    | The date the book was borrowed       |
| due\_date    | DATE      | NOT NULL    | The book's due return date           |
| return\_date | DATE      |             | The actual return date (if returned) |

---

## Key Features

The Library Management System includes several features to enhance usability:

* Intuitive interface for easy interaction and navigation.
* Detailed records for each book, including title, price, status, and quantity.
* Quick search options to help users find books by title.
* Efficient book borrowing process for both issuing and returning books.
* Centralized database that stores and organizes all book-related information.
* Automated tracking of book availability and stock levels.

These features ensure that the Library Management System provides a robust, efficient, and user-friendly way to manage library operations.

## Conclusion

This Library Management System offers an automated and more effective approach to managing a library's collection. With an intuitive user interface, detailed book information, and a powerful search engine, the system modernizes the book management process. By using SQL queries to interact with a centralized database, it makes accessing and managing library information easier for both staff and patrons.
