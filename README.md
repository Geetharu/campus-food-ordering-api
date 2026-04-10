Campus Food Ordering API 🍔

A RESTful backend API built with Node.js, Express, and MongoDB for managing a university campus food ordering system. This project demonstrates relational data modeling, advanced MongoDB aggregation pipelines, and fully paginated CRUD operations.

🚀 Features

Student Management: Register and track university students.
Menu Management: Create and manage canteen menu items with availability status.
Order Processing: Place food orders linking students to multiple menu items with auto-calculated totals.
Advanced Search & Pagination: Search menu items by partial text or category and retrieve paginated order histories.
Data Analytics: Generate complex reports using MongoDB Aggregation (Total student spending, daily order counts, and top-selling items).

🛠️ Technologies Used

Runtime: Node.js
Framework: Express.js
Database: MongoDB
ODM: Mongoose
Environment: dotenv
Middleware: cors, express.json

📦 Installation & Setup

Clone the repository

git clone [https://github.com/Geetharu/campus-food-ordering-api.git](https://github.com/Geetharu/campus-food-ordering-api.git)
cd campus-food-ordering-api

Install dependencies

npm install

Environment Variables
Create a .env file in the root directory and add the following:

PORT=3000
MONGODB_URI=mongodb://localhost:27017/campus_food_api

(Note: Make sure your local MongoDB instance is running, or replace the URI with your MongoDB Atlas connection string).

Start the server

npm start

The API will be available at http://localhost:3000.

📡 API Endpoints

Students

POST /students : Register a new student
GET /students/:id : Get student details by ID

Menu Items

POST /menu-items : Add a new menu item
GET /menu-items : Get all menu items
GET /menu-items/search : Search items (Query params: name, category)

Orders

POST /orders : Place a new order
GET /orders : Get all orders (Query params: page, limit)
GET /orders/:id : Get specific order details
PATCH /orders/:id/status : Update order status (PLACED, PREPARING, DELIVERED, CANCELLED)
DELETE /orders/:id : Delete an order

Analytics (Aggregation)

GET /analytics/total-spent/:studentId : Calculate total money spent by a specific student
GET /analytics/top-menu-items : Get highest selling menu items (Query param: limit)
GET /analytics/daily-orders : Get a count of orders grouped by day
