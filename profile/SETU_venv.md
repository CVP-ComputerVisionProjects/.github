# Python Virtual Environment Setup & Deployment Guide

This guide covers the complete workflow for setting up a local Python development environment, packaging your dependencies, and deploying your project onto a new machine.

---

## Part 1: Local Development Setup & Packaging

Follow these steps on your development machine to set up the environment and save your dependencies.

### 1. Open Terminal
Navigate to your project folder using your command line interface.
```bash
cd path/to/your/project
```

### 2. Create a Virtual Environment
Run the following command to create a new virtual environment named `venv`:
```bash
python -m venv venv
```

### 3. Activate the Environment
Depending on your operating system, use one of the following commands:
- **Windows (Command Prompt):**
  ```cmd
  venv\Scripts\activate
  ```
- **Windows (PowerShell):**
  ```powershell
  .\venv\Scripts\Activate.ps1
  ```
- **macOS / Linux:**
  ```bash
  source venv/bin/activate
  ```

### 4. Install Packages
Install your required libraries (for example, `requests`):
```bash
pip install requests
```

### 5. Export Dependencies
Save the installed packages into a `requirements.txt` file. This file acts as a snapshot of your project's dependencies.
```bash
pip freeze > requirements.txt
```

---

## Part 2: Deployment on a New Machine

Follow these steps to replicate the exact environment on another computer or server.

### 1. Transfer Project Files
Copy your project source code and the `requirements.txt` file to the new machine.
> ⚠️ **Important:** Do *not* copy the `venv` folder from the old machine. Virtual environments are tied to the specific operating system and absolute paths of the machine they were created on.

### 2. Open Terminal
Navigate to the project folder on the new machine.
```bash
cd path/to/your/project
```

### 3. Create a New Virtual Environment
Generate a clean environment specifically for this new machine:
```bash
python -m venv venv
```

### 4. Activate the Environment
Activate the new environment based on the new machine's operating system:
- **Windows (Command Prompt):**
  ```cmd
  venv\Scripts\activate
  ```
- **Windows (PowerShell):**
  ```powershell
  .\venv\Scripts\Activate.ps1
  ```
- **macOS / Linux:**
  ```bash
  source venv/bin/activate
  ```

### 5. Install from Requirements
Download and install all listed dependencies automatically from your `requirements.txt` file:
```bash
pip install -r requirements.txt
```

---
*Happy Coding!*
