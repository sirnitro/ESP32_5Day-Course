
# 👩‍🏫 Instructor’s Guide: 5-Day ESP32 Programming Course

Welcome to your guide for running the 5-day ESP32 Basics Bootcamp! This resource will help you facilitate each session with structure, timing tips, troubleshooting guidance, and extension ideas.

---

## 📋 General Course Structure

- **Audience**: Beginners (ages 13+, adult learners, hobbyists)
- **Session Duration**: 1 hour/day × 5 days
- **Delivery Format**: Hands-on, demo-led, project-based
- **Environment**: Offline-friendly (no Wi-Fi required)

---

## 🧰 Daily Breakdown

### 🟦 **Day 1: Blink & Basics**
**Objectives**:
- Install Arduino IDE
- Upload first sketch
- Understand `setup()`, `loop()`, `digitalWrite()`, `delay()`

**Instructor Tips**:
- Have sample ESP32 pre-programmed with Blink as a visual hook
- Walk through IDE installation and board setup slowly
- Reinforce pin numbers (GPIO) vs. physical pins

**Common Issues**:
- Drivers missing (especially Windows)
- Wrong board or COM port selected

**Time Guide**:
- 10 min setup + tools
- 15 min Blink walkthrough
- 20 min modify Blink, Serial intro
- 15 min Q&A + worksheet

---

### 🟩 **Day 2: Inputs & Buttons**
**Objectives**:
- Use digital inputs with buttons
- Learn `INPUT_PULLUP`
- Control LED based on input state

**Instructor Tips**:
- Show pull-up resistor logic with drawing or simulation
- Use large buttons or colorful ones for engagement
- Live-code the demo with student input

**Common Issues**:
- Loose wires causing ghost readings
- Misunderstanding LOW = pressed when using pull-up

**Time Guide**:
- 10 min review + wiring
- 20 min live build
- 20 min modify & test
- 10 min reflection

---

### 🟨 **Day 3: Analog Inputs**
**Objectives**:
- Use `analogRead()`
- Plot sensor values
- Map values to logic

**Instructor Tips**:
- Let students guess values before plotting
- Encourage use of Serial Plotter for engagement
- Emphasize 0–4095 range and what it means

**Common Issues**:
- Using GPIOs that don’t support analogRead
- Not grounding sensor circuits properly

**Time Guide**:
- 10 min setup
- 15 min potentiometer or photoresistor demo
- 20 min tinkering (trigger threshold)
- 15 min worksheet + Q&A

---

### 🟥 **Day 4: Timing & Logic**
**Objectives**:
- Understand `millis()` vs `delay()`
- Implement time-based actions
- Explore state changes and logic blocks

**Instructor Tips**:
- Live show blinking without `delay()`
- Use analogy: stopwatch vs sleep
- Link timing logic to real-world devices (motion lights, thermostats)

**Common Issues**:
- Forgetting to reset `previousMillis`
- Using `delay()` and `millis()` together incorrectly

**Time Guide**:
- 15 min review + demo
- 20 min guided coding
- 15 min experiment with timers
- 10 min wrap-up discussion

---

### 🟪 **Day 5: Serial Dashboards (Offline)**
**Objectives**:
- Use `Serial.readStringUntil()`
- Create command-driven interface
- Display and interact with sensor data via Serial

**Instructor Tips**:
- Show “terminal control” as a cool hacker vibe
- Use reflection to tie all 5 days together
- Encourage customization (“name your ESP32”)

**Common Issues**:
- Students forget to open Serial Monitor
- Typing errors in commands

**Time Guide**:
- 10 min warm-up + recap
- 20 min live command-response sketch
- 20 min add logic or sensor plotting
- 10 min course recap + preview final project

---

## 🧪 Final Project Options
**Title**: Serial-Controlled Sensor Dashboard  
**Objective**: Combine analog sensing, digital output, and serial control into one coherent system.

**Support**:  
- Provide scaffolded code  
- Let them design their own interface wording  
- Add optional challenges for advanced learners  

---

## 🧭 Teaching Tips

- **Celebrate small wins**: Uploading code is exciting for beginners!
- **Visual feedback**: LEDs and serial messages make actions tangible.
- **Check wiring first**: 90% of student bugs are physical connection issues.
- **Use reflection prompts**: Encourage students to connect the tech to their real lives.

---

## 🧰 Tools & Setup
- Preload drivers and IDE
- Have spare ESP32 boards and jumper wires
- Encourage pair programming if equipment is limited
- Optional: project rubric, certificate of completion

---

## 🏁 Closing the Course
- Collect feedback on what students enjoyed
- Offer suggestions for next steps (IoT, Bluetooth, robotics)
- Encourage them to fork the final project into something personal

Thanks for inspiring the next generation of embedded inventors! 💡🧠
