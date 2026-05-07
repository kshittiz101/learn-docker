# Task 01 - Simple Python Application

A lightweight Python script that prints a greeting message with the current timestamp, containerized with Docker.

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Project Structure](#project-structure)
- [Quick Start](#quick-start)
  - [Run Locally](#run-locally)
  - [Run with Docker](#run-with-docker)
- [Docker Guide](#docker-guide)
  - [Build the Image](#build-the-image)
  - [Run the Container](#run-the-container)
  - [Verify the Image](#verify-the-image)
- [Dockerfile Reference](#dockerfile-reference)
- [License](#license)

---

## Overview

This project demonstrates a minimal Python application that outputs a greeting message along with the current timestamp. It serves as a basic example for understanding Docker containerization with Python.

**Output Example:**

```
Hello from kc, the time is 2026-05-07 12:34:56.789012
```

---

## Requirements

| Tool   | Version | Purpose                            |
| ------ | ------- | ---------------------------------- |
| Python | 3.12+   | Running the script locally         |
| Docker | Latest  | Building and running the container |

---

## Project Structure

```
task_01/
├── app.py          # Python application script
├── Dockerfile      # Docker image configuration
└── README.md       # Project documentation
```

---

## Quick Start

### Run Locally

Execute the Python script directly on your machine:

```bash
python app.py
```

### Run with Docker

1. Build the image:

   ```bash
   docker build -t task-01 .
   ```

2. Run the container:
   ```bash
   docker run --rm task-01
   ```

---

## Docker Guide

### Build the Image

To create a Docker image from the Dockerfile:

```bash
docker build -t task-01 .
```

**Command Breakdown:**

| Component      | Description                                             |
| -------------- | ------------------------------------------------------- |
| `docker build` | Command to build a Docker image                         |
| `-t task-01`   | Tags the image with the name `task-01`                  |
| `.`            | Build context (current directory containing Dockerfile) |

### Run the Container

Execute the containerized application:

```bash
docker run --rm task-01
```

**Flags:**

- `--rm` - Automatically remove the container after it exits

To run the container again without rebuilding:

```bash
docker start -a task-01
```

### Verify the Image

Check that the image was created successfully:

```bash
docker images
```

You should see `task-01` listed in the output.

---

## Dockerfile Reference

The Dockerfile contains instructions to build the Docker image:

```dockerfile
FROM python:3.12-alpine
WORKDIR /app
COPY app.py .
CMD ["python", "app.py"]
```

| Instruction                | Description                                                     |
| -------------------------- | --------------------------------------------------------------- |
| `FROM python:3.12-alpine`  | Base image: lightweight Python 3.12 on Alpine Linux (~50MB)     |
| `WORKDIR /app`             | Sets working directory to `/app` inside the container           |
| `COPY app.py .`            | Copies `app.py` from the build context to the working directory |
| `CMD ["python", "app.py"]` | Defines the default command to run when the container starts    |

---

**Built with ❤️ by kc**
