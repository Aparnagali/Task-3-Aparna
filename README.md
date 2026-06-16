# Project 3 - Database Integration

## Overview

This project demonstrates how to integrate a PostgreSQL database with a Node.js and Express.js backend application. It provides REST API endpoints to perform CRUD (Create, Read, Update, Delete) operations on student records.

## Features

- Connect Node.js application with PostgreSQL
- Create student records
- Retrieve all students
- Retrieve a student by ID
- Update student details
- Delete student records
- RESTful API implementation

## Technologies Used

- Node.js
- Express.js
- PostgreSQL
- pg (PostgreSQL Client)
- CORS
- Nodemon

## Project Structure

```text
Project3/
│
├── server.js
├── db.js
├── package.json
├── package-lock.json
├── README.md
└── node_modules/
```

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Navaneetha995/task-3-navaneetha.git
cd task-3-navaneetha
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Create Database

Open pgAdmin and create a database:

```sql
CREATE DATABASE student_db;
```

### 4. Create Students Table

```sql
CREATE TABLE students (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL
);
```

### 5. Configure Database Connection

Update the database credentials in `db.js`:

```javascript
const { Pool } = require("pg");

const pool = new Pool({
  user: "postgres",
  host: "localhost",
  database: "student_db",
  password: "your_password",
  port: 5432,
});

module.exports = pool;
```

### 6. Run the Application

```bash
npm start
```

Or:

```bash
npm run dev
```

## Server URL

```text
http://localhost:5000
```

## API Endpoints

### Home Route

```http
GET /
```

Response:

```json
{
  "message": "Database Integration Project Running"
}
```

### Get All Students

```http
GET /students
```

### Get Student By ID

```http
GET /students/:id
```

### Create Student

```http
POST /students
```

Request Body:

```json
{
  "name": "Rahul",
  "email": "rahul@gmail.com"
}
```

### Update Student

```http
PUT /students/:id
```

Request Body:

```json
{
  "name": "Rahul Kumar",
  "email": "rahulkumar@gmail.com"
}
```

### Delete Student

```http
DELETE /students/:id
```

## Testing

Use Postman to test the API endpoints.

Example:

```http
POST http://localhost:5000/students
```

Body:

```json
{
  "name": "Rahul",
  "email": "rahul@gmail.com"
}
```

## Sample Output

```json
[
  {
    "id": 1,
    "name": "Rahul",
    "email": "rahul@gmail.com"
  }
]
```

## Learning Outcomes

- Database Integration with PostgreSQL
- Building REST APIs using Express.js
- CRUD Operations
- API Testing using Postman
- Backend Development Fundamentals

## Output Screenshots

Add your screenshots in a folder named `screenshots` and include them here:

```md
![Output 1](output1.png)
![Output 2](output2.png)
```

## Author

**Navaneetha**

## License

This project is created for educational and internship purposes.