# Abhishek_devops
# DevOps-LABFILE
# LAB-1 GIT COMMANDS
This repository contains the practical lab files and exercises related to DevOps, including Git operations and version control demonstrations.

Cloning the Repository To begin, clone this repository using the following command:

git clone https://github.com/Abhishek708844/Abhishek_devops.git
![f1](https://github.com/user-attachments/assets/f42cb4a3-035d-47fc-a073-a860d0eae136)

clone command

Staging, Committing, and Pushing Changes After making changes to the repository (e.g., editing files, creating new ones), use the following commands to stage, commit, and push those changes:

git add .
git commit -m "figure 1"
git push
git add . stages all modified and new files.

git commit -m "figure 1" saves the changes with a commit message.

git push uploads the changes to the remote GitHub repository.

![f2](https://github.com/user-attachments/assets/a2349d7a-d78f-4905-9567-370a7e201779)


add,push,commit

Checking the Status of Your Working Directory To view the current state of your working directory, run:

![f3](https://github.com/user-attachments/assets/8b600e2c-a053-4078-a6bb-b49e3c5ab63f)


 git status 
status

Viewing Code Differences To examine the changes you made before committing, use:

git diff
diff


# LAB-2 GIT COMMANDS
# 1. Simulating Team Collaboration (Branching and Feature Development) 

🟡  Create feature-user1 and edit

git checkout -b feature-user1
echo "User1: Added feature A" >> project.txt

🟡 Commit changes

git add project.txt
git commit -m "User1: Added feature A"

[feature-user1 1a2b3c4] User1: Added feature A
 1 file changed, 1 insertion(+)
 
🟡 Push branch

git push origin feature-user1

![Screenshot 2025-04-14 221102](https://github.com/user-attachments/assets/5787d901-c596-4d2a-8e2d-990e2afb20a9)

![Screenshot 2025-04-14 221032](https://github.com/user-attachments/assets/3e29f2c4-bcd2-4c76-9497-6570e0b330bc)


🟡  Switch to main and create feature-user2

git checkout main
git checkout -b feature-user2
echo "User2: Added feature B" >> project.txt

🟡Commit and push

git add project.txt
git commit -m "User2: Added feature B"
git push origin feature-user2

![Screenshot 2025-04-14 221755](https://github.com/user-attachments/assets/2f0db0b3-7328-4072-a58d-0989a16429aa)


 # 2. Merge Conflict Simulation and Resolution


🔴 Step 1: Switch to main and merge branch1

git checkout main
git merge branch1
✅ O/P (Expected):
Updating abc1234..1a2b3c4
Fast-forward
 project.txt | 1 +
✅ This will succeed if branch1 does not conflict with main.

🔴 Step 2: Push merged main

 git push origin main

🔴 Step 3: Merge branch2 (creates a conflict)

git merge branch2
⚠️ O/P (Expected Conflict):
Auto-merging project.txt
CONFLICT (content): Merge conflict in project.txt
Automatic merge failed; fix conflicts and then commit the result.

🔴 Step 4: Resolve conflict
Edit the file project.txt, and change:

text
Copy code
<<<<<<< HEAD
User1: Added feature A
=======
User2: Added feature B
>>>>>>> branch2
To this (keeping both):

text
Copy code
User1: Added feature A
User2: Added feature B

🔴 Step 5: Stage, commit & push

git add project.txt
git commit -m "Resolved merge conflict between branch1 and branch2"
git push origin main
✅ Now your main branch has both changes from branch1 and branch2, and the merge conflict is cleanly resolved.



![f4](https://github.com/user-attachments/assets/b0a24b71-242d-44e3-b9db-41642aff39f4)

![f5](https://github.com/user-attachments/assets/52c56c64-bf1d-4870-9821-49bbeb8c7c61)

![f6](https://github.com/user-attachments/assets/99a1d8db-fb2d-4db7-b1eb-ecf53fae14fa)


![f7](https://github.com/user-attachments/assets/6214bbf1-e877-4aa9-9b6c-77d5cbaccc29)

 # 3. Git Rebase Practice
🔵 Step 4.1: Create feature-rebase and modify
git checkout -b feature-rebase
echo "Rebase feature: New logic" >> project.txt

🔵 Step 4.2: Commit the changes
git add project.txt
git commit -m "Rebase feature: Added new logic"

🔵 Step 4.3: Rebase onto main
git rebase main
O/P:
Successfully rebased and updated refs/heads/feature-rebase.

🔵 Step 4.4: Push to GitHub
git push origin feature-rebase
Or if already pushed and rebasing again:

git push origin feature-rebase --force


![f8](https://github.com/user-attachments/assets/55d6943c-2ac4-4120-a131-70996035e71c)


# 4. Undoing Changes with Git Revert
🟠 Step 5.1: View commit history
git log --oneline
O/P:
9f9e111 (HEAD -> main) Resolved merge conflict...
3c3b111 User2: Added feature B
1a2b3c4 User1: Added feature A
abc1234 Initial commit


🟠 Step 5.2: Revert the last commit
git revert 9f9e111
O/P:
[main 1f1f1f1] Revert "Resolved merge conflict..."

🟠 Step 5.3: Push the revert
git push origin main

![f9](https://github.com/user-attachments/assets/f4a2536e-4be2-467f-adec-314e2ad3633f)


# GIT SUBMODULE

CREATE THREE REPO IN GITHUB AND CLONE IT TO YOUR PC REPO1:MAIN-add index.html file->add->commit->push REPO2:CSS-add style.css file->add->commit->push REPO3:JS-add script.js file->add->commit->push

![F12](https://github.com/user-attachments/assets/60db4f5a-35f4-476b-8124-9bf41495e6f7)


![F10](https://github.com/user-attachments/assets/ba3e3f65-7d30-41e9-bbb0-92ce7908d6d5)

![F11](https://github.com/user-attachments/assets/3eb0c2cd-36d1-4d6c-8a10-9ab922a564a2)


open integrated terminal of MAIN repo

git submodule add https://github.com/SAGAR-SINGH-X-CUBE/JS.git css

git submodule add https://github.com/SAGAR-SINGH-X-CUBE/CSS.git css

git add .

git commit -m "submodule added"

git push

![F13](https://github.com/user-attachments/assets/d1b8c3b2-38a7-4dc4-b0ac-03ba9a6c4457)


# Hosting Submodule 
Go to that repo containing files to run website then
Click on "Settings" → "Pages" Under "Branch," select main. Click "Save."

link:
![Screenshot 2025-04-15 130534](https://github.com/user-attachments/assets/87471101-103d-4d41-bd38-d1d99e1c2199)


![Screenshot 2025-04-15 125505](https://github.com/user-attachments/assets/362f3cef-f0f6-4313-99a8-7dc0e9d4aaf4)


# DevOps Experiment 5: FastAPI Dockerization
# Experiment 5: FastAPI Application Development and Dockerization

1. FastAPI Application Setup

Created a basic FastAPI application with the following structure:

fastapi-app/
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── models.py
│   └── schemas.py
├── requirements.txt
└── Dockerfile
#main.py:

python
from fastapi import FastAPI

from .schemas import MessageResponse


app = FastAPI(title="DevOps Experiment API")


@app.get("/", response_model=MessageResponse)

async def root():

   return {"message": "Welcome to DevOps Experiment API"}
    

@app.get("/health", response_model=MessageResponse)

async def health_check():

   return {"message": "API is healthy"}
    
    
#schemas.py:


python

from pydantic import BaseModel


class MessageResponse(BaseModel):

   message: str
    
#requirements.txt:

fastapi==0.95.2
uvicorn==0.22.0

2. Dockerization
Created a Dockerfile with multi-stage build for optimization:

#dockerfile
# Build stage
FROM python:3.9-slim as builder

WORKDIR /app
COPY requirements.txt .

RUN pip install --user -r requirements.txt

# Runtime stage
FROM python:3.9-slim

WORKDIR /app
COPY --from=builder /root/.local /root/.local
COPY ./app ./app

ENV PATH=/root/.local/bin:$PATH
ENV PYTHONPATH=/app

EXPOSE 80

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "80"]

3. Building and Running the Container
# Build the image
docker build -t fastapi-devops .

# Run the container
docker run -d -p 80:80 --name fastapi-app fastapi-devops
Verification:

Accessed http://localhost/ and http://localhost/health in browser

Verified responses:

json
{"message":"Welcome to DevOps Experiment API"}
json
{"message":"API is healthy"}

![D5](https://github.com/user-attachments/assets/0e33e789-a4a1-4af9-a9b1-80aeccb320de)





![D5 (2)](https://github.com/user-attachments/assets/942fec14-1245-4484-bb6f-e8f4f8a62932)






![D5 (3)](https://github.com/user-attachments/assets/f5b100cf-ea50-4658-add2-ea9709fd1043)




# Using browser  http://localhost/health
![D5 (4)](https://github.com/user-attachments/assets/35c41594-b30c-4d39-8d0b-4996cd3ef23c)




# Using FastAPI's automatic docs    http://localhost/docs
![D5 (5)](https://github.com/user-attachments/assets/5777f5e9-c8e2-4307-a747-08e10d0a61cb)

#NOTE
# Stop and remove the container (when done)
bash
docker stop fastapi-app
docker rm fastapi-app
Additional Verification

# You can verify the container is running with:
docker PS



# Check logs with:
docker logs fastapi-app


# Experiment 6: Automation Using GitHub Actions

# 1. Project Setup
Ensure you have:

A GitHub repository for your FastAPI app (fastapi-app)

Dockerfile (from Experiment 5)

GitHub account with Docker Hub credentials (for pushing images)

# 2. Create GitHub Actions Workflow
File Structure
fastapi-app/
├── .github/
│   └── workflows/
│       └── docker-build.yml  # GitHub Actions workflow
├── app/
│   └── ... (FastAPI code)
├── Dockerfile
└── requirements.txt
Workflow File (.github/workflows/docker-build.yml)
yaml
name: Docker Build and Push

on:
  push:
    branches: ["main"]
  pull_request:
    branches: ["main"]

env:
  IMAGE_NAME: fastapi-devops

jobs:
  build-and-push:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKER_HUB_USERNAME }}
          password: ${{ secrets.DOCKER_HUB_TOKEN }}

      - name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v3

      - name: Build and push Docker image
        uses: docker/build-push-action@v5
        with:
          context: .
          push: ${{ github.ref == 'refs/heads/main' }}
          tags: |
            ${{ secrets.DOCKER_HUB_USERNAME }}/${{ env.IMAGE_NAME }}:latest
            ${{ secrets.DOCKER_HUB_USERNAME }}/${{ env.IMAGE_NAME }}:${{ github.sha }}

  test:
    needs: build-and-push
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Run API tests
        run: |
          docker run -d -p 8000:80 --name test-api ${{ secrets.DOCKER_HUB_USERNAME }}/${{ env.IMAGE_NAME }}:latest
          sleep 5  # Wait for API to start
          curl -s http://localhost:8000/ | grep -q "Welcome to DevOps"
          curl -s http://localhost:8000/health | grep -q "API is healthy"
          
# 3. Configure GitHub Secrets
Go to Repository Settings → Secrets → Actions.

Add:

DOCKER_HUB_USERNAME → Your Docker Hub username

DOCKER_HUB_TOKEN → Docker Hub access token (Create one here)

# 4. Push to GitHub & Trigger Workflow
bash
git add .
git commit -m "Add GitHub Actions workflow"
git push origin main

# 5. Monitor Workflow Execution
Go to GitHub → Actions tab.

Check the Docker Build and Push workflow.

Verify:

✅ Docker image is built.

✅ Tests pass.

✅ Image pushed to Docker Hub (on main branch push).

# 6. Expected Output
Successful Workflow Run:

✓ Docker image built: username/fastapi-devops:latest
✓ API tests passed

![D6 (2)](https://github.com/user-attachments/assets/a155ab35-e34b-445b-965e-1fe17c480ff5)






![D6](https://github.com/user-attachments/assets/9beb45be-7aab-403f-92fe-bd308a93c2b7)


# Docker Hub:

https://hub.docker.com/r/username/fastapi-devops



# Final Step: Deploy!
Now you can deploy your FastAPI app anywhere (AWS, Azure, etc.) using:

bash
docker run -d -p 80:80 username/fastapi-devops:latest



# Experiment 7: Jenkins Pipeline Integration

Aim:
Automate project build and deployment using Jenkins with GitHub.

Tools/Technologies:
Jenkins, GitHub

Procedure:

Installed Jenkins locally.

Set up GitHub webhook for Jenkins.

Created a Jenkins pipeline pulling code from GitHub.

Configured auto-build on GitHub push.

Deployed project after successful build.

Output:
Automated build and deployment completed successfully.

Learning/Conclusion:
Understood CI/CD basics using Jenkins and GitHub integration.





![Screenshot 2025-04-29 121645](https://github.com/user-attachments/assets/22f7e8d3-7527-44ed-92f6-c62497be62b1)



![Screenshot 2025-04-29 121645](https://github.com/user-attachments/assets/82d24474-cf08-46de-9681-d801cf1e0f50)


![Screenshot 2025-04-29 121659](https://github.com/user-attachments/assets/3b6875e9-1a28-4be3-be8f-96e10387a1d2)


![Screenshot 2025-04-29 121713](https://github.com/user-attachments/assets/9b3cd786-3bd0-4ec7-9586-02f26a45c82a)



![Screenshot 2025-04-29 121756](https://github.com/user-attachments/assets/345a2ea1-382b-4574-9868-879ccecd42cf)



![Screenshot 2025-04-29 121818](https://github.com/user-attachments/assets/ad35bc6a-1e3d-4d96-9326-d25c9985967d)



![Screenshot 2025-04-29 121835](https://github.com/user-attachments/assets/7ecc1d40-3ef9-4f0f-b271-9dccaf8ad036)








