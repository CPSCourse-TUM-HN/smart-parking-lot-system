# Smart Parking Lot System 🚗🅿

An IoT-based *automated parking management system* built on a *Raspberry Pi 5*.  
The system integrates *license plate recognition, real-time parking availability detection, automated gate control, and ultrasonic sensor* to provide a seamless parking experience.

## 📌 Features
- *Automated Gate Control*
    - Servo motor gate controlled by Raspberry Pi
    - Opens automatically for authorized vehicles via License Plate Recognition (LPR)
    - Exit gate opens automatically when a vehicle approaches (detected by ultrasonic sensor)

- *License Plate Recognition (LPR)*
    - Uses camera + EasyOCR to recognize plates in real time
    - Grants access only to vehicles with authorized plates

- *Parking Space Monitoring*
    - Dedicated camera monitors predefined parking spots
    - Image processing with OpenCV to detect occupied vs free spaces
    - Availability displayed on *LCD screen at entrance* (e.g., “Empty spaces: 2”)

## 🛠 System Architecture

*Hardware*
- Raspberry Pi 5
- Servo motor (for entrance/exit gate)
- Ultrasonic sensor (for exit detection)
- 2x Cameras (LPR + Parking lot monitoring)
- LCD Display
- Breadboard, resistors, jumper wires

*Software*
- Python 3
- OpenCV (image processing)
- EasyOCR (license plate recognition)
- RPi.GPIO + gpiozero (hardware control)
- Multithreading for parallel task management

## 📂 Project Structure
├── MainManager.py # Entry point – initializes and coordinates managers  
├── ParkingLotManager # Handles parking space detection + LCD updates  
├── LPRManager # License plate recognition and gate access control  
├── GateManager # Controls servo motor gate  
├── UltrasonicSensorManager # Handles ultrasonic car detection at exit  
├── requirements.txt # Python dependencies  
└── README.md # Documentation


## 🚀 Installation & Setup

1. *Clone this repository*

2. *Install dependencies*

3. *Connect hardware* : like shown in our presentation <br>
    For extra, check out: https://learn.voltaat.com/tutorials/how-to-use-ultrasonic-sensor-with-raspberry-pi-5
    https://learn.voltaat.com/tutorials/how-to-controll-a-servo-motor-with-raspberry-pi-5

5. *Run the MainManager.py*

## 📖 Usage

- On system start, *background parking lot frame is captured* → all spots must be empty at this time
- Vehicle approaches entrance → *camera scans plate*
    - If *authorized*, gate opens (servo motor)
    - Else, “UNKNOWN PLATE” is displayed  and access is denied
- Inside, parking camera updates *free space count* in real time and displays it on LCD at the entrance
- At exit, ultrasonic sensor detects car → gate opens automatically

## 🔮 Future Improvements

- Cloud-based database for authorized plates
- Mobile app for remote parking reservation
- Payment integration (e.g., QR code)

## 👨‍ Links
- Presentation: https://www.canva.com/design/DAGxWguKL7k/bwEL6-hzl0Xvzvregf7PWA/view?utm_content=DAGxWguKL7k&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=hf090097a75
- Video: https://drive.google.com/file/d/1fABJYouk212EobbKSyIVoGG0b6SzOfHl/view?usp=sharing
- Animation: https://drive.google.com/file/d/1JEy--Q0mIUG9SozQGVx-62XzAKyMxZDw/view?usp=sharing

## 👨‍💻 Contributors

- Andrei Koshelev
-  Boryana Buyuklieva
- Dart Musta
- Jana Elagamy
- Loran Pllana
- Mariya Kezdekbayeva
- Volodymyr Cherednychenko
