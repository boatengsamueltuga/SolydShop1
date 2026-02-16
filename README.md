# SolydShop

Full stack ecommerce web app. React frontend + Spring Boot backend with Stripe payments, JWT auth, and an admin dashboard.

Built this as a personal project to learn full stack development with modern tools.

## Tech used

**Frontend:**
- React 19, Vite 7
- Redux Toolkit for state management
- TailwindCSS + Material UI
- Stripe integration for payments
- React Router v7, React Hook Form

**Backend:**
- Spring Boot 3.5 (Java 21)
- PostgreSQL
- Spring Security + JWT (cookie-based auth)
- Cloudinary for image uploads
- Stripe API

## Features

- Browse and search products with filters
- Shopping cart
- Checkout with Stripe payments
- User registration/login with JWT
- Role-based access (User, Seller, Admin)
- Admin dashboard - manage products, categories, orders, sellers
- Seller dashboard
- Address management
- Responsive design

## Getting started

### Prerequisites
- Node.js 20+
- Java 21
- PostgreSQL
- Stripe account (for payment testing)

### Run with Docker (easiest)

```bash
# clone the repo
git clone https://github.com/yourusername/SolydShop3.git
cd SolydShop3

# set your stripe keys
export STRIPE_SECRET_KEY=sk_test_your_key
export VITE_STRIPE_PUBLISHABLE_KEY=pk_test_your_key

# spin it up
docker compose up --build
```

Frontend will be at `http://localhost:3000` and backend at `http://localhost:8080`.

### Run manually

**Backend:**
```bash
cd myecomm-backend
./mvnw spring-boot:run
```
Make sure you have a PostgreSQL database called `ecommerce` running on port 5432.

**Frontend:**
```bash
cd Ecom-Frontend/vite-reactEcomfrontend
npm install
npm run dev
```

### Environment variables

Create a `.env` file in `Ecom-Frontend/vite-reactEcomfrontend/`:
```
VITE_BACK_END_URL=http://localhost:8080
VITE_FRONTEND_URL=http://localhost:3000
VITE_STRIPE_PUBLISHABLE_KEY=pk_test_yourkey
```

## Project structure

```
SolydShop3/
├── Ecom-Frontend/          # React frontend
│   └── vite-reactEcomfrontend/
│       ├── src/
│       │   ├── api/        # Axios config
│       │   ├── components/ # All React components
│       │   ├── store/      # Redux (actions + reducers)
│       │   ├── hooks/      # Custom hooks
│       │   └── utils/
│       ├── Dockerfile
│       └── package.json
├── myecomm-backend/        # Spring Boot backend
│   ├── src/
│   ├── Dockerfile
│   └── pom.xml
├── docker-compose.yml
└── render.yaml             # Render deployment config
```

## Deployment

There's a `render.yaml` for deploying to Render. You'll need to update the placeholder URLs and set your Stripe + Cloudinary keys in the Render dashboard.

## Roles

| Role | Access |
|------|--------|
| User | Browse, cart, checkout, orders |
| Seller | Product management |
| Admin | Everything + user management + analytics |


Actual Link to the Main Application : https://ecommerce-frontend-lq52.onrender.com/
