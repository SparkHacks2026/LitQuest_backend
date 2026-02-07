SparkHacks 2026 – Backend

LitQuest Scene API

This is a minimal Express + MongoDB backend used to serve interactive story scenes for the LitQuest project at SparkHacks 2026.

The backend exposes one endpoint that allows the frontend to fetch a story scene by its scene_id.

🚀 Features

Express server

MongoDB Atlas connection (via Mongoose)

CORS enabled for frontend access

No authentication

No complex schemas

Fetch scenes by ID

📦 Tech Stack

Node.js

Express

MongoDB Atlas

Mongoose

dotenv

cors

📁 Project Structure
backend/
├── server.js
├── .env
├── package.json
└── README.md

🔧 Setup Instructions
1. Install dependencies
npm install

2. Create a .env file

Create a .env file in the root of the backend directory:

PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/LitQuestDemo?retryWrites=true&w=majority


Make sure your MongoDB Atlas IP whitelist allows connections from your machine.

3. Start the server
node server.js


You should see:

Backend Live on Port 5000

🌐 API Usage
Get a scene by ID
GET /api/scenes/:id

Example:
GET http://localhost:5000/api/scenes/01-sidewalk-complete

Response:

Returns the full scene document stored in MongoDB:

{
  "scene_id": "01-sidewalk-complete",
  "title": "Meeting Clarisse McClellan",
  "content": [ ... ],
  "choices": [ ... ]
}

🧠 Scene Format

Scenes are stored in MongoDB with a scene_id

Content is an ordered array of narrative, dialogue, actions, and choice points

Branching is handled using next_index (frontend-controlled)

This backend does not process game logic — it simply serves data.

🏁 Hackathon Philosophy

This backend is intentionally minimal:

No validation

No game rules

No branching logic on the server

Frontend controls flow using scene data

Perfect for rapid iteration during a hackathon.

🛠 Troubleshooting

Server runs but frontend can’t fetch data

Check MongoDB IP whitelist

Verify scene_id exists in the database

Confirm .env values are loaded correctly
