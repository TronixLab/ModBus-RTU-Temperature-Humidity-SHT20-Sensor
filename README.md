# ModBus RTU Temperature & Humidity (SHT20) Sensor

## MAX485 TTL to RS-485 Interface Module

| ![space-1.jpg](https://github.com/TronixLab/ModBus-RTU-Temperature-Humidity-SHT20-Sensor/blob/main/Docs/MAX485-RS-485-Interface-Module-Connections.jpg) | 
|:--:| 
| **Fig. 1** *MAX485 TTL to RS-485 Interface Module* |

### Description
This low-power transceiver module uses the Maxim MAX485 IC to enable serial communication over extremely long cable runs (up to 4000 feet / 1200 meters). At a data rate of up to 2.5Mbps, serial data can be transmitted in both directions (half duplex). The modules run on a standard 5V power supply and use 5V logic levels, allowing them to be interfaced to the hardware serial ports of microcontrollers like Atmega, PIC, ESP, Pico, among others. It is also possible to connect multiple modules together to communicate with up to 32 devices. In Modbus RTU, RS485 allows for master/slave communication, with a maximum of 247 slaves for one master. A repeater module is required in the circuit to achieve this.

### Key Features of MAX485 TTL to RS-485 Interface Module
* Use MAX485 Interface chip
* Uses differential signaling for noise immunity
* Distances up to 1200 meters
* Speeds up to 2.5Mbit/Sec
* Multi-drop supports up to 32 devices on same bus
* Red power LED
* 5V operation

**Note**: RS-485 is widely used in industrial environments because it allows for reliable serial communications over large distances of up to 1200 meters (4000 feet) or in electrically noisy conditions. It can support data speeds of up to 2.5MBit/sec, however as distance increases, the maximum data rate that can be comes down.

#### *Multi-Drop Support for Multiple Devices*
RS-485 has the advantage of supporting numerous devices (up to 32) on the same wire, a feature known as "multi-drop."
As demonstrated below, this works by running the bus through each device, which picks up the signal as it passes by.
With one Master and one or more Slave devices, these devices are often set up in a Master / Slave arrangement. Because they all ride the same bus, the Slave devices only communicate with each other when the Master requests something, such as a temperature reading.

| ![space-1.jpg](https://github.com/TronixLab/ModBus-RTU-Temperature-Humidity-SHT20-Sensor/blob/main/Docs/rs485_line.jpg) | 
|:--:| 
| **Fig. 2** *RS-485 Wiring Guide* |

#### *Differential Signaling*
Only two wires and a common ground are required for the RS-485, which employs differential signaling. Differential signals work by connecting one wire to the signal and the other wire to the inverse of the signal. As noise tends to couple into both lines equally and thus cancels out at the receiving end, this enhances the signal's noise tolerance and capacity to recover the signal at the far end of the cable.

#### *Pull-up Resistors*
On the data lines of the module, there are four 10K pull-up resistors. On the A/B differential lines, two 20K resistors are used. When data is not being transferred, these pull the lines to a known condition. A single 120-ohm resistor completes the circuit (R7). To prevent reflections, place this resistor between the A/B differential lines on each end of the cable. The resistors on the two ends of the line should be kept if employed in a multi-drop setup. 

### Module Wiring
| ![space-1.jpg](https://github.com/TronixLab/ModBus-RTU-Temperature-Humidity-SHT20-Sensor/blob/main/Docs/RS485_Module_HCMODU0081_Diagram.png) | 
|:--:| 
| **Fig. 2** *RS-485 Wiring Guide* |

The module has two 4-pin headers on the assembly. The headers are spaced 1.6″ apart, so if using with solderless breadboards, it is necessary to bridge two different breadboards.
**1 x 4 Header (Data side)**
* RO = Receiver Output. Connects to a serial RX pin on the microcontroller
* RE = Receiver Enable. Active LOW. Connects to a digital output pin on a microcontroller. Drive LOW to enable receiver, HIGH to enable Driver
* DE = Driver Enable. Active HIGH. Typically, jumper to RE Pin.
* DI = Driver Input. Connects to serial TX pin on the microcontroller
**1 x 4 Header (Output side)**
* VCC = 5V
* B = Data ‘B’ Inverted Line. Common with the B
* A = Data ‘A’ Non-Inverted Line. Connects to A on far end module
* GND = Ground
**1 x 2 Screw Terminal Block (Output side)**
* B = Data ‘B’ Inverted Line. Connects to B on far end module
* A = Data ‘A’ Non-Inverted Line. Connects to A on far end module
