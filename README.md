# Conveyor Belt and Hopper Control System

## Overview

This RSLogix 500 project controls a conveyor belt and hopper system to automatically fill boxes with either pecans or walnuts based on the color label on the box. Red labels correspond to pecans, while blue labels correspond to walnuts.

## System Components

- **Conveyor Belt**: Transports boxes to the filling station.
- **Hopper 1**: Dispenses pecans.
- **Hopper 2**: Dispenses walnuts.
- **Color Sensor**: Detects the color label on the boxes (red for pecans, blue for walnuts).
- **PLC**: Allen-Bradley MicroLogix 1100 Series B.

## Ladder Logic Description

The ladder logic program for this project includes the following main components:

### I/O Configuration

- **Inputs**:
  - `I:0/0`: Proximity sensor input
  - `I:0/1`: Level sensor input
  - `I:0/2`: Red color sensor input
  - `I:0/3`: Blue color sensor input
  - `I:0/4`: Start button
- **Outputs**:
  - `O:0/0`: Conveyor motor output
  - `O:0/1`: Walnut hopper output
  - `O:0/2`: Pecan hopper output

### Binary Data Bits

- `B3:0/0`: Proximity bit
- `B3:0/1`: Level bit
- `B3:0/2`: Red sensor bit
- `B3:0/3`: Blue sensor bit
- `B3:0/4`: Conveyor bit
- `B3:0/5`: Walnut hopper bit
- `B3:0/6`: Pecan hopper bit
- `B3:0/7`: One-shot rising (ONS)

### Integer Data Files

- `N7:0`: Conveyor state (0 = stopped, 1 = moving)
- `N7:1`: Hopper state (0 = off, 1 = pack pecan, 2 = pack walnut)

### Ladder Logic

1. **Rung 0**: Start/Stop Control
    - Controls the conveyor motor based on the start button.

2. **Rung 1**: Box Detection
    - Stops the conveyor when a box is detected.

3. **Rung 2**: Color Detection and Filling
    - Activates the appropriate hopper based on the detected color.

4. **Rung 3**: Restart Conveyor
    - Restarts the conveyor after the box is filled.

### Program Files

- `LAD 2`: Main routine calling subroutines
- `LAD 3`: IO handling
- `LAD 4`: State handling
- `LAD 5`: Control logic

## How to Use

1. **Setup the Hardware**:
   - Connect the conveyor belt motor, hopper solenoids, and sensors to the appropriate PLC input/output terminals as described above.
   - Ensure that the color sensor is correctly positioned to read the labels on the boxes as they arrive at the filling station.

2. **Load the RSLogix 500 Program**:
   - Open RSLogix 500 and load the provided `.RSS` file.
   - Download the program to the PLC.

3. **Operation**:
   - Press the start button to begin the operation.
   - Place boxes on the conveyor belt with the appropriate labels (red for pecans, blue for walnuts).
   - Monitor the system and ensure that boxes are correctly filled based on their labels.

## Screenshots

![image](https://github.com/user-attachments/assets/a958ced0-7be8-4a23-9588-f6bdde442345)

![image](https://github.com/user-attachments/assets/066deccf-2cda-4ee7-ad05-c824d4f37c2e)

![image](https://github.com/user-attachments/assets/4369ece1-6a28-43e3-b0fa-bb13377a017d)

![image](https://github.com/user-attachments/assets/34226845-152c-4101-b4f4-207b9bfa60f3)


