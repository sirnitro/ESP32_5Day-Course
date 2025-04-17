

# Day 3: Analog Sensors & Inputs

## 🧭 Overview
Today, we’ll introduce **analog input** — the ESP32’s ability to read values from the real world, like light, temperature, or twisty knobs. You’ll use `analogRead()` and visualize values in real time.

## 🛠 What You Need
- ESP32 Dev Module
- Potentiometer **or** photoresistor + 10kΩ resistor
- Breadboard and jumper wires

## ⚙️ Concepts Introduced
- Analog vs Digital
- `analogRead()` for voltage-based input
- Mapping values for control
- Serial Plotter visualization

## 🔌 Circuit Setup
- Potentiometer: one side to 3.3V, one side to GND, middle to GPIO 34
- Photoresistor: one side to 3.3V, other to a resistor to GND, junction to GPIO 34

## 🧪 Example Code: Read & Print

```cpp
const int sensorPin = 34;

void setup() {
  Serial.begin(115200);
}

void loop() {
  int value = analogRead(sensorPin);
  Serial.println(value);
  delay(100);
}
```

## 🔍 How it Works
- `analogRead(pin)` returns a value from **0 to 4095**
- 0 = 0V, 4095 = 3.3V
- You can use this to track light, position, sound, etc.

## 🖥 Visualizing with Serial Plotter
- Open **Tools > Serial Plotter**
- You’ll see your sensor data drawn like a graph
- Great for observing changes over time

## 🧪 Tinkering Ideas
- Dim an LED based on analog input
- Trigger an action if the value is too low/high
- Try multiple analog pins for fun combos

## 🏁 Wrap-Up
Today you:
- Read real-world data from a sensor
- Visualized analog values live
- Used sensor input to control logic

Tomorrow: timers and smarter decisions!


---


# Day 3 Worksheet: Analog Sensors

## 💡 Fill in the Blanks
1. `analogRead()` returns a number between __________ and __________.
2. 3.3V corresponds to a value of about __________.
3. A potentiometer is a type of __________ divider.

## 🔧 Code Analysis

```cpp
int light = analogRead(34);
if (light < 1000) {
  Serial.println("It's dark!");
} else {
  Serial.println("It's bright!");
}
```

❓ What is the code trying to detect?  
❓ What kind of sensor might be used here?

## 🧪 Tinker Time!
- Connect a potentiometer and print its value
- Add an `if` statement to light up the LED only when the value is > 2000
- Change the printout to say “Too much light!” when it’s too bright

## ✏️ Reflection
- What did you learn about analog inputs today?
- What are some real-world examples of analog sensors?

