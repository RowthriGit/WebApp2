# Use a lightweight Python base image
FROM python:3.10-slim

# Set the working directory
WORKDIR /app

# Install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy your entire app
COPY . .

# Expose the port Flask runs on (adjust if different)
EXPOSE 5000

# Set the command to run your Flask app
CMD ["python", "app.py"]
