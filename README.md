

![image](https://github.com/user-attachments/assets/317f64b8-9d66-4d03-806c-e93f5309c5f8)

# PyScan

**PyScan** is a Python-based security scanning tool that uses [YARA](https://virustotal.github.io/yara/) rules to detect malware or suspicious files. It supports scanning individual files, entire directories, the Downloads folder, and performs a “Persistence Remover” scan for malicious registry entries, startup folders, scheduled tasks, Windows services, and WMI subscriptions.

> **Developed by pydev and chatgpt**

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Exclusions](#exclusions)
- [Optional: Building a Single Executable](#optional-building-a-single-executable)
  - [PyInstaller Example](#pyinstaller-example)
- [Contributing](#contributing)
- [License](#license)
- [Credits](#credits)

---

## Features

1. **YARA Integration**  
   Load and compile YARA rules to detect suspicious signatures in files.

2. **Multiple Scan Modes**  
   - **Single File:** Prompt for a file and scan it immediately.  
   - **Directory Scan:** Recursively scan a user-selected directory.  
   - **Downloads Folder:** Quickly scan the user’s default Downloads folder.  
   - **Persistence Remover:** Search for malicious persistence mechanisms in registry run keys, startup folders, scheduled tasks, Windows services, and WMI subscriptions (Windows-only).

3. **Exclusions**  
   - Exclude single files (via the detection pop-up) or entire folders (via an “Exclude Folder” button).  
   - Manage (remove) these exclusions dynamically during runtime.

4. **Logging & Alerts**  
   - Timestamped logging in a text area and an external log file (`pyscan_scan_results.log` by default).  
   - Pop-up alerts when a match is found, allowing you to Quarantine, Delete, Exclude, or Ignore the detection.

5. **Scheduling (Optional)**  
   - Uses [APScheduler](https://apscheduler.readthedocs.io/en/stable/) to automate scans at set intervals, if desired (in-memory only).

6. **Clean UI**  
   - Built with [PyQt5](https://pypi.org/project/PyQt5/).  
   - Group boxes and a simple style sheet provide a professional layout.  
   - “About” button displaying “Developed by...”

---

## Requirements

- **Python 3.7+**
- **Dependencies**:

  ```bash
  pip install PyQt5 yara-python APScheduler

pip install rarfile

pip install wmi


Usage
Run PyScan:


python PyScan.py


## Exclusions
Exclude Folder – Skips all files in that folder (and subfolders).

Manage Exclusions – Opens a dialog listing all currently excluded paths, letting you remove them if needed.

Note: Exclusions are in-memory only by default. Once you exit PyScan, they reset unless you modify the code to save them.

