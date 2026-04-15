Simple Python Multi-User Chat
A lightweight, terminal-based chat application built using Python's socket and threading libraries. This project demonstrates the fundamentals of Client-Server architecture and network programming.

🚀 Features
Multi-User Support: Multiple clients can connect to a single server simultaneously.

Real-time Broadcasting: Messages sent by one user are instantly received by all other connected users.

Nickname System: Users can choose a custom nickname upon joining the chat.

Concurrency: Uses Python's threading module to handle sending and receiving data at the same time without blocking.

🛠️ Technical Stack
Language: Python 3.x

Modules: * socket: For low-level network communications (TCP).

threading: To handle multiple connections and simultaneous I/O.

📂 Project Structure
Plaintext
.
├── server.py      # The central hub that manages connections and broadcasts messages.
└── client.py      # The user interface for sending and receiving messages.
⚙️ Setup and Installation
Clone the repository (or save the files to a local folder):

Bash
git clone https://github.com/yourusername/python-chat-app.git
cd python-chat-app
Ensure Python is installed:

Bash
python --version
🖥️ Usage
To run the application, you will need to open multiple terminal windows.

1. Start the Server
Run the server script first. It will begin listening for incoming connections on 127.0.0.1:55555.

Bash
python server.py
2. Connect Clients
Open a new terminal window for every user you want to add to the chat and run:

Bash
python client.py
The client will prompt you to enter a nickname.

Once entered, you can start typing messages.

🧠 How It Works
The Handshake: When a client connects, the server sends a specific keyword ('NICK'). The client responds with the chosen nickname, which the server stores in a list.

Threading:

Server-side: A new thread is spawned for every connected client to monitor incoming messages.

Client-side: One thread handles incoming messages from the server, while the main thread waits for user input.

Broadcasting: When the server receives a message from a client, it iterates through its list of active connections and sends that message to everyone.

📝 License
This project is open-source and available under the MIT License.