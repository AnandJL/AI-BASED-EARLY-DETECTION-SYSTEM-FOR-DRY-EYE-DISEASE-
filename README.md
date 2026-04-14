# AI-BASED-EARLY-DETECTION-SYSTEM-FOR-DRY-EYE-DISEASE-
End-to-end IoT &amp; Computer Vision system for Dry Eye detection using Python, OpenCV, Firebase, and an ESP32 hardware response.

> **Why This Project Matters: The Impact of Dry Eye Disease**
> In today’s digital-first world, prolonged screen exposure has drastically reduced our natural blink rates, leading to a silent epidemic of Dry Eye Disease (DED). Beyond chronic burning, redness, and blurred vision, untreated DED can cause irreversible corneal scarring. Furthermore, severe ocular fatigue often triggers "microsleeps"—brief, involuntary lapses in consciousness that destroy workplace productivity and pose severe safety risks.
> 
> **The Paradigm Shift:** Traditional healthcare treats visual fatigue *after* the symptoms become painful. This project shifts the paradigm to **proactive, closed-loop care**. By tracking ocular morphology in real-time, this system not only alerts users to dangerous fatigue but actually *fixes the environment* by autonomously triggering a physical humidifier to restore ambient moisture before damage occurs.


# PREREQUISITES

> Note: You will need the shape_predictor_68_face_landmarks.dat file to run this system.
 Download it [here](https://www.google.com/search?q=http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2), extract it, and place it in the root directory.

## <b> 1. Computer Vision & Math Engine <b>

> pip install opencv-python numpy scipy imutils

## <b> 2. Face Recognition <b>

> pip install cmake

> pip install dlib

> pip install face-recognition

## <b> 3. Clinical Data Visualization <b>

> pip install matplotlib


# Tools & Technologies

> Python –  Core application logic, edge processing, and backend AI pipeline.

> OpenCV & dlib – Real-time video frame capture, image processing, and 68-point facial landmark extraction.

> NumPy & SciPy – Mathematical computations, array structuring, and calculating Euclidean distances for the Eye Aspect Ratio (EAR).

> face_recognition – Deep learning-based facial authentication for the Smart Identity Lock system.

> Firebase (Realtime Database) – Asynchronous cloud synchronization, IoT data management, and live telemetry hosting.

> HTML5, CSS3 & Vanilla JavaScript – Development of the responsive, zero-reload clinical web dashboard.

> Chart.js & Matplotlib – Generating dynamic historical medical graphs and session data visualizations.

> ESP32 & PySerial – Edge microcontroller processing and serial communication for automated hardware actuation.

> VS Code / Anaconda – Primary development environment and Python package management.


<img width="843" height="730" alt="image" src="https://github.com/user-attachments/assets/1a8516e7-cf30-4904-8f2b-87c0bb93add5" />

# Project Workflow / Steps

## <b> 1. User Registration & Authentication

> Captured initial facial profiles using the webcam and face_recognition library.

> Implemented a Smart Identity Lock to verify the user continuously and prevent imposter data logging.

## <b> 2. Computer Vision & Frame Processing

> Initialized real-time video capture using OpenCV.

> Converted frames to grayscale and applied dlib to extract 68-point facial landmarks.

<img width="652" height="555" alt="image" src="https://github.com/user-attachments/assets/41feb71d-3d07-4cb8-833e-ca284045fe2f" />


## <b> 3. Clinical Metric Calculation

> Computed the Eye Aspect Ratio (EAR) using Euclidean distance mathematics (SciPy).

> Tracked consecutive frames to classify natural blinks, calculate Blinks Per Minute (BPM), and identify extended microsleep events.

<img width="682" height="158" alt="image" src="https://github.com/user-attachments/assets/9bc7bec3-16bc-407d-8103-9022f0b63669" />


## <b> 4. Hardware Automation & Edge Actuation

> Evaluated active BPM against clinical thresholds (Healthy, Moderate, Severe).

> Transmitted serial commands (PySerial) to the ESP32 microcontroller when severe dry eye was detected.

> Actuated a 5V relay to trigger the physical room humidifier and read environmental data via a DHT11 sensor.

<img width="474" height="209" alt="image" src="https://github.com/user-attachments/assets/b1202b6d-b0b0-42ae-963a-f88e61cad499" />


## <b> 5. Cloud Data Synchronization

> Formatted processed metrics (BPM, Dry Eye Events, Temperature, Humidity) into JSON payloads.

> Pushed telemetry asynchronously to a Firebase Realtime Database at 3-second intervals.

## <b> 6. Dashboard Development

> Fetched real-time cloud data into a Vanilla JS frontend using Firebase onValue listeners.

> Designed dual-view interfaces (Live Telemetry & Patient History) to visualize real-time hardware status and historical medical graphs via Chart.js.

## <b> Clinical Web Dashboard

> The web-based dashboard provides a dual-view interface, allowing users to monitor live ocular health and review longitudinal analytics.

<img width="1895" height="899" alt="Screenshot 2026-04-10 214017" src="https://github.com/user-attachments/assets/cf0c57c9-b913-4434-bd9e-4fa392281c73" />
<img width="1895" height="906" alt="Screenshot 2026-04-10 214101" src="https://github.com/user-attachments/assets/bb9707d6-8ac2-41a6-9735-e6e5b51bea77" />


### Features include:

> Live KPI Indicators: Real-time active BPM, Dry Eye Event count, and environmental conditions.

> Hardware Telemetry: Live visualization of the ESP32 humidifier relay status (Active/Standby).

> Interactive Historical Graphs: Dual-axis Chart.js plots comparing average BPM against isolated dry eye events over time.

> Dynamic Alerts: High-priority visual overlays triggered by severe microsleep detections.

# Key Results & Insights

> Some of the main outcomes of the system include:

> Real-Time Intervention: Successfully closed the loop between software detection and physical hardware mitigation for Dry Eye Disease.

> Zero-Trust Data Integrity: The Smart Identity Lock successfully prevented cross-contamination of medical data between multiple users sharing the same workstation.

> Accurate Ocular Tracking: The custom EAR thresholding reliably filtered out facial movements and isolated genuine blinks and fatigue events.

# Future Improvements

> Deploy the cloud dashboard to a dedicated hosting service (e.g., Vercel or Firebase Hosting).

> Implement advanced Deep Learning models (e.g., CNNs) to detect actual sclera redness alongside blink rates.

> Integrate a dedicated secure portal for medical professionals to download patient CSV reports.

> Expand environmental controls to adjust screen brightness automatically based on room conditions.


