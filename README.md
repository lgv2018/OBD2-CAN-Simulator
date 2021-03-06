# OBD2-CAN-Simulator
This project simulates CAN BUS of OBD2 port, helping to develop OBD2 CAN BUS projects

# How It Works:
This project get the third byte of data of received CAN message and return then with randomic values on fourth-seventh data of CAN message.
To read OBD protocol our device need to have an ID = 0x7DF, ECM will return with ID = 0x7E8. Knowing this, we configure CAN filter to receive only ID = 0x7E8, with this filter any other ID will be ignored.

# Software:
It uses cubeMX for generate a pre-code. Compiler Keil uVision, but you can easily migrate to another suported compiler by cubeMX, like IAR.
Using STM32F103, we can't uses CAN and USB at same time, because both peripherals share same SRAM. It can works if turning off CAN and turning ON USB, and vice-versa, but I didn't have success. If anyone want's help with this I will be very happy.
NOTE: in folder "CAN_simulator" have an archive "Drivers.zip", you need to extract.

# Hardware:
This hardware uses a STM32F103C8T6 (bluepill board) with a CAN transceiver (MCP2251).
MCP2551 is 5V logic, because of that we need to use PB9 and PB8 pins (this pins are 5V tolerant). Pins PA11 and PA12 aren't 5V tolerant.

<a href="https://imgur.com/2QnrXvz"><img src="https://i.imgur.com/2QnrXvz.jpg" title="source: imgur.com" /></a>

# CAN SPEED
Clock was configured at 72MHz, with this clock we set: 
* CAN preescaler = 9
* Time Quantum in Bit Segment 1 = 3TQ
* Time Quantum in Bit Segment 2 = 4TQ

This configuration gives a CAN speed = 500kbps, 2uS for each bit (most commom on OBD2).

# Enclosure
I made a 3D printed enclosure for this project, STL's and STEP's are avaiable for download on this repository.
<a href="https://imgur.com/not0J4A"><img src="https://i.imgur.com/not0J4A.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/ZdDIA5H"><img src="https://i.imgur.com/ZdDIA5H.png" title="source: imgur.com" /></a>

# Final project
It was not of the best quality, but it met perfectly.
<a href="https://imgur.com/UenPx3U"><img src="https://i.imgur.com/UenPx3U.jpg" title="source: imgur.com" /></a>

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/SRPcslP5UJQ/0.jpg)](https://www.youtube.com/watch?v=SRPcslP5UJQ)

https://www.youtube.com/watch?v=SRPcslP5UJQ&t=1s
