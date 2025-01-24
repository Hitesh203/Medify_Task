# Medify Task

This repository contains the code and Docker setup for a Python-based task that utilizes the `google.generativeai` library to optimize and process generative AI tasks. It also includes a Dockerfile for containerizing the application.

## Features
- Python script (`code_optimizer.py`) that integrates with the `google.generativeai` library.
- Docker setup to containerize the application for easy deployment.
- Environment variable support for secure API key management.

## Prerequisites
- Python 3.9 or later
- Docker installed on your system
- Google Generative AI API key (set as `GEMINI_API_KEY`)

## Project Structure
```
Medify_Task/
├── Dockerfile             # Docker configuration file
├── requirements.txt       # Python dependencies
├── code_optimizer.py      # Main application script
└── README.md              # Project documentation
```

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/Hitesh203/Medify_Task.git
cd Medify_Task
```

### 2. Install Dependencies
If you want to run the application locally:
```bash
pip install -r requirements.txt
```

### 3. Set Up Environment Variables
Set the `GEMINI_API_KEY` environment variable with your Google Generative AI API key:

On Linux/MacOS:
```bash
export GEMINI_API_KEY=your_api_key_here
```
On Windows:
```bash
set GEMINI_API_KEY=your_api_key_here
```

### 4. Run the Application
Run the script locally:
```bash
python code_optimizer.py
```

## Using Docker

### 1. Build the Docker Image
Run the following command to build the Docker image:
```bash
docker build -t medify-task-app .
```

### 2. Run the Docker Container
Start the container and pass the API key as an environment variable:
```bash
docker run -p 8000:8000 -e GEMINI_API_KEY=your_api_key_here medify-task-app
```

### 3. Access the Application
The application will be available at:
```
http://localhost:8000
```

## Notes
- Replace `your_api_key_here` with your actual Google Generative AI API key.
- Make sure `code_optimizer.py` is configured to listen on port `8000` for compatibility with the Docker setup.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing
Feel free to fork this repository and submit pull requests for improvements or fixes. For major changes, please open an issue first to discuss the proposed changes.

## Contact
For any questions or feedback, reach out at [Hitesh Kumar](mailto:hiteshkumarmz16@gmail.com).

---

Happy coding!

