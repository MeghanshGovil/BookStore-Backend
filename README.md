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

## API Endpoints

### Authentication
- `POST /api/users/register` - Register a new user
- `POST /api/users/login` - Login a user
- `GET /api/users/profile` - Get user profile

### Books
- `GET /api/books` - Get all books
- `GET /api/books/:id` - Get specific book
- `POST /api/books` - Add new book (Admin only)
- `PUT /api/books/:id` - Update book (Admin only)
- `DELETE /api/books/:id` - Delete book (Admin only)

### Orders
- `POST /api/orders` - Create a new order
- `GET /api/orders` - Get all orders (Admin only)
- `GET /api/orders/myorders` - Get user's orders
- `GET /api/orders/:id` - Get specific order
- `PUT /api/orders/:id` - Update order status (Admin only)

## Installation

```bash
# Clone the repository
git clone https://github.com/MeghanshGovil/BookStore-Backend.git

# Navigate to project directory
cd BookStore-Backend

# Install dependencies
npm install

# Create .env file with the following variables
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
PORT=5000

# Run the server
npm start
```

## Project Structure

```
BookStore-Backend/
├── config/             # Configuration files
├── controllers/        # Request handlers
├── middleware/         # Custom middleware functions
├── models/             # Mongoose models
├── routes/             # API routes
├── utils/              # Utility functions
├── app.js              # Express app configuration
├── server.js           # Server entry point
└── package.json        # Project dependencies
```

## Development

To run the server in development mode with hot reloading:

```bash
npm run dev
```

## Testing

```bash
# Run tests
npm test
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
- Performance optimization
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
