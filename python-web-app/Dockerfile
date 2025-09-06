# Use official Python slim image (smaller & faster)
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy requirements first for caching
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the project code
COPY devops/ .

# Expose port Django will run on
EXPOSE 8000

# Set environment variable to avoid .pyc files and buffering issues
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Run Django development server
CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]