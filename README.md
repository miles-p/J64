# J64 Build Guide

## Abstract
A Raspberry-Pi based RetroPie machine that is DIY designed for MAME and S/NES.

## STOP - Are you building this for a Jaycar?
If you're building this for a Jaycar or a demonstration of any of the software/skills/processes, please email me with photos and info about building it, my email is miles@punchav.com. I want to see a few built, because they're cool!
Author: Miles Punch

## Preface
So, you want to build the J64! It will serve you with good fun, and many hours of assembly, programming, and gaming. It is a Raspberry Pi based game console, designed for RetroPie and EmulationStation, enclosed in a 3D printed box. In this project, you will be faced with many common maker tools, such as Raspberry Pi’s, Soldering, 3D Printing, and Coding. Careful, as this may lead to a career in engineering!

## Tools Required
- Set of Small Screwdrivers (Jaycar CAT# TD2182)
- Basic Soldering Iron (Jaycar CAT# TS1470)
- Pliers/Crimp/Cutter (Jaycar CAT# TH1986)

## Bill of Materials

### Parts Required
| Part                         | Jaycar CAT# | Quantity Needed |
|------------------------------|-------------|-----------------|
| Round Arcade Switch (Blue)   | SP0666      | 3               |
| Round Arcade Switch (White)  | SP0669      | 3               |
| Arcade Joystick              | SM1052      | 1               |
| Small Normally Open Switch   | SP0656      | 2               |
| USB Joystick Interface       | XC9046      | 1               |
| M3 x 10mm Spacers            | HP0900      | 2               |
| M3 x 10mm Screws             | HP0403      | 2               |
| M4 Nylon Washer              | HP0166      | 4               |
| M4 x 15mm Screws             | HP0453      | 4               |
| M4 Nuts                      | HP0462      | 4               |
| Rubber Sticky Feet           | HP0825      | 4               |
| Raspberry Pi 4B 4GB          | XC9100      | 1               |
| Pi 4 Case                    | XC9110      | 1               |
| 16GB SD Card                 | XC9030      | 1               |
| 5V 3A USB-C PSU              | XC9122      | 1               |

## 3D Print
The model for the J64 was done in Fusion 360 and sliced in Creality Print. All files (Fusion 360, STL) can be found in the “3D Models” directory of the GitHub page. The 3D Print for this project was originally done on an Ender 3 V3 KE and finished in just under 4 hours for the body, and 2 hours for the base. It used roughly 1/4 of a 600g roll and didn’t require supports. It did print with a brim, and this was removed with a sharp knife.

**CAUTION:** When using a knife, never hold the blade towards yourself, and exercise precaution when trimming the brim off a 3D print.

## Button Layout
The button layout mimics the MAME button layout, and thus will work best with MAME ROMS and S/NES.

## Pi Required
RetroPie is supported on every version of Raspberry Pi, including:
- Pi Zero
- Pi One
- Pi Two
- Pi Zero 2W
- Pi Four
- Pi Four Hundred

Other PCs can be used to run the RetroPie machine, such as a laptop, both Linux, Mac, and Windows Machines, as well as RockPi and ODroid.

## Assembly

### Buttons
1. Remove the body of the controller from the print bed. Use care to lift it minimizing damage to both the print bed and the object.
2. Take the six arcade-style switches, and put the button face through the front of the controller body. Secure them by putting the plastic nuts and washers on, from the other side. Make sure they’re not too tight.
3. Construct the six switch/light assemblies, by pushing the LED wedge into the socket on the black mount piece, and clipping the switch into the mount piece, paying attention to the dots on the switch, and the holes in the mount piece. Make sure the orange clicky notch on the switch faces towards the LED.
4. Screw the switch/light assemblies into the switches by means of an eighth turn into the switch clockwise. Note the notches on the lip of the button face to line up the entryway.
5. Take the four M4 bolts, and four of the nylon spacers, and thread the spacer onto the bolt. Pass the screws with spacers (screw end outside) through the holes on the body where the joystick will sit, and insert the joystick, stick upwards, into the hole. It should line up evenly with the holes. Take the M4 bolts and fasten them up on the underside of the housing. Pass the joystick’s cover plate onto the stick, and screw the joystick’s ball on top.

### Wiring
1. Attach the crimps to the top and second-top spade terminal of each button, and the start and coin button. Then, connect these to any of the bottom row spaces on the controller board.
2. Via soldering, connect the joystick switches to the 5V rail (red socket). This can also be done with piggyback crimp lugs (PT4810), however it is up to you to connect these.
3. The joystick wires into a larger JST connector on the bottom of the controller board, which can be cut and recrimped to connect the joystick. Watch the polarity and pinout to correctly wire it. VSS (+5V) should connect to one leg of the switch, and the other 4 should connect to the separate legs of the switches on the joystick.
4. Order into the bottom row is not important. The mapping phase will organize these into the software stage.
5. Plug the USB cable into the board, and pass it out the hole.

### Closing it up
1. Put the M3 spacer in the hex hole and use a soldering iron to close the edges of the hole and hold the spacer in place. You can use the iron to push the edge plastic over the lip of the spacer.
2. Place the M3 screw through a nylon spacer, through the baseplate and screw it into the body once all cables are passed through the hole.
3. Unstick the rubber feet, and stick them evenly on the controller. This concludes the construction of the controller. Plug it in, via USB to the Raspberry Pi.

**CAUTION:** When using a soldering iron, always pay attention to where it is, and when it’s on. Never leave the iron unattended when powered.

## Installation

### RetroPie Installation
To get an installation of RetroPie, head to the [RetroPie Downloads page](https://retropie.org.uk/download/).

#### Do you have a Pi 2/3?
Click on the link circled in blue, to download the Raspberry Pi 2/3 package. This will download a .img file that can later be used to install RetroPie on the Pi.

#### Do you have a Pi 4/400?
Click on the link circled in green, to download the Raspberry Pi 4/400 package. This will download a .img file that can later be used to install RetroPie on the Pi.

#### Using Balena Etcher
To write the installer to the SD card, you will need an etching program, such as [Balena Etcher](https://www.balena.io/etcher/).

1. Once downloaded, unzip and run to reveal the interface.
2. Press "Flash from file" and navigate to the file just downloaded. Press "Open", which will take you back to the Etcher interface.
3. Press "Select target" and tick the box of the SD card. It is important you tick only the box that is the SD card you would like to write it to.

   **CAUTION:** When formatting drives, be careful of other drives on the computer. Data can be lost by ticking the wrong box.

4. Press "Flash!" This process may take up to 20 minutes.
5. Remove your SD card from the computer, and put it in the Raspberry Pi. Apply power to the Pi via the MicroUSB port, plug in a monitor via HDMI, and watch as RetroPie installs. The first time booting will take longer as RetroPie installs. You may need to follow the installation with a keyboard to enter some values.

## Controller Setup & Compatible Controllers

### J64 Controller
MAME controllers and RetroPie go together like butter and toast, but need a little work to work optimally for all games. On RetroPie’s first boot into EmulationStation, it will prompt the user to configure a controller.

Hold down any button on the J64 to register the gamepad to RetroPie. It will then ask you for a series of “mappings” to tie buttons to controls, however, there aren’t enough buttons for each game control. Below is a table of what to press for each one.

| Screen Name        | What to Press                            |
|--------------------|------------------------------------------|
| D-PAD UP           | Joystick UP                              |
| D-PAD DOWN         | Joystick DOWN                            |
| D-PAD LEFT         | Joystick LEFT                            |
| D-PAD RIGHT        | Joystick RIGHT                           |
| START              | Start Button (Right Black Mini Switch)   |
| SELECT             | Coin Button (Left Black Mini Switch)     |
| BUTTON A/EAST      | Bottom Middle Arcade Switch              |
| BUTTON B/SOUTH     | Bottom Left Arcade Switch                |
| BUTTON X/NORTH     | Top Middle Arcade Switch                 |
| BUTTON Y/WEST      | Top Left Arcade Switch                   |
| LEFT BUMPER        | N/A                                      |
| RIGHT BUMPER       | N/A                                      |
| LEFT TRIGGER       | N/A                                      |
| RIGHT TRIGGER      | N/A                                      |
| LEFT THUMB         | N/A                                      |
| RIGHT THUMB        | N/A                                      |
| HOTKEY ENABLE      | Bottom Right Arcade Switch               |

Afterwards, use the J64 to navigate through the main screen, and press Start to enter the Main Menu, select “Configure Input” and change inputs if necessary.

### Hotkeys
Hotkeys are combinations of buttons pressed together to enable or disable certain functions. The hotkey allows button shortcuts for tasks such as saving, quitting, and other important functions during gameplay. Set the hotkey to the bottom right button.

**Hotkeys List:**

| Function           | Hotkey Combination       |
|--------------------|--------------------------|
| Exit Emulator      | Hotkey + Start           |
| Save State         | Hotkey + Y               |
| Load State         | Hotkey + X               |
| Reset              | Hotkey + B               |
| Pause              | Hotkey + Start           |
| Shutdown           | Hotkey + Left Shoulder   |
| Volume Up          | Hotkey + D-Pad Right     |
| Volume Down        | Hotkey + D-Pad Left      |

For more information about hotkeys, visit the [RetroPie Hotkeys Documentation](https://retropie.org.uk/docs/).

## Conclusion
Congratulations on building the J64! Enjoy your new gaming experience and share it with friends and family. For additional help, visit the [RetroPie Documentation](https://retropie.org.uk/docs/), and join the community forums.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
