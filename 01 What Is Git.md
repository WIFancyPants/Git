## Learning Outcomes
By the end of this lesson, you will be able to
- Explore the purpose of Git
- Define a repository.
- Explain the basic workflow of Git, such as pull, stage, and commit.
- Differentiate between Git and GitHub.

---
### What Problem Does Git Solve? 

You make a lot of changes to your code as you develop. How do you keep track of them? What if you want to revert back to an older version of your project? Git allows you to do that.

**Git** is a free, open-source tool used for tracking changes in files. This is incredibly useful as you need to see change history and is critical collaborating with other developers on the same project. It is essential in software development for managing different versions of a codebase, allowing developers to work on features, fix bugs, and merge contributions seamlessly.

For now, you will use Git to manage versions and track your code's history.

---
### Basic Parts of Git

1. **Repository (Repo)**: A repository is the core structure where your project's files and their history are stored. It contains all versions of your files and the history of changes made to them. A repository can be **local** on your machine and/or **remote**, hosted on a server, so you can access it from any computer connected to the internet. It's kinda like how you can choose to work "offline" on some Google Drive documents: you can make changes on your local machine, and once it's connected back to the internet, it will sync those changes up to the Drive.

2. **Commit**: A commit is like a snapshot of your project at a given point in time. It records changes to the files in your repository and allows you to go back to any previous state if needed.

---
### How to Save Your Commits and Update your Repository?

Since Git is designed to protect you from accidently losing some of your code when you update, it requires a few steps to "save" your changes:

1. **Pull** updates from the remote repository to get the latest project state.
2. You make some changes to the code.
3. **Stage** changes to prepare them for a commit.
4. **Commit** changes to save a snapshot of the project.
5. **Push** changes to share them with the remote repository.

**Example Workflow**:
```bash
git pull origin main        # Update local repository
# Make changes to your files
git add .                   # Stage changes
git commit -m "Add new feature"  # Commit changes with a message
git push origin main        # Share changes with the remote repository
```
### Details of Each Part of Git Workflow

**1. Pulling Changes**
Pulling is the process of updating your local repository with changes from a remote repository. This ensures that you have the latest version of the project before you start making new changes.

- **High-Level View**: Fetch updates from the shared project repository and integrate them into your local work.
- **How It Works**: When you pull, Git combines new changes from the remote repository into your local copy.

  ```bash
  git pull origin main
  ```
  *This command fetches and integrates updates from the remote `main` branch.*

**2. Staging Changes**
Staging involves selecting changes in your local files to be included in the next commit. It's like preparing specific modifications to be recorded, while other changes remain uncommitted.

- **High-Level View**: Choose which changes to include in the next snapshot of your project.
- **How It Works**: You use the `git add` command to mark files for inclusion in the upcoming commit.

  ```bash
  git add filename
  ```
  *To stage all changes:*
  ```bash
  git add .
  ```
  *These commands stage the specified file(s) or all changes.*

**3. Committing Changes**
Committing captures the current state of your staged changes and saves it to the repository's history. Each commit represents a point you can revert to or reference in the future.

- **High-Level View**: Save a snapshot of your selected changes with a description of what was done.
- **How It Works**: When you commit, Git takes the staged changes and records them in the repository with a message.

  ```bash
  git commit -m "Describe your changes here"
  ```
  *This command commits the staged changes with a descriptive message.*

**4. Pushing Changes**
Pushing sends your committed changes to a remote repository so others can see and incorporate your work.

- **High-Level View**: Share your changes with the central project repository for others to use.
- **How It Works**: The `git push` command uploads your local commits to the remote repository.

  ```bash
  git push origin main
  ```
  *This command pushes your changes to the remote `main` branch.*

#### Key Points

- **Repository**: The storage for project files and their history.
- **Commit**: A snapshot of the project at a given time.
- **Branch**: A separate line of development.
- **Pull**: Fetch and integrate updates from a remote repository.
- **Stage**: Prepare changes to be recorded.
- **Push**: Upload changes to a remote repository.

**Git** provides a robust framework for managing changes, collaborating with others, and maintaining a reliable project history. This workflow ensures that you can work efficiently, avoid conflicts, and keep a clear record of your project’s evolution.
