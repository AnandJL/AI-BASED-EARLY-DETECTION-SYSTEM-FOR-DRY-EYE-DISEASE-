# How to Run the System (Execution Guide)
> Follow these steps in order to properly initialize the cloud, hardware, frontend, and AI backend without experiencing serial port conflicts.

## Step 1: Connect to Firebase

> Navigate to your Firebase Console and generate a new Private Key (.json file) from Project Settings > Service Accounts.

> Place the downloaded .json file into the root directory of your project.

> Open PROJECT.py and ensure the databaseURL and the credential path accurately point to your Firebase project.

## Step 2: Flash the ESP32 Hardware

> Connect your ESP32 microcontroller to your PC via a USB cable.

> Open the Arduino IDE and load your ESP32 hardware script.

 Go to Tools > Port and select the active COM port for your ESP32 (e.g., COM4).

> Click Upload to push the code to the ESP32 board.

IMPORTANT: Once the upload is complete, close the Arduino IDE completely (or at least close the Serial Monitor). If you leave it open, it will block the serial port, and the Python script will crash when trying to trigger the humidifier!

## Step 3: Launch the Clinical Dashboard

> Open the project folder in VS Code.

> Right-click on index.html and select Open with Live Server to launch the real-time cloud dashboard in your browser.

> Note on Navigation: The live dashboard handles real-time telemetry. You can click the "Patient History" button in the top right to navigate to history.html, which will dynamically load past session data and Matplotlib/Chart.js graphs for recognized patients.

## Step 4: Execute the AI Processing Engine

> Open a new terminal instance in your project directory (or use the VS Code integrated terminal).

> Run the main AI tracking script:

### python PROJECT.py -p shape_predicotr_68_landmarks.dat

> Look at your webcam. If you are an unregistered user, press "r" follow the terminal prompts to register your face. If recognized, the system will instantly begin monitoring your blink rate, updating Firebase, and standing by to trigger the ESP32!

> Press "h" or "l" to increase or decrease the longetivity of the humidification respectively. Each 10 % increase confine to 1 second increase in duration of spray.

> Press "q" to end the program .
