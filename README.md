# Cogate-Hack-duino

# CoGate
Wearing mask, please enter!

[![Netlify Status](https://api.netlify.com/api/v1/badges/c019311c-de4d-420d-9bca-f37ac85ccc3b/deploy-status)](https://test-cogate.netlify.app/)

## How to use it?
- Download the Zip file. And store it in your local directory.

- As per the circuit diagram, connect the Arduino.

- Open CoGate folder in any HTML editor and go to sketch.js and change the COM Port according to your COM Port.

- Connect your device's serial port. [Download](https://github.com/p5-serial/p5.serialcontrol/releases)  and unzip p5.js serial control program. Connect your device to USB and run the p5.serialcontrol.exe (for Windows). You may have to set it allowed to run in your antivirus program.

- Employ the power of AI!

- Upload the code(below) to Arduino 

```cpp
#include <Servo.h>
  Servo myservo;
  char result;

  void setup() {
     Serial.begin(9600);
      myservo.attach(9);
     myservo.write(90);
  }

  void loop() {
      while (Serial.available() > 0) {
          result = Serial.read();
          switch (result) {
              case '2':
                   myservo.write(90); //With Mask
                 break;
         }
      }
      delay(100);
  } 
```
- Run the index.html and make sure that you are connected to internet.
- Now you are good to go! 


#### Thanks to Alan Wang
Check Alan Wang's Project and for more reference too: 
[Alan Wang](https://github.com/alankrantas/TeachableMachine-p5js-serialport)
