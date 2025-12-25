## GenZFashion Backend

A robust backend API for an e-commerce fashion platform built with Node.js, Express, and MongoDB. This backend supports modern e-commerce features including user authentication, product management, shopping cart, payment processing, and administrative controls.

## 📋 Table of Contents

## Features

## Tech Stack

## Project Structure

## Installation

## Environment Variables

## API Endpoints

## Models

## Authentication

## Payment Integration

## Image Upload

## Running the Project

## Scripts

## Dependencies

## ✨ Features

## User Features

## User registration and authentication with JWT

## Guest and registered user shopping carts

## Profile management

## Order history tracking

## Newsletter subscription

## Product Features

Product catalog with filtering (category, size, color, gender, price)

## Product search functionality

## Best seller and new arrivals sections

## Similar product recommendations

## Product reviews and ratings

## Shopping Features

## Persistent cart for logged-in users

## Guest cart that merges on login

## Multiple product variations (size, color)

## Real-time stock management

## Payment & Checkout

## Stripe payment integration

## Secure checkout process

## Order confirmation

## Payment status tracking

## Admin Features

Full CRUD operations for products, users, and orders

## Order status management

## User role management (admin/customer)

## Product inventory management

## 🛠 Tech Stack

## Backend:

## Node.js

## Express.js

## MongoDB with Mongoose

## Authentication:

## JSON Web Tokens (JWT)

## bcryptjs for password hashing

## Payment Processing:

## Stripe API

## File Upload:

## Cloudinary

## Multer for file handling

## Streamifier for memory storage

## Security:

## CORS protection

## Environment variables

## Input validation

## Development Tools:

## Nodemon for development

## Dotenv for environment configuration

## 📁 Project Structure

## backend/

## ├── models/

## │ ├── User.js

## │ ├── Product.js

## │ ├── Cart.js

## │ ├── Order.js

## │ ├── Checkout.js

## │ └── Subscriber.js

## ├── routes/

## │ ├── adminOrders.js

## │ ├── adminProducts.js

## │ ├── adminUsers.js

## │ ├── cart.js

## │ ├── checkout.js

## │ ├── orders.js

## │ ├── products.js

## │ ├── subscribe.js

## │ ├── upload.js

## │ └── users.js

## ├── middleware/

## │ └── authMiddleware.js

## ├── server.js

## ├── package.json

## └── .env.example

## 🚀 Installation

## Clone the repository

## git clone <repository-url>

## cd backened

## Install dependencies

## npm install

## Set up environment variables

## cp .env.example .env

Edit .env with your configuration values.

## Start the development server

## npm run dev

## 🔧 Environment Variables

## Create a .env file in the root directory:

## env

## PORT=5000

## MONGODB_URI=your_mongodb_connection_string

## JWT_SECRET=your_jwt_secret_key

## STRIPE_SECRET_KEY=your_stripe_secret_key

## CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name

## CLOUDINARY_API_KEY=your_cloudinary_api_key

## CLOUDINARY_API_SECRET=your_cloudinary_api_secret

