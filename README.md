# Loan Management System Using Python OOP

## Project Overview

This project is a simple Loan Management System developed using Python and Object-Oriented Programming (OOP). The goal was to build a program that demonstrates how a bank might handle loan applications, from the point where a customer applies for a loan to when the loan is approved, disbursed, and eventually repaid.

I developed the system using different classes to represent the people involved in the loan process, including customers, loan officers, bank managers, and compliance officers. Each person has specific responsibilities, just as they would in a real banking environment.

The project also helped me practice working with classes, objects, inheritance, methods, lists, conditional statements, loops, and exception handling in Python.

## How the System Works

The loan process starts when a customer is registered in the system. Each customer has basic information such as their name, user ID, phone number, and monthly income.

Once registered, the customer can apply for a loan by providing the amount needed, the purpose of the loan, and the repayment duration in months.

The system checks the information before creating an application. For example, a customer cannot request a negative loan amount or enter a repayment duration of zero months. It also checks for duplicate application IDs.

Every new application starts with a **PENDING** status.

Before the bank manager can approve the loan, a compliance officer must verify the application. The compliance officer records whether the verification passed or failed, along with notes explaining the result.

If the application passes compliance verification, the bank manager can approve it. Otherwise, the manager can reject the application and provide a reason.

Once a loan is approved, it can be disbursed to the customer. The system then records the outstanding balance.

Customers can make repayments toward their loans. Each repayment reduces the outstanding balance, and once the full amount has been paid, the loan status changes to **PAID**.

## Classes Used in the Project

I divided the program into different classes so that each class handles a particular responsibility.

**1. User**

This is the parent class for customers and employees. It stores information that both groups have in common, such as their names, user IDs, and phone numbers.

**2. Customer**

The Customer class inherits from User. It allows customers to apply for loans, view their applications, and make repayments. Each customer also has a list that keeps track of their loan applications.

**3. Employee**

This class also inherits from User. It adds employee-specific information, including employee ID and department.

**4. LoanOfficer**

The LoanOfficer class inherits from Employee. Its main responsibility is registering loan applications and viewing applications that are still pending.

**5. BankManager**

The BankManager class inherits from Employee. It handles loan approval and rejection. The manager cannot approve an application that has not passed compliance verification.

**6. ComplianceOfficer**

The ComplianceOfficer class inherits from Employee. It is responsible for verifying loan applications and recording the outcome of the verification.

**7. OperationsLead**

This class inherits from both BankManager and ComplianceOfficer. I used it to demonstrate multiple inheritance in Python, where one class can access methods from more than one parent class.

**8. LoanApplication**

This class manages the actual loan information. It stores the application ID, customer ID, requested amount, loan purpose, repayment duration, compliance result, loan status, amount repaid, and outstanding balance.

It also contains methods for approving, rejecting, disbursing, and recording repayments.

## Python Concepts Practiced

Some of the main Python concepts I worked with in this project include:

- **Classes and objects:** Creating separate classes for customers, employees, and loan applications.
- **Inheritance:** Allowing classes such as Customer and Employee to reuse attributes and methods from User.
- **Multiple inheritance:** Using OperationsLead to inherit from BankManager and ComplianceOfficer.
- **Methods:** Defining functions inside classes to handle specific tasks.
- **Lists:** Storing customers and their loan applications.
- **Conditional statements:** Checking whether an application meets the conditions for approval, disbursement, or repayment.
- **Loops:** Searching through customers and loan applications.
- **Exception handling:** Using `try` and `except` to handle invalid inputs without stopping the entire program.
- **Docstrings and comments:** Documenting the methods using Google-style docstrings and adding comments to explain important parts of the code.

## Testing the System

I developed and tested the project in JupyterLab. Instead of testing everything at once, I separated the tests into different notebook cells so I could understand how each method works and identify errors more easily.

Some of the scenarios I tested include:

1. Creating valid loan applications.
2. Attempting to apply for a loan with a negative amount or an invalid repayment duration.
3. Checking for duplicate application IDs.
4. Trying to approve a loan before compliance verification.
5. Recording successful and failed compliance verification.
6. Approving and rejecting loan applications.
7. Disbursing approved loans.
8. Making partial and full repayments.
9. Checking the outstanding balance after repayment.
10. Confirming that OperationsLead inherits methods from both BankManager and ComplianceOfficer.

I also used these tests to check that the system returns appropriate messages when an operation is not allowed.

## Running the Project

The project was written in Python and tested using JupyterLab.

To run it:

1. Download the notebook file from this repository.
2. Open it using JupyterLab or another environment that supports Jupyter notebooks.
3. Run the cell containing the class definitions.
4. Run the test setup cell to create the customer and employee objects.
5. Run the testing cells in order to see how the different methods work.

The notebook also contains a `main()` function with a menu for interacting with the system. To use the menu, run the program's entry-point cell and follow the displayed options.

## Current Limitations

This is a learning project, so the system is not intended for use in an actual bank.

All customer and loan information is stored in memory, meaning the data is lost when the program is restarted. There is no database, user authentication, interest calculation, or actual transfer of money.

The current repayment process tracks the amount borrowed and the outstanding balance without calculating interest or additional bank charges.

These features could be added later as the project is improved.

## What I Learned

Working on this project helped me better understand how Object-Oriented Programming can be used to organize a program into smaller, manageable parts.

One of the most useful things I learned was how different objects interact. For example, a loan officer can register an application through a customer object, while a bank manager can approve the application only after compliance verification.

I also learned the importance of testing both successful and unsuccessful operations. Some errors only became clear when I started running the methods individually in JupyterLab, especially when working with objects created in different notebook cells.

Overall, this project gave me practical experience in writing Python classes, connecting their methods, validating input, handling exceptions, and testing a complete process from beginning to end.

## Tools Used

- Python 3
- JupyterLab
- Visual Studio Code
- GitHub for version control and project documentation
