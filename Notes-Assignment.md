# 🗒️ Notes App – Simple REST API Project

## 🎯 Goal

Build a backend-only application where users can **Create**, **Read**, **Update**, and **Delete** notes (CRUD operations). This project uses **JSON file (no database required)**.

---

## 🧠 What You'll Learn

- REST API principles
- Express routing and middleware
- Handling JSON data
- HTTP methods and status codes
- File I/O

---

## 📌 API Endpoints

| Method | Endpoint     | Description       |
| ------ | ------------ | ----------------- |
| GET    | `/notes`     | Get all notes     |
| GET    | `/notes/:id` | Get a single note |
| POST   | `/notes`     | Create a new note |
| PUT    | `/notes/:id` | Update a note     |
| DELETE | `/notes/:id` | Delete a note     |

---

## 📥 Note Format (JSON)

```json
{
  "id": "1",
  "title": "Meeting Notes",
  "content": "Discuss API design at 10 AM"
}
```

---

## ✅ Steps to Build

1. **Initialize the project**

2. **Set up Express server**

3. **Create CRUD Endpoints**
   Add routes to handle:

   - `GET /notes`
   - `GET /notes/:id`
   - `POST /notes`
   - `PUT /notes/:id`
   - `DELETE /notes/:id`

4. Save notes to a file:
   - Read/write notes to `notes.json` inside a `data/` folder

---

## 🧪 Test with Postman

### ➕ POST `/notes`

**Request Body**

```json
{
  "title": "New Note",
  "content": "Learning REST APIs!"
}
```

**Response**

```json
{
  "id": "123",
  "title": "New Note",
  "content": "Learning REST APIs!"
}
```

---

### 📄 GET `/notes`

Returns an array of all notes:

```json
[
  {
    "id": "123",
    "title": "New Note",
    "content": "Learning REST APIs!"
  }
]
```

---

### ➕ PUT `/notes/{id}`

**Request Body**

```json
{
  "title": "Updated Note",
  "content": "Learning REST APIs with examples."
}
```

**Response**

```json
{
  "id": "123",
  "title": "Updated Note",
  "content": "Learning REST APIs with examples."
}
```

---

### ➕ DELETE `/notes/{id}`

**Response**

```json
{
  "message": "Note deleted successfully."
}
```

---

### ➕ GET `/notes/search?query=REST`

**Response**

```json
[
  {
    "id": "123",
    "title": "Updated Note",
    "content": "Learning REST APIs with examples."
  }
]
```

---

## 🚀 Additional Goals (Brownie points)

- [ ] ✅ Add input validation (e.g. title and content are required)
- [ ] ⏱ Add timestamps: `createdAt`, `updatedAt`
- [ ] 🔐 Add basic authentication using JWT (from auth project)
- [ ] Add a simple **React frontend** or **HTML/CSS client**
- [ ] Use **Swagger** to document the API

---
