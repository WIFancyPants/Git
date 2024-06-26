## Learning Outcome
By the end of this lesson, you will be able to 
- Explain the purpose of branches in Git.
- Create, switch, and delete branches.
- View a branch.
- Work with branches in VSCode.

- Create a pull request (adv)
- Pull changes from GitHub. (adv)
- Review and merge a pull request (adv)


---

### Why Use Branches in Git?

#### Problem in Development
Managing multiple features, bug fixes, or experiments in a single codebase can be chaotic, especially when multiple developers are involved. Working on the same main branch can lead to conflicts and instability.

#### How Branches in Git Solve the Problem
Branches allow developers to work on isolated snapshots of the codebase. This enables parallel development, experimentation, and safe integration of new features or fixes without disturbing the main code. Merging branches integrates changes from different branches into a unified codebase, ensuring controlled updates.

---

### High-Level Overview of Branch Operations

1. **Create Branches**: Use `git branch` to create a new branch.
2. **Switch Branches**: Use `git checkout` or `git switch` to move between branches.
3. **Delete Branches**: Use `git branch -d` to remove branches that are no longer needed.
4. **View Branches**: Use `git branch` or `git branch -a` to list branches.
5. **Merge Branches**: Use `git merge` to combine changes from one branch into another.
6. **Resolve Merge Conflicts**: Manually edit conflicting files, then commit the resolved changes.

---

### Detailed Instructions for Branch Operations

#### 1. Creating Branches

**Command: `git branch`**

- **Purpose**: Create a new branch.
- **Syntax**:
  ```bash
  git branch branch_name
  ```

- **Examples**:
  ```bash
  git branch feature-x    # Create a branch named feature-x
  git branch bugfix-101   # Create a branch named bugfix-101
  ```

*Explanation*: `git branch feature-x` creates a new branch named `feature-x` from the current branch's state.

#### 2. Switching Branches

**Command: `git checkout` or `git switch`**

- **Purpose**: Switch to a different branch.
- **Syntax**:
  ```bash
  git checkout branch_name
  ```
  or
  ```bash
  git switch branch_name
  ```

- **Examples**:
  ```bash
  git checkout feature-x  # Switch to feature-x
  git switch bugfix-101   # Switch to bugfix-101
  ```

*Explanation*: `git checkout feature-x` or `git switch feature-x` changes the working directory to the branch `feature-x`.

#### 3. Deleting Branches

**Command: `git branch -d`**

- **Purpose**: Delete a branch.
- **Syntax**:
  ```bash
  git branch -d branch_name
  ```

- **Examples**:
  ```bash
  git branch -d feature-x    # Delete the branch feature-x
  git branch -D bugfix-101   # Force delete the branch bugfix-101
  ```

*Explanation*: `git branch -d feature-x` deletes the `feature-x` branch if it has been fully merged. `-D` forces deletion.

#### 4. Viewing Branches

**Command: `git branch`**

- **Purpose**: List all branches.
- **Syntax**:
  ```bash
  git branch
  ```

- **Examples**:
  ```bash
  git branch         # List local branches
  git branch -a      # List all branches, including remote-tracking branches
  ```

*Explanation*: `git branch` shows all local branches and highlights the current one. `git branch -a` lists both local and remote branches.

#### 5. Merging Branches

**Command: `git merge`**

- **Purpose**: Merge changes from one branch into another.
- **Syntax**:
  ```bash
  git merge branch_name
  ```

- **Examples**:
  ```bash
  git checkout main
  git merge feature-x    # Merge feature-x into main
  ```

*Explanation*: 
- `git checkout main` switches to the `main` branch.
- `git merge feature-x` merges the changes from `feature-x` into `main`.

#### 6. Resolving Merge Conflicts

**Scenario**: A merge conflict occurs when changes in different branches affect the same lines in a file, and Git cannot automatically merge them.

**Steps to Resolve**:

1. **Identify Conflicts**:
   - Run `git status` to see conflicting files.
   - Open the conflicting files; conflicts are marked within `<<<<<<<`, `=======`, and `>>>>>>>` sections.

2. **Edit and Resolve Conflicts**:
   - Manually edit the file to resolve conflicts.
   - Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).

3. **Add and Commit Resolved Changes**:
   - Use `git add` to stage the resolved file.
   - Commit the changes to finalize the merge.

**Example**:
```bash
# Edit the conflicting file(s) to resolve conflicts
git add resolved_file.txt
git commit -m "Resolved merge conflict in resolved_file.txt"
```

---

### 4. Examples of Branch Operations

**Example 1: Creating and Switching Branches**
```bash
git branch feature-new-ui
git checkout feature-new-ui
```
*Explanation*: Creates a new branch `feature-new-ui` and switches to it.

**Example 2: Merging Branches**
```bash
git checkout main
git merge feature-new-ui
```
*Explanation*: Switches to the `main` branch and merges the changes from `feature-new-ui` into `main`.

**Example 3: Deleting a Branch**
```bash
git branch -d feature-new-ui
```
*Explanation*: Deletes the branch `feature-new-ui` after its changes have been merged or are no longer needed.

---

### 5. Troubleshooting Common Issues

1. **Merge Conflicts**:
   - **Symptom**: Conflicts occur during `git merge`.
   - **Solution**: Resolve conflicts by manually editing the conflicting files, then stage and commit the resolved files.

2. **Branch Not Found**:
   - **Symptom**: Error stating branch does not exist when switching.
   - **Solution**: Ensure the branch name is correct and that the branch exists. Use `git branch` to list available branches.

3. **Unmerged Changes**:
   - **Symptom**: Error when trying to delete a branch with unmerged changes.
   - **Solution**: Force delete with `-D` if sure, or merge the branch first.

---

### Key Takeaways

- **Create Branches**: Use `git branch branch_name` to create a new branch.
  - **Example**:
    ```bash
    git branch feature-x
    ```

- **Switch Branches**: Use `git checkout branch_name` or `git switch branch_name` to switch branches.
  - **Example**:
    ```bash
    git checkout feature-x
    git switch feature-x
    ```

- **Delete Branches**: Use `git branch -d branch_name` to delete a branch.
  - **Example**:
    ```bash
    git branch -d feature-x
    ```

- **View Branches**: Use `git branch` to list branches.
  - **Example**:
    ```bash
    git branch
    git branch -a
    ```

- **Merge Branches**: Use `git merge branch_name` to merge branches.
  - **Example**:
    ```bash
    git checkout main
    git merge feature-x
    ```

- **Resolve Merge Conflicts**: Manually edit conflicting files, stage the resolved files, and commit.
  - **Example**:
    ```bash
    git add resolved_file.txt
    git commit -m "Resolved merge conflict in resolved_file.txt"
    ```

Understanding and managing branches effectively in Git is crucial for maintaining a clean and organized codebase, especially in collaborative environments. This knowledge ensures smooth feature development, bug fixing, and integration processes.
