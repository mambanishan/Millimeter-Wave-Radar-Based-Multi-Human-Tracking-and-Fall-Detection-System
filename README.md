# Millimeter-Wave-Radar-Based-Multi-Human-Tracking-and-Fall-Detection-System
Overview
This repository contains the full implementation of our project:
Millimeter-Wave Radar-Based Multi-Human Tracking and Fall Detection System,
designed to track multiple humans and detect falls in real time using mmWave radar sensors.
The system leverages non-intrusive radar-based sensing, eliminating the limitations of wearable devices and camera‑based monitoring such as lighting issues, privacy concerns, and restricted mobility. By processing radar point-cloud data, the framework enables robust multi-human tracking and fall classification in indoor environments.
Key Features


Multi-Human Tracking
Detects and tracks multiple individuals simultaneously with high accuracy.


Real-Time Fall Detection
Classifies human activity states and detects falls based on motion dynamics.


Advanced Signal Processing
Incorporates DBSCAN-based clustering, trajectory estimation, and noise filtering.


Privacy-Friendly System
No cameras required — ensuring high privacy.
(Note: Any camera module included is used only for ground‑truth validation.)



Table of Contents

#system-architecture
#installation-and-usage
#license


System Architecture
Components


Radar Hardware
System uses Texas Instruments mmWave radar sensors (e.g., IWR6843, AWR series).


Real-Time Processing Framework

Radar data parsing
Point-cloud preprocessing
Clustering & tracking
Fall detection
Optional visualization module



Workflow
Below is the system flowchart representing the end‑to‑end processing pipeline:
Sys_flowchart.jpg

Installation and Usage
Prerequisites
Ensure the following are installed:

Python 3.8+
Required Python libraries:
numpy
Send2Trash
scipy
pyserial
matplotlib
scikit-learn
opencv-python
google-api-python-client
google-auth-oauthlib
func-timeout
moviepy




Steps
1. Clone this repository
Shellgit clone https://github.com/mambanishan/mmwave-human-tracking-fall-detection.gitcd mmwave-human-tracking-fall-detectionShow more lines

2. Install dependencies
Shellpip install -r requirements.txtShow more lines

3. Connect the mmWave radars
Attach your TI mmWave sensors to your system.

4. Identify radar COM ports
Check the port numbers assigned to:

cfg_port_name
data_port_name

You can find them via:

Device Manager (Windows)
ls /dev/tty* (Linux/Mac)


5. Configure radar parameters
Navigate to the configuration folder:
Shellcd cfgShow more lines
Open config_demo.py and update:

cfg_port_name
data_port_name

for each radar in RADAR_CFG_LIST.

6. Run the main system
Return to the root folder and start the system:
Shellpython main.pyShow more lines

License
This project is licensed under the MIT License.
You are free to:

Use
Modify
Distribute

the project, as long as you include the original copyright notice.
See the full license in the LICENSE file.
