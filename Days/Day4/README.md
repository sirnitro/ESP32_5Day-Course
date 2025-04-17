

# Day 4: Timing & Smarter Logic

## 🧭 Overview
Today, you’ll learn how to make your ESP32 think with more nuance—without freezing up using `delay()`. We’re diving into timing logic with `millis()`, conditions, and simple state tracking.

## 🛠 What You Need
- ESP32 Dev Module
- LED
- Button (optional)
- Breadboard and jumper wires

## ⚙️ Concepts Introduced
- `millis()` vs `delay()`
- State machines (basic form)
- Comparison operators: `<`, `>`, `==`, `!=`
- Timed events

## 🧪 Example Code: Non-blocking Blink

```cpp
const int ledPin = 2;
unsigned long previousMillis = 0;
const long interval = 1000;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  unsigned long currentMillis = millis();
  if (currentMillis - previousMillis >= interval) {
    previousMillis = currentMillis;
    digitalWrite(ledPin, !digitalRead(ledPin)); // Toggle LED
  }
}
```

## 🔍 How it Works
- `millis()` returns the number of milliseconds since the board started.
- We check whether enough time has passed to toggle something.
- `delay()` pauses everything—`millis()` lets everything *keep running*.

## 🧠 Smarter Logic Examples
- Turn on a fan if a sensor reads hot **and** it's been hot for 5 seconds.
- Auto-shutoff for a light 10 seconds after a button is pressed.
- Countdown timer using `millis()`.

## 🧪 Tinkering Ideas
- Add a button that resets a timer
- Flash different LEDs at different rates
- Use `millis()` to time how long a button is held down

## 🏁 Wrap-Up
Today you:
- Replaced `delay()` with `millis()`
- Built non-blocking timed actions
- Learned to use logic and states more powerfully

Tomorrow: Wi-Fi and the web!


---


# Day 4 Worksheet: Timing & Logic

## 💡 Fill in the Blanks
1. `millis()` returns __________ since the board turned on.
2. `delay()` __________ the entire processor, stopping all code during that time.
3. `if (millis() - start >= duration)` is an example of a __________ check.

## 🔧 Code Debugging

```cpp
const int led = 2;
unsigned long lastToggle = 0;
void setup() {
  pinMode(led, OUTPUT);
}
void loop() {
  if (millis() > lastToggle + 2000) {
    digitalWrite(led, !digitalRead(led));
  }
}
```

❓ What’s wrong with this code?  
❓ How can you make the blink work continuously?

## 🧪 Tinker Time!
- Make an LED flash every 3 seconds using `millis()`
- Add a button: pressing it resets the flash timer
- Time how long a button is held and use that value to adjust LED brightness

## ✏️ Reflection
- How did `millis()` change the way you thought about timing?
- Why is non-blocking code important in real-world projects?

