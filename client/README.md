# Medi-Link 💊

Medi-Link is a full-stack MERN web application that connects medicine donors, recipients, and pharmacists to reduce medicine wastage. Donors can list their unused medicines, pharmacists verify the donations for safety, and verified medicines become visible to recipients who need them.

> **Don't let your unused medicines expire — donate them and help save a life.**

---

## ✨ Features

- **Role-based accounts** — Register/login as a Donor, Recipient, or Pharmacist
- **JWT authentication** with hashed passwords using bcrypt
- **Donor Dashboard** — Add medicines with name, expiry date, quantity, and photo
- **Pharmacist Dashboard** — Review pending donations and approve or reject them
- **Recipient Dashboard** — Browse pharmacist-verified medicines
- **Image upload** for medicines
- **Toast notifications**
- **Protected role-based navigation**
- **Responsive Tailwind CSS UI**

---

## 🛠️ Tech Stack

### Frontend (`/client`)

- React 19 + Vite
- React Router DOM
- Tailwind CSS
- Axios
- react-hot-toast
- lucide-react (icons)

### Backend (`/server`)

- Node.js
- Express 5
- MongoDB with Mongoose
- JSON Web Tokens (JWT) for authentication
- bcryptjs for password hashing
- Multer for image handling
- CORS
- dotenv

---

## 📁 Project Structure

```text
Medi App/
├── client/                         # React frontend
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   │   └── Navbar.jsx
│   │   ├── context/
│   │   │   └── AuthContext.jsx
│   │   ├── pages/
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── AddMedicine.jsx
│   │   │   ├── DonorDashboard.jsx
│   │   │   ├── RecipientDashboard.jsx
│   │   │   └── PharmacistDashboard.jsx
│   │   ├── App.jsx
│   │   └── main.jsx
│   └── package.json
│
└── server/                         # Express backend
    ├── models/
    │   ├── User.js
    │   └── Medicine.js
    ├── routes/
    │   ├── auth.js
    │   └── medicine.js
    ├── index.js
    └── package.json
```

---

## 🚀 Getting Started

### Prerequisites

Before running the project, make sure you have:

- Node.js v18 or higher
- MongoDB database (local MongoDB or MongoDB Atlas)
- Git
- npm

---

### 1. Clone the Repository

```bash
git clone https://github.com/alishbahbsse4658-alt/Medi-Link-.git
cd Medi-Link-
```

---

### 2. Backend Setup

Open a terminal in the project directory and run:

```bash
cd server
npm install
```

Create a `.env` file inside the `/server` folder:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
```

Replace the placeholder values with your own MongoDB connection string and JWT secret.

Start the backend server:

```bash
npm run dev
```

The API will start on:

```text
http://localhost:5000
```

---

### 3. Frontend Setup

Open a **new terminal** and run:

```bash
cd client
npm install
npm run dev
```

The frontend will start on:

```text
http://localhost:5173
```

Open the URL in your browser to use the application.

---

## 🔌 API Endpoints

### Authentication Routes

**Base URL:** `/api/auth`

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/register` | Register a new user |
| POST | `/login` | Login and receive a JWT token |

---

### Medicine Routes

**Base URL:** `/api/medicine`

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/add` | Add a new medicine donation |
| GET | `/pending` | Get all medicines awaiting verification |
| GET | `/verified` | Get all verified medicines |
| GET | `/my-donations/:donorId` | Get donations by a specific donor |
| PUT | `/:id/verify` | Verify or reject a medicine |

---

## 👥 User Roles

| Role | Capabilities |
|------|--------------|
| **Donor** | Register, add medicines for donation, and view own donations |
| **Pharmacist** | View pending donations and approve or reject them |
| **Recipient** | Browse verified and available medicines |

---

## 🔄 How Medi-Link Works

```text
Donor
  │
  │ Adds unused medicine
  ▼
Pending Donation
  │
  │ Pharmacist reviews
  ▼
┌─────────────────┐
│                 │
▼                 ▼
Verified        Rejected
  │
  │
  ▼
Recipient views
verified medicine
  │
  ▼
Medicine can be requested
```

---

## 🔐 Authentication & Security

Medi-Link uses:

- JWT-based authentication
- Password hashing with bcryptjs
- Role-based access control
- Protected routes
- Environment variables for sensitive information
- CORS configuration
- Input validation

---

## 📷 Medicine Image Upload

Donors can upload an image of the medicine while creating a donation.

The uploaded image can then be reviewed by the pharmacist before the medicine is approved.

---

## 📌 Notes

- Never commit your real `.env` file to GitHub.
- The `.env` file should contain your own MongoDB connection string and JWT secret.
- The `.env` file is already included in `.gitignore`.
- Make sure MongoDB is running or your MongoDB Atlas connection is active before starting the backend.

---

## 🎯 Project Goal

The main goal of Medi-Link is to reduce medicine wastage and make unused medicines available to people who need them through a structured and verified donation process.

The platform provides a simple workflow:

**Donate → Verify → Find → Help**

---

## 📄 License

This project is open for educational and academic use.