# ⚙️ DC Motor Speed Control Using Arduino  
**5th Semester Project**  
**Duration:** August 2022 – December 2022  
**Institution:** Sukkur IBA University  
**Department:** Electrical Engineering  
**Course:** Electrical Machines  
**Instructor:** Dr. Qasim Ali  

---

## 👥 Group Members
- Wakeel Ahmed (CMS ID: 033-19-0026)  
- Bhai Khan (CMS ID: 033-19-0015)  

---

## 📌 Project Overview  
In this project, we designed and implemented a method to control the **speed** and **direction** of a DC motor using **Arduino UNO**. This was done **without using any motor driver IC**, instead leveraging a **PN2222 transistor** and **PWM** control via Arduino.

The project focuses on:
- Spinning the DC motor via digital output
- Controlling speed using analog PWM values
- Basic transistor-based switching mechanism

---

## 🧰 Components Used

| Component         | Quantity |
|------------------|----------|
| Arduino UNO       | 1        |
| PN2222 Transistor | 1        |
| 270 ohm Resistor  | 1        |
| 1N4001 Diode      | 1        |
| Breadboard        | 1        |
| Jumper Wires      | As required |
| DC Motor          | 1        |

---

## 🔌 Circuit Diagram  
<img src="images/schematic.png" width="500">

### ⚠️ Precautions
- The **flat side** of the transistor must face toward the Arduino.
- The **striped end** of the diode should connect to the **+5V line**.

---

## ⚙️ Working Principle

- To spin the motor, Arduino pin 3 is connected to the transistor's base. Using `digitalWrite`, the transistor is switched on or off.
- To **control speed**, `analogWrite` is used instead. A PWM value between 0 (stop) and 255 (full speed) is sent.
- Direction control can be added using an **H-bridge** or **L298 Motor Driver IC**.

---

## 💻 Code

### A. Spin Motor at Full Speed
```cpp
int motorPin = 3;

void setup() {
  pinMode(motorPin, OUTPUT);
}

void loop() {
  digitalWrite(motorPin, HIGH); // Motor ON
  delay(3000);
  digitalWrite(motorPin, LOW);  // Motor OFF
  delay(3000);
}
```

### B. Control Motor Speed with PWM
```cpp
int motorPin = 3;
int speedValue = 150; // Range: 0 to 255

void setup() {
  pinMode(motorPin, OUTPUT);
}

void loop() {
  analogWrite(motorPin, speedValue); 
}
```

---

## 🧠 Conclusion

- We successfully used **Arduino UNO and a transistor** to spin a DC motor.
- **Digital HIGH/LOW** controlled ON/OFF of the motor.
- **Analog PWM** values allowed smooth speed control.
- Future improvement: add **direction control** using H-bridge or L298 driver.

---

## 🔗 References

- [TutorialsPoint – DC Motor Control](https://www.tutorialspoint.com/arduino/arduino_dc_motor.htm)  
- [Slideshare – Speed Control of DC Motor](https://www.slideshare.net/mafazahmed/speed-control-of-dc-motor)  
- [ElectronicsHub](https://www.electronicshub.org/speed-and-direction-control-of-dc-motor-using-arduino/)

---

## 📂 Project Structure

```
DC-Motor-Speed-Control-Arduino/
│
├── README.md
├── code/
│   ├── Spin_Control.ino
│   └── Speed_Control.ino
├── images/
│   └── schematic.png
├── docs/
│   └── DC_Motor_Project_Report.pdf
```

---

> 🛠️ *This project was completed as part of the Electrical Machines course in Fall 2022 at Sukkur IBA University.*
