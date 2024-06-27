## Learning Outcomes
By the end of this lesson, you will be able to
- Identify in what directory the terminal currently is.
- Nagivate between directories.
- List items within a directory.
- Create and remove files or directories.

---

### Why Learn Basic Terminal Commands?

#### Problem in Development
To use Git, you need to be comfortable navigating your computer's file and folder system using your terminal. Understanding terminal commands allows you to quickly and effectively manage your files without relying solely on graphical interfaces.

#### How Using Basic Terminal Commands Solves the Problem
Basic terminal commands provide a quick and powerful way to navigate and manage your files and folders. They enable you to perform operations such as moving between directories, listing contents, creating and deleting files and directories, and more directly from the command line.

---

### High-Level Overview of Terminal Commands

1. **Navigate Directories**: Move between different folders using commands like `cd`.
2. **List Directory Contents**: View the files and folders within a directory using `ls`.
3. **Create and Remove Files/Directories**: Use commands like `touch`, `mkdir`, `rm`, and `rmdir`.

---

### Navigating Directories

**Command: `cd` (Change Directory)**

- **Purpose**: Moves you to a different directory.
- **Syntax**:
  ```bash
  cd path/to/directory
  ```

- **Examples**:
  ```bash
  cd Documents        # Navigate to the Documents directory
  cd ..               # Move up one directory level
  cd /                # Move to the root directory
  cd ~                # Move to your home directory
  ```

*Explanation*: 
- `cd Documents` moves to the `Documents` folder within the current directory.
- `cd ..` goes up one level in the directory structure.
- `cd /` goes to the root of the file system.
- `cd ~` takes you to your home directory.

---

### Listing Directory Contents

**Command: `ls` (List)**

- **Purpose**: Lists the contents of the current directory.
- **Syntax**:
  ```bash
  ls [options] [path]
  ```

- **Examples**:
  ```bash
  ls                # List files in the current directory
  ls -l             # List files with detailed information
  ls -a             # List all files, including hidden ones
  ls /path/to/dir   # List files in the specified directory
  ```

*Explanation*:
- `ls` displays the names of files and folders in the current directory.
- `ls -l` provides detailed information, such as file permissions, owner, size, and modification date.
- `ls -a` shows all files, including those starting with a dot (hidden files).
- `ls /path/to/dir` lists files in a specific directory.

---

### Creating and Removing Files/Directories

**Command: `touch` (Create File)**

- **Purpose**: Creates an empty file.
- **Syntax**:
  ```bash
  touch filename
  ```

- **Example**:
  ```bash
  touch myfile.txt  # Create an empty file named myfile.txt
  ```

*Explanation*: `touch myfile.txt` creates a new, empty file named `myfile.txt` in the current directory.

**Command: `mkdir` (Make Directory)**

- **Purpose**: Creates a new directory.
- **Syntax**:
  ```bash
  mkdir directoryname
  ```

- **Example**:
  ```bash
  mkdir myfolder    # Create a new directory named myfolder
  ```

*Explanation*: `mkdir myfolder` creates a new directory named `myfolder` in the current directory.

**Command: `rm` (Remove File)**

- **Purpose**: Deletes a file.
- **Syntax**:
  ```bash
  rm filename
  ```

- **Example**:
  ```bash
  rm myfile.txt     # Delete the file named myfile.txt
  ```

*Explanation*: `rm myfile.txt` deletes the file `myfile.txt` from the current directory.

**Command: `rmdir` (Remove Directory)**

- **Purpose**: Deletes an empty directory.
- **Syntax**:
  ```bash
  rmdir directoryname
  ```

- **Example**:
  ```bash
  rmdir myfolder    # Delete the empty directory named myfolder
  ```

*Explanation*: `rmdir myfolder` removes the empty directory `myfolder`. If the directory is not empty, use `rm -r` to remove it and its contents.

---

### Viewing and Managing Files

