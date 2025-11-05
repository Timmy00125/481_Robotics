# **ROBOTIC CRAB PROJECT DRAFT DOCUMENTATION**

## **1\. Project Title**

**Design and Construction of a Robotic Crab**

---

## **2\. Project Overview**

This project involves the design and construction of a robotic crab capable of mimicking the natural movement of a crab, particularly its sideways locomotion and obstacle avoidance behavior. The robot will be built using affordable, lightweight components and programmed to perform semi-autonomous navigation with optional Bluetooth control.

The aim is to demonstrate the integration of mechanical design, electronics, and programming to create a functional biomimetic robot.

---

## **3\. Objectives**

* To design a crab-like robot that can walk sideways using servo-actuated legs.

* To enable the robot to detect and avoid obstacles autonomously.

* To integrate Bluetooth control for manual operation via a mobile device.

* To promote understanding of robotics principles including motion control, power management, and sensor integration.

---

## **4\. Project Scope**

The robotic crab will feature:

* four to six servo-driven legs for motion.

* An Arduino microcontroller for logic and control.

* Ultrasonic sensors for object detection.

* Bluetooth module for wireless control.

* Rechargeable battery system for mobility and portability.

---

## **5\. Project Components**

### **Mechanical Components**

* Frame (Plastic, Acrylic, or 3D Printed)

* Mounting brackets and screws

* Servo horns and connectors

* Lightweight legs (plastic or aluminum)

### **Electronic Components**

* Arduino Uno (or compatible microcontroller)

* SG90 Micro Servos (6–8 units)

* L298N Motor Driver

* Ultrasonic Sensor (HC-SR04)

* Bluetooth Module (HC-05)

* Jumper wires

* Breadboard

* Rechargeable Li-ion batteries with holder

* LED indicators (optional for eyes)

* On/Off switch

* Connectors and resistors as needed

### **Software Components**

* Arduino IDE

* Bluetooth Controller Android App (optional)

* CAD software (Fusion 360 or TinkerCAD for frame design)

---

## **6\. Phases of the Project**

### **Phase 1: Research and Design**

* Study crab locomotion and leg mechanics.

* Sketch or CAD model of the crab frame and leg placements.

* Identify required electronic components and confirm availability.

### **Phase 2: Mechanical Construction**

* Fabricate or assemble the crab frame.

* Mount servos and connect mechanical linkages for the legs.

* Ensure balanced weight distribution for stability.

### **Phase 3: Circuit Assembly**

* Connect all servos to Arduino through L298N driver.

* Connect ultrasonic sensor and Bluetooth module.

* Setup power supply from Li-ion batteries.

* Test basic power flow and servo motion.

## **Programming and Logic**

The code determines the robot's movement and overall behavior. Below is the logical structure and programming setup for the Robotic Crab project.

### **1\. Setup**

* Install the **Arduino IDE**.

* Install the **Adafruit\_PWMServoDriver** library.

* Connect the Arduino board and ensure all servos and sensors are properly connected.

### **2\. Inverse Kinematics (IK)**

Inverse Kinematics translates a desired foot position (e.g., move forward or sideways 5cm) into the specific angles required for the two leg servos.

* **Do not code this from scratch.** Use an existing Arduino hexapod IK library.

This library provides high-level functions such as:

 setFootPosition(leg\_number, x, y, z);

*   
* These functions allow you to define how far and in which direction each leg should move, simplifying servo angle calculations.

### **3\. Gait Engine**

The gait engine determines the sequence of leg movements for walking.

For a **sideways crab walk**, the recommended gait is the **tripod gait**:

1. Lift three legs at a time (e.g., front-left, middle-right, back-left).

2. Move these three legs sideways in the desired direction.

3. Place them down.

4. Lift the other three legs (front-right, middle-left, back-right).

5. Shift the body over the planted legs and move the airborne legs back to their starting position.

