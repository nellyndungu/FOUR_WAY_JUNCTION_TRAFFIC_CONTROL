# AUTOMATIC FOUR-WAY JUNCTION TRAFFIC CONTROL
This project demonstrates the design and simulation of an automatic 4-way junction traffic control system using an Arduino Uno. The system controls both motorist and pedestrian traffic lights automatically, ensuring smooth traffic flow and safe pedestrian crossing at an intersection.

The main principle of the project is that pedestrian lights take priority when:
- The pedestrian lights show green, all motorist lights remain red.
- The pedestrian lights show red, the system cycles through the motorist traffic lights lane by lane, allowing each direction to move in turn.

A pedestrian button is included to request crossing. When pressed, it immediately sets all motorist lights to red and pedestrian lights to green. Once pedestrians finish crossing, the system resumes from the point in the sequence where it was interrupted.

## Working principle
1. Normal operation - Motorist control
The Arduino runs a timing loop that sequentially activates the green, yellow, and red signals for each motorist lane. Only one lane shows green at a time while the others remain red.
2. Pedestrian control
When no button is pressed, the pedestrian lights remain red. If the button is pressed, the Arduino overrides the motorist lights, setting them all to red, and activates the pedestrian green light.
3. System resume
After the pedestrian green period ends, the Arduino automatically switches back to motorist traffic control, continuing from the point where the cycle was interrupted.

## Components
The simulation requires the following components:
1. Hardware (Virtual in Proteus)
- Arduino Uno Board (1) – The microcontroller that runs the control logic.
- Traffic Lights (8) – Representing 4-way junction signals for motorists (red, yellow, green per lane) and pedestrian signals.
- Push Button (1) – Used by pedestrians to request crossing.
- 10kΩ Resistor (1) – Used as a pull-down resistor for the button.
2. Software Tools
- Proteus 8 Professional – Used to design the schematic and simulate the traffic control system.
- Arduino IDE – Used to write, compile, and generate the program code for the Arduino.

## Software Implementation

1. Schematic Design in Proteus
- Place the Arduino Uno and connect traffic lights (LEDs) and pedestrian signals to the digital pins.
- Include the button input with a pull-down resistor.
2. Code Development in Arduino IDE
- The logic is written in Arduino C++ to control the sequence of lights.
- Pedestrian override logic is included to prioritize pedestrian requests.
- Once the code is complete, the HEX file is generated using Sketch → Export Compiled Binary.
3. Simulation in Proteus
- Load the compiled HEX file into the Arduino component in Proteus.
- Run the simulation to observe automatic switching of traffic lights and pedestrian button functionality.
