# FABulous_Arduino_Bitbang
This repo contains a header file and the corresponding assembly implementation file to program FABulous FPGAs with Arduino

According to the [FABulous Documentation](https://fabulous.readthedocs.io/en/latest/simulation/simulation.html) FABulous spports:
- Serial (Mode 0): Send configuration in through UART

- Parallel (Mode 1) - default in the testbench: Use parallel configuration port

- Bitbang configuration port (To be supported in the testbench)

This repository gives a AVR assembly implementation of the protocol to be used in Arduino Microcontrollers.
