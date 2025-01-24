# Code Optimizer Dockerized

This project demonstrates how to run a Python script for code optimization and analysis inside a Docker container. The script utilizes Google's Generative AI API for tasks like analyzing and improving code.

---

## Features

- **Python Script:** Runs a script (`code_optimizer.py`) to interact with Google's Generative AI.
- **Dockerized Environment:** Encapsulates all dependencies and configuration in a Docker container.
- **API Integration:** Integrates with Google's Generative AI API using an API key.

---

## Prerequisites

1. **Docker**: Ensure Docker is installed. You can download it from [Docker's official website](https://www.docker.com/get-started/).
2. **Google API Key**: Obtain an API key for the Generative AI API from the [Google Cloud Console](https://console.cloud.google.com/).
3. **Python Requirements**:
   - `google-generativeai`
   - `python-dotenv` (optional, for managing environment variables)

---

## Project Structure

```
/Docker_Task
├── code_optimizer.py       # Python script for code optimization
├── Dockerfile              # Docker configuration
|── requirements.txt        # Python dependencies
```

---

## Setup and Usage

### 1. Clone the Repository
```bash
git clone https://github.com/Hitesh203/Medify_Task
cd Medify_Task
```

### 2. Set the Environment Variable Locally
Run this command on Windows Powershell
```env
$env:GEMINI_API_KEY = "your_api_key_here"

```

### 3. Build the Docker Image
Build the Docker image using the provided `Dockerfile`:
```bash
docker build -t code-optimizer .
```

### 4. Run the Docker Container
Run the container with your API key:

#### Option 1: Pass API Key as an Environment Variable
```bash
docker run -e GEMINI_API_KEY=your_api_key_here code-optimizer
```

---

## Example Output
The script will:
1. Interact with the Google Generative AI API.
2. Analyze and optimize a sample Python function.
3. Print the results to the console.

---

## Dockerfile Overview

```dockerfile
# Use an official Python runtime as a base image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy requirements.txt and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY . .

# Expose the port your application runs on
EXPOSE 8000

# Run your Python application
CMD ["python", "code_optimizer.py"]

```

---

## Dependencies
The Python script relies on the following libraries:
- **google-generativeai**: For interacting with Google's Generative AI.
- **python-dotenv**: For managing environment variables (optional).

Install these libraries locally (if needed) using:
```bash
pip install -r requirements.txt
```

---

## Troubleshooting

### Error: `KeyError: 'GEMINI_API_KEY'`
- Ensure the `GEMINI_API_KEY` environment variable is set.
- If using `.env`, confirm the file exists and contains the key.

### Error: `docker run" requires at least 1 argument`
- Verify that the `docker run` command includes the image name (e.g., `code-optimizer`).

---

## License
This project is licensed under the MIT License. Feel free to use and modify as needed.

---

## Author
Developed by Hitesh Kumar.

