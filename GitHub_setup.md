# Git & GitHub Setup Guide

Follow these steps to set up Git and connect your project with GitHub using Visual Studio Code.

---

## **1. Download Git**

- Visit the official Git website:  
```
https://git-scm.com/downloads
```
- Download and install Git for your operating system.

---

## **2. Create a GitHub Account**

- Visit :
```
    https://github.com/
```
- Sign up and create your GitHub account.

---

## **3. Create a GitHub Repository**

After signing in to GitHub:
- Click on the **+** icon (top right).
- Select **New Repository**.
- Give it a name (e.g., `my-project`).
- Click **Create Repository**.

---

## **4. Create a Local Project Folder**

- On your PC, create a folder with the **same name** as your GitHub repository.
  - Example: If your repository is `my-project`, then your folder should also be `my-project`.

---

## **5. Connect VS Code with GitHub Repository**

- Open the folder in **Visual Studio Code**.
- Open the **Terminal** in VS Code (`Ctrl + J`).
- Copy & paste the GitHub-provided command lines (after you create the repository) **one by one** into the terminal.
  - Example:
    ```bash
    git init
    git add .
    git commit -m "first commit"
    git branch -M main
    git remote add origin https://github.com/yourusername/your-repo-name.git
    git push -u origin main
    ```

---

## **6. One-Time Git Configuration**

- The **first time** you run Git commands, it may show an error and prompt for your GitHub **Username** and **Email**.
  - Enter the same credentials you used to create the GitHub account.

```bash
git config --global user.name "Your GitHub Username"
git config --global user.email "youremail@example.com"
```

----

### ✅GitHub is now ready to use with VS Code!

---