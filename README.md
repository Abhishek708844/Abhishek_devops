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




