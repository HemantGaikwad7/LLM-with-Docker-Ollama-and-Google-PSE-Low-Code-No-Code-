# LLM-with-Docker-Ollama-and-Google-PSE-Low-Code-No-Code-
Overview
This project demonstrates how to deploy a Large Language Model (LLM) with no-code/low-code capabilities using Docker, Ollama, and Google Programmable Search Engine (PSE). The LLM (phi3) runs in a Docker container, enhanced by GPU support for faster inference, and features web search integration using Google PSE to augment model responses with real-time data.

Features
No-Code Deployment: Easy-to-deploy LLM without any need for writing code.
Web Search Integration: Real-time search using Google PSE API for more relevant and updated responses.
GPU Acceleration: Uses available GPUs to improve the model's performance.
Persistent Storage: Uses Docker volumes to store model data even after the container is stopped.
Auto Restart: Ensures high availability by automatically restarting the container if it stops.
Prerequisites
Ollama installed on your machine.
Docker installed.
A Google Programmable Search Engine (PSE) API key.
Installation
Step 1: Pull the Model
To pull the phi3 model using Ollama, run the following command:

bash
Copy code
ollama pull phi3
Step 2: Run the Docker Container
Start the Docker container using the following command:

bash
Copy code
docker run -d -p 3000:8080 --gpus=all -v ollama:/root/.ollama-v -v /app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
Step 3: Set Up Google PSE Integration
Obtain a Google PSE API key by creating a Programmable Search Engine on Google Custom Search.
Add the API key and search engine ID to your Docker container environment or configuration files to enable web search functionality.
Step 4: Access the Web Interface
Once the container is running, open your browser and go to:

arduino
Copy code
http://localhost:3000
You will see the deployed phi3 model, now capable of responding with integrated web search results.

Usage
LLM Interaction: You can query the phi3 model from the web interface.
Web Search Augmentation: Responses from the model can be enhanced with real-time search results using the Google PSE API.
Technologies Used
Ollama: For model management and deployment.
Docker: For containerizing the project.
Google Programmable Search Engine (PSE): For real-time web search integration.
NVIDIA GPUs: For fast inference via GPU acceleration.
License
This project is licensed under the MIT License. See the LICENSE file for details.

Additional Notes
Ensure Docker and Ollama are installed and configured properly before running the project.
If you encounter issues with GPU support, verify your NVIDIA drivers and Docker setup.
