# 📚 Books REST API

A simple REST API built with Node.js and Express to manage a list of books. This API provides CRUD (Create, Read, Update, Delete) operations for books stored in memory.

## 🚀 Quick Start

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Start the server:**
   ```bash
   npm start
   ```

3. **Server will run on:** `http://localhost:3000`

## 📋 API Endpoints

### 1. Get All Books
- **URL:** `GET /books`
- **Description:** Returns all books in the system
- **Response:**
  ```json
  {
    "success": true,
    "message": "Books retrieved successfully",
    "data": [
      {
        "id": 1,
        "title": "The Great Gatsby",
        "author": "F. Scott Fitzgerald"
      }
    ]
  }
  ```

### 2. Get Book by ID
- **URL:** `GET /books/:id`
- **Description:** Returns a specific book by its ID
- **Response:**
  ```json
  {
    "success": true,
    "message": "Book retrieved successfully",
    "data": {
      "id": 1,
      "title": "The Great Gatsby",
      "author": "F. Scott Fitzgerald"
    }
  }
  ```

### 3. Add New Book
- **URL:** `POST /books`
- **Description:** Adds a new book to the system
- **Request Body:**
  ```json
  {
    "title": "New Book Title",
    "author": "Author Name"
  }
  ```
- **Response:**
  ```json
  {
    "success": true,
    "message": "Book added successfully",
    "data": {
      "id": 4,
      "title": "New Book Title",
      "author": "Author Name"
    }
  }
  ```

### 4. Update Book
- **URL:** `PUT /books/:id`
- **Description:** Updates an existing book by ID
- **Request Body:**
  ```json
  {
    "title": "Updated Book Title",
    "author": "Updated Author Name"
  }
  ```
- **Response:**
  ```json
  {
    "success": true,
    "message": "Book updated successfully",
    "data": {
      "id": 1,
      "title": "Updated Book Title",
      "author": "Updated Author Name"
    }
  }
  ```

### 5. Delete Book
- **URL:** `DELETE /books/:id`
- **Description:** Removes a book from the system
- **Response:**
  ```json
  {
    "success": true,
    "message": "Book deleted successfully",
    "data": {
      "id": 1,
      "title": "The Great Gatsby",
      "author": "F. Scott Fitzgerald"
    }
  }
  ```

## 🧪 Testing with Postman

### Step 1: Import the Collection
1. Open Postman
2. Click "Import" button
3. Select the file: `Books_API_Postman_Collection.json`
4. The collection will be imported with all endpoints ready to test

### Step 2: Test Each Endpoint

#### 1. Get All Books
- Method: `GET`
- URL: `http://localhost:3000/books`
- Click "Send"

#### 2. Get Book by ID
- Method: `GET`
- URL: `http://localhost:3000/books/1`
- Click "Send"

#### 3. Add New Book
- Method: `POST`
- URL: `http://localhost:3000/books`
- Headers: `Content-Type: application/json`
- Body (raw JSON):
  ```json
  {
    "title": "The Hobbit",
    "author": "J.R.R. Tolkien"
  }
  ```
- Click "Send"

#### 4. Update Book
- Method: `PUT`
- URL: `http://localhost:3000/books/1`
- Headers: `Content-Type: application/json`
- Body (raw JSON):
  ```json
  {
    "title": "Updated Title",
    "author": "Updated Author"
  }
  ```
- Click "Send"

#### 5. Delete Book
- Method: `DELETE`
- URL: `http://localhost:3000/books/2`
- Click "Send"

## ⚠️ Error Responses

### 404 - Book Not Found
```json
{
  "success": false,
  "message": "Book not found"
}
```

### 400 - Bad Request (Missing Required Fields)
```json
{
  "success": false,
  "message": "Title and author are required"
}
```

## 📁 Project Structure

```
task3/
├── server.js                              # Main Express server
├── package.json                           # Project configuration
├── README.md                              # This documentation
├── Books_API_Postman_Collection.json      # Postman collection
└── node_modules/                          # Dependencies
```

## 🛠️ Technologies Used

- **Node.js** - JavaScript runtime
- **Express.js** - Web framework for Node.js
- **JSON** - Data format for API communication

## 🎓 Learning Outcomes

This project demonstrates:
- REST API design principles
- HTTP methods (GET, POST, PUT, DELETE)
- Express.js routing and middleware
- JSON request/response handling
- Error handling and status codes
- API documentation and testing 