# Use the official Python image from the DockerHub
FROM python:3.11-slim

# Set environment variables to prevent python from writing pyc files
ENV PYTHONUNBUFFERED 1

# Create and set the working directory
WORKDIR /app

# Copy the requirements.txt file to the container
COPY backend/mysite/requirements.txt /app/

# Install the dependencies
RUN pip install --no-cache-dir -r /app/requirements.txt

# Copy the Django project code into the container
COPY backend/mysite /app/

# Expose port 8000 for Django
EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

# Run Django server (with gunicorn in production)
# CMD ["gunicorn", "--bind", "0.0.0.0:8000", "mysite.wsgi:application"]
