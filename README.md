
# Journal Application

This project is a local journaling application built with Django, Electron.js, and Elasticsearch.

## Features
- **Local Storage**: Journal entries are stored locally with encryption.
- **Advanced Search**: Elasticsearch integration for full-text search and autocomplete.
- **Frontend**: Desktop application experience built with Electron.js.
- **Dockerized Environment**: Backend and frontend are containerized for easy setup and scaling.

## Project Structure
```
project_root/
├── backend/
│   ├── manage.py                # Django entry point
│   ├── settings.py              # Project settings
│   ├── urls.py                  # URL configuration
│   ├── wsgi.py                  # WSGI configuration for production
│   ├── journal/                 # Django app for journal functionality
│       ├── models.py            # Data models for journal entries
│       ├── views.py             # API views for CRUD and search
│       ├── serializers.py       # DRF serializers for journal data
│       ├── elasticsearch.py     # Elasticsearch integration and helper methods
│       ├── tests.py             # Unit tests for backend functionality
├── frontend/
│   ├── index.html               # Main HTML for the Electron app
│   ├── renderer.js              # JavaScript for frontend functionality
│   ├── package.json             # Frontend dependencies and scripts
├── dockerfile/
│   ├── Dockerfile.backend       # Docker configuration for Django backend
│   ├── Dockerfile.frontend      # Docker configuration for Electron frontend
├── docker-compose.yml           # Docker Compose configuration for multi-service setup
└── README.md                    # Project documentation
```

## Getting Started

### Prerequisites
- Python 3.9+
- Node.js
- Docker

### Local Setup

#### 1. Clone the Repository
```bash
git clone <repository_url>
cd journal_project
```

#### 2. Backend Setup
- Navigate to the backend directory and install dependencies:
  ```bash
  pip install -r requirements.txt
  ```
- Run migrations and start the server:
  ```bash
  python manage.py migrate
  python manage.py runserver
  ```

#### 3. Frontend Setup
- Navigate to the frontend directory and install dependencies:
  ```bash
  npm install
  npm start
  ```

#### 4. Docker Setup
- Build and run the containers:
  ```bash
  docker-compose build
  docker-compose up
  ```

## API Endpoints

### Backend API
| Endpoint                     | Method | Description                     |
|------------------------------|--------|---------------------------------|
| `/api/journal_entries/`      | GET    | List all journal entries        |
| `/api/journal_entries/`      | POST   | Create a new journal entry      |
| `/api/search/?q=<query>`     | GET    | Full-text search for entries    |
| `/api/autocomplete/?q=<query>` | GET   | Fetch autocomplete suggestions  |

## Tests

### Backend Tests
Run backend tests using Django's `unittest`:
```bash
python manage.py test
```

### Frontend Tests
Run frontend tests using Jest:
```bash
npm test
```

## Future Enhancements
- **Deployment**: Automate deployment to cloud platforms like AWS, Azure, or Google Cloud.
- **CI/CD**: Add a CI/CD pipeline for automated builds and deployments.
- **Mobile App**: Extend functionality with a React Native mobile application.

## License
This project is licensed under the MIT License.

## Contributors
Developed and maintained by [Your Name].
