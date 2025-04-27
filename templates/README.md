# Flask Cognate Project

## 1. Framework Used

This project uses **Flask**, a lightweight Python web framework, for building the web application. Flask is chosen because of its simplicity, flexibility, and ease of deployment in virtualized environments like VirtualBox.

## 2. Prerequisites
- Make sure Python is installed on the machine where the Flask app will run (either your host machine or the VirtualBox VM).
- Recommended Python Version: 3.x (already installed by default with Python 3).
- It is highly recommended to use a *virtual environment* to keep dependencies isolated.

## 3. Setup Steps
*(Perform these on the machine running the Flask app — inside the VM)*

- **Clone/Copy** the project directory:
  - Transfer the project files onto the target machine.
  - Open a Terminal and change to the project's root directory:

```bash
cd ~/LABORATORY/FLASK_COGNATE
```

- **Activate Virtual Environment** (Recommended):

```bash
# Install virtualenv if not already installed
python3 -m pip install virtualenv

# Create a virtual environment
python3 -m venv venv

# Activate Virtual Environment:
source venv/bin/activate   # (in Linux/macOS terminal)
# OR
.\venv\Scripts\activate    # (in Windows terminal prompt)
```

- **Install Required Packages**:

```bash
pip install -r requirements.txt
```

*(This command will install Flask and any other requirements if you created a `requirements.txt` file.)*

- Ensure your project structure includes `templates/` (with `.html` files) and `static/` (with `style.css`) folders at the same level as `app.py`.

---

## 4. How to Run the Project

- **Start the Flask Development Server**  
While inside the project directory with the virtual environment activated, run:

```bash
python app.py
# OR
flask run --host=0.0.0.0 --port=5000
```

- The output will indicate the server is running, usually on:

```
http://0.0.0.0:5000/
```

(`0.0.0.0` means it's listening on all available network interfaces.)

### Accessing the Application (Virtualbox/VM Scenario)

- Make sure the VM network setting is either **Bridged Adapter** or configured with port forwarding.
- If using **Bridged Adapter**, find the VM's IP address (e.g., using `ip addr` command inside the VM).
- From the host machine’s browser, access the app using:

```
http://<YOUR_VM_IP_ADDRESS>:5000
```

Example:

```
http://192.168.0.150:5000
```

- If using **port forwarding** in VirtualBox:
  - Navigate to:

```
http://localhost:5000
```

or

```
http://127.0.0.1:5000
```

---

## 5. Basic Description of the Web App

- **Home Page (`/`)**:  
  Displays a welcome message and an introductory text about the project, focusing on cloud and VM deployment concepts.

- **About Page (`/about`)**:  
  Provides details about the project, the technologies used (Flask, Python, etc.), and discusses the overall design concept.

- **Simple Contact Form**:  
  Displays a contact form with fields for Name, Email, and Message.

- **Routing Logic**:
  - Routes are defined in `app.py`.
  - Server handles form submissions and basic error handling.

- **Web Design Features**:
  - Utilizes Bootstrap for layout, typography (using Google Fonts), color, responsiveness, and component design.
  - Integrates minor CSS customizations.
  - Handles 404 (page not found) and 500 (internal server error) pages using templates located in the `templates/` folder.

---

## 6. Issues Encountered and Solutions

### Issue 1: Syntax Errors

**Problem**: Incorrect usage of an f-string in `app.py`, causing server failure to start.

**Solution**: Properly corrected the f-string by ensuring valid expressions inside curly braces. Regular code reviews and testing were emphasized.

### Issue 2: Wrong Commands

**Problem**: Mistyped Flask command as `run flask --host=0.0.0.0 --port=5000` instead of the correct `flask run --host=0.0.0.0 --port=5000`.

**Solution**: Careful review of command structure and order when using the terminal to prevent future delays.

### Issue 3: Cannot be Reached on Host Terminal

**Problem**: After starting the Flask server, the app could not be accessed via the host machine's browser.

**Solution**: Fixed syntax errors first, verified server listening on `0.0.0.0`, checked network settings and firewall rules to open port 5000.

---

## 7. Notes

- Always ensure the virtual environment is activated before running the app.
- Confirm that the firewall and network configurations allow access to port 5000.
- For easier debugging, always check the terminal logs when an error occurs.

---

## Git Repository

[Group VI Flask Web App Repository](https://github.com/Tonetxcz/GroupVI_Flask-WebApp)

---
