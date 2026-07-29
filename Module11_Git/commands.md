# Module 11 - Version Control with GIT

This guide lists the Git command workflows for **GIT Hands-On Labs (HOL 1 to 5)**. 

* **Developer:** Guna Byraju
* **Email:** gunavardhan779@gmail.com
* **Git Repository:** https://github.com/Guna42/Cognizant-

---

## 💻 GIT HOL 1: Git Installation & Configuration

### Step 1: Verify Git Client & User Configuration
Open **Git Bash** (or terminal) and execute the following commands:

1. **Verify Git Installation:**
   ```bash
   git --version
   ```
   *Expected Output:* `git version 2.x.x`

2. **Configure Global User Name & Email:**
   ```bash
   git config --global user.name "Guna Byraju"
   git config --global user.email "gunavardhan779@gmail.com"
   ```

3. **Verify Global Configurations:**
   ```bash
   git config --list
   ```
   *Verify that `user.name=Guna Byraju` and `user.email=gunavardhan779@gmail.com` are present.*

### Step 2: Configure Notepad++ as default Editor
To integrate Notepad++ as your default Git editor:

1. **Configure Editor Path (depending on architecture):**
   *For 64-bit Notepad++ (Default):*
   ```bash
   git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"
   ```
   *For 32-bit Notepad++:*
   ```bash
   git config --global core.editor "'C:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"
   ```

2. **Create Alias Command in Git Bash:**
   Edit your bash profile configuration file (`~/.bashrc` or `~/.bash_profile`) to add an alias:
   ```bash
   alias npp="'C:/Program Files/Notepad++/notepad++.exe'"
   ```
   Reload the profile shell:
   ```bash
   source ~/.bashrc
   ```
   You can now launch Notepad++ directly using:
   ```bash
   npp test.txt
   ```

---

## 🚫 GIT HOL 2: Git Ignore Rules (`.gitignore`)

Configure Git to ignore log extensions (`*.log`) and the log directory (`log/`):

1. **Verify the local [.gitignore](.gitignore) content:**
   ```text
   # Git HOL 2: Ignore .log files and log folders
   *.log
   log/
   ```

2. **Create log files and folder to test:**
   ```bash
   mkdir log
   touch app.log log/debug.log info.txt
   ```

3. **Verify status of ignored files:**
   ```bash
   git status
   ```
   *Expected Output: Only `info.txt` and `.gitignore` will be shown as untracked. The `.log` files and `log/` folder will be ignored by Git.*

---

## 🌿 GIT HOL 3: Branching & Merging

1. **Verify master is in clean state:**
   ```bash
   git status
   ```

2. **Create a new branch:**
   ```bash
   git branch GitNewBranch
   ```

3. **List all branches (observe `*` denoting current branch):**
   ```bash
   git branch -a
   ```

4. **Switch to the newly created branch:**
   ```bash
   git checkout GitNewBranch
   ```

5. **Create a file and commit inside the branch:**
   ```bash
   echo "This file was created in GitNewBranch by Guna Byraju" > info.txt
   git add info.txt
   git commit -m "Add info.txt in GitNewBranch"
   ```

6. **Switch back to main (or master):**
   ```bash
   git checkout main
   ```

7. **Compare differences between main and the branch:**
   ```bash
   git diff main GitNewBranch
   ```

8. **Merge the branch into main:**
   ```bash
   git merge GitNewBranch
   ```

9. **View commit history graph decorated:**
   ```bash
   git log --oneline --graph --decorate --all
   ```

10. **Delete the merged branch:**
    ```bash
    git branch -d GitNewBranch
    ```

---

## ⚔️ GIT HOL 4: Conflict Resolution

1. **Create and switch to branch `GitWork`:**
   ```bash
   git checkout -b GitWork
   ```

2. **Create `hello.xml` on `GitWork` and commit:**
   ```bash
   echo "<greeting>Hello from GitWork branch - Guna Byraju</greeting>" > hello.xml
   git add hello.xml
   git commit -m "Add hello.xml on GitWork"
   ```

3. **Switch back to `main`:**
   ```bash
   git checkout main
   ```

4. **Create `hello.xml` on `main` with different contents and commit:**
   ```bash
   echo "<greeting>Hello from main branch - Guna Byraju</greeting>" > hello.xml
   git add hello.xml
   git commit -m "Add hello.xml on main"
   ```

5. **Observe branch divergence in logs:**
   ```bash
   git log --oneline --graph --decorate --all
   ```

6. **Attempt to merge `GitWork` (this will trigger a MERGE CONFLICT):**
   ```bash
   git merge GitWork
   ```
   *Terminal Output:*
   ```text
   Auto-merging hello.xml
   CONFLICT (content): Merge conflict in hello.xml
   Automatic merge failed; fix conflicts and then commit the result.
   ```

7. **Resolve Conflict inside `hello.xml`:**
   Open `hello.xml` in your editor. You will see conflict markers:
   ```xml
   <<<<<<< HEAD
   <greeting>Hello from main branch - Guna Byraju</greeting>
   =======
   <greeting>Hello from GitWork branch - Guna Byraju</greeting>
   >>>>>>> GitWork
   ```
   Clean up the file to keep the desired result (e.g., combine them):
   ```xml
   <greeting>Hello from Guna Byraju (Combined Main & GitWork)</greeting>
   ```

8. **Stage and Commit resolved conflict:**
   ```bash
   git add hello.xml
   git commit -m "Resolve merge conflict in hello.xml"
   ```

9. **Add backup files to .gitignore if created by merge tools (like `*.orig` files):**
   ```bash
   echo "*.orig" >> .gitignore
   git add .gitignore
   git commit -m "Ignore merge backup files"
   ```

10. **Delete merged branch and observe logs:**
    ```bash
    git branch -d GitWork
    git log --oneline --graph --decorate
    ```

---

## 🌐 GIT HOL 5: Remote Repositories Operations

1. **Verify your remote URL config:**
   ```bash
   git remote -v
   ```

2. **Pull the latest remote repository changes to sync:**
   ```bash
   git pull origin main
   ```

3. **Push all pending changes to the GitHub remote repository:**
   ```bash
   git push origin main
   ```

4. **Check GitHub repository dashboard online to verify changes have reflected.**
