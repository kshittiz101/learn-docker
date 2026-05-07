# Task 01 - Simple Python Application

A basic Python script that prints a greeting message with the current timestamp.

## Description

This project demonstrates a minimal Python application containerized with Docker. When executed, it prints "Hello from kc, the time is [current timestamp]" to the console.

## Requirements

- Python 3.12+ (for local execution)
- Docker (for containerized execution)

## Local Execution

Run the Python script directly:

```bash
python app.py
```

Expected output:

```
Hello from kc, the time is 2026-05-07 12:34:56.789012
```

## Docker Execution

### Build the Docker Image

```bash
docker build -t task-01 .
```

### Run the Container

```bash
docker run --rm task-01
```

This will execute the Python script inside the Docker container and display the greeting with the current timestamp.

## Project Structure

```
task_01/
├── app.py      # Main Python script
├── Dockerfile  # Docker container configuration
└── README.md   # This file
```

## Docker Details

- **Base Image**: Python 3.12 Alpine (lightweight Python image)
- **Working Directory**: `/app`
- **Entry Point**: `python app.py`
