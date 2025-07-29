<div align="center">
    <h1>AI Coding Challenge Generator </h1>
</div>

---

## Contents

- [Overview](#1--overview)
- [Development Philosophy](#2--development-philosophy)
- [Folder Structure](#3--folder-structure)
- [Running the Application Locally](#4--running-the-application-locally)
- [Technology Stack](#5--technology-stack)

## `1` 🎯 Overview

The Coding Challenge Generator is a full-stack web application designed to generate coding challenges 
for users to practice and improve their skills. It features a React frontend with routing, 
where users can navigate between the challenge page and a history page displaying past challenges. 
The backend is powered by FastAPI, and the application integrates Clerk for secure user authentication and 
leverages OpenAI's API to generate coding challenges using AI/LLM (Large Language Model) technology.

## `2` 📚 Development Philosophy

A philosophy is a set of guiding principles. It provides a foundation for the project's design and implementation.
The philosophy for this project was shaped by a balance of delivering a functional and user-friendly product while 
also exploring new technologies and frameworks.
- **Modularity**: The system is divided into clear, independent modules (frontend and backend), each focusing on specific functionalities. This allows for easier maintenance, scalability, and debugging.
- **Simplicity & Clarity**: Code is written to be easy to read and maintain.
- **Security**: Authentication and sensitive data handling are taken seriously, with Clerk providing token-based user verification.
- **Learning & Exploration**: The project was also driven by my curiosity to dive into new technologies like React, FastAPI, and AI integration. It was an opportunity to deepen my understanding of modern web development while experimenting with real-world applications of artificial intelligence.

## `3` 📂 Folder Structure

```
├── frontend/
├──── src/                - Contains the source code for the React application
│     ├── auth/          
│     ├── challenge/     
│     ├── history/       
│     ├── layout/        
│     ├── utils/         
│     ├── App.jsx         - Core component that manages the game's logic and user interface
│     ├── main.tsx        - Entry point for rendering the React app into the HTML template
├──── index.html          - Template file which is served up when script is run
├──── .eslint.config.js   - ESLint configuration for linting code
├──── package.json        - Configuration file for npm packages and project settings
├── backend/
│     ├── src/            
│     │   ├── database/   - Database connection and ORM models
│     │   ├── routes/     
├──── ai_generator.py     
├──── app.py              
├──── utils.py            
├──── server.py           
├──── pyproject.toml      
└── README.md
```

## `4` 🚀 Running the Application Locally
Before you begin, ensure you have met the prerequisites, and then
follow these steps to run the application locally.
> [!IMPORTANT]
>
> Because the project includes a client side and a server side, you need to install & run each separately.

<details><summary><b>Show instructions</b></summary>

1. **Clone the repository**: Start by cloning the repository to your local machine.
2. **Navigate to the frontend/backend directory**: Go to each folder within the project's root directory.
3. **Install dependencies**
4. **Set up environment variables**:
   - Create a .env file in the backend and frontend directory.
   - Add your Clerk API keys and OpenAI API key (from the respective dashboards).
    - Example `.env` file for the backend:
      ```plaintext
      CLERK_SECRET_KEY
      JWT_KEY
      OPENAI_API_KEY
      CLERK_WEBHOOK_SECRET
      ```
    - Example `.env` file for the frontend:
        ```plaintext
        VITE_CLERK_PUBLISHABLE_KEY
        ```
5. Start the development server:
    ```shell
    npm run dev # For the frontend
    ```
   
    ```shell
    uv run server.py # For the backend
    ```

</details>

<details><summary><b>Prerequisites</b></summary>

- Python
  - uv (Python package manager)
  - Unlike pip, uv is faster and more efficient, offering better performance for managing the virtual environment and dependencies for the backend.
- Node.js: Make sure you have Node.js installed.
  Node.js includes npm (package manager) by default.  
  To confirm that Node.js is installed correctly, open your terminal or command prompt and run the following commands:
    - ```shell 
      node -v # Displays the current version of Node.js.
      ```
    - ```shell
      npm -v # Displays the current version of npm.
      ```
- An Integrated Development Environment (IDE)
  - PyCharm
  - Visual Studio Code
- Clerk Account
  - Sign up for an account at [Clerk](https://clerk.com/).
  - Create a new application in Clerk and obtain your API keys.
  - Set up the environment variables in the `.env` file in the backend directory with your Clerk API keys.
- OpenAI Account
  - Sign up for an account at [OpenAI](https://platform.openai.com/).
  - Obtain your API key from the OpenAI dashboard.
  - Set up the environment variables in the `.env` file in the backend directory with your OpenAI API key.
  - _Note: You need to set up a payment method to add credit balance to use the API._

</details>

## `5` 🛠️ Technology Stack
- **Frontend**: React, Javascript
- **Backend**: FastAPI, Python, uv (Python package manager)
- **Authentication**: Clerk
- **AI/LLM**: OpenAI
  - Used this because it provides a powerful and flexible way to generate coding challenges. 
    Also, it is easy to use and integrate with the application.
- **Database**: SQLite
    - Database runs locally, a file that is created in the backend directory.
    - SQLAlchemy Object Relational Mapper
    - Allows us to write Python classes that represent SQL (Structured Query Language) tables, 
      making it easier to interact with the database with the python wrapper instead of writing raw SQL queries ourselves.

<figure align="center">
  <img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/6715e9f8-f81e-4f2b-81f6-811a1a03128d" />
  <br>
  <figcaption><em>Tech Stack Diagram</em></figcaption>
</figure>