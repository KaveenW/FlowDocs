# Google Docs Clone

A full-stack, real-time collaborative text editor inspired by Google Docs. This application allows multiple users to edit the same document simultaneously and persists all data to a database.

## 🚀 Features

* **Real-Time Collaboration:** Edit documents with others at the same time using WebSockets.
* **Persistent Storage:** Documents are saved to MongoDB so you never lose your work.
* **Rich Text Editing:** Full formatting (Bold, Italics, etc.) powered by Quill.js.
* **Auto-Sync:** Changes sync instantly across all open browser windows.

## 🛠️ Tech Stack

**Frontend:**
* React
* Quill.js
* Socket.io-client
* React Router

**Backend:**
* Node.js & Express
* Socket.io
* MongoDB & Mongoose

## 📋 Prerequisites

* Node.js (v14 or higher)
* MongoDB (Local or Atlas)

## 🔧 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone <your-repository-link>
   cd google-docs-clone

2. **Setup the Server:**
   ```bash
   cd server
   npm install
   npm run devStart

3. **Setup the Server:**
   ```bash
   cd client
   npm install
   npm start
