README
In this project, 3 STM32 F334R8 microcontrollers are utilized for CAN bus communication without using a filter. A data packet with the identifier 0x446 is transmitted, and if the DLC (Data Length Code) equals 8, the LED pin (pin 5) is activated. It's essential to note that all MCP2561 FD transceivers need to be powered from the same source and connected to a common ground. A 120-ohm resistor should be connected at each end of the CAN bus line to prevent signal reflections.

How do I get set up?
Configuration HSI 8Mhz PLLCLK SYSCLK = 64 Mhz AHB Prescaler = 1 HCLK = 64 MHz
Activated CAN Rx0 interrup Preescaler TQ = 8 TQBit segment 1 = 3 times TQBit segment 2 = 4 times time for one Bit = 2000ns Baut Rate = 500kbit/s

Deployment instructions Connection of MCP2561 FD with STM32 Nucleo F334R8:
Pins:

Txd => P11 Vss => GND Vdd => 5V Rxd => P12 STBY => GND CANH => CAN H line with resistor 120 ohm between CANH and CAN L CANL => CAN L line with resistor 120 ohm between CANH and CAN L SPLIT => Not connected, normal mode Pin connection of MCP2561 to STM32 Nucleo F334R8:

Txd (Transmitter Data) of MCP2561 is connected to pin P11 of STM32. Vss (Ground Supply Pin) of MCP2561 should be connected to the ground (GND) of STM32 to complete the power circuit. Vdd (Supply Voltage Pin) of MCP2561 should be connected to a 5V source on the STM32 to power the transceiver. Rxd (Receiver Data Output Pin) of MCP2561 is connected to pin P12 of ST32. STBY (Standby Mode Input Pin) of MCP2561 is connected to ground (GND) as mentioned. If you want to activate normal mode, make sure it is connected to Vdd or held through a resistor to Vdd. CANH and CANL should be connected to the CAN bus along with 120-ohm terminal resistors to ensure proper termination of the CAN bus.

Contribution guidelines
Referential video https://www.youtube.com/shorts/Cmko3YY6l-k

Writing tests
Code review
Other guidelines
Who do I talk to?
Repo owner or admin
Other community or team contact
