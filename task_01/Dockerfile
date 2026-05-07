FROM python:3.12-alpine

WORKDIR /app

# Copy your script from the build context into the container's /app directory
COPY app.py .

# Run the script when the container starts
CMD ["python", "app.py"]