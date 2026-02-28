# Socket.IO Advanced Chat App

A complete, end-to-end real-time chat application built with **Node.js**, **Express**, and **Socket.IO**. This project is based on the official Socket.IO tutorial but goes all the way to Step 9, implementing advanced production-ready features like database persistence, reliable message delivery, and horizontal scaling.

## ✨ Features

* **Real-Time Bidirectional Communication:** Instant messaging powered by WebSockets via Socket.IO.
* **Connection State Recovery:** Automatically restores missed events and connection state if a user temporarily loses internet access.
* **Server Delivery (Database Persistence):** Integrates **SQLite** to persist all chat messages, ensuring data isn't lost if the server restarts.
* **Client Delivery (Exactly-Once Semantics):** Utilizes `clientOffset` and server acknowledgments to ensure messages are delivered exactly once, preventing duplicate entries even if a client retries sending a message.
* **Horizontal Scaling:** Uses Node.js `cluster` module and `@socket.io/cluster-adapter` to spawn multiple server worker threads across available CPU cores, allowing the app to handle thousands of concurrent clients.

---

## 🚀 Getting Started

### Prerequisites

Make sure you have **Node.js** installed on your machine.

### Installation

1. Clone the repository:
   ```bash
   git clone [https://github.com/OmChauhan9/Socket-chat.git](https://github.com/OmChauhan9/Socket-chat.git)
   cd Socket-chat
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the server:
   ```bash
   npm start
   ```
   > **Note:** Because horizontal scaling is enabled, you will see multiple server processes running on different ports (e.g., 3000, 3001, 3002) depending on your machine's CPU cores.

---

## 💻 Usage

1. Open your browser and navigate to one of the local ports provided in your terminal (e.g., `http://localhost:3000`).
2. Open another tab or a different browser and navigate to a **different** port (e.g., `http://localhost:3001`) to see the cluster adapter sync messages across different server processes.
3. Use the **Disconnect / Connect** button to test the connection state recovery and exactly-once delivery mechanisms.

---

## 🛠️ Tech Stack

* **Backend:** Node.js, Express.js
* **WebSockets:** Socket.IO, `@socket.io/cluster-adapter`
* **Database:** SQLite, `sqlite3`
* **Frontend:** HTML, CSS, Vanilla JavaScript

---

## 👨‍💻 Author

**Om Chauhan**
