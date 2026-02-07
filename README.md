# SparkHacks 2026 Backend

Simple Express + MongoDB backend for LitQuest.

This server only does one thing:
**return a story scene from MongoDB by `scene_id`.**

---

## How to run

1. Install dependencies
npm install


2. Create a `.env` file
PORT=5000
MONGO_URI=mongodb+srv://<user>:<password>@<cluster>.mongodb.net/LitQuestDemo


3. Start the server
node server.js


You should see:
Backend Live on Port 5001


---

## API

Get a scene:
GET /api/scenes/:id


Example:
http://localhost:5000/api/scenes/01-sidewalk-complete


Returns the scene JSON stored in MongoDB.
- No validation
- No game logic
- Frontend controls all branching using `next_index`

Built for fast iteration at SparkHacks 2026.
