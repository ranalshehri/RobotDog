# Quadruped Robot Dog
Preliminary mechanical design for a simple quadruped robot.

## Overview
Preliminary Mechanical Design of a Simple Quadruped Robot

1. General Concept

The proposed design is a simple quadruped robot consisting of a central rectangular body and four mechanically identical legs.

The main objective of the design is to create a simple and stable robot that can support its own weight and perform basic walking movements without unnecessary mechanical complexity.

The robot consists of:

* A central rectangular body.
* Four legs.
* Two main joints per leg.
* Eight degrees of freedom in total.
* Wide feet to improve ground contact and stability.
* A central compartment for the battery and electronic components.

The design focuses on simplicity, ease of construction, and sufficient stability for basic movement.

⸻

2. Body and Main Structure

The robot uses a rectangular body as its main structural frame.

The body is designed to contain the main electronic components, such as:

* Battery
* Microcontroller
* Motor control electronics
* Sensors

The battery and other heavy components should be placed as close to the center of the body as possible. This helps maintain a balanced center of gravity and reduces the possibility of the robot tipping over.

The body can be constructed using lightweight materials such as:

* Aluminum
* Carbon fiber
* 3D-printed components
* A combination of these materials

A lightweight but rigid structure is preferred in order to reduce the amount of torque required from the motors.

⸻

3. Leg Design

The robot has four identical legs. Each leg consists of:

1. An upper leg link
2. A knee joint
3. A lower leg link
4. A foot

The upper section of the leg connects to the robot’s body through a motorized joint. The knee joint connects the upper and lower sections of the leg.

The wide feet provide a larger contact area with the ground, helping improve stability and reduce the possibility of slipping.

⸻

4. Number of Joints and Degrees of Freedom

Each leg has two main joints:

Hip Joint

The hip joint connects the leg to the main body and allows the leg to move forward and backward.

Knee Joint

The knee joint connects the upper and lower leg links and allows the lower part of the leg to move upward and downward.

Therefore:

2 \text{ joints per leg} \times 4 \text{ legs} = 8 \text{ degrees of freedom}

The robot therefore has a total of:

8 Degrees of Freedom (8-DOF)

This simplified design is suitable for a basic quadruped robot and is easier to control and manufacture than a robot with a larger number of joints.

⸻

5. Motor Selection

The motors should be selected based on the weight of the robot and the torque required at each joint.

High-torque servo motors are a suitable option for this design because they:

* Allow relatively simple position control.
* Are widely available.
* Can provide sufficient torque for a small prototype.
* Can be used with motor controllers and microcontrollers.

Metal-geared servos would be preferred for the main load-bearing joints because the joints will experience repeated forces during walking.

The most important factors when selecting the motors are:

* Required torque
* Operating voltage
* Motor weight
* Speed
* Gear durability
* Ability to withstand repeated loading

⸻

6. Initial Torque Calculation

As an initial estimate, assume that the robot has a total mass of:

m = 4 \text{ kg}

The gravitational force acting on the robot is:

F = mg

F = 4 \times 9.81 = 39.24 \text{ N}

During a walking cycle, assume that three legs are supporting the robot’s weight.

The approximate force supported by each leg is therefore:

F_{\text{leg}} = \frac{39.24}{3}

F_{\text{leg}} \approx 13.08 \text{ N}

Assuming that the effective distance from the knee joint to the load is:

r = 0.12 \text{ m}

The required static torque can be estimated using:

\tau = F \times r

\tau = 13.08 \times 0.12

\tau \approx 1.57 \text{ Nm}

Therefore, the estimated static torque required at the knee joint is approximately:

1.57 Nm

However, the robot will experience additional forces while walking due to acceleration, sudden movements, and impact when the feet contact the ground.

Using a safety factor of 2:

\tau_{\text{required}} = 1.57 \times 2

\tau_{\text{required}} \approx 3.14 \text{ Nm}

Therefore, the selected knee motor should ideally provide at least approximately:

3.14 Nm of torque

The actual required torque should be recalculated after the final dimensions, mass, and center of gravity of the robot have been determined.

⸻

7. Stability and Center of Gravity

The robot’s center of gravity is an important factor in maintaining stability.

The battery and other heavy components should be positioned near the center of the robot and as low as possible.

When the robot is standing, the points where the feet touch the ground form a support polygon.

The robot remains statically stable when its center of gravity is located inside this support polygon.

To improve stability, the design should:

* Keep heavy components near the center.
* Keep the center of gravity as low as possible.
* Maintain a balanced distribution of weight.
* Use feet with sufficient ground contact.
* Avoid placing too much weight toward the front or rear of the body.

If the center of gravity moves outside the support polygon, the robot may lose balance and fall.

⸻

8. Proposed Walking Method

A trot gait is proposed for the robot.

In this walking pattern, diagonal pairs of legs move together:

* Front-left leg + rear-right leg
* Front-right leg + rear-left leg

The robot alternates between these two pairs.

For example:

Phase 1

One diagonal pair moves forward while the other pair supports the robot.

Phase 2

The second diagonal pair moves forward while the first pair supports the robot.

This walking method provides a good balance between:

* Stability
* Walking speed
* Control simplicity
* Mechanical complexity

However, because this design has only two degrees of freedom per leg, the walking motion may be more limited than that of more advanced quadruped robots.

A slower walking pattern could be used during the initial testing stage to reduce instability.

⸻

9. Expected Mechanical Problems

Several mechanical problems may occur during the development of the robot.

Motor overheating

The motors may overheat if they continuously support the robot’s weight or operate near their maximum torque.

Gear wear

Repeated loading and impacts may cause wear on the motor gears, especially if low-quality gears are used.

Joint looseness

Small amounts of play or looseness in the joints can lead to vibration and inaccurate movement.

Structural bending

The leg links or body may bend if the selected material is too thin or cannot withstand the applied loads.

Foot slipping

The feet may slip on smooth surfaces, reducing the robot’s stability.

Excessive weight

A heavier robot requires more motor torque. This can create a cycle in which heavier motors are required, increasing the total weight even further.

Impact forces

The forces experienced when a foot makes contact with the ground may be higher than the robot’s static weight. This is why a safety factor is included when selecting the motors and structural components.
