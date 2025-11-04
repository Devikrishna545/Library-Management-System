# Library Management System

A comprehensive SQL-based Library Management System that manages branches, employees, customers, books, and issue/return transactions.

## 📚 Overview

This project implements a relational database system for managing library operations across multiple branches. It tracks book inventory, customer registrations, book issues and returns, employee information, and branch details.

## 🗄️ Database Structure

### Tables

1. **BRANCH** - Library branch information
   - Branch_no (Primary Key)
   - Manager_Id
   - Branch_address
   - Contact_no

2. **EMPLOYEE** - Employee details
   - Emp_Id (Primary Key)
   - Branch_no (Foreign Key)
   - Emp_name
   - Position
   - Salary

3. **CUSTOMER** - Customer registration data
   - Customer_Id (Primary Key)
   - Customer_name
   - Customer_address
   - Reg_date

4. **BOOKS** - Book inventory
   - ISBN (Primary Key)
   - Book_title
   - Rental_Price
   - Category
   - Status (availability)
   - Author
   - Publisher

5. **ISSUESTATUS** - Book issue tracking
   - Issue_Id (Primary Key)
   - Issued_cust (Foreign Key)
   - Issued_book_name
   - Issue_date
   - Isbn_book (Foreign Key)

6. **RETURNSTATUS** - Book return tracking
   - Return_Id (Primary Key)
   - Return_cust
   - Return_book_name
   - Return_date
   - Isbn_book2 (Foreign Key)

## 🚀 Features

### Data Management
- **10 Library Branches** across major Indian cities (Chennai, Goa, Bangalore, Cochin, Hyderabad, Pune, Jaipur, Ahmedabad, Lucknow, Kolkata)
- **20 Employees** with various positions and salary structures
- **20 Customers** with registration tracking
- **23 Books** across multiple categories (Fiction, Science Fiction, Romance, Classic, Fantasy, Philosophy, History, Malayalam Literature, Mystery)
- **20 Issue Records** and **10 Return Records**

### Query Capabilities

The system includes pre-built queries for:

1. **Available Books Query** - Lists all available books with rental prices and categories
2. **Employee Salary Report** - Displays employees sorted by salary (descending)
3. **Customer Book Count** - Shows number of books issued per customer
4. **Category Statistics** - Counts books in each category
5. **High Salary Filter** - Lists employees earning above ₹50,000
6. **Inactive Customer Report** - Identifies customers registered before 2022 with no book issues
7. **Branch Employee Count** - Shows number of employees per branch
8. **Monthly Issue Report** - Lists customers who issued books in a specific month (May 2023)
9. **Category Filter** - Retrieves books by category (History)
10. **Large Branch Analysis** - Identifies branches with more than 5 employees

## 📊 Sample Data

### Book Categories
- Fiction
- Science Fiction
- Romance
- Classic
- Fantasy
- Philosophy
- History
- Malayalam Literature
- Mystery

### Employee Positions
- Manager
- Assistant Manager
- Accountant
- Sales Executive
- HR Manager
- Marketing Executive
- IT Specialist
- Customer Service Representative
- Operations Manager
- Data Analyst

## 🛠️ Installation & Setup

1. **Prerequisites**
   - MySQL Server (5.7 or higher recommended)
   - MySQL Workbench or any SQL client

2. **Database Creation**
   ```sql
   CREATE DATABASE LIBRARY;
   USE LIBRARY;
   ```

3. **Execute the SQL Script**
   - Run the `MAIN_PROJECT_SQL.sql` file in your MySQL client
   - This will create all tables and populate them with sample data

## 💡 Usage Examples

### Find Available Books
```sql
SELECT BOOK_TITLE, RENTAL_PRICE, CATEGORY 
FROM BOOKS 
WHERE STATUS IS TRUE;
```

### Get Employee Salary Report
```sql
SELECT EMP_NAME, SALARY 
FROM EMPLOYEE 
ORDER BY SALARY DESC;
```

### Find Customers Who Issued Books in May 2023
```sql
SELECT C.CUSTOMER_NAME 
FROM CUSTOMER C 
INNER JOIN ISSUESTATUS I ON I.ISSUED_CUST = C.CUSTOMER_ID
WHERE I.ISSUE_DATE < '2023-06-01' 
  AND I.ISSUE_DATE >= '2023-05-01';
```

### Identify Inactive Customers (Registered Before 2022, No Issues)
```sql
SELECT DISTINCT customer_Id, Reg_date 
FROM (
    SELECT DISTINCT c.customer_Id, c.CUSTOMER_NAME, c.reg_date 
    FROM CUSTOMER c 
    WHERE c.Reg_Date < CAST('2022-01-01' AS DATETIME)
) AS cust 
LEFT JOIN ISSUESTATUS i ON i.issued_cust = cust.customer_id 
WHERE i.issued_cust IS NULL;
```

## 📈 Advanced Features

- **Window Functions** - Used for partitioned counting (books per customer, employees per branch)
- **Foreign Key Constraints** - Ensures referential integrity with CASCADE delete
- **Date/Time Tracking** - Precise tracking of registration, issue, and return dates
- **Boolean Status Flags** - Quick availability checking for books

## 🔐 Database Relationships

- EMPLOYEE.Branch_no → BRANCH.Branch_no (ON DELETE CASCADE)
- ISSUESTATUS.Issued_cust → CUSTOMER.Customer_Id (ON DELETE CASCADE)
- ISSUESTATUS.Isbn_book → BOOKS.ISBN (ON DELETE CASCADE)
- RETURNSTATUS.Isbn_book2 → BOOKS.ISBN (ON DELETE CASCADE)

## 📝 Business Insights

The system can provide insights on:
- Most popular book categories
- Branch performance metrics
- Customer engagement levels
- Employee salary distribution
- Book rental revenue analysis
- Issue/return patterns

## 🤝 Contributing

Feel free to fork this project and submit pull requests for improvements or bug fixes.

## 📄 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

**Devikrishna545**

GitHub: [@Devikrishna545](https://github.com/Devikrishna545)

Repository: [Library-Management-System](https://github.com/Devikrishna545/Library-Management-System)

## 📞 Support

For questions or issues, please open an issue in the GitHub repository.

---

**Note**: This is a demonstration project with sample data. For production use, consider adding:
- User authentication and authorization
- Data validation constraints
- Audit logging
- Backup and recovery procedures
- Performance optimization indexes
- Stored procedures for common operations
