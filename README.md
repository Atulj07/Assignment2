# Git Assignment Documentation

---

# Question 1: Initialize Git Repository and Push to Remote

## Step 1: Check Git Status

```powershell
git status
```

### Output

```powershell
No commits yet

Untracked files:
    app.py

nothing added to commit but untracked files present
```

---

## Step 2: Add File to Staging Area

```powershell
git add app.py
```

---

## Step 3: Verify Staged Files

```powershell
git status
```

### Output

```powershell
Changes to be committed:
    new file: app.py
```

---

## Step 4: Create Initial Commit

```powershell
git commit -m "First commit"
```

### Output

```powershell
[master (root-commit) d740a3a] First commit
 1 file changed, 1 insertion(+)
 create mode 100644 app.py
```

---

## Step 5: Add Remote Repository

```powershell
git remote add origin https://github.com/Atulj07/Assignment2.git
```

---

## Step 6: Verify Remote Repository

```powershell
git remote -v
```

### Output

```powershell
origin  https://github.com/Atulj07/Assignment2.git (fetch)
origin  https://github.com/Atulj07/Assignment2.git (push)
```

---

## Step 7: Check Current Branch

```powershell
git branch
```

### Output

```powershell
* master
```

---

## Step 8: Push Code to GitHub

```powershell
git push origin master
```

### Output

```powershell
[new branch]      master -> master
```

---
<img width="1440" height="944" alt="Question 1" src="https://github.com/user-attachments/assets/62209754-386e-42b2-bac0-01c13475f170" />

# Question 2: Partial Staging and Multiple Commits

## Step 1: Modify `app.py`

Added multiple print statements:

```python
print("Hello, World!")
print("Hello, Git Project! change 1")
print("Hello, Git Project! change 2")
```

---

## Step 2: Check Modified Files

```powershell
git status
```

### Output

```powershell
modified: app.py
```

---

## Step 3: View Changes

```powershell
git diff
```

---

## Step 4: Perform Partial Staging

```powershell
git add -p app.py
```

### Output

```powershell
Stage this hunk [y,n,q,a,d,e,p,?]? y
```

---

## Step 5: Commit Partial Changes

```powershell
git commit -m "Added second print statement to app.py"
```

### Output

```powershell
[master eb49d63] Added second print statement to app.py
```

---

## Step 6: Verify Remaining Changes

```powershell
git status
```

### Output

```powershell
Changes not staged for commit:
    modified: app.py
```

---

## Step 7: Stage Remaining Changes

```powershell
git add .
```

---

## Step 8: Commit Remaining Changes

```powershell
git commit -m "Added third print statement to app.py"
```

### Output

```powershell
[master 13c6fa8] Added third print statement to app.py
```

---

## Step 9: View Commit History

```powershell
git log --oneline
```

### Output

```powershell
13c6fa8 Added third print statement to app.py
eb49d63 Added second print statement to app.py
d740a3a First commit
```

---

## Step 10: View Detailed Commit Log

```powershell
git log
```

---
<img width="1440" height="902" alt="Question 2A" src="https://github.com/user-attachments/assets/ef76b1fb-11fe-465e-b101-c102e608b6a1" />
<img width="1440" height="902" alt="Question 2B" src="https://github.com/user-attachments/assets/d4dc4aa9-8109-41a7-b92a-791e71647ee3" />


# Question 3: Branching and Merging

## Step 1: Create New Branch

```powershell
git checkout -b feature-update
```

### Output

```powershell
Switched to a new branch 'feature-update'
```

---

## Step 2: Verify Branches

```powershell
git branch
```

### Output

```powershell
* feature-update
  master
```

---

## Step 3: Add Changes in Feature Branch

```powershell
git add .
```

---

## Step 4: Commit Changes

```powershell
git commit -m "Added change 3 in branch feature-update"
```

### Output

```powershell
[feature-update f60d7c4] Added change 3 in branch feature-update
```

---

## Step 5: Switch Back to Master Branch

```powershell
git checkout master
```

---

## Step 6: Merge Feature Branch

```powershell
git merge feature-update
```

### Output

```powershell
Fast-forward
```

---

## Step 7: View Commit History

```powershell
git log --oneline
```

### Output

```powershell
f60d7c4 Added change 3 in branch feature-update
13c6fa8 Added third print statement to app.py
eb49d63 Added second print statement to app.py
d740a3a First commit
```

---

## Step 8: Delete Feature Branch

```powershell
git branch -d feature-update
```

### Output

```powershell
Deleted branch feature-update
```

---
<img width="1440" height="902" alt="Question 3" src="https://github.com/user-attachments/assets/ee71c6ef-8950-4b76-a608-37d6becb4a24" />

# Question 4: Branch Delete Force Operation

## Step 1: Create Dummy Branch

```powershell
git checkout -b dummy-branch
```

### Output

```powershell
Switched to a new branch 'dummy-branch'
```

---

## Step 2: Add Changes

```powershell
git add .
```

---

## Step 3: Commit Changes in Dummy Branch

```powershell
git commit -m "Added change 4 in branch dummy branch"
```

### Output

```powershell
[dummy-branch 83b7817] Added change 4 in branch dummy branch
```

---

## Step 4: Switch Back to Master

```powershell
git checkout master
```

---

## Step 5: Verify Branches

```powershell
git branch
```

### Output

```powershell
dummy-branch
* master
```

---

## Step 6: Try Deleting Branch Normally

```powershell
git branch -d dummy-branch
```

### Output

```powershell
error: the branch 'dummy-branch' is not fully merged
```

---

## Step 7: Force Delete Branch

```powershell
git branch -D dummy-branch
```

### Output

```powershell
Deleted branch dummy-branch
```

---

## Step 8: Verify Remaining Branches

```powershell
git branch
```

### Output

```powershell
* master
```

---

# Final Git Log

```powershell
git log --oneline
```

### Output

```powershell
f60d7c4 Added change 3 in branch feature-update
13c6fa8 Added third print statement to app.py
eb49d63 Added second print statement to app.py
d740a3a First commit
```

---
<img width="1440" height="902" alt="Question 4" src="https://github.com/user-attachments/assets/dd8bd2a2-f7e7-4cb7-bea5-fbad9bdac4d9" />

# Summary of Commands Used

| Command | Purpose |
|---|---|
| `git init` | Initialize Git repository |
| `git add .` | Stage files |
| `git commit -m` | Commit staged changes |
| `git remote add origin` | Add remote repository |
| `git push origin master` | Push code to GitHub |
| `git add -p` | Partial staging |
| `git diff` | View file changes |
| `git log --oneline` | View compact commit history |
| `git checkout -b` | Create and switch branch |
| `git merge` | Merge branches |
| `git branch -d` | Delete merged branch |
| `git branch -D` | Force delete unmerged branch |

---

# Key Learnings

- Git tracks project changes efficiently.
- Partial staging allows selective commits.
- Branching helps isolate development work.
- Merge operations combine branch histories.
- Force delete removes unmerged branches safely when required.
- Git log helps track complete project history.
