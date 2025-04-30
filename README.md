## Setup Guide (Linux)

Ensure that your system has the correct permissions and dependencies before running the application.

---

### 🔧 Requirements
- A Linux-based operating system
- Python 3.x installed
- `pip` (Python package installer)
- Access to hardware ports (e.g., serial ports)

---

### 🔐 Step 1: Check Serial Port Permissions
To use serial ports, your user account must belong to the `dialout` group.

1. Open a terminal and run:
    ```bash
    groups
    ```
2. If `dialout` is **not** listed in the output, add your user to the group:
    ```bash
    sudo usermod -a -G dialout $USER
    ```

---

### 🔁 Step 2: Restart Your Computer
After modifying group memberships, a system restart is required to apply the changes.

---

### 📦 Step 3: Install Project Dependencies
Navigate to your project directory and install the required Python packages:
```bash
pip install -r requirements.txt
```
This will install all dependencies listed in `requirements.txt`.

---

### 🚀 Step 4: Run the Application
Once everything is set up, execute your Python script:
```bash
python car_entry.py
```
---

### ✅ You're Ready!
Your environment should now be properly configured to run the application.

