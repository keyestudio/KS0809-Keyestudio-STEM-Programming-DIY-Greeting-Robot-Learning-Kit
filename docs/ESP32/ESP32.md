# 2.2 ESP32 Easy Coding Board Greeting Robot Projects

## 1. Projects

[Click to download codes](./Code/code.zip).

### 1.1 Servo

A servo is a kind of position driver, which is mainly composed of housing, circuit board, core-less motor, gear and position detector. The receiver or microcontroller sends a signal to the servo which has an internal reference circuit that generates a reference signal with a period of 20ms and a width of 1.5ms, and compares the DC bias voltage with the voltage of the potentiometer to output voltage difference.

There are many specifications of servos, yet all contains three colors of wires: brown, red and orange. Brown is the grounded, red is the positive, and orange is signal. The wire colors may vary from brands.

![](img/cou41.png)

The rotation Angle of the servo is controlled by adjusting the duty cycle of the PWM (pulse width modulation) signals. Theoretically, the period of the standard PWM signal is fixed at 20ms (50Hz), so the pulse width should be 1ms ~ 2ms. But in fact, it is 0.5ms ~ 2.5ms, corresponding to the servo angle of  0° ~ 180°.

![](img/cou42.png)

**1.1.1 Parameters**

Operating voltage: DC 3.3 ~ 5V

Operating Angle range: approx. 180°(at 500→2500 μsec)

Pulse width: 500→2500 μsec

No load speed: 0.12± 0.01sec /60 (DC 4.8V)        0.1± 0.01sec /60 (DC 6V)

No load current: 200±20mA (DC 4.8V)         220±20mA (DC 6V)

Stopping torque: 1.3±0.01kg·cm (DC 4.8V)          1.5±0.1kg·cm (DC 6V)

Stop current: ≦850mA (DC 4.8V)           ≦1000mA (DC 6V)

Standby current: 3±1mA (DC 4.8V)           4±1mA (DC 6V)

**1.1.2 Wiring Diagram**

![](img/00_581.png)

![](img/00_582.png)

![](img/00_583.png)

------

| Expansion board |  Servo A   |
| :-------------: | :--------: |
|       GND       | G (brown)  |
|       3V3       |  V (red)   |
|    P0 / io12    | S (yellow) |

| Expansion board |  Servo B   |
| :-------------: | :--------: |
|       GND       | G (brown)  |
|       3V3       |  V (red)   |
|    P1 / io14    | S (yellow) |

**1.1.3 Test Code**

<p style="color:red;">ATTENTION: The servo is able to rotate from 0 to 180 degrees. Yet after assembly, it can only move within 0-90 degrees. Otherwise, it may burn out due to stuck and overheating.</p>

[**Click to download codes**](./Code/code.zip).

**Build code blocks manually:**

1\. Click ![a28](./img/a28.png) and choose `Actuator`, find `Servo` and click to load it.

![a29](./img/a29.png)

If you see Loaded, the extension is successfully imported, and then click ![a30](./img/a30.png).

![a31](./img/a31.png)

2\. In ![a1](./img/a1.png), add a ![a2](./img/a2.png).

3\. In ![a1](./img/a1.png), drag a ![a5](./img/a5.png) and put it under ![a2](./img/a2.png).

4\. In ![a32](./img/a32.png), add a ![a33](./img/a33.png), set the pin to `IO12`, angle to 0 degree and delay to `1000`(ms), and put it into ![a5](./img/a5.png).

5\. In ![a32](./img/a32.png), add one more ![a33](./img/a33.png), set pin to `IO12`, angle to 90 degrees and delay to `1000`(ms), and put it under the previous one.

**Complete code:**

![3-4](./img/3-4.png)

**1.1.4 Test Result**

The arm of the greeting robot moves.

------

### 1.2 Waving Arm

We combine two servos to make the robot to do some actions.

**1.2.1 Test Code: Left-turn** 

1\. In ![a1](./img/a1.png), add a ![a2](./img/a2.png).

2\. In ![a1](./img/a1.png), put ![a5](./img/a5.png) under ![a2](./img/a2.png).

3\. In ![a32](./img/a32.png), add a ![a33](./img/a33.png), set the pin to `IO12`, angle to `0` degree and delay to `1000`(ms), and put it under ![a5](./img/a2.png).

4\. In ![a32](./img/a32.png), add a ![a33](./img/a33.png), set the pin to `IO14`, angle to `0` degree and delay to `1000`(ms), and put it into ![a5](./img/a5.png).

![](img/cou58.png)

5\. Repeat the above steps but set pin io14 to 90°.

![](img/cou59.png)

