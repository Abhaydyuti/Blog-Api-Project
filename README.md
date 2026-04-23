# 📝 Blog API Project

A full-stack blog application built with **Node.js** and **Express**, featuring a RESTful API backend and an EJS-powered frontend server.

---

## 🏗️ Project Structure

```
blog-api-project/
├── public/
│   └── styles/
│       └── main.css
├── views/
│   ├── index.ejs
│   └── modify.ejs
├── index.js       # REST API server (Port 4000)
└── server.js      # Frontend server (Port 3000)
```

---

## ⚙️ How It Works

The project runs two servers simultaneously:

| Server | File | Port | Responsibility |
|--------|------|------|----------------|
| API Server | `index.js` | 4000 | Handles data — CRUD operations on posts |
| Frontend Server | `server.js` | 3000 | Serves EJS views, communicates with API via Axios |

The frontend server acts as a middleman — it receives requests from the browser, calls the API server using Axios, and renders the response using EJS templates.

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18+ recommended)
- npm

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/blog-api.git
cd blog-api

# Install dependencies
npm install
```

### Running the App

You need to start **both servers** in separate terminals:

```bash
# Terminal 1 — Start the API server
node index.js

# Terminal 2 — Start the frontend server
node server.js
```

Then open your browser and visit: [http://localhost:3000](http://localhost:3000)

---

## 📡 API Reference

Base URL: `http://localhost:4000`

### Get All Posts
```
GET /posts
```

### Get a Single Post
```
GET /posts/:id
```

### Create a New Post
```
POST /posts

Body (JSON):
{
  "title": "Post Title",
  "content": "Post content here...",
  "author": "Author Name"
}
```

### Update a Post (Partial)
```
PATCH /posts/:id

Body (JSON) — include only fields to update:
{
  "title": "Updated Title"
}
```

### Delete a Post
```
DELETE /posts/:id
```

---

## 🖥️ Frontend Routes

Base URL: `http://localhost:3000`

| Route | Description |
|-------|-------------|
| `GET /` | View all blog posts |
| `GET /new` | Form to create a new post |
| `GET /edit/:id` | Form to edit an existing post |
| `POST /api/posts` | Submit a new post |
| `POST /api/posts/:id` | Submit edits to an existing post |
| `GET /api/posts/delete/:id` | Delete a post |

---

## 🛠️ Built With

- [Express.js](https://expressjs.com/) — Web framework
- [EJS](https://ejs.co/) — Templating engine
- [Axios](https://axios-http.com/) — HTTP client for server-to-server requests
- [body-parser](https://www.npmjs.com/package/body-parser) — Request body parsing

---

## 📌 Notes

- Data is stored **in-memory** — all posts reset when the API server restarts.
- There is no database connected; this project is intended as a learning exercise for RESTful API design and Express routing.
