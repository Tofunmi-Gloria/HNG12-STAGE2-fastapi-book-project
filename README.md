# FastAPI Book Management API

## Overview

This project is a RESTful API built with FastAPI for managing a book collection. It provides comprehensive CRUD (Create, Read, Update, Delete) operations for books with proper error handling, input validation, and documentation. Continuous Integration (CI) and Continuous Deployment (CD) workflows are also configured for automated testing and deployment.

## Features

- 📚 Book management (CRUD operations)
- ✅ Input validation using Pydantic models
- 🔍 Enum-based genre classification
- 🧪 Automated CI/CD pipeline for tests and deployments
- 📝 Auto-generated API documentation (Swagger UI and ReDoc)
- 🔒 CORS middleware enabled

## Project Structure

```nginx
HNG 12 Stage 2/
├── FastAPIBookProject/
│   ├── api/
│   │   ├── db/
│   │   │   ├── __init__.py
│   │   │   └── schemas.py      # Data models and in-memory database
│   │   ├── routes/
│   │   │   ├── __init__.py
│   │   │   └── books.py        # Book route handlers
│   │   └── router.py           # API router configuration
│   ├── core/
│   │   ├── __init__.py
│   │   └── config.py           # Application settings
│   ├── tests/
│   │   ├── __init__.py
│   │   └── test_books.py       # API endpoint tests
│   ├── .github/
│   │   └── workflows/
│   │       ├── ci.yml          # CI workflow
│   │       └── cd.yml          # CD workflow
│   ├── main.py                 # Application entry point
│   ├── requirements.txt        # Project dependencies
│   └── README.md
└── VEMV/                       # Additional folder (not used here)
```

## Technologies Used

- Python 3.12
- FastAPI
- Pydantic
- pytest
- Uvicorn

## Installation

- Clone the repository:

```bash
git clone https://github.com/hng12-devbotops/fastapi-book-project.git
cd fastapi-book-project
```

- Create a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

- Install dependencies:

```bash
pip install -r requirements.txt
```

## Running the Application

### Start the server:

```bash
uvicorn main:app
```

## Access the API documentation:

- Swagger UI: http://localhost:8000/docs
- ReDoc: http://localhost:8000/redoc

## API Endpoints

### Books

- GET /api/v1/books/ - Get all books
- GET /api/v1/books/{book_id} - Get a specific book
- POST /api/v1/books/ - Create a new book
- PUT /api/v1/books/{book_id} - Update a book
- DELETE /api/v1/books/{book_id} - Delete a book

### Health Check

- GET /healthcheck - Check API status

## Book Schema

```json
{
  "id": 1,
  "title": "Book Title",
  "author": "Author Name",
  "publication_year": 2024,
  "genre": "Fantasy"
}
```

### Available genres:

- Science Fiction
- Fantasy
- Horror
- Mystery
- Romance
- Thriller

## Continuous Integration and Deployment (CI/CD)

- CI Workflow (ci.yml): Automatically runs tests on every push to ensure code quality.
- CD Workflow (cd.yml): Deploys the application upon successful CI checks.

To manually trigger the workflows, push your changes to the GitHub repository:

```bash
git add .
git commit -m "Add feature"
git push origin main
```

## Running Tests

### Run all tests using the following command:

```bash
pytest
```

## Error Handling

### The API includes proper error handling for:

- Non-existent books
- Invalid book IDs
- Invalid genre types
- Malformed requests

## Contributing

- Fork the repository
- Create a feature branch (git checkout -b feature/AmazingFeature)
- Commit changes (git commit -m 'Add AmazingFeature')
- Push to branch (git push origin feature/AmazingFeature)
- Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, please open an issue in the GitHub repository.
