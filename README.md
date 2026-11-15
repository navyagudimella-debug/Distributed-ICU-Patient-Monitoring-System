
# Distributed ICU Patient Monitoring System

A distributed embedded patient monitoring prototype using LPC2129 ARM7 microcontrollers and CAN communication.

## Project Overview

This project demonstrates a two-node embedded monitoring architecture designed to acquire patient-related parameters and transfer monitoring data to a centralized PC through CAN and UART communication.

The system uses two LPC2129-based nodes:

- **Node A (Transmitter):** Acquires sensor data and transmits it through CAN.
- **Node B (Receiver):** Receives CAN data and forwards the information to a PC through UART.

## System Architecture

```text
LM35 Temperature Sensor
          |
       ADC 0
          |
MAX30100 -- I2C
          |
       Node A
       LPC2129
          |
       CAN Bus
          |
       Node B
       LPC2129
          |
        UART
          |
      PC / Server
```

## Hardware Components

| Component | Purpose |
|---|---|
| LPC2129 | ARM7 microcontroller |
| LM35 | Temperature measurement |
| MAX30100 | Pulse rate and SpO2 sensing |
| TJA1050 | CAN transceiver |
| CAN twisted-pair cable | Node-to-node communication |
| PC | Monitoring and data display |

## Communication Protocols

| Protocol | Application |
|---|---|
| ADC | Analog sensor acquisition |
| I2C | MAX30100 communication |
| CAN 2.0 | Communication between Node A and Node B |
| UART | Communication between Node B and PC |

## Repository Structure

```text
Distributed-ICU-Patient-Monitoring-System/
|
|-- node_tx/
|   |-- main.c
|   |-- adc_driver.c
|   |-- can_driver.c
|   |-- i2c_driver.c
|   |-- uart_driver.c
|   |-- max_init.c
|   |-- spo2_driver.c
|   |-- max30100.h
|   |-- header.h
|
|-- node_rx/
|   |-- main.c
|   |-- can_driver.c
|   |-- uart_driver.c
|   |-- header.h
|
|-- Documentation/
|-- Results/
|-- README.md
|-- .gitignore
```

## Software and Tools

- Embedded C
- Keil uVision
- LPC2129 Development Board
- Flash Magic
- UART Serial Terminal

## Key Learning Outcomes

- Embedded C programming
- Peripheral driver development
- ADC interfacing
- I2C communication
- CAN protocol implementation
- UART serial communication
- Multi-node embedded system design

## Future Enhancements

- Support for additional sensor nodes
- Real-time monitoring dashboard
- Data logging and storage
- Threshold-based alerts
- Improved communication error handling

## Disclaimer

This is an academic embedded systems prototype intended for learning and demonstration. It is not a certified medical device and must not be used for clinical diagnosis or patient-care decisions.

