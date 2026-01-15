Google Docs Clone (Real-Time Collaborative Editor)
A full-stack, real-time collaborative text editor inspired by Google Docs. This application allows multiple users to edit the same document simultaneously, seeing each other's changes in real-time, and automatically persists all data to a database.
🚀 Features
Real-Time Collaboration: Multiple users can edit the same document at once using WebSockets.
Persistent Storage: Documents are saved to MongoDB, allowing you to refresh the page or return later without losing progress.
Auto-Syncing: Changes are synced instantly across different browser instances.
Unique Document IDs: Automatic redirection to a unique URL for every new document session.
Rich Text Editing: Full formatting support including Bold, Italics, Lists, and more, powered by the Quill.js editor.
Delta-based Syncing: Uses Quill's "Delta" format to handle concurrent edits efficiently without overwriting other users' work.
🛠️ Tech Stack
Frontend:
React - UI Framework
Quill.js - Rich Text Editor engine
Socket.io-client - Real-time communication
React Router - Client-side routing and dynamic IDs
Backend:
Node.js & Express - Server environment
Socket.io - WebSocket server for bi-directional communication
MongoDB - Database for storing document deltas
Mongoose - MongoDB object modeling
📋 Prerequisites
Before running this project, ensure you have the following installed:
Node.js (v14 or higher)
MongoDB (Local instance or Atlas URI)
🔧 Installation & Setup
Clone the repository:
bash
git clone github.com
cd google-docs-clone
Use code with caution.

Setup the Server:
bash
cd server
npm install

# Create a .env file and add your MONGODB_URI

npm run devStart
Use code with caution.

Setup the Client:
bash
cd client
npm install
npm start
Use code with caution.

💡 How it Works
The Editor (Quill)
The application uses Quill.js because of its "Delta" system. Instead of saving the entire HTML of the document every time a key is pressed, it saves specific operations (e.g., "Insert 'A' at index 5"). This prevents users from overwriting each other's work during simultaneous editing.
Real-Time Communication (Socket.io)
When a user types, a "delta" is emitted via WebSockets to the server. The server then broadcasts that specific change to all other users in that specific "room" (Document ID).
Data Persistence
The server listens for changes and periodically saves the current state of the document to MongoDB. When a user loads a specific URL (e.g., /documents/uuid-string), the server fetches the saved data and populates the editor.
