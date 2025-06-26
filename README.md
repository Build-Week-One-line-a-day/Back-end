# 📚 One Line A Day — Back-End API

This is the back-end for the One Line A Day journaling app, built with Node.js and Express. It provides secure authentication and CRUD operations for user journal entries.

**Base URL**:  
https://back-end-c9ai.onrender.com

---

## 🔐 Authentication Routes

### 📝 Register a New User  
**POST** `/api/auth/register`  
Create a new user account.

**Request Body**:
Takes an object including:
```json
{
    "username": "username",
    "password": "pass"
}
```

Returns newly created user object as well as JSON Web Token (JWT)

---

### 🔑 Login Existing User  
**POST** `/api/auth/login`  
Authenticate an existing user.

**Request Body**:
```json
{
  "username": "username",
  "password": "pass"
}
```

**Response**:
Takes an object including:
```json
{
  "username": "username",
  "password": "pass"
}
```
Returns JWT

---

## 🗒️ Posts Endpoints

### 📥 Get Posts by User ID  
**GET** `/api/users/:id/posts`  

> 🧪 **Testing Note**:  
> Database is seeded with 3 users (IDs: 1, 2, 3) and one sample post each.
Returns an array of post objects


---

### ➕ Create a New Post  
**POST** `/api/users/:id/posts`

**Request Body**:
Where :id in URL is user id

Takes an object including:
```json
{
    "title": "title",
    "contents": "contents"
}
```

Returns id of post
**Testing Notice**
Database is seeded with 3 users and 1 sample post for each of them. Use id 1,2 or 3 in URL

---

### ✏️ Update a Post  
**PUT** `/api/users/posts/:id`

**Request Body**:
Where :id in URL is post id

Takes an object including:
```json
{
    "title": "title UPDATED",
    "contents": "contents UPDATED"
}
```

Returns 1 for successful update

---

### ❌ Delete a Post  
**DELETE** `/api/users/posts/:id`

Where :id in URL is post id

Returns "removed: 1" for successful delete

---

## 🧪 How to Run the Backend Locally

### 1. Clone the repo:
```bash
git clone https://github.com/your-username/one-line-a-day-backend.git
cd one-line-a-day-backend
```

### 2. Install dependencies:
```bash
npm install
```

### 3. Set up environment variables:
Create a `.env` file in the root directory and add:
```env
JWT_SECRET=your_super_secret_key
PORT=5000
```

### 4. Run database migrations and seeds:
```bash
npx knex migrate:latest
npx knex seed:run
```

### 5. Start the server:
```bash
npm run server
```

Backend should now be running on:  
[http://localhost:5000](http://localhost:5000)

---

## ⚙️ Technologies Used

- Node.js  
- Express  
- SQLite3 & Knex.js  
- bcryptjs (password hashing)  
- JSON Web Token (JWT) for auth  
- dotenv for environment variables  
- Helmet & CORS for security  
- Nodemon (for development)


### 📫 Contact & Contributors
Built with ❤️ by: [Jesse Tingle](https://github.com/Jesse-Tingle), [Robert Allen](https://github.com/robertjallen), [Wayne Mittelstaedt](https://github.com/WayneMitt)

Project guided by BloomTech / Lambda School curriculum