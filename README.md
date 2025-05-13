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

# Run with custom project name
docker-compose -p visitor-counter up --build

Visit 👉 http://localhost:9000


⚙️ Configuration

FLASK_APP=app.py
FLASK_ENV=development
REDIS_HOST=redis
REDIS_PORT=6379


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


