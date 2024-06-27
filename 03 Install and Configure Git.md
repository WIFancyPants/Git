## Learning Outcomes
By the end of this lesson, you should be able to:
- Install Git on their local machine and verify the installation.
- Configure Git with a username and email address.

---

### Why Install and Configure Git?

#### Problem in Development
To effectively use Git for version control and collaboration, it must be installed on your local machine. Additionally, configuring Git with your username and email address is crucial for identifying your contributions to projects and enabling seamless collaboration.

#### How Installing and Configuring Git Solves the Problem
Installing Git provides the tools necessary to manage code versions locally. Configuring Git with your identity ensures that all your commits are associated with you, making it easier to track changes and collaborate with others.

---

### High-Level Steps to Install and Configure Git

1. **Download Git**: Obtain the Git installer from the official Git website or your system's package manager.
2. **Run the Installer**: Execute the downloaded installer and follow the prompts to complete the installation.
3. **Verify the Installation**: Ensure Git is installed correctly by running a command in your terminal or command prompt.
4. **Configure Git**: Set up your username and email address to identify your contributions.

---

### Detailed Installation and Configuration Instructions

#### Windows

1. **Download the Installer**
   - Visit the [Git for Windows](https://gitforwindows.org/) website.
   - Click the “Download” button to get the latest version of the Git installer.

2. **Run the Installer**
   - Locate the downloaded `.exe` file and double-click it.
   - Follow the setup prompts:
     - **Choose components**: Keep the default options, including Git Bash and Git GUI.
     - **Adjust your PATH environment**: Select “Git from the command line and also from 3rd-party software” for command line access.

3. **Verify the Installation**
   - Open Command Prompt.
   - Run the following command:
     ```bash
     git --version
     ```
   - If Git is installed correctly, you’ll see the version number, e.g., `git version 2.x.x`.

4. **Configure Git**
   - Open Command Prompt.
   - Set your username and email:
     ```bash
     git config --global user.name "Your Name"
     git config --global user.email "your.email@example.com"
     ```
   - Verify the configuration:
     ```bash
     git config --list
     ```
   - This command displays your Git settings, including the username and email.

#### macOS

1. **Use Homebrew and Then Git**
   - Open Terminal.
   - Install Homebrew if not already installed:
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```
     Follow the prompts that appear.
     
   - Install Git using Homebrew:
     ```bash
     brew install git
     ```
     Follow the prompts that appear.

2. **Verify the Installation**
   - Run the following command in Terminal:
     ```bash
     git --version
     ```
   - You should see the Git version number, e.g., `git version 2.x.x`.

3. **Configure Git**
   - Open Terminal.
   - Set your username and email:
     ```bash
     git config --global user.name "Your Name"
     git config --global user.email "your.email@example.com"
     ```
   - Verify the configuration:
     ```bash
     git config --list
     ```

#### Linux

1. **Install via Package Manager**
   - Open Terminal.
   - Use the appropriate package manager for your distribution:

     - **Debian/Ubuntu**:
       ```bash
       sudo apt update
       sudo apt install git
       ```

     - **Fedora**:
       ```bash
       sudo dnf install git
       ```

     - **Arch Linux**:
       ```bash
       sudo pacman -S git
       ```

2. **Verify the Installation**
   - Run the following command in Terminal:
     ```bash
     git --version
     ```
   - You should see the Git version number, e.g., `git version 2.x.x`.

3. **Configure Git**
   - Open Terminal.
   - Set your username and email:
     ```bash
     git config --global user.name "Your Name"
     git config --global user.email "your.email@example.com"
     ```
   - Verify the configuration:
     ```bash
     git config --list
     ```
---

### 5. Troubleshooting Common Issues

1. **Command Not Found Error**
   - **Symptom**: `git: command not found`
   - **Solution**: Ensure Git is installed correctly and added to your system’s PATH.

2. **Permissions Issues**
   - **Symptom**: Permission errors during installation.
   - **Solution**: Run the installer or terminal with elevated privileges (e.g., "Run as Administrator" on Windows or `sudo` on Linux).

3. **Outdated Version**
   - **Symptom**: Older Git features not available.
   - **Solution**: Download and install the latest version from the Git website or update via your package manager.
  
4. **Forgot to Configure Git with Username and Email**
   - **Symptom:** You forgot to configure before you closed the terminal.
   - **Solution**: Follow the "Configure Git" step above at any time.

---

### Key Takeaways

- **Installing Git** is the first step to using version control for your projects.
- **Download and Install** Git from the official website or use a package manager.
- **Verify Installation** by running `git --version`.
- **Configure Git** with your username and email to identify your changes.
  - **Example**:
    ```bash
    git config --global user.name "Jane Doe"
    git config --global user.email "jane.doe@example.com"
    ```
  - Verify by running `git config --list`.
- **Troubleshoot** common issues like command not found or permissions errors.
