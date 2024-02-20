<!--
  If you have any question about this then rise an issue https://github.com/mbed-ce-libraries-examples/LibraryTemplate/issues
  
  Under this block replace the text with a name of new library and some short description.
-->
# OneWire library for MbedCE
This OneWire library brings implementation of OneWire protocol over GPIO or UART for MCU without One-Wire module and its purpose (for now) to be just a part of another library with a Dalas device (like temp sensor DS18B20).

<!--
  Under this block edit How to start with the library under MbedCE
  ## How to start
-->



<!--
  Under this block edit the simple example code for the new library.
  But if the library is too sophisticated and need an advanced code then rather make an example project for this library, delete the simple example code and replace it with a link to the example
  ## Example code
-->

<!--
  Under this block replace the text with more detailed description about the library.
  For example:
  - pinout of the component what this library interface for
  - pictures
  - troubleshoting 
-->

## Description

This library is able do two variants

1. establish standard one-wire communication over GPIO pin
```
           ----------------
          |                |   ----------------------->  +3.3V
          |   MBED BOARD   |  |
          |                |  |   ------
          |          +3.3V |--o--| 4.7k |-------
          |                |      ------        |
          |                |                    |
          |                |                    |
          |                |                    |
          |                |                    |
          |           GPIO |--------------------o----->  1-wire bus/line
          |                |
          |                |
          |            GND |-------------------------->  GND
          |                |
           ----------------

```
2. establish one-wire communication over UART pins
```
           ----------------
          |                |   ----------------------->  +3.3V
          |   MBED BOARD   |  |
          |                |  |   ------
          |          +3.3V |--o--| 4.7k |-------
          |                |      ------        |
          |                |      ------        |
          |        UART TX |-----|  470 |---    |
          |                |      ------    |   |
          |                |                |   |
          |        UART RX |----------------o---o----->  1-wire bus/line
          |                |
          |                |
          |            GND |-------------------------->  GND
          |                |
           ----------------
```

The variant with UART is for special cases. For example STM32L families are very slow in changing GPIO from output to input and then the one-wire can not achieve correct protocol timing.

## Special info:
Special thanks to Zoltan Hudak for his contribution to Mbed. Peace friend.
