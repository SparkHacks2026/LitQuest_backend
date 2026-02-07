Returns the scene JSON stored in MongoDB.

---

Instructions: 
1. git clone https://github.com/LitQuestSparkHacks2026/LitQuest_backend.git
2. Create .env file in the folder that has the server.js file. Put as content:
PORT=5001
MONGO_URI=mongodb+srv://Cluster44801:123@litquestdemo.ny6qfgj.mongodb.net/LitQuestDemo?retryWrites=true&w=majority
3. npm install
4. node server.js

---

## Scene JSON Format

Scenes are stored as **raw JSON documents** in MongoDB.

Each scene should include:
- `scene_id` (string) -- Identifier for the scene
- `title` (string) -- Name of the Scene (Is showcased on front end)
- `location` (string) -- Setting of current scene
- `next_scene_id` (string) -- ID of the next scene
- `content[]` (array) -- Dialogue/Narrative/Action content
- `choices[]` (array) -- Branching options presented to the user

Example scene files used in this project:
- `01-sidewalk-complete.json`
- `03-firehouse-complete.json`
- `04-OldWomanHouse-complete.json`

These JSON files should be **inserted directly into MongoDB** (one document per scene).

The frontend handles:
- dialogue progression
- branching via `next_index`
- difficulty levels (`beginner`, `intermediate`, `advanced`)

The backend does **not** process game logic. It primarily acts as a data provider.


