# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install build tools and dependencies
RUN apt-get update && apt-get install -y build-essential gcc

# Update pip to the latest version
RUN pip install --upgrade pip

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Verify installation
RUN echo "Installed packages:" && pip list

# Make port 8080 available to the world outside this container
EXPOSE 8080

# Define environment variable
ENV NAME World

# Run manage.py when the container launches
CMD ["python", "manage.py", "runserver", "0.0.0.0:8080"]
