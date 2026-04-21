# LAFBOT-Collision-Avoidance-via-Low-Level-Components
LAFBOT is a black-line following robot used at Lafayette College to teach circuit design using CNY70 IR sensors and PWM-controlled DC motors. My task was to add a collision-avoidance feature using only basic electronic components, enabling the robot to detect obstacles, deviate from the line, and return to it—without using a microcontroller.

I implemented obstacle detection with an HC-SR04 ultrasonic sensor and designed analog circuits to replicate Arduino functionality. A 555 timer generated the 10 µs trigger pulse, while the echo signal was processed through an RC low-pass filter and a comparator. A threshold of 2 V (~9 cm) was selected to detect nearby obstacles.

The comparator output was used to control motor PWM, stopping the robot when an obstacle was within range. An inverting comparator and a second 555 timer in monostable mode were later added to convert pulsed signals into a near-DC control voltage using RC filtering.

Finally, I integrated the distance-sensing circuit with the existing line-following system under hardware constraints (non-removable, grounded CNY70 sensors). I designed wheel-specific control circuits using RTL logic and differential amplifiers to dynamically adjust PWM thresholds, enabling smooth obstacle avoidance and line reacquisition.
