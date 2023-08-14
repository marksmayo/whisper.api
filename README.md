# whisper.api

This is a production level project structure for a Python FastAPI project.

## Project Structure

```
whisper.api
├── app
│   ├── __init__.py
│   ├── api
│   │   ├── __init__.py
│   │   ├── endpoints
│   │   │   ├── __init__.py
│   │   │   ├── items.py
│   │   │   └── users.py
│   │   └── models
│   │       ├── __init__.py
│   │       ├── item.py
│   │       └── user.py
│   ├── core
│   │   ├── __init__.py
│   │   ├── config.py
│   │   ├── security.py
│   │   └── database.py
│   ├── tests
│   │   ├── __init__.py
│   │   ├── conftest.py
│   │   ├── test_api
│   │   │   ├── __init__.py
│   │   │   ├── test_items.py
│   │   │   └── test_users.py
│   │   └── test_core
│   │       ├── __init__.py
│   │       ├── test_config.py
│   │       ├── test_security.py
│   │       └── test_database.py
│   └── main.py
├── .env
├── .gitignore
├── Dockerfile
├── requirements.txt
├── README.md
└── .vscode
    ├── settings.json
    └── launch.json
```

## Description

The project structure is organized as follows:

- `app`: contains the main application code.
- `app/api`: contains the API endpoints.
- `app/api/endpoints`: contains the endpoint functions.
- `app/api/models`: contains the data models.
- `app/core`: contains the core application code.
- `app/core/config.py`: contains the application configuration.
- `app/core/security.py`: contains the security functions.
- `app/core/database.py`: contains the database connection code.
- `app/tests`: contains the test code.
- `app/tests/test_api`: contains the API endpoint tests.
- `app/tests/test_core`: contains the core application tests.
- `app/main.py`: contains the main application entry point.
- `.env`: contains environment variables.
- `.gitignore`: specifies files and directories to ignore in Git.
- `Dockerfile`: specifies the Docker image configuration.
- `requirements.txt`: specifies the Python dependencies.
- `README.md`: this file.
- `.vscode`: contains Visual Studio Code configuration files.

## Active Paths
| Path                     | Name                 | Methods     |
| ------------------------|----------------------|-------------|
| /api/v1/openapi.json     | openapi              | GET, HEAD   |
| /docs                    | swagger_ui_html      | GET, HEAD   |
| /docs/oauth2-redirect    | swagger_ui_redirect  | GET, HEAD   |
| /redoc                   | redoc_html           | GET, HEAD   |
| /api/v1/items/           | read_items           | GET         |
| /api/v1/items/{item_id}  | read_item            | GET         |
| /api/v1/users/           | create_user          | POST        |
| /api/v1/users/{user_id}/ | read_user            | GET         |
| /api/v1/users/{user_id}/ | update_user          | PUT         |
| /api/v1/users/{user_id}/ | delete_user          | DELETE      |
| /api/v1/transcribe/      | post_audio           | POST        |

## Install Dependecy
```bash
# Install ffmpeg for Audio Processing
sudo apt install ffmpeg

# Install Python Package
pip install -r requirements.txt

```

## Run this Project

```bash
uvicorn app.main:app --reload
```

## Run Test

```bash
python -m unittest
```

# Upload File
```bash
curl -X 'POST' \
  'http://localhost:8000/api/v1/transcribe/' \
  -H 'accept: application/json' \
  -H 'Content-Type: multipart/form-data' \
  -F 'audio_file=@ElevenLabs_2023-08-10T13 53 05.000Z_VedVoice_bFrkzQsyKvReo52Q6712.mp3;type=audio/mpeg'
```