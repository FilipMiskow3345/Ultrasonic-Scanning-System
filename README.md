# Ultrasonic-Scanning-System
## Phase 1
During this phase I learnt the fundamentals of coding in Arduino and how a HC-SR04 sensor works, learnt how to wire it and how to make it display distances of objects in centimeters on the serial monitor of the software 

<img width="278.9" height="268.7" alt="unnamed" src="https://github.com/user-attachments/assets/39f1a93f-d61d-493d-be0e-ada853557925" />

Code: **Pin Configuration-** The trig and echo variables define the Arduino pins connected to the sensor. The trigger pin is set as an output while the echo pin is set as an input. **Instillation-** Serial.begin(9600) begins a serial communication at the speed of 9600 bits per second so the measured distance can be displayed on the serial monitor. **Ultrasonic Pulse-** The Arduino sends a short pulse through the trig pin by setting the pin to high then low with a very short delay, causing the sensor to emit an ultrasonic wave. **Echo measurement-** pulseIn(echo, HIGH) measures how long the echo pin stays HIGH while the reflected sound wave returns to the sensor, when the wave is detected the echo pin is set to LOW and the duration of that pulse is recorded. **Distance Calculation-** The measured time is multiplied by 343 (speed of sound in air) then by 100 ( to convert meters into centimeters) then divided by 1,000,000 (to convert microseconds into seconds) and finally divided by 2 ( as the current time is for the loop, sound wave hitting the object and reflecting) all together this equals 0.01715 rounded to 0.017

<img width="746" height="505" alt="image" src="https://github.com/user-attachments/assets/f09db779-2e68-4728-91d5-0332623c4749" />


Phase 1 Scanner Demonstration: (https://youtube.com/shorts/vN23DvDkqHc?feature=share)

No issues occurred during this phase, except later on the 0.017 multiplier is unrounded for greater precision

## Phase 2

