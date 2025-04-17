
# 🧾 ESP32 Programming Cheat Sheet

## 🔧 Setup Essentials
```cpp
// Start Serial
Serial.begin(115200);

// Set pin mode
pinMode(pin, INPUT);
pinMode(pin, OUTPUT);
pinMode(pin, INPUT_PULLUP);
```

---

## 💡 Digital I/O
```cpp
// Set pin HIGH or LOW
digitalWrite(pin, HIGH);
digitalWrite(pin, LOW);

// Read digital pin
int value = digitalRead(pin);
```

---

## 🌈 Analog Input
```cpp
// Read analog pin (0–4095)
int sensor = analogRead(pin);
```

---

## ⏱ Timing Functions
```cpp
// Pause code (not recommended for multitasking)
delay(ms);

// Track time without blocking
unsigned long now = millis();
if (now - previous >= interval) {
  previous = now;
  // do something
}
```

---

## 🖥 Serial Communication
```cpp
// Print to Serial Monitor
Serial.print("Value: ");
Serial.println(sensor);

// Read string input
if (Serial.available()) {
  String input = Serial.readStringUntil('\n');
}
```

---

## 🧪 Common Pins (ESP32 Dev Module)
| Function | GPIO |
|----------|------|
| Onboard LED | 2 |
| Analog Input | 32–39 |
| PWM Output | Most pins |
| I2C SDA | 21 |
| I2C SCL | 22 |

---

## 🛠 Useful Tips
- Use `INPUT_PULLUP` for buttons
- Analog values range from 0 (0V) to 4095 (3.3V)
- Avoid using `delay()` when reading inputs
- Use Serial Plotter for visualizing values
