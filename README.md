📊 DolfinED Visitor Counter

A simple Flask + Redis web app that tracks and displays page visit counts along with the visitor's country and flag, using
geolocation. Built with Docker and Docker Compose.

🚀 Features

🔢 Counts visits in real time using Redis
🌍 Detects visitor country via IP (with flag emoji 🇺🇸)
📜 Displays the 50 most recent visits (timestamp + country)
🔁 One-click reset button
🐳 Dockerized with Redis persistence

🧱 Project Structure

visitor-counter/
│
├── app.py                  # Flask application
├── Dockerfile              # Docker build for Flask
├── docker-compose.yml      # Orchestration: Flask + Redis + volumes
├── requirements.txt        # Flask, Redis, Requests
├── .env                    # Environment config for Flask & Redis
│
├── templates/
│   └── index.html          # Jinja2 template (HTML + CSS)
│
└── README.md               # This file

🛠️ Getting Started
✅ Prerequisites

Docker & Docker Compose installed


📦 Build and Run

To download (clone) this to your Docker host
git clone https://github.com/your-username/visitor-counter.git

cd visitor-counter
docker-compose -p visitor-counter up --build
# This will run it with a custom project name "visitor-counter"

# to test
Visit 👉 http://localhost:9000


⚙️ Configuration
You will need to create a .env file in the visitor-counter directory after cloning this repository to your docker host. If the .env file is not created, the application will break and will not function properly.

An example .env file that is required for this app can be found below

FLASK_APP=app.py          # Informs Flask which file contains the app - in this case app.py. When you run "flask run", it looks for this variable to start the app
FLASK_ENV=development     # Enables auto-reload (needed for cirtical code changes), it shows details error messages with stack traces. Use it for development, not for production.
REDIS_HOST=redis          # Informs Flask app where to find the Redis Host with the name redis. If Redis was external, this can be a localhost or an IP address. Docker resolves the name redis to IP
REDIS_PORT=6379           # Specifies the port that Redis is listening on


🔄 Reset Counter

Click the green Reset Counter button on the home page to:
Reset the visitor count to zero
Clear the recent visitors log

💾 Redis Data Persistence

All Redis data (visitor counts, logs) are stored in a named Docker volume:
volumes:
  redis-data:

This ensures your data survives container restarts.

📦 Dependencies

(requirements.txt)

Flask
redis
requests


📜 License

MIT License – do what you want, attribution appreciated!
Made with ❤️ by DolfinED Academy (www.dolfined.com)


