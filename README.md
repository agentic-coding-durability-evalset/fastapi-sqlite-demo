# FastAPI SQLite Demo

A Python Web application demo project based on [FastAPI](https://fastapi.tiangolo.com/) and SQLite. Uses SQLModel as ORM and demonstrates how to build modern asynchronous APIs.

## Tech Stack

- **Python**: 3.13+
- **FastAPI**: 0.112.1+
- **SQLModel**: 0.0.27+ (Based on SQLAlchemy and Pydantic)
- **SQLAlchemy**: 2.0.41+
- **aiosqlite**: 0.21.0+ (Async SQLite driver)
- **Pytest**: 8.4.2+ (Testing framework)

## Project Structure

```
fastapi-sqlite-demo/
├── app/
│   ├── main.py              # FastAPI application entry point
│   ├── dependencies.py      # Dependency injection
│   ├── domain/
│   │   ├── models.py        # Data model definitions
│   │   ├── infra/
│   │   │   └── db.py        # Database connection configuration
│   │   └── repository/
│   │       ├── hero_repo.py # Hero data repository
│   │       └── tests/       # Repository tests
│   └── routers/
│       └── heros.py         # Hero API routes
├── db/
│   ├── schema.ddl          # Database schema definition
│   └── demo.sqlite3        # SQLite database file
├── tests/
│   └── test_sqlmodel.py   # Integration tests
├── pyproject.toml          # Project configuration and dependencies
├── pytest.ini             # Pytest configuration
├── Dockerfile             # Docker configuration
├── Justfile               # Just build tool configuration
└── README.md
```

## Features

- RESTful API design
- Asynchronous database operations
- SQLModel ORM (combining SQLAlchemy and Pydantic)
- Automatic API documentation (Swagger/OpenAPI)
- Dependency injection
- Unit and integration testing
- Docker support

## Quick Start

### Prerequisites

- Python 3.13 or higher
- pip or uv (recommended)

### Installation and Running

```bash
# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -e ".[dev]"

# Run application
fastapi dev app/main.py
```

The application will start at `http://localhost:8000`.

## API Endpoints

### Root Path
```http
GET http://localhost:8000/
```
Response: `{"message": "Hello World!"}`

### Hero API

All Hero-related API endpoints are defined in `/app/routers/heros.py`.

## Development Tools

### Just

The project includes a `Justfile` that provides convenient commands:

```bash
# View available commands
just

# Run development server
just dev

# Run tests
just test
```

## Project Features

### Domain-Driven Design

The project adopts a Domain-Driven Design (DDD) structure:
- **Domain**: Business logic and models
- **Infrastructure**: Infrastructure layer (database)
- **Repository**: Data access layer
- **Routers**: API routing layer

### Dependency Injection

Uses FastAPI's dependency injection system to manage resources such as database sessions.

## References

- [FastAPI Documentation](https://fastapi.tiangolo.com/)
- [SQLModel Documentation](https://sqlmodel.tiangolo.com/)
- [Simple Hero API with FastAPI](https://sqlmodel.tiangolo.com/tutorial/fastapi/simple-hero-api/)
