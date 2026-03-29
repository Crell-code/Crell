# 🎮 Python Quiz Generator (Kahoot-Style)

A **FREE**, open-source, multiplayer quiz generator built with Python and Flask. Host live quizzes and let multiple players compete in real-time!

## Features ✨

✅ **Free & Open Source** - No subscriptions, no paywalls  
✅ **Real-time Multiplayer** - Multiple players join and answer simultaneously  
✅ **Live Scoring** - Points awarded based on correct answers and speed  
✅ **Beautiful UI** - Modern, responsive design  
✅ **Question Ordering** - Players must answer questions in order (Kahoot-style)  
✅ **Leaderboard** - Live scores and final rankings  
✅ **Easy Setup** - Works locally or deploy to cloud

## How It Works

1. **Host** creates a quiz session and gets a unique session code
2. **Players** join using the session code and their name
3. **Questions** appear one at a time
4. **Players** select answers and get instant feedback
5. **Scoring** is automatic - correct answers + speed = points
6. **Leaderboard** updates in real-time
7. **Results** shown at the end with rankings

## Installation

### 1. Clone the Repository
```bash
git clone https://github.com/Crell-code/Crell.git
cd Crell
```

### 2. Install Python (if not already installed)
Download from [python.org](https://www.python.org/downloads/)

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Application
```bash
python main.py
```

The app will start at `http://localhost:5000`

## Usage

### Starting a Quiz

1. Go to `http://localhost:5000`
2. Click **Host** on any quiz
3. Share the **Session Code** with players
4. Click **START QUIZ** when ready
5. Click **Next Question →** after players answer

### Joining a Quiz

1. Go to `http://localhost:5000`
2. Click **Join** on any quiz
3. Enter the **Session Code** (from the host)
4. Enter your name
5. Answer questions as they appear
6. Watch your score climb the leaderboard!

## Quiz Format

Each quiz contains multiple choice questions with 4 options.

```json
{
  "title": "Science Quiz",
  "description": "Test your science knowledge",
  "questions": [
    {
      "id": 1,
      "question": "What is the capital of France?",
      "options": ["London", "Berlin", "Paris", "Madrid"],
      "correct": 2
    }
  ]
}
```

## Scoring System

- **Correct Answer**: `1000 - (time_in_ms / 100)` points
- **Wrong Answer**: 0 points
- **Faster answers** = more points!

## Creating Custom Quizzes

Edit `main.py` and add quizzes to the `SAMPLE_QUIZZES` dictionary:

```python
'my_quiz': {
    'title': 'My Custom Quiz',
    'description': 'A quiz about anything',
    'questions': [
        {
            'id': 1,
            'question': 'Your question?',
            'options': ['Option 1', 'Option 2', 'Option 3', 'Option 4'],
            'correct': 1  # Index of correct answer (0-3)
        }
    ]
}
```

## Deployment

### Free Hosting Options

#### Heroku (Easiest)
```bash
# 1. Create Heroku account
# 2. Install Heroku CLI
# 3. Create Procfile with content: web: python main.py
# 4. Deploy:
heroku create your-app-name
git push heroku main
```

#### Replit
1. Upload repo to Replit
2. Click Run - it deploys automatically!
3. Share the link with your players

#### PythonAnywhere
1. Create account at pythonanywhere.com
2. Upload files
3. Configure app settings
4. Get public URL

## Architecture

```
quiz-generator/
├── main.py              # Flask app with SocketIO
├── requirements.txt     # Python dependencies
├── README.md           # This file
└── templates/
    ├── index.html      # Home page
    ├── host.html       # Host dashboard
    └── player.html     # Player interface
```

## Technologies Used

- **Backend**: Python, Flask, Flask-SocketIO
- **Frontend**: HTML, CSS, JavaScript
- **Real-time**: WebSockets (Socket.IO)
- **Hosting**: Flask development server (or any Python WSGI server)

## Contributing

Found a bug? Have an idea? Fork and create a pull request!

## License

MIT License - Feel free to use and modify!

## Questions?

- Check issues on GitHub
- Create a new issue with your question
- Contact the maintainers

---

**Made with ❤️ by Crell-code**

Have fun hosting quizzes! 🎉