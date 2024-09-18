# LLM-with-Docker-Ollama-and-Google-PSE-Low-Code-No-Code-
📚 Overview
This project demonstrates how to deploy a Large Language Model (LLM) with no-code/low-code capabilities using Docker, Ollama, and Google Programmable Search Engine (PSE). The LLM (phi3) runs in a Docker container, enhanced by GPU support for faster inference, and integrates web search functionality using Google PSE to augment model responses with real-time data.

✨ Features
No-Code Deployment: Simple to deploy and interact with the LLM without writing any code.
Web Search Integration: Real-time web search capability powered by the Google PSE API.
GPU Acceleration: Utilizes available GPUs to accelerate model inference.
Persistent Storage: Docker volumes ensure model data is retained across container restarts.
Auto Restart: Ensures the container restarts automatically in case of a crash or failure.
🛠️ Prerequisites
Ollama installed on your machine.
Docker installed.
A Google Programmable Search Engine (PSE) API key.
🚀 Installation

Step 1: Pull the Model
To download the phi3 model using Ollama, run the following command:

bash
Copy code
ollama pull phi3


Step 2: Run the Docker Container
Start the Docker container using this command:

bash
Copy code
docker run -d -p 3000:8080 --gpus=all -v ollama:/root/.ollama-v -v /app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama


Step 3: Set Up Google PSE Integration
Obtain a Google PSE API key by creating a Programmable Search Engine on Google Custom Search.
Configure the API key and Search Engine ID in the Docker container environment to enable real-time web search.
Step 4: Access the Web Interface
Open your browser and go to:

arduino
Copy code
http://localhost:3000
The web UI will display the phi3 model, now enhanced with real-time search capabilities.

💡 Usage
Interact with the LLM: You can query the phi3 model via the web interface.
Web Search Integration: Responses from the model are enhanced with real-time web search results using the Google PSE API.
🛠️ Technologies Used
Ollama: For managing and deploying the LLM.
Docker: For containerization and deployment.
Google Programmable Search Engine (PSE): For integrating web search functionality.
NVIDIA GPUs: For accelerated model inference.
📜 License
This project is licensed under the MIT License. See the LICENSE file for details.

⚙️ Additional Notes
Make sure to have Docker and Ollama installed and configured before running the project.
For issues related to GPU support, ensure that your NVIDIA drivers and Docker GPU setup are correctly configured.
