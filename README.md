# Simple Python Multi-User Chat

> A lightweight, terminal-based chat application built with Python's standard library, demonstrating client-server architecture and real-time network programming.

![Python](https://img.shields.io/badge/Python-3.x-blue) ![License](https://img.shields.io/badge/License-MIT-green) ![Modules](https://img.shields.io/badge/Modules-socket%20%7C%20threading-purple)

---

## Features

- **Multi-user support** — Multiple clients can connect to a single server simultaneously.
- **Real-time broadcasting** — Messages sent by one user are instantly received by all others.
- **Nickname system** — Users choose a custom display name when joining the chat.
- **Non-blocking I/O** — Python's `threading` module handles sending and receiving concurrently without blocking.

---

## Technical Stack

| Component   | Details                                      |
|-------------|----------------------------------------------|
| Language    | Python 3.x                                   |
| `socket`    | Low-level TCP network communications         |
| `threading` | Concurrent handling of connections and I/O   |

---

## Project Structure

```
.
├── server.py   # Central hub — manages connections and broadcasts messages
└── client.py   # User-facing interface for sending and receiving messages
```

---

## Setup & Installation

**1. Clone the repository**

```bash
git clone https://github.com/yourusername/python-chat-app.git
cd python-chat-app
```

**2. Verify Python is installed**

```bash
python --version
```

> Requires Python 3.x. No external dependencies needed.

---

## Usage

You'll need multiple terminal windows — one for the server, and one per client.

**Start the server**

Run this first. It begins listening for connections on `127.0.0.1:55555`.

```bash
python server.py
```

**Connect a client**

Open a new terminal for each user and run:

```bash
python client.py
```

You'll be prompted to enter a nickname. Once set, you can start sending messages.

---

## How It Works

### 1. Handshake
When a client connects, the server sends the keyword `NICK`. The client responds with its chosen nickname, which the server stores alongside the connection.

### 2. Threading
- **Server-side:** A new thread is spawned for each connected client to monitor incoming messages.
- **Client-side:** One thread handles incoming messages from the server; the main thread waits for user input.

### 3. Broadcasting
When the server receives a message from a client, it iterates through all active connections and forwards the message to every other user.

---

## License

This project is open-source and available under the [MIT License](LICENSE).
