# Dig-tool
header
A highly configurable automation tool specifically for the ROBLOX game "Dig" where several algorithms are used in order achieve accuracy during the minigame.

Note

If in any circumstances tools like these become banned by Dig staff, this repository and its contents will be archived.

Installation
Option 1: Quick Start (Recommended)
Download the pre-compiled executable from the releases page
No Python installation required - just run the .exe file
Warning

Antiviruses will flag the compiled executable as a virus! These are FALSE POSITIVES. Everything leading up to the compiled executable is open source.

Option 2: Run from Source
Clone this repository: git clone https://github.com/Jamaicaboom
Install dependencies: pip install -r requirements.txt
Run the application: python main.py
If you wish to also compile from source you can run: python -m nuitka --onefile --enable-plugin=tk-inter --include-package=ahk --include-package-data=ahk --include-package-data=jinja2 --lto=yes --windows-console-mode=disable --windows-icon-from-ico=assets/icon.ico main.py

Note

Option 1 is recommended for most users as it requires no technical setup and comes with a performance boost due to it's compilation nature. Choose Option 2 if you want to modify the code or prefer running from source.

Usage
You just need to select an area where it is not being interfered by text or other icons. See the example picture below. example This is different for other resolutions as the UI elements in-game will be scaled differently! That also means you may have to change detection parameters like Zone Min. Width since it measures by pixels.

Technical Overview
How It Works
The tool captures the screen continuously and analyzes each frame to find moving lines and colored zones. When it detects a line moving toward the target area, it calculates where the line will be in the future and attempts to click precisely in the middle of the colored zone.

Detection Process
Setup: The user selects an area on the screen, in this case, it would be the minigame's bar itself
Zone Finding: Automatically detects colored target zones within the bar. The color found is then used to "lock" the color for better tracking
Line Tracking: Continuously scans for vertical lines using edge detection
Speed Calculation: Tracks how fast and in which direction the line is moving in order to perform predictive clicking
This tool is meant to perform its detection tasks with minimal delay and minimal resource usage.
