
# FastAPI Demo

A simple FastAPI application demonstrating api endpoints for product management and inventory tracking.

## Features

- **GET /products/**: Get all products
- **GET /products/{product_id}**: Get a specific product by ID
- **POST /products/**: Create a new product
- **PUT /products/{product_id}**: Update an existing product
- **DELETE /products/{product_id}**: Delete an existing product

## Setup

1. **Create and activate virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # MacOS
   ```

2. **Install dependencies:**
   ```bash
   pip install fastapi uvicorn
   ```

3. **Run the application:**
   ```bash
   uvicorn main:app --reload
   ```

4. **Access the API:**
   - API: http://localhost:8000
   - Interactive docs: http://localhost:8000/docs
   - ReDoc: http://localhost:8000/redoc

## Project Structure

```
fastapi-demo/
├── main.py          # FastAPI application with endpoints
├── models.py        # Pydantic models
├── .gitignore       # Git ignore file
└── README.md        # This file
```

## API Usage Examples

### Get all products
```bash
curl http://localhost:8000/products/
```

### Get product by ID
```bash
curl http://localhost:8000/products/1
```

### Create a new product
```bash
curl -X 'POST' \
  'http://localhost:8000/products/' \
  -H 'Content-Type: application/json' \
  -d '{
        "id": 5,
        "name": "Monitor",
        "description": "4K monitor",
        "price": 299.99,
        "quantity": 15
      }'
```

### Update an existing product
```bash
curl -X 'PUT' \
  'http://localhost:8000/products/2' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
        "id": 5,
        "name": "Laptop",
        "description": "A powerful laptop",
        "quantity": 30,
        "price": 9.99
      }'
```

### Delete an existing product
```bash
curl -X 'DELETE' \
  'http://localhost:8000/products/2' \
  -H 'accept: application/json'
```

## Models

### Product
- `id`: integer
- `name`: string
- `description`: string
- `price`: float
- `quantity`: integer

## Built With

- [FastAPI](https://fastapi.tiangolo.com/) - Modern, fast web framework for building APIs
- [Pydantic](https://pydantic-docs.helpmanual.io/) - Data validation using Python type hints
- [Uvicorn](https://www.uvicorn.org/) - ASGI server implementation