6. Repeat this sequence continuously for smooth, coordinated sideways motion.

This gait ensures balance, stability, and a realistic crab-like walking pattern.

### **4\. Bluetooth Control**

Integrate Bluetooth control using the **HC-05 Bluetooth module** to allow manual commands from a smartphone.

Steps:

1. Write code that listens for single characters on the serial port from the Bluetooth module.

   * Example control scheme:

     * `'L'` \= move left

     * `'R'` \= move right

     * `'S'` \= stop movement

2. Use a simple Bluetooth serial terminal app on your phone to send these commands.

3. In the Arduino code, the `loop()` function checks for incoming Bluetooth characters and calls the corresponding gait function.

This approach enables real-time manual control and testing of different gait sequences without re-uploading the Arduino code each time.

### **5\. Summary**

* Use existing libraries to handle servo math and motion logic efficiently.

* Implement the tripod gait for stable and smooth crab movement.

* Enable Bluetooth control for manual testing and demonstration.

* Structure your Arduino code to separate movement logic, sensor input, and control input for maintainability.

### **Phase 5: Testing and Evaluation**

* Verify crab motion pattern and direction.

* Test obstacle avoidance at different distances.

* Evaluate Bluetooth response delay and control accuracy.

* Make necessary mechanical and software adjustments.

### **Phase 6: Documentation and Presentation**

* Prepare technical documentation of the project.

* Record demo video of the robotic crab in action.

* Create PowerPoint slides for presentation.

---

## **7\. How We Will Achieve It**

1. **Design Phase:**  
    The design will begin with a study of crab movement mechanics to replicate leg coordination patterns. CAD modeling will define servo placements and body structure.

2. **Component Integration:**  
    After sourcing the components, the electronic system will be assembled on a breadboard for testing before permanent mounting. The mechanical frame will be built from lightweight plastic or acrylic to support the servos.

3. **Programming:**  
    The Arduino will be programmed to control the sequence of servo movements for side-walking, and an ultrasonic sensor will provide feedback for obstacle avoidance. Bluetooth communication will be added to allow remote commands via a smartphone app.

4. **Testing & Optimization:**  
    The robot’s gait and sensor accuracy will be refined through multiple tests to achieve stable movement and efficient obstacle detection. Calibration of servo angles will ensure balance and fluid motion.

5. **Final Assembly:**  
    Once performance is satisfactory, components will be neatly integrated into the final frame, with wiring organized for durability and aesthetics.

---

## **8\. Tasks to Be Completed**

| Task | Description | Assigned To |
| ----- | ----- | ----- |
| Research and design study | Study crab motion and plan robot structure | Timmy |
| Component sourcing | Purchase or gather all components | Timmy, Greg, Godswill |
| Frame fabrication | Build or print crab frame | Greg, Godswil, Timmy, Sinclair |
| Circuit assembly | Connect Arduino, sensors, and servos | Timmy,  |
| Programming | Develop Arduino code for movement and sensors | Greg, Timmy, Godswill |
| Power system setup | Assemble battery and power circuit | Timmy, Victor, Jackson, Bello |
| Bluetooth integration | Implement Bluetooth module control | Timmy, Greg, Sinclair |
| Testing and calibration | Verify motion, sensor response, and control | Greg and Godswill |
| Documentation | Prepare project report and presentation slides | Greg |
| Final demonstration | Present working robotic crab | All active members |

---

## **9\. Expected Outcome**

By the end of the project, a functional robotic crab prototype will be produced that can:

* Walk sideways using servo-actuated legs.

* Detect and avoid obstacles automatically.

* Respond to Bluetooth commands for manual control.

This project will demonstrate practical understanding of mechatronics, embedded systems, and programming integration.

---

## **10\. Deliverables**

* Functional robotic crab prototype

* Arduino source code

* Circuit diagram and connection schematic

* Project documentation report

* Presentation slide deck

* Demonstration video

