# Quadruped Robot Dog

Preliminary mechanical design for a simple quadruped robot, modeled in **Tinkercad**.

## Overview

This repository documents the preliminary mechanical design of a simple quadruped robot. The design consists of a central rectangular body and four mechanically identical legs, focused on simplicity, ease of construction, and enough stability for basic walking movement — without unnecessary mechanical complexity.

**Key specs:**

| | |
|---|---|
| Body | Central rectangular frame |
| Legs | 4, mechanically identical |
| Joints per leg | 2 (hip + knee) |
| Total degrees of freedom | 8 |
| Feet | Wide, for ground contact and stability |
| Payload bay | Central compartment for battery + electronics |
| Design tool | Tinkercad |

---

## Body and Main Structure

The robot uses a rectangular body as its main structural frame, housing the core electronics:

- Battery
- Microcontroller
- Motor control electronics
- Sensors

The battery and other heavy components are placed as close to the center of the body as possible to maintain a balanced center of gravity and reduce the risk of tipping.

**Candidate materials:**
- Aluminum
- Carbon fiber
- 3D-printed components
- A combination of the above

A lightweight but rigid structure is preferred, to reduce the torque required from the motors.

---

## Leg Design

Each of the four identical legs consists of:

1. An upper leg link
2. A knee joint
3. A lower leg link
4. A foot

The upper section connects to the body through a motorized hip joint; the knee joint connects the upper and lower leg links. Wide feet increase ground contact area, improving stability and reducing slippage.

---

## Joints and Degrees of Freedom

Each leg has two main joints:

- **Hip joint** — connects the leg to the body; allows forward/backward motion.
- **Knee joint** — connects the upper and lower leg links; allows the lower leg to move up/down.

```
2 joints/leg × 4 legs = 8 degrees of freedom (8-DOF)
```

This simplified 8-DOF layout is easier to control and manufacture than designs with more joints per leg.

---

## Motor Selection

**High-torque servo motors** are a good fit for this design because they:

- Allow relatively simple position control
- Are widely available
- Provide sufficient torque for a small prototype
- Work with common motor controllers/microcontrollers

**Metal-geared servos** are preferred for the main load-bearing joints, since those joints see repeated forces during walking.

**Selection criteria:**
- Required torque
- Operating voltage
- Motor weight
- Speed
- Gear durability
- Ability to withstand repeated loading

---

## Initial Torque Calculation

As an initial estimate, assume a total robot mass of `m = 4 kg`.

**Gravitational force:**
```
F = m × g = 4 × 9.81 = 39.24 N
```

**Force per leg** (assuming 3 legs support the robot's weight during a walking cycle):
```
F_leg = 39.24 / 3 ≈ 13.08 N
```

**Static torque at the knee joint**, assuming an effective distance from the knee joint to the load of `r = 0.12 m`:
```
τ = F × r = 13.08 × 0.12 ≈ 1.57 Nm
```

Walking introduces additional forces from acceleration, sudden movement, and foot impact, so a **safety factor of 2** is applied:

```
τ_required = 1.57 × 2 ≈ 3.14 Nm
```

The selected knee motor should provide **at least ~3.14 Nm** of torque. This figure should be recalculated once final dimensions, mass, and center of gravity are locked in.

---

## Stability and Center of Gravity

When standing, the points where the feet contact the ground form a **support polygon**. The robot is statically stable as long as its center of gravity stays inside that polygon.

To improve stability:

- Keep heavy components near the center of the body
- Keep the center of gravity as low as possible
- Maintain a balanced weight distribution
- Use feet with sufficient ground contact
- Avoid concentrating weight toward the front or rear

If the center of gravity moves outside the support polygon, the robot may lose balance and fall.

---

## Proposed Walking Method — Trot Gait

A **trot gait** is proposed, where diagonal leg pairs move together:

- Front-left + rear-right
- Front-right + rear-left

**Phase 1:** One diagonal pair moves forward while the other pair supports the robot.
**Phase 2:** The second diagonal pair moves forward while the first pair supports the robot.

This offers a good balance of stability, walking speed, and control simplicity. Since each leg only has 2 degrees of freedom, the walking motion is more limited than in more advanced quadrupeds — a slower gait is recommended during initial testing to reduce instability.

---

## Anticipated Mechanical Challenges

- **Motor overheating** — from continuously supporting the robot's weight or running near max torque
- **Gear wear** — from repeated loading and impacts, especially with lower-quality gears
- **Joint looseness** — play in the joints causing vibration and inaccurate movement
- **Structural bending** — if leg links or body material is too thin for the applied loads
- **Foot slipping** — on smooth surfaces, reducing stability
- **Excessive weight** — heavier robots need more torque, which can mean heavier motors, which adds more weight
- **Impact forces** — forces on ground contact can exceed static weight, hence the safety factor used in motor/structural selection

---

## Notes

This design was made purely for educational purposes, and is not at a professional level yet.

## Author

**Rana Ali** ([@ranalshehri](https://github.com/ranalshehri))
