# ShopNest – MERN E-Commerce Website

ShopNest is a full-stack e-commerce application built with the MERN stack. It includes a product storefront, shopping cart, user authentication, checkout and order management, plus an admin dashboard for managing products, users, and orders.

## Features

- Browse the store and view product details
- Shopping cart and checkout flow
- User registration, login, and profile
- Order history and order success page
- Admin dashboard
- Admin product creation, editing, and management
- Admin order and user management
- Product image uploads through Cloudinary
- Razorpay payment integration
- Email support through Nodemailer
- Product, order, authentication, payment, and analytics API routes

## Tech Stack

**Frontend**
- React
- React Router
- Redux Toolkit
- React Context API
- CSS

**Backend**
- Node.js
- Express
- MongoDB and Mongoose
- JWT authentication
- bcryptjs
- Cloudinary
- Razorpay
- Nodemailer

## Project Structure

```text
ShopNest/
├── backend/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── utils/
│   ├── .env.example
│   ├── seed.js
│   └── server.js
├── frontend/
│   ├── public/
│   └── src/
├── ShopNest_Postman_Collection.json
└── README.md
```

## Prerequisites

Install the following before running the project:

- [Node.js](https://nodejs.org/) (includes npm)
- [MongoDB](https://www.mongodb.com/) local installation or a MongoDB Atlas database
- Git

Cloudinary, Razorpay, and Gmail credentials are only needed for the related image-upload, payment, and email features.

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/banti8974/Shopnest_Ecommerse_Website.git
cd Shopnest_Ecommerse_Website
```

### 2. Configure the backend

```bash
cd backend
npm install
```

Create a `.env` file inside the `backend/` directory. You can copy `.env.example` and replace the placeholder values:

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/shopnest
JWT_SECRET=replace_with_a_long_random_secret

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_key_secret

GMAIL_USER=your_email@gmail.com
GMAIL_PASS=your_email_app_password

FRONTEND_URL=http://localhost:3000
NODE_ENV=development
```

Make sure MongoDB is running, or set `MONGO_URI` to your MongoDB Atlas connection string. Use valid credentials for any third-party services you intend to use. Never commit your real `.env` file or secrets to GitHub.

Start the backend:

```bash
npm run dev
```

The API runs at `http://localhost:5000` by default.

### 3. Configure the frontend

Open a second terminal from the project root:

```bash
cd frontend
npm install
npm start
```

The React development server normally opens at `http://localhost:3000`. The frontend is configured to proxy API requests to `http://localhost:5000`.

## Seed Sample Data (Optional)

The backend includes a seed script that creates an admin user and sample products.

**Warning:** The seed script deletes existing users and products before inserting the sample data. Only run it against a development database where data loss is acceptable.

From the `backend/` directory, with your `.env` configured:

```bash
npm run seed
```

Seeded admin credentials:

- **Email:** `admin@shopnest.com`
- **Password:** `password123`

Change or remove these credentials before using the application outside local development.

## API Routes

The backend mounts these route groups:

| Route | Purpose |
|---|---|
| `/api/auth` | User authentication and account-related actions |
| `/api/products` | Product operations |
| `/api/orders` | Order operations |
| `/api/payment` | Payment operations |
| `/api/analytics` | Analytics operations |

For request examples, import `ShopNest_Postman_Collection.json` into [Postman](https://www.postman.com/).

## Production Build

Build the frontend from its directory:

```bash
cd frontend
npm run build
```

For production hosting, configure the backend environment variables, MongoDB connection, and frontend build output. When `NODE_ENV=production`, the backend is configured to serve the build from `frontend/build`. Deploy according to your hosting provider's setup and ensure all required environment variables are configured.

## Environment Variables

| Variable | Description |
|---|---|
| `PORT` | Backend port (defaults to `5000`) |
| `MONGO_URI` | MongoDB connection string |
| `JWT_SECRET` | Secret used to sign JWTs |
| `CLOUDINARY_CLOUD_NAME` | Cloudinary account name |
| `CLOUDINARY_API_KEY` | Cloudinary API key |
| `CLOUDINARY_API_SECRET` | Cloudinary API secret |
| `RAZORPAY_KEY_ID` | Razorpay key ID |
| `RAZORPAY_KEY_SECRET` | Razorpay key secret |
| `GMAIL_USER` | Email account used by Nodemailer |
| `GMAIL_PASS` | Email app password or configured SMTP credential |
| `FRONTEND_URL` | Frontend origin allowed by the backend CORS configuration |
| `NODE_ENV` | Runtime environment, e.g. `development` or `production` |

## Contributing

1. Fork the repository.
2. Create a branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push the branch: `git push origin feature/your-feature`
5. Open a pull request.

## License

No license is specified in this repository yet. Add a `LICENSE` file if you want to publish the project under a particular open-source license.