**Command: `cat` (Concatenate and Display File)**

- **Purpose**: Displays the contents of a file.
- **Syntax**:
  ```bash
  cat filename
  ```

- **Example**:
  ```bash
  cat myfile.txt    # Display the contents of myfile.txt
  ```

*Explanation*: `cat myfile.txt` shows the text inside `myfile.txt`.

**Command: `mv` (Move or Rename File/Directory)**

- **Purpose**: Moves or renames a file or directory.
- **Syntax**:
  ```bash
  mv source destination
  ```

- **Example**:
  ```bash
  mv myfile.txt newfile.txt  # Rename myfile.txt to newfile.txt
  mv myfile.txt /path/to/directory  # Move myfile.txt to another directory
  ```

*Explanation*: 
- `mv myfile.txt newfile.txt` renames `myfile.txt` to `newfile.txt`.
- `mv myfile.txt /path/to/directory` moves `myfile.txt` to a different directory.

**Command: `cp` (Copy File/Directory)**

- **Purpose**: Copies a file or directory.
- **Syntax**:
  ```bash
  cp source destination
  ```

- **Example**:
  ```bash
  cp myfile.txt copyfile.txt    # Copy myfile.txt to copyfile.txt
  cp -r myfolder /path/to/newlocation  # Copy myfolder to another location recursively
  ```

*Explanation*:
- `cp myfile.txt copyfile.txt` copies `myfile.txt` to `copyfile.txt`.
- `cp -r myfolder /path/to/newlocation` copies `myfolder` and its contents to another directory.

---

### Examples of Navigating and Managing Files

**Example 1: Navigating and Listing Contents**
```bash
cd Documents
ls -l
```
*Explanation*: This navigates to the `Documents` directory and lists its contents with detailed information.

**Example 2: Creating and Viewing a File**
```bash
touch notes.txt
echo "Hello, World!" > notes.txt
cat notes.txt
```
*Explanation*: Creates `notes.txt`, writes "Hello, World!" to it, and displays its content.

**Example 3: Moving and Deleting a File**
```bash
mv notes.txt archives/
rm archives/notes.txt
```
*Explanation*: Moves `notes.txt` to the `archives` directory and then deletes it from there.

---

### Troubleshooting Common Issues

1. **Directory Not Found**
   - **Symptom**: `cd: no such file or directory`
   - **Solution**: Ensure the path is correct and that the directory exists. Use `ls` to list directories before navigating.

2. **Permission Denied**
   - **Symptom**: `rm: cannot remove 'file': Permission denied`
   - **Solution**: Use `sudo` for elevated permissions if necessary, but be cautious as it grants higher access rights.

3. **Invalid Command**
   - **Symptom**: `command not found`
   - **Solution**: Verify the command and its syntax. Ensure you’re using the terminal/command prompt correctly.

---

### Key Takeaways

- **Navigate Directories**: Use `cd` to move between directories.
  - **Examples**:
    ```bash
    cd Documents  # Navigate to the Documents directory
    cd ..         # Move up one directory level
    ```

- **List Directory Contents**: Use `ls` to view files in a directory.
  - **Examples**:
    ```bash
    ls            # List files in the current directory
    ls -l         # List files with detailed information
    ```

- **Create and Remove Files/Directories**: Use `touch`, `mkdir`, `rm`, and `rmdir` for file and directory management.
  - **Examples**:
    ```bash
    touch myfile.txt     # Create an empty file
    mkdir myfolder       # Create a new directory
    rm myfile.txt        # Remove a file
    rmdir myfolder       # Remove an empty directory
    ```

- **View and Manage Files**: Use `cat`, `mv`, and `cp` to view and manage files.
  - **Examples**:
    ```bash
    cat myfile.txt       # Display file contents
    mv myfile.txt newfile.txt  # Rename or move a file
    cp myfile.txt copyfile.txt  # Copy a file
    ```
