## 🚀 Git Commands & Setup Notes

---

### 🔧 Initial Project Setup

- `git init` — Initialize a new Git repository  
- `git add .` — Stage all changes in the directory  
- `git commit -m "first commit"` — Commit changes with a message  
- `git branch -M main` — Rename the current branch to `main`  
- `git remote add origin <repo-url>` — Link local repo to GitHub  
- `git push -u origin main` — Push code and set upstream  

---

### 🌿 Branch Management

- `git branch` — List all branches  
- `git branch name` — Create a new branch  
- `git checkout name` — Switch to a specific branch  
- `git branch -d name` — Delete a branch  
- `git checkout -b name-branch` — Create and switch to a new branch  
- `git push origin name-branch` — Push new branch to remote  

---

### 🌐 Remote Management

- `git remote -v` — Show remote URL(s)  
- `git branch -m main` — Rename current branch to `main`  
- `git remote set-url origin <new-url>` — Change the GitHub remote URL  
- `git remote -v` — Confirm updated remote URL  
- `git push` — Push committed changes to the remote repository  

---

## 🌍 Open Source Contribution Guide (GitHub)

---

### ✅ Step 1: Fork the Repository

### ✅ Step 2: Clone & Setup Locally

### ✅ Step 3: Create a Feature Branch & Push Changes

- `git checkout -b feature-branch-name`  
- `git add .`  
- `git commit -am "✨ Added feature XYZ"`  
- `git push origin feature-branch-name ` 

### ✅ Step 4: Create a Pull Request

- `Go to your forked repo on GitHub`
- `Click Compare & Pull Request`
- `Add a clear title and description`
- `Submit PR to the original repository’s main branch`

### ✅ Step 5: Sync Your Fork (Optional but Recommended)

- `git remote add upstream https://github.com/ORIGINAL_OWNER/quiz-hero.git  `
- `git fetch upstream  `
- `git pull upstream main ` 
- `git push origin main  `
