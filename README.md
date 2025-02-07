# Traffic Light Control System

## Introduction
This project emulates a traffic light system, featuring multiple system routines that users can switch by altering the `mode` signal. The system follows **The World Advanced Traffic Light Control System**, which could be implemented as part of **Oman Vision 2040**. It includes dedicated traffic lights for cars and separate lights for pedestrians on each side of the crossroad.
![image](https://github.com/user-attachments/assets/ef15a77b-624c-4941-a1af-18cb5215e6c3)

---

## Traffic Light States and Meanings

| State                | Meaning                            |
|----------------------|------------------------------------|
| **RED**             | STOP                               |
| **YELLOW**          | Signal is about to change         |
| **LEFT-TURN GREEN** | Left Turn                          |
| **GREEN**           | Go Straight                       |

---

## Existing Logic Circuit Solution
This project is based on the [Capella87/traffic-light-system](https://github.com/Capella87/traffic-light-system) GitHub repository. It focuses on implementing a logic circuit solution for a traffic light system, including designs, code, and possibly simulations or hardware implementations.

---

## Control Circuit Explanation
A **4-bit counter** cycles through states for a single traffic light, interfacing with:
- **Controller:** Manages signal direction for East, North, West, and South.
- **SIG Line:** Carries traffic light signal sequences like green, left turn green, yellow, and red phases.
- **Clock Signal and Mode Switch:** Controls timing and mode selection.

---

## Features

### Simultaneous Signal
Cars can make left turns or go straight simultaneously.

### Left Turn After Straight
Cars go straight first and then transition to left turns.

### Straight After Left Turn
Cars turn left first and then transition to straight.

### Go Straight Only Both Sides
Cars are only permitted to go straight when the straight-ahead green light is active.

### Flickering Modes
- **Red Flickering:** Red light flickers while all other signals are deactivated. Cars must stop before proceeding. Typically used at low-traffic intersections or late-night hours.
- **Yellow Flickering:** Yellow light flickers, indicating vehicles should proceed cautiously.

### Pedestrian Traffic Lights
Separate red and green lights for pedestrians. These are deactivated during flickering modes.

---

## System Modes

| Mode      | Description                                   |
|-----------|-----------------------------------------------|
| `000`     | Simultaneous Signal                          |
| `001`     | Left Turn After Straight                     |
| `010`     | Straight After Left Turn                     |
| `011`     | Go Straight Only Both Sides                 |
| `100`     | Red Flickering                               |
| `101`     | Yellow Flickering                            |
| `110/111` | Turn Off All Traffic Lights                 |

---

## Enhancements
- **Synchronized Blinking:** Improved red and yellow flickering for coordinated operation.
- **Deleted NOT Gates:** Simplified circuit design to synchronize blinking across all signals.

---

## Simulation
### Mode `000`: Simultaneous Signal
Traffic flows from South to East, North, and West in sequence, repeating continuously.

### Mode `001`: Left Turn After Straight
Both sides proceed straight, followed by simultaneous left turns.

### Mode `010`: Straight After Left Turn
Both sides turn left first, then proceed straight.

### Mode `011`: Go Straight Only Both Sides
Straight movement only, no left turns.

### Mode `100`: Red Flickering
Red light flickers; all other lights deactivated except pedestrian lights.

### Mode `101`: Yellow Flickering
Yellow light flickers; vehicles proceed cautiously.

### Modes `110/111`: Turn Off
All traffic lights deactivated.

---

## Conclusions
This project demonstrates:
- **Safety Enhancements:** Adaptive modes like Red and Yellow Flickering improve road safety.
- **Traffic Flow Optimization:** Modes like Simultaneous Signal and Go Straight Only optimize flow.
- **Scalability and Adaptability:** Modular design ensures flexibility for future upgrades.
- **Future Vision:** Integrates scalable solutions, paving the way for AI-based traffic management.

---

## References
- [Modern Network Enterprises](https://www.mne.om/MNE/)
- [Hi-Tech Projects LLC Oman](https://hi-techprojects.com/traffic-engineering-and-road-safety/product/)
- [4-Way Traffic Light System using Logic Gates](https://www.youtube.com/watch?v=2HgFHPS6g4o)
- [GitHub: Capella87/traffic-light-system](https://github.com/Capella87/traffic-light-system)
- [Google AI and Traffic Lights](https://www.wired.com/story/googles-ai-traffic-lights-driving-annoying/)
