

# Day 2: Inputs & Buttons

## 🧭 Overview
Today, you’ll learn how to receive **input** from the world around your ESP32—starting with a button. You’ll write code that lets your ESP32 *react*.

## 🛠 What You Need
- ESP32 Dev Module
- Momentary push button
- 10kΩ resistor (if using pull-down configuration)
- Breadboard and jumper wires

## ⚙️ Concepts Introduced
- Digital input pins
- Pull-up vs pull-down resistors
- `digitalRead()` and conditionals

## 📶 Circuit Setup
- Connect one side of the button to **GND**
- Connect the other side to **GPIO 12**
- Enable internal pull-up in software

## 🧪 Example Code: Button LED Control

```cpp
const int buttonPin = 12;
const int ledPin = 2;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP);  // Internal pull-up enabled
  pinMode(ledPin, OUTPUT);
}

void loop() {
  int buttonState = digitalRead(buttonPin);
  if (buttonState == LOW) {
    digitalWrite(ledPin, HIGH);  // Turn on LED if button pressed
  } else {
    digitalWrite(ledPin, LOW);   // Turn off LED otherwise
  }
}
```

## 🔍 How it Works
- We use `INPUT_PULLUP` to avoid needing an external resistor.
- A pressed button connects to GND, pulling the input LOW.
- ESP32 checks button state and responds accordingly.

## 🧪 Tinkering Ideas
- Make the LED toggle with each press (requires logic/state tracking)
- Control multiple LEDs with multiple buttons
- Use serial output to print “Pressed!” each time

## 🏁 Wrap-Up
Today you learned:
- How to read a button input
- How to use pull-up logic
- How to control output based on input

Tomorrow: analog sensors and *feeling* the world!


---


# Day 2 Worksheet: Inputs & Buttons

## 💡 Fill in the Blanks
1. `pinMode(buttonPin, __________);` enables the internal pull-up resistor.
2. When a button connects to GND and is pressed, `digitalRead()` returns `__________`.
3. Which function reads the state of a digital pin? `__________`

## 🔧 Code Debugging
What does this code do?

```cpp
const int buttonPin = 14;
void setup() {
  pinMode(buttonPin, INPUT_PULLUP);
  Serial.begin(115200);
}

void loop() {
  if (digitalRead(buttonPin) == LOW) {
    Serial.println("Pressed!");
  } else {
    Serial.println("Not pressed");
  }
}
```

❓ What will appear in the Serial Monitor if nothing is connected to GPIO14?  
❓ Why might that be a problem?

## 🧪 Tinker Time!
Try these:
- Make a button turn on the onboard LED
- Add a second button that *turns it off*
- Make the LED toggle on/off each time the button is pressed

## ✏️ Reflection
- What was tricky about using buttons with `INPUT_PULLUP`?
- What real-world devices might use this logic?

