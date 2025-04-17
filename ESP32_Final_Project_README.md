
# 🧪 Final Project: Serial-Controlled Sensor Dashboard

## 🏁 Project Goal
Create a **Serial Dashboard** where you can:
- View real-time sensor values
- Control outputs like LEDs
- Interact through commands (e.g., “on”, “off”, “status”)

This project reinforces **everything** you've learned in the past 5 days—and works *without* Wi-Fi!

---

## 🛠️ What You'll Need
- ESP32 Dev Module
- Potentiometer or analog sensor (connected to GPIO 34)
- 1x LED (connected to GPIO 2)
- Breadboard + Jumper wires
- USB cable and computer with Arduino IDE

---

## ⚙️ Core Concepts Used
- `analogRead()` for sensor input
- `Serial.begin()` for communication
- `Serial.readStringUntil()` for command parsing
- `digitalWrite()` to control outputs
- `millis()` for non-blocking logic

---

## 🧩 System Overview

```text
User types a command in Serial Monitor ──► ESP32 reads input
                                  │
    +-----------------------------┼------------------------------+
    │                             │                              │
"on" command                 "off" command               "status" command
│                             │                              │
LED turns ON            LED turns OFF        Prints current analog sensor value
```

---

## 💻 Code Walkthrough

```cpp
const int sensorPin = 34;
const int ledPin = 2;

void setup() {
  Serial.begin(115200);
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // Print sensor value periodically
  static unsigned long lastRead = 0;
  if (millis() - lastRead > 1000) {
    lastRead = millis();
    int sensorVal = analogRead(sensorPin);
    Serial.print("Sensor: ");
    Serial.println(sensorVal);
  }

  // Read command from serial
  if (Serial.available()) {
    String input = Serial.readStringUntil('\n');
    input.trim();

    if (input == "on") {
      digitalWrite(ledPin, HIGH);
      Serial.println("LED turned ON");
    } else if (input == "off") {
      digitalWrite(ledPin, LOW);
      Serial.println("LED turned OFF");
    } else if (input == "status") {
      int val = analogRead(sensorPin);
      Serial.print("Current Sensor Value: ");
      Serial.println(val);
    } else {
      Serial.println("Unknown command. Try: on, off, status");
    }
  }
}
```

---

## 🧪 Challenge Upgrades (Optional)
- 🔁 Add a “blink” command that flashes the LED 3x
- 🌡️ Add thresholds: e.g., if sensor > 3000, automatically turn LED on
- ⏱️ Use `millis()` to make the LED toggle every few seconds in “auto” mode
- 🧭 Display a menu on boot with all available commands

---

## 🎓 What You’ve Mastered
✅ Inputs  
✅ Outputs  
✅ Analog sensors  
✅ Serial communication  
✅ Non-blocking logic  
✅ User interaction  
✅ A complete, testable embedded system

You're now officially **ESP32-empowered**. Go forth and build! 🔧💡
