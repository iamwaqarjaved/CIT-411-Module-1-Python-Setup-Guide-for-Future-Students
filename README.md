# CIT 411 Module 1: Python Setup Guide for Future Students

**Course:** CIT 411  
**Audience:** Future CIT 411 students with little or no command-line experience  
**Goal:** Install Python, configure VS Code, create a virtual environment, and run a working “Hello World” script on Windows or macOS.

---

## Table of Contents

1. [What You Will Install](#1-what-you-will-install)  
2. [Before You Start](#2-before-you-start)  
3. [Windows Installation](#3-windows-installation)  
4. [macOS Installation](#4-macos-installation)  
5. [Install and Configure VS Code](#5-install-and-configure-vs-code)  
6. [Create a Project and Virtual Environment](#6-create-a-project-and-virtual-environment)  
7. [Hello World Verification Script](#7-hello-world-verification-script)  
8. [Recommended VS Code Shortcuts and Settings](#8-recommended-vs-code-shortcuts-and-settings)  
9. [Common Errors and Troubleshooting](#9-common-errors-and-troubleshooting)  
10. [Next Steps](#10-next-steps)  
11. [Final Verification Checklist](#11-final-verification-checklist)

---

## 1. What You Will Install

By the end of this guide, your computer should have:

- Python 3 installed
- Visual Studio Code installed
- VS Code Python extension installed
- VS Code Pylance extension installed
- A working project folder
- A Python virtual environment
- A successful `hello.py` test script

Python is the programming language. VS Code is the editor where you will write and run code. A virtual environment keeps each project’s Python packages separate so one class project does not accidentally break another.

---

## 2. Before You Start

### You need

- A Windows 10/11 computer or a macOS computer
- Administrator permission to install software
- Internet access
- About 30–45 minutes
- A GitHub repository for your final submission

### Recommended folder location

Use a simple folder path with no special characters:

**Windows**

```text
C:\Users\YourName\Documents\cit411-python-setup
```

**macOS**

```text
/Users/YourName/Documents/cit411-python-setup
```

Avoid saving your first project inside OneDrive, iCloud Drive, Dropbox, or Google Drive. Cloud-sync folders sometimes lock files while Python or VS Code is trying to use them.

---

## 3. Windows Installation

### Step 1: Download Python for Windows

1. Open your browser.
2. Go to the official Python download page: <https://www.python.org/downloads/>
3. Click the button for the latest Python 3 release.
4. Download the **Windows installer (64-bit)**.

**Decision point:**  
Use the official Python website, not a random download site. This reduces the risk of installing an outdated or unsafe package.

---

### Step 2: Run the Windows installer

1. Open the downloaded `.exe` installer.
2. On the first installer screen, check:

```text
Add python.exe to PATH
```

3. Click **Install Now**.

**Important:**  
This is one of the most common places students make a mistake. If you do not check **Add python.exe to PATH**, Windows may not recognize the `python` command in PowerShell.

---

### Step 3: Confirm installation completed

When the installer finishes, click **Close**.

---

### Step 4: Verify Python in PowerShell

1. Open **PowerShell**.
2. Run:

```powershell
python --version
```

You should see output similar to:

```text
Python 3.x.x
```

Then run:

```powershell
pip --version
```

You should see output similar to:

```text
pip 25.x from ... (python 3.x)
```

If this works, Python is installed correctly.

---

## 4. macOS Installation

### Step 1: Download Python for macOS

1. Open your browser.
2. Go to the official Python download page: <https://www.python.org/downloads/>
3. Click the latest Python 3 release.
4. Download the **macOS 64-bit universal2 installer** if it is available.

**Decision point:**  
macOS may already include a system Python, but do not rely on it for class projects. Install the current Python 3 version from python.org.

---

### Step 2: Run the macOS installer

1. Open the downloaded `.pkg` file.
2. Click **Continue** through the installer screens.
3. Accept the license agreement.
4. Choose the default install location.
5. Click **Install**.
6. Enter your Mac password if prompted.

---

### Step 3: Verify Python in Terminal

1. Open **Terminal**.
2. Run:

```bash
python3 --version
```

You should see:

```text
Python 3.x.x
```

Then run:

```bash
pip3 --version
```

You should see:

```text
pip 25.x from ... (python 3.x)
```

**Note:**  
On macOS, the command is usually `python3`, not `python`.

---

## 5. Install and Configure VS Code

### Step 1: Download VS Code

1. Go to: <https://code.visualstudio.com/>
2. Download VS Code for your operating system.
3. Install it using the default options.


---

### Step 2: Install Python extension

1. Open VS Code.
2. Click the **Extensions** icon on the left sidebar.
3. Search for:

```text
Python
```

4. Install the official **Python** extension from Microsoft.

---

### Step 3: Install Pylance extension

1. In the Extensions search bar, search:

```text
Pylance
```

2. Install the official **Pylance** extension from Microsoft.

![VS Code Pylance extension](screenshots/vscode-03-pylance-extension.png)

Pylance gives better autocomplete, code analysis, and type-checking support.

---

### Step 4: Install Black Formatter extension

1. In the Extensions search bar, search:

```text
Black Formatter
```

2. Install the official **Black Formatter** extension from Microsoft.


Black automatically formats Python code in a consistent style.

---

### Step 5: Open your project folder

1. In VS Code, click **File > Open Folder**.
2. Create or select this folder:

**Windows**

```text
Documents\cit411-python-setup
```

**macOS**

```text
Documents/cit411-python-setup
```

3. Click **Select Folder** or **Open**.


---

## 6. Create a Project and Virtual Environment

A virtual environment is a private Python workspace for one project. It helps avoid package conflicts.

### Step 1: Open the integrated terminal

In VS Code, open the terminal:

```text
Terminal > New Terminal
```

---

### Step 2: Create the virtual environment

#### Windows PowerShell

Run:

```powershell
python -m venv .venv
```

#### macOS Terminal

Run:

```bash
python3 -m venv .venv
```


This creates a hidden folder named `.venv`.

---

### Step 3: Activate the virtual environment

#### Windows PowerShell

Run:

```powershell
.\.venv\Scripts\Activate.ps1
```

If activation works, your terminal prompt should begin with:

```text
(.venv)
```

#### macOS Terminal

Run:

```bash
source .venv/bin/activate
```

If activation works, your terminal prompt should begin with:

```text
(.venv)
```

---

### Step 4: Select the Python interpreter in VS Code

1. Press:

**Windows**

```text
Ctrl + Shift + P
```

**macOS**

```text
Command + Shift + P
```

2. Search for:

```text
Python: Select Interpreter
```

3. Choose the interpreter inside `.venv`.

It should look similar to:

**Windows**

```text
.\.venv\Scripts\python.exe
```

**macOS**

```text
./.venv/bin/python
```

![VS Code select Python interpreter command](screenshots/vscode-08-select-interpreter-command.png)

![VS Code selected .venv interpreter](screenshots/vscode-09-selected-venv-interpreter.png)

**Decision point:**  
Do not select the global Python interpreter if your `.venv` interpreter is available. For class projects, use the `.venv` interpreter.

---

## 7. Hello World Verification Script

### Step 1: Create `hello.py`

In your project folder, create a file named:

```text
hello.py
```

---

### Step 2: Add this code

Copy this code into `hello.py`:

```python
import platform
import sys
from datetime import datetime


def main() -> None:
    print("Hello, CIT 411!")
    print(f"Python executable: {sys.executable}")
    print(f"Python version: {platform.python_version()}")
    print(f"Operating system: {platform.system()} {platform.release()}")
    print(f"Verification time: {datetime.now().strftime('%Y-%m-%d %H:%M:%S')}")


if __name__ == "__main__":
    main()
```

---

### Step 3: Run the script

#### Windows PowerShell

Make sure your virtual environment is active, then run:

```powershell
python hello.py
```

#### macOS Terminal

Make sure your virtual environment is active, then run:

```bash
python hello.py
```

or:

```bash
python3 hello.py
```

Expected output should look similar to:

```text
Hello, CIT 411!
Python executable: C:\Users\YourName\Documents\cit411-python-setup\.venv\Scripts\python.exe
Python version: 3.x.x
Operating system: Windows 11
Verification time: 2026-05-16 14:30:00
```

On macOS, the Python executable path will look different:

```text
/Users/YourName/Documents/cit411-python-setup/.venv/bin/python
```

If your output shows the `.venv` path, your setup is working end-to-end.

---

## 8. Recommended VS Code Shortcuts and Settings

### Useful keyboard shortcuts

| Action | Windows | macOS |
|---|---:|---:|
| Open Command Palette | `Ctrl + Shift + P` | `Command + Shift + P` |
| Open Terminal | `` Ctrl + ` `` | `` Control + ` `` |
| Save File | `Ctrl + S` | `Command + S` |
| Format Document | `Shift + Alt + F` | `Shift + Option + F` |
| Quick Open File | `Ctrl + P` | `Command + P` |
| Toggle Sidebar | `Ctrl + B` | `Command + B` |
| Run Python File | Right-click file > Run Python File in Terminal | Right-click file > Run Python File in Terminal |

---

### Recommended VS Code settings

Open Command Palette and search:

```text
Preferences: Open User Settings (JSON)
```

Add or update the following settings:

```json
{
  "editor.formatOnSave": true,
  "editor.tabSize": 4,
  "editor.insertSpaces": true,
  "files.autoSave": "afterDelay",
  "python.analysis.typeCheckingMode": "basic",
  "python.defaultInterpreterPath": ".venv/bin/python",
  "[python]": {
    "editor.defaultFormatter": "ms-python.black-formatter",
    "editor.formatOnSave": true
  },
  "terminal.integrated.defaultProfile.windows": "PowerShell",
  "terminal.integrated.defaultProfile.osx": "zsh"
}
```

![VS Code settings JSON](screenshots/vscode-13-settings-json.png)

### Windows note for `python.defaultInterpreterPath`

If you are on Windows and VS Code does not automatically find your `.venv`, use this path instead:

```json
"python.defaultInterpreterPath": ".venv\\Scripts\\python.exe"
```

---

## 9. Common Errors and Troubleshooting

### Error 1: `python is not recognized as an internal or external command`

**Where it happens:** Windows PowerShell

**Cause:** Python was not added to PATH during installation.

**Fix:**

1. Re-run the Python installer.
2. Choose **Modify**.
3. Make sure **Add Python to environment variables** is enabled.
4. Finish the installer.
5. Close and reopen PowerShell.
6. Run:

```powershell
python --version
```

---

### Error 2: macOS says `python: command not found`

**Where it happens:** macOS Terminal

**Cause:** macOS often uses `python3` instead of `python`.

**Fix:**

Run:

```bash
python3 --version
```

Use this command to create your virtual environment:

```bash
python3 -m venv .venv
```

---

### Error 3: PowerShell says script execution is disabled

**Where it happens:** Windows PowerShell when activating `.venv`

Error may look like:

```text
Activate.ps1 cannot be loaded because running scripts is disabled on this system.
```

**Cause:** Windows PowerShell execution policy blocks activation scripts.

**Fix:**

Run this command in PowerShell:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Then try again:

```powershell
.\.venv\Scripts\Activate.ps1
```

---

### Error 4: Wrong Python version is selected in VS Code

**Where it happens:** VS Code

**Symptom:** Your script runs, but the output does not show the `.venv` path.

**Cause:** VS Code is using the global Python interpreter instead of your virtual environment.

**Fix:**

1. Press `Ctrl + Shift + P` on Windows or `Command + Shift + P` on macOS.
2. Search **Python: Select Interpreter**.
3. Choose the interpreter inside `.venv`.
4. Re-run `hello.py`.

![Wrong interpreter selected](screenshots/errors-04-wrong-interpreter.png)

---

### Error 5: `No module named ...`

**Where it happens:** Running Python files after installing a package

**Cause:** You installed a package globally or in a different environment.

**Fix:**

1. Activate your virtual environment.
2. Confirm the Python executable:

```bash
python -c "import sys; print(sys.executable)"
```

3. Install the package again while `.venv` is active:

```bash
python -m pip install package-name
```

Replace `package-name` with the package required by your assignment.


---

### Error 6: VS Code says no formatter is installed

**Where it happens:** VS Code format command

**Cause:** Black Formatter extension is missing or not selected.

**Fix:**

1. Install the **Black Formatter** extension from Microsoft.
2. Open Settings JSON.
3. Confirm:

```json
"[python]": {
  "editor.defaultFormatter": "ms-python.black-formatter",
  "editor.formatOnSave": true
}
```

4. Save the file and restart VS Code.

---

### Error 7: Virtual environment activation command fails

**Where it happens:** Windows or macOS terminal

**Cause:** You are in the wrong folder or used the wrong activation command.

**Fix:**

Check that `.venv` exists:

#### Windows

```powershell
dir
```

Then activate:

```powershell
.\.venv\Scripts\Activate.ps1
```

#### macOS

```bash
ls -la
```

Then activate:

```bash
source .venv/bin/activate
```

---

## 10. Next Steps

After your setup works, continue with these official and beginner-friendly resources.

### Official Python documentation

- Python documentation home: <https://docs.python.org/3/>
- Python tutorial: <https://docs.python.org/3/tutorial/>
- Virtual environments and packages: <https://docs.python.org/3/tutorial/venv.html>
- `venv` library reference: <https://docs.python.org/3/library/venv.html>

### VS Code documentation

- VS Code Python documentation: <https://code.visualstudio.com/docs/python/python-tutorial>
- Python formatting in VS Code: <https://code.visualstudio.com/docs/python/formatting>
- Python settings reference: <https://code.visualstudio.com/docs/python/settings-reference>

### Real Python tutorials

- Installing Python: <https://realpython.com/installing-python/>
- Python Basics tutorials: <https://realpython.com/tutorials/basics/>
- Setting Up Python course: <https://realpython.com/courses/setting-up-python/>

---

```


A student who follows this guide should be able to install Python, configure VS Code, activate a virtual environment, and run the verification script without needing extra help.
