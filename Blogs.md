# Blog API – Full Stack REST API with a Real Database

## 🎯 Goal

Build a feature-rich blogging API where users (authors) can create, read, update, and delete blog posts. Add support for features like filtering, pagination, and bonus features like comments and likes. This project introduces how to interact with a real database and handle relations.

---

## 🧠 What You'll Learn

- How to structure an Express project
- Connecting to and querying a real database
- Performing CRUD operations with persistent storage
- Modeling one-to-many relationships (e.g., 1 author → many posts)
- Handling pagination and filtering with query params
- Building RESTful APIs that follow best practices
- Error handling and HTTP status codes

---

## 📌 Main Features

### ✅ Authors

Create an author (username, email, bio, etc.)
Get list of authors
View author profile and their posts

### ✅ Posts

Create, read, update, delete a blog post
Associate a post with an author
List posts with pagination
Filter posts by category, tags, or author
🗨️ Comments: Users can comment on posts
❤️ Likes: Add a like count to posts or comments

---

## 🧪 Example API Endpoints

| Method | Endpoint           | Description                    |
| ------ | ------------------ | ------------------------------ |
| GET    | /posts             | Get all blog posts (paginated) |
| GET    | /posts/:id         | Get a single post              |
| POST   | /posts             | Create a new post              |
| PUT    | /posts/:id         | Update a post                  |
| DELETE | /posts/:id         | Delete a post                  |
| GET    | /authors/:id/posts | Posts by a specific author     |

---

## 🧪 Test with Postman

### ➕ POST `/authors`

**Request Body**

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "bio": "A backend developer and tech blogger."
}
```

**Response**

```json
{
  "id": "a1b2c3",
  "name": "John Doe",
  "email": "john@example.com",
  "bio": "A backend developer and tech blogger.",
  "createdAt": "2025-04-10T10:00:00Z"
}
```

### ➕ POST /posts

**Request Body**

```json
{
  "title": "How to Build a REST API",
  "content": "This is a guide on building a REST API with Express.",
  "authorId": "a1b2c3",
  "tags": ["api", "nodejs", "express"]
}
```

**Response**

```json
{
  "id": "p123",
  "title": "How to Build a REST API",
  "content": "This is a guide on building a REST API with Express.",
  "authorId": "a1b2c3",
  "tags": ["api", "nodejs", "express"],
  "likes": 0,
  "comments": [],
  "createdAt": "2025-04-10T10:05:00Z"
}
```

### 📄 GET /posts?page=1&limit=10?tag=api?author=John Doe

Query Parameters

?page=1&limit=10 – Pagination

?tag=api – Filter by tag

?author=John Doe – Filter by author name

**Response**

```json
{
  "page": 1,
  "limit": 10,
  "totalPosts": 2,
  "posts": [
    {
      "id": "p123",
      "title": "How to Build a REST API",
      "author": "John Doe",
      "tags": ["api", "nodejs"],
      "createdAt": "2025-04-10T10:05:00Z"
    },
    {
      "id": "p124",
      "title": "Intro to MongoDB",
      "author": "Jane Smith",
      "tags": ["mongodb", "nosql"],
      "createdAt": "2025-04-09T08:00:00Z"
    }
  ]
}
```

### ✏️ PUT /posts/:id

**Request Body**

```json
{
  "title": "How to Build a RESTful API with Express",
  "tags": ["api", "nodejs", "rest"]
}
```

**Response**

```json
{
  "id": "p123",
  "title": "How to Build a RESTful API with Express",
  "content": "This is a guide on building a REST API with Express.",
  "tags": ["api", "nodejs", "rest"],
  "updatedAt": "2025-04-10T11:30:00Z"
}
```

### ❌ DELETE /posts/:id

**Response**

```json
{
  "message": "Post deleted successfully"
}
```

### 🗨️ POST /posts/:id/comments

**Request Body**

```json
{
  "author": "Alice",
  "text": "Great article! Thanks for sharing."
}
```

**Response**

```json
{
  "id": "c456",
  "author": "Alice",
  "text": "Great article! Thanks for sharing.",
  "createdAt": "2025-04-10T12:00:00Z"
}
```

### ❤️ POST /posts/:id/like

**Response**

```json
{
  "postId": "p123",
  "likes": 1
}
```

---

## 🚀 Additional Goals (Brownie points)

- [ ] 🔐 Add basic authentication using JWT (from auth project)
- [ ] 📃 Use **Swagger** to document the API
- [ ] Tagging system for posts
- [ ] Search functionality (by title/content)
