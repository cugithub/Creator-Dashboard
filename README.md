

A full-stack web application that allows content creators to manage their profile, earn credits, and engage with a personalized feed aggregated from social platforms like Reddit and Twitter.

## ✨ Features

### User Features
- **Authentication:** Register/Login with JWT.
- **Credit System:** Earn points for:
  - Daily login
  - Completing profile
  - Interacting with feed
- **Feed Aggregator:**
  - Fetches content from Reddit and Twitter.
  - Users can save, share, or report content.
- **Dashboard:**
  - View credit stats and saved posts.
  - Recent user activity tracking.

### Admin Features
- Role-based access control (Admin/User).
- Admin dashboard to view and update user credit balances.
- View overall user engagement and feed reports.

---

## 🛠 Tech Stack

| Layer     | Tech                      |
|-----------|---------------------------|
| Frontend  | React.js, Tailwind CSS    |
| Backend   | Node.js, Express.js       |
| Database  | MongoDB Atlas             |
| Auth      | JWT                       |
| Deployment| Google Cloud Run / Firebase Hosting |

---

## 🚀 Getting Started Locally

### Prerequisites
- Node.js (v16+)
- MongoDB Atlas account
- Twitter API key
- Git

### 1. Clone the Repo
```bash
git clone https://github.com/your-username/creator-feed-app.git
cd creator-feed-app

2. Backend Setup
bash
Copy
Edit
cd server
npm install
Create a .env file:

env
Copy
Edit
PORT=5000
MONGO_URI=mongodb+srv://<your-mongo-uri>
JWT_SECRET=your_jwt_secret
TWITTER_BEARER_TOKEN=your_twitter_bearer_token
Start the server:

bash
Copy
Edit
npm start
3. Frontend Setup
bash
Copy
Edit
cd ../client
npm install
npm start
The frontend runs at http://localhost:3000 and backend at http://localhost:5000.

🌐 Deployment
Backend: Google Cloud Run
Create a Dockerfile in the server/ folder:

dockerfile
Copy
Edit
FROM node:18
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm", "start"]
Deploy via Google Cloud CLI:

bash
Copy
Edit
gcloud run deploy creator-backend \
  --source . \
  --region us-central1 \
  --set-env-vars MONGO_URI=...,JWT_SECRET=...,TWITTER_BEARER_TOKEN=... \
  --allow-unauthenticated
Frontend: Firebase Hosting
Inside client/, install Firebase CLI and initialize:

bash
Copy
Edit
npm install -g firebase-tools
firebase login
firebase init hosting
Build and deploy:

bash
Copy
Edit
npm run build
firebase deploy
🧪 Testing
Unit tests and API tests can be added using Jest and Supertest for backend.

For the frontend, use React Testing Library.

