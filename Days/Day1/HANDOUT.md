# Day 1: Blink & Basics

## 🧭 Overview
Welcome to Day 1 of your ESP32 journey! Today, you'll learn how to:
- Set up the Arduino IDE
- Connect and program your ESP32
- Upload your very first sketch: **Blink**

## 🛠 What You Need
- ESP32 Dev Module
- Micro USB Cable
- Arduino IDE installed
- Internet access

## ⚙️ Concepts Introduced
- What is a microcontroller?
- Digital output pins
- Serial Monitor

## 🧪 Your First Sketch: Blink
We’ll blink the onboard LED (usually on pin 2).

```cpp
void setup() {
  pinMode(2, OUTPUT);
}

void loop() {
  digitalWrite(2, HIGH); // LED ON
  delay(1000);           // Wait 1 second
  digitalWrite(2, LOW);  // LED OFF
  delay(1000);           // Wait 1 second
}
