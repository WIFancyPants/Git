## Learning Outcome
By the end of this lesson, you will be able to 
- Undo changes in the working directory.
- Revert a commit.
- Explain the difference between `git reset` and `git revert.`

---

### Why Undo Changes in Git?

#### Problem in Development
Making mistakes or unwanted changes in a codebase is inevitable. Without proper tools, undoing these changes can be error-prone and cumbersome, leading to lost work or further issues.

#### How Git’s Undo Features Solve the Problem
Git provides several commands to undo changes at various stages of the development process. These commands help developers efficiently manage and correct mistakes, ensuring that the codebase remains stable and clean.

---

### High-Level Overview of Undoing Changes

1. **Undo Changes in the Working Directory**: Use `git restore` or `git checkout` to discard changes in the working directory.
2. **Revert a Commit**: Use `git revert` to create a new commit that undoes the changes introduced by a previous commit.
3. **Difference Between `git reset` and `git revert`**: 
   - `git reset` changes the commit history and can affect other branches.
   - `git revert` creates a new commit to negate a previous commit, preserving the commit history.

---

### Detailed Instructions for Undoing Changes

#### 1. Undoing Changes in the Working Directory

**Command: `git restore` or `git checkout`**

- **Purpose**: Discard changes in the working directory.
- **Syntax**:
  ```bash
  git restore filename
  git restore --staged filename
  ```
  or
  ```bash
  git checkout -- filename
  ```

- **Examples**:
  ```bash
  git restore index.html       # Discard changes in index.html
  git restore --staged script.js  # Unstage changes in script.js
  git checkout -- style.css     # Old method to discard changes in style.css
  ```

*Explanation*: 
- `git restore index.html` reverts `index.html` to its state in the last commit.
- `git restore --staged script.js` unstages `script.js` but leaves the changes in the working directory.

**Visual Example**:
```bash
# Changes before undoing
echo "New text" >> index.html
# Undo changes
git restore index.html
```
*Explanation*: Appends "New text" to `index.html` and then discards that change using `git restore`.

#### 2. Reverting a Commit

**Command: `git revert`**

- **Purpose**: Create a new commit that undoes the changes from a previous commit.
- **Syntax**:
  ```bash
  git revert commit_hash
  ```

- **Examples**:
  ```bash
  git revert abc1234     # Revert the commit with hash abc1234
  ```

*Explanation*:
- `git revert abc1234` creates a new commit that negates the changes introduced by the commit `abc1234`.

**Visual Example**:
```bash
git revert abc1234
```
*Explanation*: If `abc1234` added a new feature, this command creates a new commit that removes that feature.

#### 3. Explaining the Difference Between `git reset` and `git revert`

**`git reset`**:
- **Purpose**: Undo changes by resetting the current branch to a specified state, potentially modifying commit history.
- **Syntax**:
  ```bash
  git reset [--soft | --mixed | --hard] commit_hash
  ```

- **Examples**:
  ```bash
  git reset --soft HEAD~1  # Move HEAD back one commit, keep changes staged
  git reset --mixed HEAD~1 # Move HEAD back one commit, unstage changes
  git reset --hard HEAD~1  # Move HEAD back one commit, discard all changes
  ```

**Explanation**:
- `--soft`: Moves the current branch pointer and keeps all changes staged.
- `--mixed` (default): Moves the current branch pointer and unstages changes.
- `--hard`: Moves the current branch pointer and discards all changes in the working directory and index.

**Visual Example**:
```bash
# Changes before resetting
echo "Feature X" >> feature.txt
git add feature.txt
git commit -m "Add feature X"
# Reset changes
git reset --hard HEAD~1
```
*Explanation*: Adds and commits "Feature X" to `feature.txt`, then discards this commit using `git reset --hard`.

**`git revert`**:
- **Purpose**: Safely undo a commit by creating a new commit that reverses its changes, preserving the commit history.
- **Syntax**:
  ```bash
  git revert commit_hash
  ```

- **Example**:
  ```bash
  git revert abc1234     # Create a new commit to reverse changes from abc1234
  ```

**Comparison**:
- **`git reset`** modifies the commit history, potentially causing issues in collaborative projects or shared branches.
- **`git revert`** is safer in shared projects as it does not alter the commit history but rather adds a new commit that undoes a previous commit.

**Visual Comparison**:

- **Before `git reset`**:
  ```bash
  Commit A - Commit B (HEAD)
  ```

- **After `git reset --hard HEAD~1`**:
  ```bash
  Commit A (HEAD)
  ```

- **Before `git revert`**:
  ```bash
  Commit A - Commit B (HEAD)
  ```

- **After `git revert B`**:
  ```bash
  Commit A - Commit B - Revert Commit B (HEAD)
  ```

---

### 4. Examples of Undoing Changes

**Example 1: Undoing Changes in the Working Directory**
```bash
# Modify a file
echo "Temp change" >> temp.txt
# Undo changes
git restore temp.txt
```
*Explanation*: Appends "Temp change" to `temp.txt`, then discards the changes using `git restore`.

**Example 2: Reverting a Commit**
```bash
git revert abc1234
```
*Explanation*: Reverts the commit `abc1234` by creating a new commit that negates its changes.

**Example 3: Using `git reset`**
```bash
# Stage and commit a change
echo "Change" >> change.txt
git add change.txt
git commit -m "Make change"
# Undo the commit
git reset --hard HEAD~1
```
*Explanation*: Commits a change to `change.txt`, then discards this commit using `git reset --hard`.

---

### 5. Troubleshooting Common Issues

1. **Unintended Reset**:
   - **Symptom**: Changes are lost after `git reset`.
   - **Solution**: Use `git reflog` to find the commit hash and recover changes by resetting back to the commit.

2. **Merge Conflicts in Revert**:
   - **Symptom**: Revert causes merge conflicts.
   - **Solution**: Manually resolve conflicts, then stage and commit the resolved files.

3. **Failed Restore**:
   - **Symptom**: `git restore` fails to discard changes.
   - **Solution**: Ensure the file is not staged or already committed. Use `git checkout -- filename` for older versions of Git.

---

### Key Takeaways

- **Undo Changes in Working Directory**: Use `git restore` or `git checkout` to discard changes.
  - **Example**:
    ```bash
    git restore index.html
    git checkout -- style.css
    ```

- **Revert a Commit**: Use `git revert commit_hash` to create a new commit that undoes the changes from a previous commit.
  - **Example**:
    ```bash
    git revert abc1234
    ```

- **Difference Between `git reset` and `git revert`**:
  - **`git reset`**: Changes commit history and can affect other branches.
  - **`git revert`**: Creates a new commit that reverses changes from a previous commit, preserving the commit history.
  
- **Pull Repository**: Use `git pull` to update your local repository from the remote repository.
  - **Example**:
    ```bash
    git pull origin main
    ```

Understanding and using these Git commands effectively will allow you to manage and correct changes in your codebase, maintaining a clean and accurate history.
