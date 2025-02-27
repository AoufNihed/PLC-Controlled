# PLC-Controlled Door Locking System

## Overview
This project presents a programmable logic controller (PLC)-based door locking system designed to ensure secure, efficient access control. The system offers user-selectable locking and unlocking programs to meet specific security needs, reducing the need for manual supervision and enhancing reliability.

## Project Features
- **Complete and Partial Locking**: Choose between a full locking cycle (Program 1) and a partial lock mechanism (Program 2).
- **Automatic Reset**: Both programs reset after each operation, ensuring the system is always ready for new commands.
- **User Interface**: Operated through a user-friendly interface with simple inputs for each program and reset commands.

## System Logic
The system operates using four main relays and a push button:
- **Program 1**: Activates all relays, completing a full lock cycle within two minutes. Pressing the button again resets the cycle.
- **Program 2**: Activates only the first two relays for partial locking. The program resets if no further input is detected.

### Outputs (Relays)
- **Relay ES.0 / ES.1**: Controls primary locking.
- **Relay ES.3 / ES.4**: Engages secondary locking.
- **Relay ES.5 / ES.6**: Activates tertiary security.
- **Relay ES.7 / ES.8**: Completes the lock cycle.

### Inputs (Commands)
- **Input qc.0**: Initiates Program 1 (Full lock).
- **Input qc.1**: Initiates Program 2 (Partial lock).
- **Input qc.2**: Manual reset for Program 1.
- **Input qc.3**: Manual reset for Program 2.

## Setup and Configuration

### Step 1: PLC Configuration and Selection
- Select an appropriate PLC model compatible with the project requirements.
- Configure the PLC to interface with the input and output relays.

### Step 2: Input and Output Configuration
- Map the inputs (qc.0 - qc.3) and outputs (ES.0 - ES.8) based on the specified functionality.
- Ensure that each relay and input aligns with the desired program functionality.

### Step 3: Define Tags and Assign Logic Addresses
- Create and assign logical addresses for each input, output, and memory bit.

### Step 4: Program Implementation

#### Program 1 (Full Lock)
- **Configuration**: Define the logic to trigger all relays in sequence.
- **Implementation**: Code the full lock sequence with a two-minute duration.

#### Program 2 (Partial Lock)
- **Configuration**: Define the logic to trigger the first two relays only.
- **Implementation**: Code the partial lock sequence with an auto-reset.

### Step 5: Multi-Floor Logic
The locking logic is applied identically across all floors, using:
- **Buttons and Input Signals**: Configured for interactions on each floor.
- **Memory Bits**: Store temporary states for each floor.
- **Outputs**: Activate lock/unlock actions per floor.

This approach standardizes control across multiple floors, reducing redundancy and enhancing scalability.

### Step 6: Link Programs to Activation (Allumer)
- Link both programs to a main controller that initiates the appropriate locking sequence.

### Step 7: Integrate Programs into Main Logic
- Integrate all programs into the main logic for unified control.

### Step 8: Run the Simulation
- Conduct an online simulation to validate functionality and timing.

## Conclusion
The **PLC-Controlled Door Locking System** provides an efficient, flexible solution for automated door control. It offers:
- **Enhanced Security**: Flexibility to choose between full and partial locking.
- **User-Friendly Interface**: Simple commands enable quick activation and reset.
- **Automatic Reset**: Ensures the system is always prepared for the next cycle.

This system delivers reliable access management while providing a foundation for advanced security automation solutions.
