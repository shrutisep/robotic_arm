#include <Servo.h>

// Define servo objects
Servo servo1, servo2, servo3, servo4, servo5;

// Potentiometer pins
const int pot1 = A0;
const int pot2 = A1;
const int pot3 = A2;
const int pot4 = A3;
const int pot5 = A4;

// Servo pins
const int servoPin1 = 5;
const int servoPin2 = 6;
const int servoPin3 = 7;
const int servoPin4 = 8;
const int servoPin5 = 9;

void setup() {
    // Attach servos to respective pins
    servo1.attach(servoPin1);
    servo2.attach(servoPin2);
    servo3.attach(servoPin3);
    servo4.attach(servoPin4);
    servo5.attach(servoPin5);
}

void loop() {
    // Read potentiometer values (0-1023) and map to servo angles (0-180)
    int angle1 = map(analogRead(pot1), 0, 1023, 0, 180);
    int angle2 = map(analogRead(pot2), 0, 1023, 0, 180);
    int angle3 = map(analogRead(pot3), 0, 1023, 0, 180);
    int angle4 = map(analogRead(pot4), 0, 1023, 0, 180);
    int angle5 = map(analogRead(pot5), 0, 1023, 0, 180);

    // Move servos to corresponding angles
    servo1.write(angle1);
    servo2.write(angle2);
    servo3.write(angle3);
    servo4.write(angle4);
    servo5.write(angle5);

    delay(15); // Small delay for smooth movement
}
