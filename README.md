# Millimeter-Wave-Radar-Based-Multi-Human-Tracking-and-Fall-Detection-System
https://img.shields.io/badge/mmWave-Radar-blue
https://img.shields.io/badge/Python-3.8%2B-3776AB?logo=python&logoColor=white
https://img.shields.io/badge/Status-Active-success
https://img.shields.io/badge/License-MIT-green
A real-time multi-human tracking and fall detection system powered by millimeter-wave radar technology.
Designed for healthcare, elderly monitoring, smart homes, and privacy-preserving indoor tracking.
🚫 No cameras
🌙 Works in darkness
🔒 Privacy-friendly
📡 Robust against clutter

📘 Table of Contents

#-features
#-installation
#-system-architecture
#-flowchart
#-dataset-documentation
#-running-the-system
#-visualization-tools
#-contributing
#-license


✨ Features
🧍‍♂️🧍‍♀️ Multi-Human Tracking

DBSCAN / CFAR clustering
ID assignment
Smooth trajectory tracking

🤕 Fall Detection

Height change analysis
Velocity & acceleration monitoring
Point-cloud dispersion changes
Threshold-based + ML‑ready architecture

⚙️ Real-Time Pipeline

Point-cloud parsing
Noise filtering
Feature extraction
Live visualization

🧩 Modular System
Customize:

Tracking algorithm
Fall detection logic
Radar configuration


📦 Installation
🔧 1. Clone Repository
git clone https://github.com/your-username/mmwave-human-tracking-fall-detection.git
cd mmwave-human-tracking-fall-detection
``
🧱 2. Create Virtual Environment
Shellpython3 -m venv venvsource venv/bin/activate     # Mac/Linuxvenv\Scripts\activate        # WindowsShow more lines
📚 3. Install Dependencies
Shellpip install -r requirements.txtShow more lines
📡 4. Connect mmWave Radar (Optional)

Place .cfg files in config/
Update config.json with your port settings


📐 System Architecture
+------------------+         +------------------+         +------------------+
|   mmWave Radar   | ----->  | Data Interface   | ----->  | Preprocessing    |
| (TI IWR/AWR)     |         | (UART/Serial)    |         |  Noise Filtering |
+------------------+         +------------------+         +------------------+
                                                                   |
                                                                   v
                                                          +------------------+
                                                          |  Clustering      |
                                                          | (DBSCAN/CFAR)    |
                                                          +------------------+
                                                                   |
                                                                   v
                                                          +------------------+
                                                          |   Tracking       |
                                                          |  ID Assignment   |
                                                          +------------------+
                                                                   |
                                                                   v
                                                          +------------------+
                                                          | Fall Detection   |
                                                          +------------------+
                                                                   |
                                                                   v
                                                          +------------------+
                                                          | Visualization    |
                                                          +------------------+


🔁 Flowchart: Tracking + Fall Detection
+-----------------------------+
|         Start System        |
+--------------+--------------+
               |
               v
+-----------------------------+
| Read Radar Point Cloud      |
+--------------+--------------+
               |
               v
+-----------------------------+
| Preprocess Data             |
+--------------+--------------+
               |
               v
+-----------------------------+
| Cluster Points (DBSCAN)     |
+--------------+--------------+
               |
               v
+-----------------------------+
| Track Objects (IDs)         |
+--------------+--------------+
               |
               v
+-----------------------------+
| Extract Movement Features   |
+--------------+--------------+
               |
               v
     +--------[ Fall? ]--------+
     |           |             |
     | Yes       | No          |
     v           v             |
+-------------+  +-------------+
| Fall Alert! |  | Continue    |
| Log Event   |  | Monitoring  |
+-------------+  +-------------+


📁 Dataset Documentation
📂 Folder Structure
data/
 ├── session_01/
 │     ├── pointcloud_0001.csv
 │     ├── pointcloud_0002.csv
 │     ├── labels.csv
 │     └── metadata.json
 ├── session_02/
 └── ...

📌 Point-Cloud Format (pointcloud_XXXX.csv)





























ColumnDescriptionxX coordinate (m)yY coordinate (m)zZ coordinate (m)dopplerRadial velocitysnrSignal-to-noise ratio
🏷️ Labels (labels.csv)

























FieldMeaningframe_idFrame numbernum_peopleDetected humansfall_event0=no fall, 1=fallbounding_idsOptional list of IDs

🚀 Running the System
Start main pipeline:
Shellpython main.py --config config/config.jsonShow more lines

📊 Visualization Tools
Launch real-time viewer:
Shellpython visualize.pyShow more lines
Features:

Live 3D scatter plot
Trajectory trails
Fall events highlighted


🤝 Contributing
PRs are welcome!
You can improve:

Tracking filters
Machine learning models
Visualization UI


📜 License
MIT License — free for personal + commercial use.
