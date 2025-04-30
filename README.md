# 🚀 **FastAPI App with Docker and GitHub Actions CI/CD**

This project is a **FastAPI application** containerized using Docker, with **GitHub Actions** for Continuous Integration and Continuous Deployment (CI/CD).

---

## 🔥 **1. Installation and Running Locally**

### ✅ **Prerequisites**
- Python (>=3.8)
- `pip` and `venv`
- Docker (for containerization)

### 🔧 **Local Setup Instructions**

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/kartikbhatt2808/Test-automation.git
   cd DevOps

1.  **Create and Activate Virtual Environment:**

    python3 -m venv venv
    source venv/bin/activate  # On Linux/Mac
    venv\Scripts\activate     # On Windows

2.  **Install Dependencies:**

    pip install --upgrade pip
    pip install -r requirements.txt

3.  **Run the FastAPI Server:**

    uvicorn main:app --host 0.0.0.0 --port 8000 --reload

4.  **Access the API:**

    -   Open your browser and visit: [http://localhost:8000](http://localhost:8000/)

    -   Interactive API docs: <http://localhost:8000/docs>

* * * * *

🐳 **2\. Build and Run Docker Image**
-------------------------------------

### ✅ **Prerequisites**

-   Docker installed and running.

### 🔧 **Steps to Build and Run with Docker**

1.  **Build the Docker Image:**

    docker build -t fastapi-app .

2.  **Run the Docker Container:**

    docker run -p 8000:8000 fastapi-app

3.  **Verify the API:**

    -   Open your browser: [http://localhost:8000](http://localhost:8000/)

    -   Interactive Swagger docs: <http://localhost:8000/docs>

* * * * *

🔥 **Push Docker Image to Docker Hub**
--------------------------------------

1.  **Login to Docker Hub:**

    docker login -u <your-docker-username> -p <your-docker-token>

2.  **Tag the Image:**

    docker tag fastapi-app <your-docker-username>/fastapi-app:latest

3.  **Push to Docker Hub:**

    bash

    Copy

    docker push <your-docker-username>/fastapi-app:latest

* * * * *

⚙️ **3\. GitHub Actions Workflow Explanation**
----------------------------------------------

This project uses GitHub Actions to automate building and pushing Docker images.

### ✅ **Workflow Trigger**

The workflow is triggered on every push event to the main branch.

### ✅ **Workflow Steps**

1.  **Checkout Repository:**\
    Pulls the latest code from GitHub.

    - name: Checkout Repository
      uses: actions/checkout@v4

2.  **Set up Docker Buildx:**\
    Allows building multi-platform images.

    - name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v2

3.  **Docker Login:**\
    Authenticates with Docker Hub using GitHub Secrets.

    - name: Docker Login
      uses: docker/login-action@v2
      with:
        username: ${{ secrets.DOCKER_USERNAME }}
        password: ${{ secrets.DOCKER_PASSWORD }}

4.  **Build and Push Docker Image:**\
    Builds a multi-platform image (amd64 and arm64) and pushes it to Docker Hub.

    - name: Build and Push Docker Image
      run: | docker buildx build\
          --platform linux/amd64,linux/arm64\
          -t <your-docker-username>/fastapi-app:latest .\
          --push

* * * * *

🔥 **4\. Setting up Docker Token and GitHub Secrets**
-----------------------------------------------------

### ✅ **Step 1: Generate Docker Hub Token**

1.  Go to Docker Hub and log in.

2.  Navigate to **Account Settings** → **Security**.

3.  Click **New Access Token** → Name it (e.g., github-actions) → Select read/write.

4.  Copy the generated token.

### ✅ **Step 2: Add GitHub Secrets**

1.  Go to your GitHub repository → **Settings** → **Secrets and Variables** → **Actions**.

2.  Click on **New Repository Secret**.

3.  Add the following secrets:

    -   `DOCKER_USERNAME`: Your Docker Hub username.

    -   `DOCKER_PASSWORD`: Your Docker Hub Access Token.

4.  Save the secrets.

### ✅ **Step 3: Test GitHub Actions**

1.  Push your code to the main branch.

2.  Go to GitHub → **Actions** and verify the workflow execution.

3.  After a successful build, you will find the Docker image in your Docker Hub account.

* * * * *

📚 **5\. API Endpoints**
------------------------

-   **GET /**\
    Returns a welcome message.

-   **GET /items/{item_id}**\
    Fetches an item by ID.

-   **POST /items/**\
    Creates a new item.

    **Request Body Example:**

    {
      "name": "Tiger",
      "description": "Big Cat",
      "price": 1500,
      "tax": 0.15
    }

* * * * *

🚀 **6\. Project Structure**
----------------------------


/app
 ├── Dockerfile               # Docker instructions for building the image
 ├── requirements.txt         # Python dependencies
 ├── main.py                  # FastAPI application
 ├── .github/workflows        # GitHub Actions CI/CD workflow
 ├── .dockerignore            # Files to ignore when building Docker image
 ├── README.md                # Project documentation

* * * * *

🎯 **7\. Key Commands Cheat Sheet**
-----------------------------------

### ✅ **Run Locally**

uvicorn main:app --reload

### ✅ **Build Docker Image**

docker build -t fastapi-app .

### ✅ **Run Docker Container**

docker run -p 8000:8000 fastapi-app

### ✅ **Push Docker Image to Docker Hub**

docker tag fastapi-app <your-docker-username>/fastapi-app:latest
docker push <your-docker-username>/fastapi-app:latest

* * * * *

🚀 **8\. Contributing**
-----------------------

1.  Fork the repo.

2.  Create a feature branch (`git checkout -b feature-branch`).

3.  Commit your changes (`git commit -m 'Add new feature'`).

4.  Push to the branch (`git push origin feature-branch`).

5.  Create a pull request.🚀 **FastAPI App with Docker and GitHub Actions CI/CD**
=======================================================

This project is a **FastAPI application** containerized using Docker, with **GitHub Actions** for Continuous Integration and Continuous Deployment (CI/CD).

* * * * *

🔥 **1\. Installation and Running Locally**
-------------------------------------------

### ✅ **Prerequisites**

-   Python (>=3.8)
-   `pip` and `venv`
-   Docker (for containerization)

### 🔧 **Local Setup Instructions**

1.  **Clone the Repository:**

    `git clone https://github.com/BhavyaDhimxn/DevOps.git
    cd DevOps`

2.  **Create and Activate Virtual Environment:**

    `python3 -m venv venv
    source venv/bin/activate  # On Linux/Mac
    venv\Scripts\activate     # On Windows`

3.  **Install Dependencies:**

    `pip install --upgrade pip
    pip install -r requirements.txt`

4.  **Run the FastAPI Server:**

    `uvicorn main:app --host 0.0.0.0 --port 8000 --reload`

5.  **Access the API:**

    -   Open your browser and visit: [http://localhost:8000](http://localhost:8000/)
    -   Interactive API docs: <http://localhost:8000/docs>

* * * * *

🐳 **2\. Build and Run Docker Image**
-------------------------------------

### ✅ **Prerequisites**

-   Docker installed and running.

### 🔧 **Steps to Build and Run with Docker**

1.  **Build the Docker Image:**

    `docker build -t fastapi-app .`

2.  **Run the Docker Container:**

    `docker run -p 8000:8000 fastapi-app`

3.  **Verify the API:**

    -   Open your browser: [http://localhost:8000](http://localhost:8000/)
    -   Interactive Swagger docs: <http://localhost:8000/docs>

* * * * *

🔥 **3\. Push Docker Image to Docker Hub**
------------------------------------------

1.  **Login to Docker Hub:**

    `docker login -u <your-docker-username> -p <your-docker-token>`

2.  **Tag the Image:**

    `docker tag fastapi-app <your-docker-username>/fastapi-app:latest`

3.  **Push to Docker Hub:**

    `docker push <your-docker-username>/fastapi-app:latest`

* * * * *

⚙️ **4\. GitHub Actions Workflow Explanation**
----------------------------------------------

This project uses **GitHub Actions** to automate building and pushing Docker images.

### ✅ **Workflow Trigger**

-   The workflow is triggered on every **push event** to the `main` branch.

### ✅ **Workflow Steps**

1.  **Checkout Repository:**\
    Pulls the latest code from GitHub.

    `- name: Checkout Repository
      uses: actions/checkout@v4`

2.  **Set up Docker Buildx:**\
    Enables building multi-platform images.

    `- name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v2`

3.  **Docker Login:**\
    Authenticates with Docker Hub using GitHub Secrets.

    `- name: Docker Login
      uses: docker/login-action@v2
      with:
        username: ${{ secrets.DOCKER_USERNAME }}
        password: ${{ secrets.DOCKER_PASSWORD }}`

4.  **Build and Push Docker Image:**\
    Builds a multi-platform image (`amd64` and `arm64`) and pushes it to Docker Hub.

    `- name: Build and Push Docker Image
      run: |
        docker buildx build\
          --platform linux/amd64,linux/arm64\
          -t <your-docker-username>/fastapi-app:latest .\
          --push `

* * * * *

🔥 **5\. Setting up Docker Token and GitHub Secrets**
-----------------------------------------------------

### ✅ **Step 1: Generate Docker Hub Token**

1.  Go to **Docker Hub** and log in.
2.  Navigate to:\
    **Account Settings → Security**
3.  Click:\
    **New Access Token → Name it (e.g., github-actions) → Select read/write**
4.  Copy the generated token.

### ✅ **Step 2: Add GitHub Secrets**

1.  Go to your **GitHub repository → Settings → Secrets and Variables → Actions**.
2.  Click on **New Repository Secret**.
3.  Add the following secrets:
    -   `DOCKER_USERNAME`: Your Docker Hub username.
    -   `DOCKER_PASSWORD`: Your Docker Hub Access Token.
4.  Save the secrets.

### ✅ **Step 3: Test GitHub Actions**

1.  Push your code to the `main` branch.
2.  Go to GitHub → **Actions** and verify the workflow execution.
3.  After a successful build, you will find the Docker image in your Docker Hub account.

* * * * *

📚 **6\. API Endpoints**
------------------------

| Method | Endpoint | Description | Example Request |
| --- | --- | --- | --- |
| `GET` | `/` | Returns a welcome message | `curl http://localhost:8000/` |
| `GET` | `/items/{item_id}` | Fetches an item by ID | `curl http://localhost:8000/items/1` |
| `POST` | `/items/` | Creates a new item | See Example Body Below |

### ✅ **POST Request Body Example**

`{
  "name": "Tiger",
  "description": "Big Cat",
  "price": 1500,
  "tax": 0.15
}`

* * * * *

🚀 **7\. Project Structure**
----------------------------

`/app
 ├── Dockerfile               # Docker instructions for building the image
 ├── requirements.txt         # Python dependencies
 ├── main.py                  # FastAPI application
 ├── .github/workflows        # GitHub Actions CI/CD workflow
 ├── .dockerignore            # Files to ignore when building Docker image
 ├── README.md                # Project documentation`

* * * * *

🎯 **8\. Key Commands Cheat Sheet**
-----------------------------------

### ✅ **Run Locally**

`uvicorn main:app --reload`

### ✅ **Build Docker Image**

`docker build -t fastapi-app .`

### ✅ **Run Docker Container**

`docker run -p 8000:8000 fastapi-app`

### ✅ **Push Docker Image to Docker Hub**

`docker tag fastapi-app <your-docker-username>/fastapi-app:latest
docker push <your-docker-username>/fastapi-app:latest`

* * * * *

🚀 **9\. Contributing**
-----------------------

1.  **Fork the Repository:**\
    Click the **Fork** button on GitHub.

2.  **Create a Feature Branch:**

    `git checkout -b feature-branch`

3.  **Commit Your Changes:**

    `git commit -m "Add new feature"`

4.  **Push to the Branch:**

    `git push origin feature-branch`

5.  **Create a Pull Request:**\
    Submit your PR on GitHub and describe the changes.

* * * * *

🌟 **10\. Future Enhancements**
-------------------------------

-   ✅ Add **unit tests** and coverage reports.
-   ✅ Deploy the app to **AWS/GCP** using Terraform.
-   ✅ Include **database integration** (PostgreSQL or MongoDB).
-   ✅ Set up **monitoring and logging** using Prometheus and Grafana.
-   ✅ Add **CI/CD badges** in the README.

* * * * *

🎉 **Thank you for using the FastAPI Dockerized CI/CD App!**\
💡 Feel free to contribute, report issues, or suggest improvements. 🚀