CLIENT_URL=[http://localhost:3000](http://localhost:3000)

## 📚 API Endpoints

## Authentication

## POST /api/users/register - Register new user

## POST /api/users/login - User login

GET /api/users/profile - Get user profile (protected)

## Products

## GET /api/products - Get all products with filters

## GET /api/products/:id - Get single product

GET /api/products/best-seller - Get best seller product

## GET /api/products/new-arrivals - Get new arrivals

GET /api/products/similar/:id - Get similar products

## Cart

## POST /api/cart - Add item to cart

## PUT /api/cart - Update cart item quantity

## DELETE /api/cart - Remove item from cart

## GET /api/cart - Get cart

POST /api/cart/merge - Merge guest cart with user cart (protected)

## Checkout & Orders

POST /api/checkout/create-stripe-session - Create Stripe session (protected)

PUT /api/checkout/:id/pay - Update payment status (protected)

POST /api/checkout/:id/finalize - Finalize checkout (protected)

GET /api/orders/my-orders - Get user orders (protected)

GET /api/orders/:id - Get order details (protected)

Admin Endpoints (All protected with admin middleware)

## Products

GET /api/admin/products - Get all products (admin)

## POST /api/admin/products - Create product (admin)

PUT /api/admin/products/:id - Update product (admin)

DELETE /api/admin/products/:id - Delete product (admin)

## Users

## GET /api/admin/users - Get all users (admin)

## POST /api/admin/users - Create user (admin)

## PUT /api/admin/users/:id - Update user (admin)

## DELETE /api/admin/users/:id - Delete user (admin)

## Orders

## GET /api/admin/orders - Get all orders (admin)

PUT /api/admin/orders/:id - Update order status (admin)

DELETE /api/admin/orders/:id - Delete order (admin)

## Other

POST /api/subscribe/subscribe - Newsletter subscription

## POST /api/upload - Image upload (protected)

## 🗄️ Models

## User Model

## name, email, password, role (admin/customer)

## Timestamps and password hashing middleware

## Product Model

name, description, price, discountPrice, countInStock

## category, brand, sizes[], colors[], collections[]

## material, gender, images[], tags[]

## isFeatured, isPublished, rating, numReviews

## dimensions, weight, sku

## Cart Model

## Supports both guest and authenticated users

## products[] with size, color, and quantity

## totalPrice calculated automatically

## User reference for authenticated users

## Order Model

## orderItems[] from checkout

## shippingAddress, paymentMethod, totalPrice

## Payment status and timestamps

## Delivery tracking

## Checkout Model

## Temporary storage for checkout process

## Payment status tracking

## Integration with Stripe

## Subscriber Model

## Simple email subscription list

## 🔐 Authentication

## The API uses JWT-based authentication:

## Registration/Login: Returns JWT token

## Protected Routes: Use protect middleware

Admin Routes: Use both protect and admin middleware

Token Expiry: 40 hours for login, 365 days for registration

## Middleware

protect: Verifies JWT and attaches user to request

## admin: Checks if user has admin role

## 💳 Payment Integration

## Stripe Integration

Create Session: POST /api/checkout/create-stripe-session

Payment Confirmation: Stripe webhook or manual confirmation

Order Creation: Converts checkout to final order after payment

## Payment Flow

## User initiates checkout from cart

## Stripe session created with checkout items

## User completes payment on Stripe

## Payment status updated in system

## Checkout finalized and order created

## User cart cleared

## 📸 Image Upload

## Cloudinary Integration

## Uploads via POST /api/upload

## Supports single image upload

## Returns secure URL for storage in product

## Uses memory storage with Multer

## Features

## File validation

## Stream-based upload to Cloudinary

## Secure URL generation

## Error handling for failed uploads

## 🚦 Running the Project

## Development

## npm run dev

Starts server with Nodemon for auto-restart on changes.

## Production

## npm start

Starts server in production mode.

## Database Seeding

## npm run seed

Runs seeder script to populate database with initial data.

## 📜 Scripts

## npm start - Start production server

npm run dev - Start development server with Nodemon

## npm run seed - Run database seeder

## 📦 Dependencies

## Production

## express: Web framework

## mongoose: MongoDB ODM

## jsonwebtoken: Authentication

## bcryptjs: Password hashing

## stripe: Payment processing

## cloudinary: Image hosting

## multer: File upload handling

## cors: Cross-origin resource sharing

## dotenv: Environment configuration

## Development

## nodemon: Development server with auto-restart

## 🎯 Key Features in Detail

## Advanced Product Filtering

Multiple filter combinations (category, size, color, gender, price range)

## Material and brand filtering

## Search by product name or description

## Sorting by price (asc/desc) and popularity

## Cart Management

## Guest Users: Temporary cart with guest ID

Registered Users: Persistent cart linked to account

Cart Merging: Automatic merging of guest cart on login

Real-time Updates: Quantity updates and price recalculation

## Admin Dashboard

## User Management: CRUD operations for users

Product Management: Full product lifecycle management

## Order Management: View, update, and delete orders

## Analytics: Order tracking and status management

## Security Features

## JWT-based authentication

## Password hashing with bcrypt

## Protected admin routes

## Input validation

## Secure payment processing

## 🔄 Workflow Example

## User Registration/Login

## POST /api/users/register

## POST /api/users/login

## Browse Products

GET /api/products?category=shirts&size=M&color=blue

## Add to Cart

## POST /api/cart

## {

## "productId": "123",

## "quantity": 2,

## "size": "M",

## "color": "blue",

## "userId": "user_123"

## }

## Checkout

## POST /api/checkout/create-stripe-session

## View Orders

## GET /api/orders/my-orders

## 🤝 Contributing

## Fork the repository

## Create a feature branch

## Commit your changes

## Push to the branch

## Open a pull request

## 📄 License

## ISC License

## 👥 Support

For support, please contact the development team or create an issue in the repository.

Note: Ensure all environment variables are properly configured before deployment. The Stripe and Cloudinary integrations require active accounts and proper API keys.
