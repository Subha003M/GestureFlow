# GestureFlow
Hand Gesture–Controlled Virtual Mouse with Login and Live Dashboard

GestureFlow Pro is a Python-based UG project that uses a webcam to recognize hand gestures and control the mouse on Windows.

# Features

User registration and secure login

Private admin login to view registered users

Live hand tracking, gesture names, actions, and FPS

Mouse movement, clicks, drag-and-drop, and scrolling

Volume and brightness control

Automatic local SQLite database

# Tech Stack

Python · OpenCV · MediaPipe · PyAutoGUI · Flask · HTML/CSS/JavaScript · SQLite

# Run Locally (Windows)

Requires Python 3.12, a webcam, and Windows.

py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python create_admin.py
python main.py

Open http://127.0.0.1:5000 in your browser. Create a user account, or sign in as the admin account you created. On the user dashboard, select Start Camera, then Enable PC Controls to control your PC.

# Basic Gestures

# Gesture
Right-hand ✌️ V sign
Move cursor

Right-hand ☝️ Index
Left click

Right-hand two fingers together
Right click

Right-hand ✊ Fist
Drag

Left-hand 🤏 Pinch + movement
Scroll

Right-hand 🤏 Pinch + movement
Volume / brightness

# Screenshots
<img width="960" height="504" alt="image" src="https://github.com/user-attachments/assets/2186fabd-8fc0-48ea-a7f3-4ed09a272720" />

<img width="960" height="504" alt="image" src="https://github.com/user-attachments/assets/19c39db7-de8d-4a87-aed7-85845ea06c1e" />



# Notes

User accounts are stored locally in instance/profiles.db; no manual database setup is needed. Never commit .venv/, instance/, .env, or passwords to GitHub.

The full app works locally on Windows. The showcase/ folder can be deployed to Vercel as a static demo only; it cannot control a visitor's PC or provide the local admin database.
