# Hand Gesture Virtual Mouse

Windows Python project to control the mouse with webcam hand gestures using OpenCV, MediaPipe, and PyAutoGUI. Also controls screen brightness and audio volume.

## Requirements

- Windows 10/11, working webcam and camera permission
- Python **3.10, 64-bit**, installed from python.org (recommended for this legacy `mp.solutions` code)
- Speakers/audio output for volume actions

## Setup in PowerShell (VS Code terminal)

```powershell
py -3.10 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
python main.py
```

If PowerShell blocks activation, use Command Prompt instead:

```cmd
.venv\Scripts\activate.bat
python -m pip install -r requirements.txt
python main.py
```

If `py -3.10` is not found, install Python 3.10 64-bit and re-open the terminal. In VS Code select the Python interpreter in `.venv\Scripts\python.exe`. No `.env` secrets file is needed for this local project.

## Operation

Run `python main.py` to open the camera. Make a V with index/middle fingers to move the pointer; an index finger to click; two fingers close together to right-click; a fist to drag. Pinch gestures are used for scrolling and for volume/brightness adjustments, with dominant vs non-dominant hand determining actions. **Press Enter in the camera window to exit.** Ctrl+C in the terminal can also interrupt.

**Safety:** This code moves the real mouse and changes system settings. Save other work first, and know how to stop it. PyAutoGUI failsafe is enabled: moving the pointer to a screen corner can abort mouse automation. It has not been tested on your webcam.

## Troubleshooting

- `No module named ...`: activate `.venv`, then `pip install -r requirements.txt`.
- `AttributeError: module 'mediapipe' has no attribute 'solutions'`: confirm `mediapipe==0.10.21` in the venv.
- Camera unavailable: close Zoom/Teams/other camera apps and enable camera permission in Windows Settings.
- `pycaw` or `comtypes` errors: use Windows and verify the venv interpreter is selected.
- If a Windows package fails to install, check that you're using Python 3.10 64-bit and share the *full error text*.

## GitHub

The `.venv` directory is excluded via `.gitignore`. Once tested, run `git init`, `git add .`, `git commit -m "Initial working version"`; add a remote and push your repository.
