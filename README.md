# Ultrasonic-Scanning-System
## Phase 1
During this phase I learnt the fundamentals of coding in Arduino and how a HC-SR04 sensor works, learnt how to wire it and how to make it display distances of objects in centimeters on the serial monitor of the software 

<img width="278.9" height="268.7" alt="unnamed" src="https://github.com/user-attachments/assets/39f1a93f-d61d-493d-be0e-ada853557925" />

Code: **Pin Configuration-** The trig and echo variables define the Arduino pins connected to the sensor. The trigger pin is set as an output while the echo pin is set as an input. **Instillation-** Serial.begin(9600) begins a serial communication at the speed of 9600 bits per second so the measured distance can be displayed on the serial monitor. **Ultrasonic Pulse-** The Arduino sends a short pulse through the trig pin by setting the pin to high then low with a very short delay, causing the sensor to emit an ultrasonic wave. **Echo measurement-** pulseIn(echo, HIGH) measures how long the echo pin stays HIGH while the reflected sound wave returns to the sensor, when the wave is detected the echo pin is set to LOW and the duration of that pulse is recorded. **Distance Calculation-** The measured time is multiplied by 343 (speed of sound in air) then by 100 ( to convert meters into centimeters) then divided by 1,000,000 (to convert microseconds into seconds) and finally divided by 2 ( as the current time is for the loop, sound wave hitting the object and reflecting) all together this equals 0.01715 rounded to 0.017

<img width="746" height="505" alt="image" src="https://github.com/user-attachments/assets/f09db779-2e68-4728-91d5-0332623c4749" />


Phase 1 Scanner Demonstration: (https://youtube.com/shorts/vN23DvDkqHc?feature=share)

No issues occurred during this phase, except later on the 0.017 multiplier is unrounded for greater precision

## Phase 2
During this phase I learnt and then brought all the components together and developed the code further, all the components in the end were working but were not physically assembled, in this phase the LCD display or custom brackets were not included

<img width="268" height="372" alt="image" src="https://github.com/user-attachments/assets/2a3a4dc9-69d0-44a2-8a1e-15a9de4ab2cc" />

Code:**Servo Control-** The servo library is included to control the SG90 servo motor. The servo is attached to pin 3, allowing the Arduino to move it to specific angles using myservo.write(deg). **Scanning Movement-** A for loop moves the servo from 0 degrees to 180 degrees, increasing the angle by 1 degree at a time. A short delay allows the servo to move before the sensor takes each measurement. **Return Scanning-** A second for loop moves the servo from 180 degrees back to 0 degrees. Together these loops create a continuous back and forth scanning motion. **Distance measurement-** same as phase 1. **Conditional Distance Detection-** The code uses if and else if statements to compare the measured distance against set thresholds. Allowing the system to respond differently depending on how close an object is. **LED Indicators-** The Arduino changes the RGB LEDs colours according to the detected distance, a green LED represents detected objects being further away then 40 centimetres, an amber LED represents a detected object within 40-12 cm and red represents a detected object closer then 12 centimetres. **Buzzer Response-** The buzzer creates a noise with the tone() function dependent on how close the object is if its further then 40 centimetres then there is no sound, if the detected object is 40-12 centimetres a lower tone sound is played and for objects detected closer than 12 centimetres a high pitch sound is played. **Continuous Operation-** Since the scanning loops are inside loop() all these steps are repeated until the Arduino loses power.

<img width="411" height="610" alt="image" src="https://github.com/user-attachments/assets/74b9bc87-cbbc-4f8a-9351-b472aa664952" /> <img width="403" height="515" alt="image" src="https://github.com/user-attachments/assets/8a1f4f9f-67d0-4af7-a189-60b59e953638" />

Phase 2 Scanner Demonstration:(https://youtu.be/3dA9U286-8o)

Issues: RGB LED would not work, reason was a resistor was loose in the breadboard, another issue was poor cable management and assemble leading to the setup being confusing and hard and unpractical

## Phase 3 
The final phase, focused on assembling the complete system and improving its layout, stability and usability 

Improvements- Added an LCD to display distance measurements, Improved cable management and made the setup more compact, added custom mounts and brackets, improved the scanners physical stability
