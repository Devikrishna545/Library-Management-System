# Library Management System - SQL Project

A comprehensive database management system for libraries, designed to efficiently manage books, members, staff, and transaction records.

## 📚 Project Overview

This Library Management System is a SQL-based project developed as part of the **Entri Course - Data Science and Machine Learning** program. The project demonstrates the practical application of database design principles, SQL queries, and data management techniques essential for real-world library operations.

## 🎯 Objectives

- Design and implement a normalized relational database for library management
- Perform CRUD operations (Create, Read, Update, Delete) on library data
- Execute complex SQL queries to extract meaningful insights
- Manage relationships between books, members, staff, and transactions
- Generate reports for library administration

## 🗂️ Database Schema

The database consists of multiple tables to manage:

- **Books**: Book inventory with details like title, author, ISBN, genre, and availability
- **Members**: Library member information and membership details
- **Staff**: Employee records and roles
- **Transactions**: Book issue and return records
- **Categories/Genres**: Book classification system

## ✨ Key Features

- **Book Management**: Add, update, and track books in the library inventory
- **Member Management**: Register and manage library member accounts
- **Transaction Tracking**: Record book issues and returns with timestamps
- **Search Functionality**: Query books by title, author, genre, or availability
- **Report Generation**: Generate reports on popular books, overdue items, and member activity
- **Data Integrity**: Implemented foreign key constraints and data validation

## 🛠️ Technologies Used

- **Database**: MySQL / PostgreSQL / SQL Server
- **Language**: SQL (Structured Query Language)
- **Tools**: MySQL Workbench / pgAdmin / SQL Server Management Studio

## 📋 SQL Operations Demonstrated

### Basic Operations
- CREATE TABLE statements for database structure
- INSERT queries for data population
- SELECT queries with WHERE, ORDER BY, and GROUP BY clauses
- UPDATE and DELETE operations

### Advanced Operations
- JOIN operations (INNER, LEFT, RIGHT)
- Subqueries and nested queries
- Aggregate functions (COUNT, SUM, AVG, MAX, MIN)
- String functions and date operations
- Views creation for complex queries
- Stored procedures (if applicable)

## 📊 Sample Queries

Examples of queries implemented in this project:

1. Find all available books in a specific genre
2. List all overdue books and their borrowers
3. Count total books issued per member
4. Identify most popular books by issue count
5. Search for books by author or title
6. Generate monthly transaction reports

## 🚀 Getting Started

### Prerequisites
- MySQL/PostgreSQL installed on your system
- Basic understanding of SQL syntax

### Installation

1. Clone or download the project files
2. Open your SQL client (MySQL Workbench, pgAdmin, etc.)
3. Create a new database:
   ```sql
   CREATE DATABASE library_management;
   USE library_management;
   ```
4. Execute the schema creation script to build tables
5. Run the data insertion script to populate sample data
6. Execute query files to test functionality

## 📁 Project Structure

```
library-management-sql/
│
├── schema/
│   └── create_tables.sql          # Database schema creation
│
├── data/
│   └── insert_data.sql            # Sample data insertion
│
├── queries/
│   ├── basic_queries.sql          # Basic CRUD operations
│   ├── advanced_queries.sql       # Complex queries and joins
│   └── reports.sql                # Report generation queries
│
└── README.md                       # Project documentation
```

## 🎓 Learning Outcomes

Through this project, I have gained practical experience in:

- Designing normalized database schemas
- Writing efficient SQL queries
- Managing relationships between tables
- Implementing data integrity constraints
- Analyzing and reporting data using SQL
- Applying database concepts to real-world scenarios

## 👨‍💻 Author

**Devikrishna545**

Project developed as part of Entri's Data Science and Machine Learning course

## 📝 License

This project is created for educational purposes as part of the Entri course curriculum.

## 🙏 Acknowledgments

- Entri Course - Data Science and Machine Learning program
- Instructors and mentors who guided this project
- Open-source SQL community for documentation and resources

---

**Note**: This is an educational project demonstrating SQL database management concepts and query writing skills.
