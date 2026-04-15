# Node.js MVC Pattern

A RESTful API built with **Node.js**, **Express**, and **MongoDB** (Mongoose), following the **Model-View-Controller (MVC)** architecture pattern.

## Project Structure

```
├── index.js              # Entry point - Express server setup
├── connections.js         # MongoDB connection handler
├── models/
│   └── user.js           # Mongoose schema & model for User
├── controllers/
│   └── user.js           # Business logic for user CRUD operations
├── routes/
│   └── user.js           # Express Router - maps endpoints to controllers
├── middlewares/
│   └── index.js          # Custom middleware (request logger)
├── package.json
└── .gitignore
```

## Tech Stack

- **Runtime**: Node.js
- **Framework**: Express.js v5
- **Database**: MongoDB with Mongoose ODM
- **Dev Tool**: Nodemon (auto-restart on file changes)

## Features

- Full **CRUD** operations for Users (Create, Read, Update, Delete)
- **MVC architecture** for clean separation of concerns
- **Custom middleware** for logging all incoming requests (method, path, IP, timestamp) to `log.txt`
- **MongoDB** integration with Mongoose schemas including timestamps
- Input validation on user creation

## API Endpoints

| Method   | Endpoint      | Description          |
|----------|---------------|----------------------|
| `GET`    | `/users`      | Get all users        |
| `POST`   | `/users`      | Create a new user    |
| `GET`    | `/users/:id`  | Get a user by ID     |
| `PATCH`  | `/users/:id`  | Update a user by ID  |
| `DELETE` | `/users/:id`  | Delete a user by ID  |

### Create User - Request Body (x-www-form-urlencoded)

| Field        | Required |
|--------------|----------|
| `first_name` | Yes      |
| `last_name`  | Yes      |
| `email`      | Yes      |
| `gender`     | Yes      |
| `job_title`  | Yes      |

## User Schema

```javascript
{
  firstName:  { type: String, required: true },
  lastName:   { type: String },
  email:      { type: String, required: true, unique: true },
  jobTitle:   { type: String },
  gender:     { type: String },
  createdAt:  { type: Date },   // auto-generated
  updatedAt:  { type: Date }    // auto-generated
}
```

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) installed
- [MongoDB](https://www.mongodb.com/) running locally on `mongodb://127.0.0.1:27017`

### Installation

```bash
# Clone the repo
git clone https://github.com/Shubham-Sharma1995/NodeJS_MVC_Pattern.git
cd NodeJS_MVC_Pattern

# Install dependencies
npm install

# Start the server (uses nodemon)
npm start
```

The server will start at **http://localhost:8000**.

## What I Learned

- Structuring a Node.js project using the **MVC design pattern**
- Creating **Mongoose schemas and models** with validation and timestamps
- Building **RESTful APIs** with Express Router
- Writing **custom middleware** for request logging
- Separating concerns: routes → controllers → models
- Using **nodemon** for a better development experience