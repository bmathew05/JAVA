# 📋 Rental Management System

## Overview
This project is a **Rental Management System** where landlords can add, update, and delete house details, and tenants can express interest in houses. It uses a database to store house details, and Maven for building and running the project.

---

## Prerequisites

Before you run the project, ensure you have the following installed:

- **Java Development Kit (JDK) 11 or higher**  
- **Maven** (for dependency management and building the project)  
- **MySQL** (or compatible database)  

---

## 🛠️ Database Setup

The application uses a **MySQL database** to store the house details. Follow these steps to set up the database:

### 1️⃣ Create the Database

Open your MySQL command line or a MySQL client (e.g., MySQL Workbench) and execute the following commands:

## 🛠️ 
CREATE DATABASE rental_management;

USE rental_management;

CREATE TABLE houses (
    
    id INT AUTO_INCREMENT PRIMARY KEY,
    
    address VARCHAR(255) NOT NULL,
    
    price DECIMAL(10,2),
    
    isRented TINYINT(1),
    
    name VARCHAR(255),
    
    isInterested TINYINT(1) DEFAULT 0,
    
    tenant_ids TEXT,
    
    approved_list TEXT
);

## 🛠️ Configure Database Connection:

Make sure to configure the database connection in your project. In the DatabaseConnection.java file, update the username and password to match the credentials you set for your MySQL database.

By default, the username is set to root and the password is 12345678:

Change these values to your actual MySQL username and password. For example:

private static final String USERNAME = "your_username";
private static final String PASSWORD = "your_password";
Configure Database URL:

Ensure that the database URL is set to point to the correct MySQL server and database:

private static final String URL = "jdbc:mysql://localhost:3306/rental_management";
Make sure localhost is correct if your database is on a remote server, and rental_management is the name of your database.

## 🛠️ Steps to Run the Project
Clone the Repository:
If you haven't cloned the repository already, you can do so using Git with code below:

git clone <repository_url>
cd <repository_directory>

## Build the Project with Maven:
If you don't have Maven installed, please install it first. You can download and install it from Maven's official site.
Once Maven is installed, navigate to the project directory and run the following command to build the project:

mvn clean install
Run the Project:

## To run the project with JavaFX, use the following Maven command:

mvn javafx:run
This will compile the project and launch the JavaFX application.

## Features
- **Landlord Functionality:**
Add, update, delete house listings.
View and manage rental status.
Approve tenants for specific houses.

- **Tenant Functionality:**
Express interest in renting a house.
View available houses.

- **Filters:**
Filter houses based on rented status.

## Notes
The database stores house details including name, address, price, isRented (boolean), and other attributes.
The application is built using JavaFX for the UI and MySQL for the database.
The tenant_ids and approved_list fields store information about tenant interactions with each house.

## 🛠️Troubleshooting
If you encounter any issues, here are a few things to check:

Ensure the database is running and that your connection details (username, password, URL) are correct.
Ensure that the houses table has been created as shown in the CREATE TABLE SQL command.

## 🛠️ Dependencies
The project uses Maven to manage dependencies. Key dependencies are:
- **JavaFX (for UI)**
- **MySQL Connector/J (for database interaction)**
- **Any other required Java libraries (listed in pom.xml)**
You can view or modify the list of dependencies in the pom.xml file.
