# Smart-Stick
[**Documentation**](https://docs.google.com/document/d/12w1c4cRsSJCyFbMJEvaP4DbLqH0vjTlH6sluh3fQ2tE/edit?usp=sharing)

# Project Overview
<img src="https://github.com/geeky-auro/Smart-Stick/blob/main/Blind%20Stick.png" alt="Blind Stick Simulation">

![image](https://github.com/geeky-auro/Smart-Stick/assets/83534307/2fd5de74-45ff-4eb8-98da-9bb83e1a1073)


# Component's Used
| Name | Quantity | Component | Usage |
| --- | --- | --- | --- |
| U1 | 1 | Arduino Uno R3 | Microcontroller board for programming and controlling the project |
| DIST1 | 1 | Ultrasonic Distance Sensor (4-pin) | Measures the distance to an object using ultrasonic waves |
| M1 | 1 | Vibration Motor | Creates vibrations or motion for tactile feedback or other purposes |
| PIEZO1 | 1 | Piezo | Produces sound or tones, often used as a buzzer or speaker |

# Sketch
[Code](https://create.arduino.cc/editor/auro_saswat/bb488ffe-5e70-46ed-8887-d5209ca72599/preview)

# Code Explanation
This code is written in Arduino programming language, which is based on C/C++. It is designed to control an ultrasonic sensor for measuring the distance of an object and then react accordingly by turning on or off a buzzer and a motor based on the measured distance. Here is a breakdown of the code:

### Variable Declarations:
- trigPin: An integer variable used to define the pin number connected to the trigger pin of the ultrasonic sensor.
- echoPin: An integer variable used to define the pin number connected to the echo pin of the ultrasonic sensor.
- buzzer: An integer variable for the pin number attached to the buzzer.
- motorPin: An integer variable for the pin number connected to the motor.
- duration: A long variable to store the time between sending and receiving the sound pulse.
- distance: An integer variable to store the calculated distance.
- safetyDistance: An integer variable used to set a threshold distance at which the buzzer and motor are activated.

### setup() Function:
This is called when the Arduino board starts:
- pinMode(): Sets the mode of specified pins. trigPin and buzzer are set as OUTPUT because they send signals, while echoPin is set as INPUT to receive signals.
- Serial.begin(9600): Initializes serial communication at a baud rate of 9600, used for data transmission between the Arduino board and a computer or other devices.

### loop() Function:
This function runs continuously after setup() is finished:
- Sends a short high pulse to the trigPin to trigger the ultrasonic pulse. This is done by first setting it to LOW for a brief period (to ensure a clean pulse), then to HIGH for 10 microseconds, and back to LOW.
- pulseIn(echoPin, HIGH): Measures the duration of the incoming pulse. This is the time taken for the echo to be received after the sound wave is transmitted.
- The distance is calculated based on the duration of the echo. The speed of sound is approximately 340 meters per second (0.034 cm/µs), and since the sound has to travel to the object and back, the distance is half the product of the speed of sound and the time (duration).
- safetyDistance is then compared to a predefined value (30 in this case). If the calculated distance is less than or equal to safetyDistance, the buzzer and motor are turned on (set HIGH); otherwise, they are turned off (set LOW).
- Finally, the distance is printed to the Serial Monitor, which allows you to view the distance on your computer using the Arduino IDE.

In summary, this code continuously measures the distance using an ultrasonic sensor. If the object is within 200 cm, it activates a buzzer and a motor; otherwise, it deactivates them. This could be used in various applications like obstacle avoidance in robotics.

# Reference Research Articles
- [Smart Stick for Blind People](https://ieeexplore.ieee.org/abstract/document/9074374)
- [Smart Stick for the Blind and Visually Impaired People](https://ieeexplore.ieee.org/abstract/document/8473344) 
- [Smart Stick For the Blind Using Arduino](https://iopscience.iop.org/article/10.1088/1742-6596/1569/3/032088/meta) 
- [Multiple distance sensors based smart stick for visually impaired people](https://ieeexplore.ieee.org/abstract/document/7868407)
- [A Design review of Smart Stick for the Blind Equipped with Obstacle Detection and Identification using Artificial Intelligence](https://www.researchgate.net/profile/Balu-N-Ilag/publication/332379082_A_Design_review_of_Smart_Stick_for_the_Blind_Equipped_with_Obstacle_Detection_and_Identification_using_Artificial_Intelligence/links/5ceeb62d4585153c3da52dbc/A-Design-review-of-Smart-Stick-for-the-Blind-Equipped-with-Obstacle-Detection-and-Identification-using-Artificial-Intelligence.pdf)
