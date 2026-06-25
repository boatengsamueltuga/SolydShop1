# SolydShop

A full-stack e-commerce web application built with React and Spring Boot, featuring Stripe payments, JWT authentication, and role-based dashboards for users, sellers, and admins.

**Live Demo:** [https://ecommerce-frontend-lq52.onrender.com](https://ecommerce-frontend-lq52.onrender.com)
> The app is hosted on Render's free tier — initial load and backend responses may take up to 30 seconds to spin up.

---

## Tech Stack

**Frontend**
- React 19, Vite 7
- Redux Toolkit
- Tailwind CSS + Material UI
- React Router v7, React Hook Form
- Stripe.js

**Backend**
- Spring Boot 3.5 (Java 21)
- PostgreSQL
- Spring Security + JWT (cookie-based)
- Cloudinary (image uploads)
- Stripe API

---

## Features

- Product browsing and search with filters
- Shopping cart and Stripe-powered checkout
- User registration and login with JWT authentication
- Role-based access control (User, Seller, Admin)
- Admin dashboard — manage products, categories, orders, and users
- Seller dashboard — manage listings
- Address management
- Responsive design

---

## Getting Started

### Prerequisites

- Node.js 20+
- Java 21
- PostgreSQL
- Stripe account (for payment testing)

### Run with Docker (Recommended)

```bash
git clone https://github.com/boatengsamueltuga/SolydShop1.git
cd SolydShop1

# Set your Stripe keys
export STRIPE_SECRET_KEY=sk_test_your_key
export VITE_STRIPE_PUBLISHABLE_KEY=pk_test_your_key

docker compose up --build
```

- Frontend: [http://localhost:3000](http://localhost:3000)
- Backend: [http://localhost:8080](http://localhost:8080)

### Run Manually

**Backend**

Ensure a PostgreSQL database named `ecommerce` is running on port 5432, then:

```bash
cd myecomm-backend
./mvnw spring-boot:run
```

**Frontend**

```bash
cd Ecom-Frontend/vite-reactEcomfrontend
npm install
npm run dev
```

### Environment Variables

Create a `.env` file in `Ecom-Frontend/vite-reactEcomfrontend/`:

```env
VITE_BACK_END_URL=http://localhost:8080
VITE_FRONTEND_URL=http://localhost:3000
VITE_STRIPE_PUBLISHABLE_KEY=pk_test_yourkey
```

---

## Project Structure

```
SolydShop1/
├── Ecom-Frontend/
│   └── vite-reactEcomfrontend/
│       ├── src/
│       │   ├── api/            # Axios configuration
│       │   ├── components/     # React components
│       │   ├── store/          # Redux actions and reducers
│       │   ├── hooks/          # Custom hooks
│       │   └── utils/
│       ├── Dockerfile
│       └── package.json
├── myecomm-backend/
│   ├── src/
│   ├── Dockerfile
│   └── pom.xml
├── docker-compose.yml
└── render.yaml                 # Render deployment config
```

---

## Role Permissions

| Role   | Access                                          |
|--------|-------------------------------------------------|
| User   | Browse products, cart, checkout, order history  |
| Seller | Product and listing management                  |
| Admin  | Full access including user management           |

---

## Deployment

A `render.yaml` file is included for deploying to [Render](https://render.com). Set the following environment variables in the Render dashboard before deploying:

- `STRIPE_SECRET_KEY`
- `CLOUDINARY_URL`
- `DB_HOST`, `DB_PORT`, `DB_NAME`, `DB_USERNAME`, `DB_PASSWORD`
- `JWT_SECRET`
- `FRONTEND_URL`
