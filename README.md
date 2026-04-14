

# Task Manager - Node.js + MySQL

A full CRUD application designed for task management, built using Node.js, Express, and MySQL.

## 🚀 Features

* ✅ Create, retrieve, update, and delete tasks
* 🎯 Priority levels available (Low, Medium, High)
* 💾 Data storage handled through MySQL
* 🔄 RESTful API structure
* 📱 Responsive interface powered by Bootstrap

## 📋 Prerequisites

* Node.js (version 14 or higher)
* MySQL Server (version 5.7 or higher)
* npm or yarn

## ⚙️ Setup

1. **Install dependencies:**

```bash
npm install
```

2. **Set up the database:**

   * Run the `database.sql` file on your MySQL server:

```bash
mysql -u root -p < database.sql
```

3. **Configure environment variables:**

   * Duplicate `.env.example` and rename it to `.env`:

```bash
cp .env.example .env
```

* Update the `.env` file with your MySQL credentials:

```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=task_manager
PORT=3000
```

## 🏃 Running the Application

**Start only the API server:**

```bash
npm start
```

**Development mode (using nodemon):**

```bash
npm run dev
```

The API server will be available at:
`http://localhost:3000`

**Note:** The frontend is served via nginx at:
`http://localhost:8080`

## 📡 API Routes

| Method | Endpoint         | Description             |
| ------ | ---------------- | ----------------------- |
| GET    | `/api/tasks`     | Retrieve all tasks      |
| POST   | `/api/tasks`     | Add a new task          |
| PUT    | `/api/tasks/:id` | Modify an existing task |
| DELETE | `/api/tasks/:id` | Remove a task           |

### Example Usage

**Create a task:**

```bash
curl -X POST http://localhost:3000/api/tasks \
  -H "Content-Type: application/json" \
  -d '{"title":"New task","priority":"High"}'
```

## 🗄️ Database Structure

```sql
CREATE TABLE tasks (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    priority ENUM('Low', 'Medium', 'High') NOT NULL,
    isCompleted BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
```

## 🛠️ Technologies Used

* **Backend:** Node.js, Express.js
* **Database:** MySQL
* **Frontend:** Vanilla JavaScript, Bootstrap 5
* **Other tools:** dotenv, cors, mysql2

## 📝 License

MIT
