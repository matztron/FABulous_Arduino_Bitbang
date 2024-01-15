# FABulous_Arduino_Bitbang
This repo contains a header file and the corresponding assembly implementation file to program FABulous FPGAs with Arduino

According to the [FABulous Documentation](https://fabulous.readthedocs.io/en/latest/simulation/simulation.html) FABulous spports:
- Serial (Mode 0): Send configuration in through UART

- Parallel (Mode 1) - default in the testbench: Use parallel configuration port

- Bitbang configuration port (To be supported in the testbench)

This repository gives a AVR assembly implementation of the protocol to be used in Arduino Microcontrollers.

## What do we have here?
There are multiple possible ways to get the bitstream from the Arduino (using Atmega AVR) onto the FPGA.
ALl approaches use the bitbang protocol that was referenced above in the FABulous documentation.

### Approach #1:
Here we load the full bitstream into the FLASH-portion of the AVR microcontroller. You need to make sure that there is sufficiently enough space for the bitstream (they can get large).
When flashing the Arduino sketch you should look at the output of avrdude to see how much space you still have left.

How it works:
1. Use the `cvrt_bitstream_2_Hfile.py` Python script to convert a FABulous bitstream into a C header file.
2. Include the header file in your sketch.
3. Include the `fpga_bitbang.S` in your sketch.
4. Flash onto the AVR microcontroller.

### Apprach #2:
The other approache is transfering the bitstream via UART to a FPGA and then sending it to the FPGA (for bitstreams larger than that fits in the FLASH of the Atmega-device. Study the output of avrdude when flashing with approach #1 to see how much free space is left.
//TODO: Add the code for that here!
