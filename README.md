## FastDCA Project

## Introduction
The FastDCA Project is a simple API built using FastAPI, a modern, high-performance web framework for building APIs with Python. This project demonstrates how to set up a FastAPI application, create basic API endpoints, and run it using the Uvicorn ASGI server. It serves as a foundation for creating scalable web applications or APIs.

## Features
GET /: A root endpoint that returns a simple message: {"Hello": "World"}

## GET /items/{item_id}: An endpoint that accepts a path parameter item_id and an optional query parameter q to fetch item data.

Interactive API documentation available at /docs.

## Requirements
Python 3.13+

Uvicorn: ASGI server to run the app

FastAPI: Web framework to create APIs

pytest (optional): Testing framework for writing unit tests

## Setup

## 1. Create a Project Directory
Start by initializing a new project and switching to the project directory:

## bash
uv init fastdca-p1
cd fastdca-p1

## 2. Create and Activate the Virtual Environment
On Windows:

bash

uv venv
.venv\Scripts\activate
On macOS/Linux:

bash
uv venv
source .venv/bin/activate

## 3. Install Dependencies
Install FastAPI and Uvicorn:

bash
uv add "fastapi[standard]"
If you want to install development dependencies like pytest for testing, run the following command:

bash
uv add --dev pytest pytest-asyncio

## 4. Create Your First API
Create a file named main.py in the project directory and add the following code:

python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Hello": "World"}

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str | None = None):
    return {"item_id": item_id, "q": q}
    
## 5. Run the FastAPI Server
Run the server using either of the following commands:

FastAPI Command (Development mode):

bash
fastapi dev main.py

## Uvicorn Command:

bash
uv run uvicorn main:app --host 0.0.0.0 --port 8000 --reload

## 6. Test Your API
You can test your API by visiting the following URLs:

## Root endpoint: http://localhost:8000 (returns {"Hello": "World"})

Items endpoint with parameters: http://localhost:8000/items/5?q=somequery

Interactive API docs: http://localhost:8000/docs

## Conclusion

This is a simple FastAPI application that can be extended to build more complex APIs and applications. FastAPI offers powerful features like automatic data validation, interactive documentation, and fast performance, making it an excellent choice for building web services.
