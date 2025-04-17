

# Day 5: Serial Dashboards & Input Control

## 🧭 Overview
No Wi-Fi? No problem! Today we’ll use the **Serial Monitor** and **Serial Plotter** to create interactive dashboards. You’ll simulate sensors, send commands, and display live feedback—all through USB.

## 🛠 What You Need
- ESP32 Dev Module
- Potentiometer or button (optional)
- LED
- Breadboard and jumper wires

## ⚙️ Concepts Introduced
- Serial input via `Serial.readString()`
- Serial output formatting
- Command-based control
- Real-time data display

## 🧪 Example: Serial Command Control

```cpp
void setup() {
  Serial.begin(115200);
  pinMode(2, OUTPUT);
}

void loop() {
  if (Serial.available()) {
    String input = Serial.readStringUntil('\n');
    input.trim();
    if (input == "on") {
      digitalWrite(2, HIGH);
      Serial.println("LED is ON");
    } else if (input == "off") {
      digitalWrite(2, LOW);
      Serial.println("LED is OFF");
    } else {
      Serial.println("Unknown command.");
    }
  }
}
```

## 🔍 How it Works
- You type commands into the **Serial Monitor**.
- ESP32 reads and matches them to perform actions.
- Feedback is sent back through the monitor.

## 📈 Serial Plotter for Visualization

```cpp
void setup() {
  Serial.begin(115200);
}

void loop() {
  int sensorValue = analogRead(34);
  Serial.println(sensorValue);
  delay(100);
}
```

Open **Tools > Serial Plotter** to see it as a graph.

## 🧪 Tinkering Ideas
- Create a menu-based system: “Type 1 for LED, 2 for sensor”
- Plot two values by printing them comma-separated: `Serial.println("val1,val2");`
- Build a quiz or prompt system in Serial

## 🏁 Wrap-Up
Today you:
- Simulated a dashboard using Serial Monitor
- Controlled the ESP32 with typed commands
- Visualized live sensor data without Wi-Fi

You’ve mastered offline control—perfect for prototyping!


---


# Day 5 Worksheet: Serial Dashboards

## 💡 Fill in the Blanks
1. `Serial.begin(__________)` starts serial communication.
2. `Serial.readStringUntil('\n')` reads input until a __________ character.
3. You can display real-time data graphically with the __________ __________ tool.

## 🔧 Code Review

```cpp
String input = Serial.readStringUntil('\n');
if (input == "blink") {
  digitalWrite(2, !digitalRead(2));
  Serial.println("Toggled LED!");
}
```

❓ What does this code do when you type “blink”?  
❓ What happens if you type something else?

## 🧪 Tinker Time!
- Add a command to make the LED blink 3 times
- Add a new command: “sayhi” prints “Hello from ESP32!”
- Plot potentiometer values with Serial Plotter

## ✏️ Reflection
- How could a serial interface be useful in real-world testing?
- What did you enjoy most about working with the ESP32 this week?

