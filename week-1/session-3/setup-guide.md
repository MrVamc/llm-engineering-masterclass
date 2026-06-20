# Week 1 - Setup Guide

Everything you need to install before Session 4 (Sunday).

Instructions are provided for **Mac (Apple Silicon)**, **Mac (Intel)**, **Windows**, and **Linux**.

---

## Required for Session 4

### 1. Python 3.10 or higher

**Mac (Apple Silicon and Intel):**

macOS comes with an older Python. Install the latest version.

Option A - Download the installer:
1. Go to https://www.python.org/downloads/
2. Download the latest version (3.12 or 3.13)
3. Run the installer

Option B - Using Homebrew (if you have it):
```bash
brew install python
```

After installing, open Terminal and verify:
```bash
python3 --version
```

On Mac, the command is `python3`, not `python`.

**Windows:**

1. Go to https://www.python.org/downloads/
2. Download the latest version (3.12 or 3.13)
3. Run the installer
4. **Important:** Check the box that says "Add Python to PATH" before clicking Install

After installing, open Command Prompt or PowerShell and verify:
```bash
python --version
```

If `python` does not work, try `python3` or `py`.

**Linux (Ubuntu/Debian):**
```bash
sudo apt update
sudo apt install python3 python3-pip python3-venv
python3 --version
```

**Linux (Fedora):**
```bash
sudo dnf install python3 python3-pip
python3 --version
```

---

### 2. Ollama

Download from https://ollama.com/download

**Mac (Apple Silicon - M1/M2/M3/M4):**
1. Download the Mac installer from the link above
2. Open the downloaded file and drag Ollama to Applications
3. Open Ollama from Applications (it runs in the menu bar)
4. Open Terminal and run:
```bash
ollama pull qwen3:0.6b
```

Apple Silicon Macs run Ollama very well. The model uses your GPU automatically.

**Mac (Intel):**
1. Download the Mac installer from the link above
2. Open the downloaded file and drag Ollama to Applications
3. Open Ollama from Applications
4. Open Terminal and run:
```bash
ollama pull qwen3:0.6b
```

Intel Macs will run the model on CPU. It will be slower than Apple Silicon but it works fine for our course. If your Intel Mac has less than 8 GB RAM, consider using Google Colab as a backup (see below).

**Windows:**
1. Download the Windows installer from the link above
2. Run the installer and follow the steps
3. Open Command Prompt or PowerShell and run:
```bash
ollama pull qwen3:0.6b
```

If you have an NVIDIA GPU, Ollama will use it automatically. If not, it runs on CPU which is slower but works.

**Linux:**
```bash
curl -fsSL https://ollama.com/install.sh | sh
ollama pull qwen3:0.6b
```

**Test it (all platforms):**
```bash
ollama run qwen3:0.6b
```

Ask it anything. If it responds, you are ready. Type `/bye` to exit.

This model is about 500 MB. On a slow connection, the download may take 10-15 minutes.

---

### 3. Code Editor

Install any code editor you prefer:

- **VS Code** (recommended): https://code.visualstudio.com/
  - Available for Mac, Windows, and Linux
  - Make sure to download the correct version for your system (Apple Silicon vs Intel on Mac)
- **Cursor**: https://cursor.com/
- Any other editor you are comfortable with

---

### 4. Jupyter Extension (inside your editor)

If you are using VS Code or Cursor:

1. Open the editor
2. Go to Extensions (left sidebar, or press `Cmd+Shift+X` on Mac / `Ctrl+Shift+X` on Windows)
3. Search for "Jupyter"
4. Click Install

This lets you run notebook files (.ipynb) which we will use for all coding sessions.

---

## Install This Week (not needed for tomorrow)

### 5. Git

**Mac:**

Git usually comes pre-installed. Check first:
```bash
git --version
```

If it is not installed, macOS will prompt you to install the Command Line Tools. Click Install and follow the steps.

Alternatively, if you use Homebrew:
```bash
brew install git
```

**Windows:**

1. Download from https://git-scm.com/downloads
2. Run the installer
3. Use the default settings (click Next through the installer)
4. Verify in Command Prompt or PowerShell:
```bash
git --version
```

**Linux:**
```bash
# Ubuntu/Debian
sudo apt install git

# Fedora
sudo dnf install git
```

---

### 6. Google Colab (just bookmark it)

Go to https://colab.research.google.com and sign in with your Google account.

Colab gives you free access to GPUs in the cloud. We will use it in later sessions for tasks that need more compute power (fine-tuning, training).

**Use Colab as your backup if:**
- Your laptop has less than 4 GB RAM
- You have an older Intel Mac or Windows machine that struggles with Ollama
- You cannot install software on your machine (work laptop restrictions)

We will share Colab notebooks for learners who need them.

---

## Verify Your Setup

Open your terminal (Terminal on Mac/Linux, Command Prompt or PowerShell on Windows) and run:

**Mac/Linux:**
```bash
python3 --version
# Expected: Python 3.10.x or higher

ollama --version
# Expected: ollama version x.x.x

git --version
# Expected: git version x.x.x
```

**Windows:**
```bash
python --version
# Expected: Python 3.10.x or higher

ollama --version
# Expected: ollama version x.x.x

git --version
# Expected: git version x.x.x
```

Then test the model:
```bash
ollama run qwen3:0.6b
```

Ask it a question. If it answers, you are ready for Session 4.

---

## Troubleshooting

### Python

**"python" or "python3" command not found (Mac):**
- Make sure you installed Python from python.org or via Homebrew
- Try `python3` instead of `python` (Mac always uses `python3`)
- Close and reopen Terminal after installation

**"python" command not found (Windows):**
- Reinstall Python and make sure "Add Python to PATH" is checked
- Try `py` or `python3` instead of `python`
- Close and reopen Command Prompt after installation

### Ollama

**"ollama" command not found (Mac):**
- Open the Ollama app from Applications first (it needs to run at least once)
- Close and reopen Terminal after installation

**"ollama" command not found (Windows):**
- Restart your computer after installation
- Check if Ollama is running in the system tray (bottom right corner)

**Ollama model download is slow or stuck:**
- The qwen3:0.6b model is about 500 MB
- If it gets stuck, press Ctrl+C and try again: `ollama pull qwen3:0.6b`
- If your internet is very slow, try downloading during off-peak hours

**Ollama is slow on my machine:**
- On Intel Macs and Windows machines without a GPU, the model runs on CPU which is slower. This is normal.
- If it takes more than 30 seconds per response, use a smaller prompt or use Google Colab as your backup

### General

**My laptop is old or has less than 4 GB RAM:**
- Use Google Colab as your backup: https://colab.research.google.com
- We will share Colab notebooks for learners who cannot run models locally

**I am on a work laptop and cannot install software:**
- Use Google Colab for all coding exercises
- If possible, request admin access to install Python and VS Code

**Other issues:**
- Reach out to our support team and we will help you sort it out

---

## What We Will Set Up Together in Session 4

- Virtual environments (venv / conda) for keeping your projects clean
- Project folder structure for AI projects
- Calling Ollama from Python code

You do not need to set these up beforehand. We will walk through them step by step in class.
