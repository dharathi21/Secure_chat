 Secure Chat App with End-to-End Encryption

  This project is a real-time, browser-based chat application that ensures private and secure communication  using  End-to-End Encryption (E2EE). Messages are encrypted on the sender’s device and decrypted only on the recipient’s device. The server simply acts as a relay and cannot read any of the message content.

 Features:
•	RSA Key Pair generation on the client-side
•	 Public key exchange using Flask-SocketIO
•	AES encryption for message confidentiality
•	 Real-time messaging powered by Flask-SocketIO
•	 Server has no access to message contents (true E2EE)
•	 Simple, clean UI built with HTML and JavaScript

 Tech Stack:

      Technology 	                   
 Python 3                              
Flask
Flask-SocketIO
JavaScript
Forge.js
HTML/CSS	Backend logic 

 Folder Structure:
secure-chat-app/
├── app.py
├── requirements.txt
├── templates/
│ ├── home.html
│ └── chat.html
├── static/ # Optional if using CSS/JS files
│ └── style.css
└── README.md

 Getting Started:
 1. Clone the Repository
git clone https://github.com/yourusername/secure-chat-app.git
cd secure-chat-app

3. Run the Flask App
python app.py
Then visit:
🔗 http://127.0.0.1:5000/

How End-to-End Encryption Works:

o	Every user generates their own RSA key pair (public + private).
o	When a user joins a room, their public key is shared with others.
o	For each message:
             An AES symmetric key is generated.
o	The message is encrypted with AES.
o	The AES key is encrypted using the receiver's RSA public key.
o	The server forwards the encrypted AES key and message.
o	The recipient:
                    Uses their private key to decrypt the AES key.
                    Uses that AES key to decrypt the message.

o	 Only the recipient can read the message.
o	 Server cannot decrypt or view any message content.


