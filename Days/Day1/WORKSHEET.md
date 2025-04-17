
---

### 🧠 [Worksheet - Markdown]
```markdown
# Day 1 Worksheet: Blink & Basics

## 💡 Fill in the Blanks
1. The function that runs once is called `__________()`.
2. `digitalWrite(2, _______)` turns the LED **on**.
3. `delay(1000)` waits for how long? __________

## 🔧 Code Analysis
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
