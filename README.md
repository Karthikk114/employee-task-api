# employee-task-api
📘 Project Explanation

This project is a Spring Boot REST API that manages Employees and their Tasks using a real MySQL database.
It demonstrates how to build a clean and scalable backend application using Spring Boot, Spring Data JPA, and Hibernate.

🎯 What This Project Does
✔ Manage Employees

You can add, update, delete, and view employees in the system.

✔ Manage Tasks

You can create tasks, assign them to employees, update task status, or delete them.

✔ Employee–Task Relationship

One employee can have multiple tasks.

A task may be linked to an employee or left unassigned.

🧱 How the Project Works (Layer Explanation)
🟦 1. Entity Layer (Model Layer)

These are Java classes mapped to database tables using JPA annotations.

Employee → represents employees table

Task → represents tasks table

Each Entity defines:

Table structure

Fields (columns)

Relationships (like employee–task)

🟩 2. Repository Layer

These are interfaces that extend JpaRepository.
They provide all necessary database operations automatically, like:

save()

findById()

findAll()

deleteById()

You don’t need to write SQL manually — JPA handles it.

🟧 3. Service Layer

This contains business logic.

Validates data

Throws error if employee/task doesn't exist

Handles update logic

Manages employee–task relationships

Services act like a "middle layer" between Controller and Repository.

🟥 4. Controller Layer

Controllers expose the REST API endpoints.

Example:

POST /api/employees → Create employee

GET /api/tasks → Get all tasks

Controllers receive HTTP requests from Postman or frontend and return JSON responses.

🗄️ Database Explanation

The project uses MySQL as the database.

Employees Table

Stores employee details.

Tasks Table

Stores task details and includes employee_id foreign key.

This means:

many tasks → belonged to 1 employee

If employee is deleted:

their tasks become unassigned (employee_id is set to NULL)

🌐 How to Use the API

You can test the API using Postman, Thunder Client, or any frontend.

Example:

Create Employee (POST)
{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "9876543210",
  "department": "IT"
}

Create Task (POST)
{
  "title": "Fix Login Page",
  "description": "Error on user login",
  "status": "OPEN",
  "employee": { "id": 1 }
}


The API returns JSON results for each operation.

💡 Why This Project Is Useful

✔ Teaches full CRUD operations
✔ Shows MySQL + Spring Boot integration
✔ Demonstrates clean architecture
✔ Simple example for beginners
✔ Can be expanded into real applications (HR system, Task Manager, Admin Dashboard)
