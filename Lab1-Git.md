### **Lab 1: Website Version Control with Git & GitHub**

---

#### **I. Objectives**

1. Understand how to manage source code using Git and GitHub.
2. Perform basic Git operations: initialize repositories, commit changes, work with branches, and handle conflicts. Alain Test
3. Create and manage repositories on GitHub to synchronize code between local and remote repositories.
4. Practice resolving merge conflicts effectively.

---

#### **II. Introduction to Git and GitHub**

- **Git**: A distributed version control system to track and manage changes in source code.
- **GitHub**: A web-based platform for hosting and sharing code repositories, enabling collaboration and version control in teams.

In this lab, we will manage the source code of a sample website stored in a folder named *`inance`*. This folder contains HTML, CSS files, and images. Our goal is to set up version control with Git, synchronize with GitHub, and practice various Git operations.

---

#### **III. Prerequisites**

- Install **Visual Studio Code (VS Code)** for editing HTML files.
- Install Git on your machine (Windows/macOS/Linux).

---

### **1. Setting Up Git on Your System**

1. **Install Git**
   
   - Visit [Git Official Website](https://git-scm.com/download/win) and download the Git installer for your operating system.
   - Run the installer and accept the default settings.

2. **Configure Git**  
   Open **Command Prompt** or **PowerShell**, and configure your username and email with the following commands:
   
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your_email@example.com"
   ```
   
   Verify your configuration:
   
   ```bash
   git config --list
   ```

---

### **2. Initializing a Local Repository**

1. Identify the project directory:  
   Ensure the folder *`inance`* exists on your machine with the website's source code.

2. Open a terminal, navigate to the folder:
   
   ```bash
   cd path_to_inance_directory
   ```

3. Initialize a Git repository:
   
   ```bash
   git init
   ```
   
   - This creates a hidden `.git` directory where Git stores version history.

4. Check the repository status:
   
   ```bash
   git status
   ```
   
   - Displays files that are untracked or modified.

---

### **3. Adding Files and Creating the First Commit**

1. Add files to the staging area:
   
   ```bash
   git add .
   ```

2. Create the first commit with a message:
   
   ```bash
   git commit -m "Initial commit: add website source code"
   ```

3. View the commit history:
   
   ```bash
   git log --oneline
   ```

---

### **4. Connecting the Local Repository to GitHub**

1. Log in to GitHub and create a new repository:
   
   - Go to [GitHub](https://github.com/), click **New Repository**, and name it (e.g., `website-template`).
   - Select **Public** or **Private** and click **Create Repository**.

2. Connect the local repository to GitHub:
   
   ```bash
   git remote add origin <repository_URL>
   ```
   
   Replace `<repository_URL>` with the URL of your GitHub repository.

3. Push the code to GitHub:
   
   ```bash
   git branch -M main
   git push -u origin main
   ```

---

### **5. Working with Branches**

1. Create a new branch and switch to it:
   
   ```bash
   git checkout -b dev
   ```

2. Make changes using VS Code:
   
   - Open the folder *`inance`* in **VS Code**.
   - Open `index.html`, add or edit content (e.g., add `<h1>Welcome to Inance</h1>` in the body section).
   - Save your changes (`Ctrl + S`).

3. Stage the modified file:
   
   ```bash
   git add index.html
   ```

4. Commit the changes:
   
   ```bash
   git commit -m "Update homepage title"
   ```

5. Push the `dev` branch to GitHub:
   
   ```bash
   git push origin dev
   ```

---

### **6. Merging Branches**

1. Switch back to the `main` branch:
   
   ```bash
   git checkout main
   ```

2. Update the `main` branch:
   
   ```bash
   git pull origin main
   ```

3. Merge the `dev` branch into `main`:
   
   ```bash
   git merge dev
   ```

4. Push the updated `main` branch:
   
   ```bash
   git push origin main
   ```

---

### **7. Resolving Merge Conflicts**

1. Create a conflict:
   
   - On the `main` branch, edit `index.html` and update the title (e.g., "Home Page"). Commit and push the changes:
     
     ```bash
     git add index.html
     git commit -m "Update title on main branch"
     git push origin main
     ```
   
   - On the `dev` branch, edit the same section of `index.html` with a different change (e.g., "Welcome Page"). Commit the changes:
     
     ```bash
     git add index.html
     git commit -m "Update title on dev branch"
     ```

2. Merge the `dev` branch into `main`:
   
   ```bash
   git checkout main
   git pull origin main
   git merge dev
   ```

3. Resolve the conflict:
   
   - Open `index.html` in VS Code, find the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`), and manually edit the file to keep the desired changes.
   
   - Save the file and stage it:
     
     ```bash
     git add index.html
     git commit -m "Resolve merge conflict in index.html"
     git push origin main
     ```

---

### **8. Practice Exercise**

1. **Add a "Contact Us" Page**:
   
   - Open VS Code and create a new file `contact.html` in the *`inance`* folder.
   
   - Add the following content:
     
     ```html
     <html>
     <head><title>Contact Us</title></head>
     <body>
        <h1>Contact Us</h1>
        <p>Email: support@inance.com</p>
     </body>
     </html>
     ```
   
   - Stage and commit the file:
     
     ```bash
     git add contact.html
     git commit -m "Add Contact Us page"
     git push origin dev
     ```

2. **Create and Resolve a Conflict in `contact.html`:**
   
   - Repeat the steps from Section 7 to introduce and resolve a conflict in `contact.html`.

3. **Create a Feature Branch**:
   
   - Create a new branch `feature` to add a new section to the website. Merge this branch into `main` after completing the changes.

---

#### **IV. Summary and Review**

- **Completion Criteria**:  
  Successfully push the website's source code to GitHub, resolve conflicts, and manage branches effectively.

- **Review Questions**:
  
  1. What are the advantages of using Git branches?
  2. How can you undo a committed change that was pushed to the remote repository?

This concludes Lab 1. Practice extensively and explore additional Git commands to enhance your skills!
