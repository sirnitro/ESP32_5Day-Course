
# Day 1: Blink & Basics

## 📘 Handout

### 🧭 Overview
Welcome to Day 1 of your ESP32 journey! Today, you'll learn how to:
- Set up the Arduino IDE
- Connect and program your ESP32
- Upload your very first sketch: **Blink**

### 🛠 What You Need
- ESP32 Dev Module
- Micro USB Cable
- Arduino IDE installed
- Internet access

### ⚙️ Concepts Introduced
- What is a microcontroller?
- Digital output pins
- Serial Monitor

### 🧪 Your First Sketch: Blink
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
```

### 🔍 How it Works
- `setup()` runs once at startup.
- `loop()` runs over and over forever.
- `pinMode()` sets the pin type (input/output).
- `digitalWrite()` sets pin HIGH or LOW.
- `delay(ms)` pauses execution.

### 🖥 Serial Monitor (Bonus)
Add this to setup to say hello:

```cpp
Serial.begin(115200);
Serial.println("Hello from your ESP32!");
```

### 🏁 Wrap-Up
You’ve:
- Installed the tools
- Flashed your first sketch
- Learned how microcontrollers “think”

Tomorrow: buttons and interactive input!

---

## 🧠 Worksheet

### 💡 Fill in the Blanks
1. The function that runs once is called `__________()`.
2. `digitalWrite(2, _______)` turns the LED **on**.
3. `delay(1000)` waits for how long? __________

### 🔧 Code Analysis
What does this code do?

```cpp
void setup() {
  pinMode(4, OUTPUT);
}

void loop() {
  digitalWrite(4, HIGH);
  delay(500);
  digitalWrite(4, LOW);
  delay(500);
}
```

❓ Which pin is used for the LED?  
❓ How fast does it blink?

### 🧪 Tinker Time!
Try one or more:
- Change the blink rate
- Try a different pin
- Use Serial Monitor to say something each time the LED changes

### ✏️ Reflection
Write 2–3 sentences:
- What surprised you about uploading to the ESP32?
- What would you like to build with LEDs?

---

## 💾 Code File: Day1_Blink.ino

```cpp
// Day 1: Blink Sketch
void setup() {
  pinMode(2, OUTPUT);
  Serial.begin(115200);
  Serial.println("ESP32 says hello!");
}

void loop() {
  digitalWrite(2, HIGH);
  delay(1000);
  digitalWrite(2, LOW);
  delay(1000);
}
```
