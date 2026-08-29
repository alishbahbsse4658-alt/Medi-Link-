Medi-Link 💊

Medi-Link is a full-stack MERN web application that connects medicine donors, recipients, and pharmacists to reduce medicine wastage. Donors can list their unused medicines, pharmacists verify the donations for safety, and verified medicines become visible to recipients who need them.

Don't let your unused medicines expire — donate them and help save a life.

✨ Features
Role-based accounts — Register/login as a Donor, Recipient, or Pharmacist
JWT authentication with hashed passwords (bcrypt)
Donor Dashboard — Add medicines (name, expiry date, quantity, photo)
Pharmacist Dashboard — Review pending donations and approve or reject them
Recipient Dashboard — Browse the list of pharmacist-verified medicines
Image upload for medicines
Toast notifications, protected role-based navigation, and a responsive Tailwind UI

🛠️ Tech Stack

Frontend (/client)

React 19 + Vite
React Router DOM
Tailwind CSS
Axios
react-hot-toast
lucide-react (icons)

Backend (/server)

Node.js + Express 5
MongoDB with Mongoose
JSON Web Tokens (JWT) for auth
bcryptjs for password hashing
Multer (image handling)
CORS, dotenv
📁 Project Structure
Medi App/
├── client/                 # React frontend
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
└── server/                 # Express backend
    ├── models/
    │   ├── User.js
    │   └── Medicine.js
    ├── routes/
    │   ├── auth.js
    │   └── medicine.js
    ├── index.js
    └── package.json
🚀 Getting Started
Prerequisites
Node.js (v18 or higher recommended)
A MongoDB database (local or MongoDB Atlas)
1. Clone the repository
bash
git clone https://github.com/alishbahbsse4658-alt/Medi-Link-.git
cd "Medi App"
2. Backend Setup
bash
cd server
npm install

Create a .env file inside /server with the following variables:

env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key

Run the server:

bash
npm run dev

The API will start on http://localhost:5000.

3. Frontend Setup

Open a new terminal:

bash
cd client
npm install
npm run dev

The app will start on http://localhost:5173 (default Vite port).

🔌 API Endpoints
Auth Routes (/api/auth)
Method	Endpoint	Description
POST	/register	Register a new user
POST	/login	Login and receive a JWT
Medicine Routes (/api/medicine)
Method	Endpoint	Description
POST	/add	Add a new medicine donation
GET	/pending	Get all medicines awaiting verification
GET	/verified	Get all verified medicines
GET	/my-donations/:donorId	Get all donations by a specific donor
PUT	/:id/verify	Update a medicine's status (verify/reject)

👥 User Roles
Role	Capabilities
Donor	Register, add medicines for donation, view own donations
Pharmacist	View pending donations, approve or reject them
Recipient	Browse the list of verified, available medicines

📌 Notes
Never commit your real .env file — it's already listed in .gitignore.
The MONGO_URI and JWT_SECRET values above are placeholders; replace them with your own credentials before running the project.

📄 License
This project is open for educational and academic use.