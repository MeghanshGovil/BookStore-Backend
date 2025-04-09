# BookStore-Backend

A robust RESTful API for managing a bookstore application, built with Node.js, Express, and MongoDB.

## Overview

The BookStore Backend is a comprehensive API that provides all necessary functionality for managing a bookstore inventory system. It includes user authentication, book management, and order processing capabilities.

## Features

- **User Authentication System**
  - Signup, login, and user management
  - JWT-based authentication
  - Role-based access control (Admin/User)

- **Book Management**
  - Create, read, update, and delete books
  - Filter books by various parameters
  - Book details including title, author, price, category

- **Order Processing**
  - Shopping cart functionality
  - Order creation and management
  - Order history tracking

- **MongoDB Integration**
  - Robust data modeling
  - Efficient database operations

## Tech Stack

- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **JWT** - JSON Web Token for authentication
- **Bcrypt** - Password hashing

## 🚀 Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone https://github.com/harshpdsingh/bookstore-api.git
   cd bookstore-api
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure environment variables:**

   Create a `.env` file in the root directory and add the following:
   ```env
   DATABASE_URL="your_postgresql_connection_string"
   JWT_SECRET="your_jwt_secret"
   ```

   Example (for local PostgreSQL):
   ```env
   DATABASE_URL="postgresql://postgres:password@localhost:5432/bookstore"
   ```

4. **Generate Prisma client and run migrations:**
   ```bash
   npx prisma generate
   npx prisma migrate dev --name init
   ```

5. **Start the development server:**
   ```bash
   npm run start:dev
   ```

---

## 📬 API Endpoints & Sample Requests

### 🔐 Auth

#### Signup
`POST /auth/signup`
```json
{
  "email": "user@example.com",
  "password": "securepassword"
}
```

#### Login
`POST /auth/login`
```json
{
  "email": "user@example.com",
  "password": "securepassword"
}
```

✅ Returns JWT token:
```json
{
  "access_token": "your.jwt.token"
}
```

---

### 📘 Books (Protected by JWT)
> Add `Authorization: Bearer <access_token>` header to all book routes.

#### Create Book
`POST /books`
```json
{
  "title": "Atomic Habits",
  "author": "James Clear",
  "category": "Self-help",
  "price": 499,
  "rating": 5,
  "publishedDate": "2021-01-01T00:00:00.000Z"
}
```

#### Get All Books
`GET /books`

Optional filters:
`/books?author=James&category=Self-help&rating=5`

#### Get Single Book
`GET /books/:id`

#### Update Book
`PATCH /books/:id`
```json
{
  "title": "Updated Book Title",
  "price": 599
}
```

#### Delete Book
`DELETE /books/:id`

## Development

To run the server in development mode with hot reloading:

```bash
npm run dev
```

## Testing

```bash
Run tests using PostMan
```

## Error Handling

The API implements robust error handling with appropriate HTTP status codes and informative error messages for different scenarios:

- Authentication errors (401)
- Authorization errors (403)
- Resource not found errors (404)
- Validation errors (400)
- Server errors (500)

## Environment Variables

| Variable | Description |
|----------|-------------|
| MONGO_URI | MongoDB connection string |
| JWT_SECRET | Secret key for JWT |
| PORT | Server port (default: 5000) |
| NODE_ENV | Environment (development/production) |

## Future Enhancements

- Payment gateway integration
- Book ratings and reviews
- Advanced search functionality
- Dockerization for easier deployment

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

If you have any questions or suggestions, please feel free to open an issue!
