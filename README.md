
#**TEAM21_DAMG**

**Library Management System (LMS)**



## **Overview**
This project automates the operations of a library by implementing a robust database solution. It adheres to key business rules, supporting user and book management, borrowing and returning transactions, and fine calculations while ensuring data accuracy and security during concurrent user interactions.



## **Features**

### **Member Management**
- Members can borrow and return books.
- Membership statuses (active/inactive) are maintained.

### **Book Inventory Management**
- Librarians can update book details, categories, and stock levels.
- Tracks book locations within the library.

### **Transaction Management**
- Borrow and return transactions are validated for member eligibility and book availability.
- Fines are calculated and imposed for overdue returns.

### **Reporting**
- Dynamic views provide insights into borrowing trends, overdue books, and fine collection.

### **Error Handling**
- Extensive validations ensure business rules are met, including preventing borrowing by inactive members or exceeding stock availability.



## **Project Components**

### **Tables**
- **Tables.sql**: Defines tables for members, books, borrowing transactions, fine dues, and locations.
- **Sample Data**: Includes 10 sample members, books, and borrow/return transactions.

### **Roles**
- **Users.sql**: Creates roles with specific access levels:
  - **LIB_ADMIN**: Full access to all library objects and management capabilities.
  - **LIB_STAFF**: Can manage books and borrowing transactions.
  - **LIB_MEMBER**: Can borrow and return books with limited access to their data.

### **Views**
- **Views.sql**: Defines views for reporting:
  - **Current_Book_Inventory**: Tracks stock levels.
  - **Member_Borrowing_History**: Tracks borrowing and returning history for members.
  - **Overdue_Books**: Lists overdue books and associated fines.
  - **Staff_Transaction_Performance**: Tracks the performance of staff members in managing books.
  - **Category_Wise_Issues**: Summarizes borrowings by book categories.

### **Procedures and Functions**
- **Procedures.sql**:
  - **borrow_book**: Validates and processes a book borrowing transaction.
  - **return_book**: Validates and processes book returns and calculates fines.
  - **add_member**: Adds or updates member details.
- **Functions.sql**:
  - **calculate_fine**: Computes fines for overdue books.

### **Triggers**
- **Triggers.sql**:
  - **Update_Book_Stock**: Adjusts book stock levels after a borrow or return transaction.
  - **Prevent_Over_Borrow**: Ensures that borrowing limits are not exceeded.
  - **Update_Fine_Status**: Automatically updates the fine status after payment.

### **Reports**
- **Reports.sql**: Provides insights such as:
  - Top borrowing members by the number of books issued.
  - Overdue books and associated fines.
  - Borrowing trends by category and location.
  - Fine collection summary by status (paid/unpaid).

## **Physcial Diagram**
![ER Diagram](images/library_er_diagram.png)


## **Execution Steps**

### **Pre-requisites**
- Oracle Database (version 12c or higher).
- SQL Client (e.g., SQL Developer or command-line interface).
- Access credentials for the admin user.

### **Steps**

1. **Create Users and Roles**
   - Execute `Users.sql` to create roles.
   - Assign grants using `Grants.sql`.

2. **Create Database Objects**
   - Run `Tables.sql` to create tables and sequences.

3. **Insert Sample Data**
   - Populate tables with initial sample data.

4. **Create Views**
   - Execute `Views.sql` to create reporting views.

5. **Compile and Execute Procedures and Functions**
   - Run `Procedures.sql` and `Functions.sql`.
   - Validate functionality using test scripts.

6. **Create Triggers**
   - Execute `Triggers.sql`.
   - Test triggers with sample transactions.

7. **Run Reports**
   - Execute `Reports.sql` to generate insights.



## **Error Handling**

### **Common Errors**
- **ORA-01031 (Insufficient Privileges)**:
  - Ensure roles and grants are correctly assigned to users.
- **ORA-02292 (Integrity Constraint Violated)**:
  - Validate foreign key dependencies before deletion.
- **ORA-00001 (Unique Constraint Violated)**:
  - Check for duplicate data during INSERT operations.



## **Conclusion**
The **Library Management System** project demonstrates comprehensive database management, including role-based access control, transaction processing, and robust reporting. It adheres to real-world business rules, ensuring seamless library operations and a secure, scalable solution for managing books and members effectively.


