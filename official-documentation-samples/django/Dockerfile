# Use the official Python image as a base
FROM python:3.11

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set the working directory inside the container
WORKDIR /app

# Install dependencies
COPY requirements.txt /app/
RUN pip install --upgrade pip && pip install -r requirements.txt

# Copy the rest of your project files into the container
COPY . /app/

# Expose port 8000 (inside the container)
EXPOSE 8000

# Start the Django application using Gunicorn on port 8000
CMD ["gunicorn", "mysite.wsgi:application", "--bind", "0.0.0.0:8000"]