**1.2.2 Result**

The palm of the greeting robot turns left.

------

**1.2.3 Test Code: Greeting**

1\. In ![a1](./img/a1.png), add a ![a2](./img/a2.png).

2\. In ![a1](./img/a1.png), put ![a5](./img/a5.png) under ![a2](./img/a2.png).

3\. In ![a32](./img/a32.png), add a ![a33](./img/a33.png), set the pin to `IO12`, angle to `90` degree and delay to `1000`(ms), and put it under ![a5](./img/a2.png).

![](img/cou60.png)

4\. In ![a32](./img/a32.png), add a ![a33](./img/a33.png), set the pin to `IO14`, angle to `0` degree and delay to `1000`(ms), and put it into ![a5](./img/a5.png).

![](img/cou61.png)

5\. Repeat the above steps but set pin io14 to 90°.

![](img/cou62.png)

**1.2.4 Result**

The robot put its arms up and wave its hand for welcome.

------

### 1.3 Ultrasonic

Before learning: In this project, we introduce the fundamentals of ultrasound. We will use the ultrasonic sensor to print detected distances on the serial monitor.

**1.3.1 Overview**

Like bats, HC-SR04 ultrasonic sensor uses sonar to determine the distance to an object. It provides excellent contact-less range inspection with high accuracy and stable readings. It is also equipped with ultrasonic transmitter and receiver. It is widely applied to electronics projects for obstacle detection and distance measurement.

**1.3.2 Module Parameters**

![](img/KS0504-7.jpg)

**1.3.3 Wiring Diagram**

| Expansion board | Ultrasonic sensor |
| :-------------: | :---------------: |
|       3V3       |        VCC        |
|      TRIG       |     P12/io15      |
|      ECHO       |      P8/io4       |
|       GND       |        GND        |

![](img/co1.png)

**1.3.4 Test Code**

Add an Extension.

![](img/co2.png)

Search **ULTRASONIC**.

![](img/co3.png)

Click to load it.

![](img/co4.png)

![](img/co6.png)

Initialize the serial port.

![](img/co5.png)

![](img/co7.png)

Add the code block of the ultrasonic sensor.

![](img/co6.png)

![](img/co8.png)

**Complete code:**

![](img/co10.png)

**1.3.5 Test Result**

Open the serial monitor and set the baud rate. <span style="color:red">NOTE that the sensor is not professional and just used for learning.</span>

Put an object in front of the ultrasonic sensor, and it will detect the corresponding distance value. 

![](img/co9.png)

------


### 1.4 Greeting Robot

Before learning: We combine the servos and ultrasonic sensor in this project. When the sensor detects any thing within the distance of 15~35CM, the greeting robot waves its arm as a welcome.

**1.4.1 Test Code**

1\. Click ![](img/cou63.png) to make a variable to store the detected distance value.

![](img/cou64.png)

2\. Assign the detected distance value to the variable. 

![](img/cou65.png)

3\. Set servo connected to pin io12 and io14 to angle 0°.

![](img/cou72.png)

4\. In ![](img/cou66.png), add a ![](img/cou67.png) into ![a5](./img/a5.png).

![](img/cou73.png)

5\. Put ![](img/cou68.png) and ![](img/cou69.png) into ![](img/cou67.png) in sequence. 

![](img/cou74.png)

When the ultrasonic sensor detects object(s) with the distance of 15~35CM;

![](img/cou75.png)

io12 servo is set to 90°, and io14 servo rotates within 0~90° to wave the arm.

![](img/cou76.png)

Or else, the robot stops waving its hand and put his arm to the original position. 

![](img/cou78.png)

**Complete code:**

![](img/cou77.png)

**1.4.2 Test Result**

When someone approaches, the robot begins to greet him/her.

------

## 2. FAQ

### Q: Battery model?

A: Four AAA batteries. Please install the batteries in the correct direction rather than reverse them! For younger students, please be accompanied by your parents!

------

### Q: Error occurs when burning programs on ESP32 board?

A: 

- Please check whether the USB port number is correct.
- Please ensure the main board model is available. 

------

### Q: Expand to external modules?

A: It can expand to external modules. For details, please follow the ESP32 pin instructions to ensure external modules can normally work.

------



## 3. Resources

Keyestudio official:

[https://www.keyestudio.com/](https://www.keyestudio.com/)

Keyestudio wiki main page:

[https://wiki.keyestudio.com/Main_Page](https://www.keyestudio.com/)

Arduino official:

[https://www.arduino.cc/](https://www.keyestudio.com/)

ESP32 espressif official:

[https://www.espressif.com/](https://www.keyestudio.com/)
