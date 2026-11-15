# 🎓 Student Management API (ASP.NET Core – 3-Tier Architecture)

## 📖 About the Project
A RESTful API for managing student records, built with ASP.NET Core and a 3-tier architecture. The API provides endpoints to retrieve students, view passing students, calculate the average grade, and create, update, or delete student records.

The application separates HTTP request handling, business logic, and SQL Server data access into distinct layers. Swagger is configured to document and test the API during development.

This project is another milestone in the Abu-Hadhoud Platform training track with Dr. Muhammed Abu-Hadhoud.

## 📌 Features

### 1. 📚 Student Queries
* **Get All Students:** Retrieve all student records.
* **Get Student by ID:** Fetch an individual student by their ID.
* **Get Passed Students:** Retrieve students classified as having passed.
* **Average Grade:** Calculate and return the average student grade.

### 2. ✏️ Student Management
* **Add Student:** Create a student record and return its generated ID.
* **Update Student:** Modify an existing student's name, age, and grade.
* **Delete Student:** Remove a student record by ID.

### 3. ✅ Request Validation
* Checks student IDs and required student data.
* Returns appropriate HTTP responses, including `200 OK`, `201 Created`, `400 Bad Request`, and `404 Not Found`.

### 4. 📖 API Documentation
* Swagger UI is enabled in the Development environment.
* API routes are grouped under `/api/Students`.

## 🏗️ Architecture & Technical Highlights
* **3-Tier Architecture:** Separates the API/controller layer, business logic layer, and data access layer.
* **RESTful API:** Uses HTTP GET, POST, PUT, and DELETE endpoints.
* **Stored Procedures:** Uses SQL Server stored procedures for database operations.
* **DTO-Based Responses:** Returns `StudentDTO` objects rather than exposing business-layer objects.
* **ADO.NET:** Uses `Microsoft.Data.SqlClient` to connect to SQL Server.

## 🛠️ Technologies Used
* **C#**
* **ASP.NET Core Web API**
* **ADO.NET**
* **Microsoft.Data.SqlClient**
* **SQL Server**
* **Swagger / OpenAPI**

## 🔗 API Endpoints

| Method | Route | Description |
|---|---|---|
| `GET` | `/api/Students/All` | Get all students |
| `GET` | `/api/Students/Passed` | Get passed students |
| `GET` | `/api/Students/AverageGrade` | Get the average grade |
| `GET` | `/api/Students/{id}` | Get a student by ID |
| `POST` | `/api/Students` | Add a student |
| `PUT` | `/api/Students/{id}` | Update a student |
| `DELETE` | `/api/Students/{id}` | Delete a student |

## ⚠️ Notes
* The current connection string contains hard-coded credentials. Use configuration such as `appsettings.json` or user secrets for real deployments.
* The passing criteria is defined by the `SP_GetPassedStudents` stored procedure.
* The API's validation currently checks for negative ages and grades, but does not enforce upper bounds.
