# **Git & GitHub – Beginner’s Guide (Python Project Example)**

---

## **1\. What is Git?**

Git is a **tool** that tracks changes in your code so you can go back in time, work with others, and manage versions easily.

Think of it as a **time machine for code**.

---

## **2\. What is GitHub?**

GitHub is a **website** where you can store Git repositories online and collaborate with others.

---

## **3\. Basic Git Commands**

| Command | Meaning |
| ----- | ----- |
| `git init` | Create a Git repository in the folder |
| `git add .` | Stage all changes for commit |
| `git commit -m "message"` | Save changes with a message |
| `git status` | See the current status of changes |
| `git log` | View commit history |
| `git remote add origin <url>` | Link local repo to GitHub |
| `git push -u origin main` | Upload to GitHub |
| `git pull` | Download latest changes |

---

## **4\. Project Folder Structure**

Example **Python Project**:

my-python-project/  
│  
├── main.py  
├── requirements.txt  
├── .env  
├── .gitignore  
└── README.md

---

### **main.py**

import os

\# Load environment variables  
API\_KEY \= os.getenv("API\_KEY")

def main():  
    print("Hello, Git & GitHub\!")  
    print(f"Your API Key is: {API\_KEY}")

if \_\_name\_\_ \== "\_\_main\_\_":  
    main()

---

### **.env**

*(Stores sensitive info – never commit to GitHub)*

API\_KEY=123456abcdef

---

### **.gitignore**

*(Tells Git which files to ignore)*

\# Python cache files  
\_\_pycache\_\_/  
\*.pyc

\# Virtual environment  
venv/

\# Environment variables  
.env

---

## **5\. Step-by-Step Workflow**

1️⃣ **Initialize Git**

git init

2️⃣ **Add files to staging**

git add .

3️⃣ **Commit changes**

git commit \-m "Initial commit"

4️⃣ **Create GitHub Repo** (on github.com)

5️⃣ **Connect Local Repo to GitHub**

git remote add origin https://github.com/username/my-python-project.git  
git branch \-M main  
git push \-u origin main

6️⃣ **Update Project Later**

git add .  
git commit \-m "Updated main.py"  
git push

---

## **Best Practices**

✅ Never commit `.env` or other sensitive files  
 ✅ Commit often with clear messages  
 ✅ Pull before pushing changes when working in teams  
 ✅ Use `.gitignore` to keep repo clean

---

## **1\. What Happens If You Don’t Follow Best Practices?**

| Best Practice | What Happens If You Ignore It? |
| ----- | ----- |
| **Never commit `.env` or sensitive files** | Your API keys, passwords, or private data could become **public** — anyone can misuse them. Even in private repos, teammates may accidentally expose them later.  |
| **Commit often with clear messages** | You won’t know what changes were made when — making debugging and rollback difficult. |
| **Pull before pushing** | If someone else pushed changes, your push might be rejected, causing **merge conflicts** that are hard to fix. |
| **Use `.gitignore`** | Your repo will get filled with unnecessary files (e.g., logs, temporary files, large datasets), making it slower and messy. |

⚠️ **Real risk**: Forgetting `.gitignore` \+ `.env` has caused actual companies to leak database credentials publicly.

---

## 

## 

## **2\. How to Create a Branch and Merge into `main`**

We’ll pretend you’re adding a new feature to `main.py`.

---

### **Step 1 – Create a New Branch**

\# Create branch named 'feature-welcome'

git branch feature-welcome

\# Switch to that branch

git checkout feature-welcome

*(Shortcut: `git checkout -b feature-welcome` creates \+ switches in one command)*

---

### **Step 2 – Make Changes**

In `main.py`:

def welcome\_user(name):

    return f"Welcome, {name}\!"

if \_\_name\_\_ \== "\_\_main\_\_":

    print(welcome\_user("Ostad"))

---

### **Step 3 – Commit Changes**

git add main.py

git commit \-m "Added welcome\_user function"

---

### **Step 4 – Merge Back to `main`**

\# Switch to main branch

git checkout main

\# Merge the feature branch into main

git merge feature-welcome

---

### **Step 5 – Push Changes to GitHub**

git push origin main

---

### **Step 6 – Delete the Branch (Optional)**

git branch \-d feature-welcome

***Additional Resource***: [https://www.w3schools.com/git/](https://www.w3schools.com/git/) 

