# ThinkPad TrackPoint Remap
![GitHub release (latest by date)](https://img.shields.io/github/v/release/Dark-Zeus/thinkpad-trackpoint-remap?label=Github%20Release)

This project remaps the input of a ThinkPad TrackPoint to the arrow keys (Up, Down, Left, Right). It was created to address a personal situation where the physical arrow keys on the keyboard were broken, but the TrackPoint was still functional.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Features

- Detects input from the ThinkPad TrackPoint.
- Remaps TrackPoint movements:
  - **Left** → Left Arrow Key
  - **Right** → Right Arrow Key
  - **Up** → Up Arrow Key
  - **Down** → Down Arrow Key
- Includes configuration to automatically detect the TrackPoint device and store its information for future use.
- Supports a tolerance threshold for TrackPoint movement to avoid accidental key presses from minor movements.

## Prerequisites

- Windows operating system
- Visual Studio or any C++ compiler that supports Windows APIs
- A ThinkPad laptop with a functioning TrackPoint

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/trackpoint-remapper.git
   ```
2. Open the project in your preferred IDE (such as Visual Studio).
3. Build the project.
4. Run the executable.
5. Follow the guidlines given in the terminal.

## Configuration
The program automatically generates a config.ini file on its first run. This file contains the devicePath and hDevice information for the TrackPoint, which is used to map its inputs.

## Steps to Configure the TrackPoint:
On first launch, if no configuration is found, the program will prompt you to press Enter to configure the TrackPoint.
After pressing Enter, make sure not to click or move any other device except for the TrackPoint.
The TrackPoint will be detected, and the configuration will be saved in config.ini for future runs.

If you need to reset the configuration, delete config.ini and re-run the program.

## How It Works
* The program listens for raw input from the TrackPoint using the Windows Raw Input API.
* It identifies the TrackPoint device by comparing device paths and hardware identifiers.
* Based on the direction of TrackPoint movement, the corresponding arrow key is sent as input to the system.
* A tolerance is applied to avoid triggering key presses for minor or accidental movements.

## Usage
Move the TrackPoint in the direction of the desired arrow key action (up, down, left, right).
The corresponding arrow key will be triggered.

## Known Issues
* The program assumes the TrackPoint is not in use by any other software that requires precise movement.
* May not work well with certain external pointing devices if misconfigured.
* Does not provide a way to configure tolarance and timing after compiled. (for now).

## Acknowledgments
This project uses the Windows Raw Input API for device handling.
Created for the specific issue I had, made public to help ThinkPad who may face hardware issues with their arrow keys.

