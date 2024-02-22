# OneWire library for MbedCE
This OneWire library brings implementation of OneWire protocol over GPIO or UART for MCU without One-Wire module and its purpose (for now) to be just a part of another library with a Dalas device (like temp sensor DS18B20).

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
