Imitating an sduino UNO with an STM8S-DISCOVERY board
=====================================================

The sduino UNO can be imitated using one of ST's STM8S-DISCOVERY boards
combined with a CH340G-based USB to Serial converter with switchable
voltage levels (5V, 3.3V) and jumper wires.
This setup can be completed with an LED connected via LM358 OpAmp and
a voltage regulator for battery operation.
All components can be arranged on or connected to a prototyping shield for
easier use.

The following figures describe the required pin mapping.

STM8S-DISCOVERY
---------------

The STM8S-DISCOVERY board incorporates an STM8S105C6T6 microcontroller with
48 pins that are accessible through four connectors.

      +3V3 VDD U5V

                    0   5   3   4
                   PD6 PD4 PD2 PD0 PE1 PE3
                   PD7 PD5 PD3 PD1 PE0 PE2
                    2   1   6   7
      NRST PA1                                 PG1 PG0
       PA2 VSS                              12 PC7 PC6 11
       VSS VCAP                                VDD VSS
       VDD VDD                              13 PC5 PC4 10
       PA3 PA4                           9¹ EX_PC3 PC2 23
       PA5 PA6                           8¹ EX_PC1 PE5 24
                            A5  A2  A0
                   VSS PB6 PB4 PB2 PB0 PE6
                  VDDA PB7 PB5 PB3 PB1 PE7
                            A4  A3  A1

¹ Requires solder bridges

sduino UNO
----------

The sduino UNO board is designed for an STM8S105K6T6 or -U6 microcontroller
with 32 pins, most of which are accessible through connectors.

     A5  A4  22²     13  12  11  10  9   8   7   6   5   4   3   2   1   0
    PB4 PB5 PF4 VSS PC5 PC7 PC6 PC4 PC3 PC1 PD1 PD3 PD4 PD0 PD2 PD7 PD5 PD6
    
                                                                 12 PC7 U5V
                    U5V                                          13 PC5 PC6 11
                    VDD                                            NRST VSS
                    +3V3                                         23 PC2 PE5 24
    
                    IOREF NRST +3V3 U5V VSS VSS Vin PB0 PB1 PB2 PB3 PB5 PB4
                                                     A0  A1  A2  A3  A4  A5

² Not present on STM8S-DISCOVERY (STM8S105C6T6)
