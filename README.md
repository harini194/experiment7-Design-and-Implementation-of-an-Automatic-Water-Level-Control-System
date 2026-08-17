# Experiment: UART Communication Using STM32 Nucleo-L031K6

## Aim

To configure and demonstrate **UART serial communication using the STM32 Nucleo-L031K6** and display messages on the **Wokwi Serial Monitor**.

---

## Components Required

- STM32 Nucleo-L031K6
- Wokwi Simulator
- USART2 Peripheral
- Virtual Serial Monitor

---

## Theory

**UART (Universal Asynchronous Receiver/Transmitter)** is a serial communication method used to transmit and receive data between a microcontroller and other devices.

UART communication mainly uses:

- **TX (Transmit)** – Sends data
- **RX (Receive)** – Receives data
- **GND** – Common ground

UART is called **asynchronous communication** because it does not require a separate clock signal. The transmitter and receiver must use the same communication parameters such as **baud rate, data bits, parity, and stop bits**.

In this experiment, **USART2** of the STM32 Nucleo-L031K6 is configured with:

- **Baud Rate:** 115200 bps
- **Data Bits:** 8
- **Parity:** None
- **Stop Bits:** 1

This configuration is commonly represented as **115200, 8-N-1**.

---

## Pin Configuration

| UART Function | STM32 Pin |
|---|---|
| USART2 TX | PA2 |
| USART2 RX | PA15 |
| Ground | GND |

In Wokwi, the transmitted UART data is displayed using the **Serial Monitor**.

---

## Block Diagram

~~~text
+-------------------------+
| STM32 Nucleo-L031K6     |
|                         |
|        USART2           |
|                         |
| PA2 (TX)  --------------+------> Serial Monitor
|                         |
| PA15 (RX) <-------------+------- Serial Input
|                         |
+-------------------------+
~~~

---

## Algorithm



---

## Program



## Procedure

1. Open **Wokwi**.
2. Create a project using the **STM32 Nucleo-L031K6**.
3. Enter the UART program.
4. Configure **USART2** for serial communication.
5. Set the baud rate to **115200 bps**.
6. Configure **PA2 as USART2 TX**.
7. Configure **PA15 as USART2 RX**.
8. Compile the program.
9. Start the Wokwi simulation.
10. Open the **Serial Monitor**.
11. Observe the messages transmitted by the STM32.

---

## Expected Output

~~~text
STM32 UART Communication Experiment

Hello from STM32 Nucleo-L031K6!
Hello from STM32 Nucleo-L031K6!
Hello from STM32 Nucleo-L031K6!
~~~

A new message is transmitted approximately **once every second**.

---

## Working

The STM32 initializes **USART2** and transmits characters serially through the UART TX line.

The `_write()` function redirects the output of `printf()` to USART2 using the `HAL_UART_Transmit()` function.

The transmitted UART data is received by the **Wokwi Serial Monitor** and displayed on the screen.

The program waits for **1000 ms (1 second)** using `HAL_Delay(1000)` and transmits the message repeatedly.

---

## Result

Thus, **UART serial communication using the STM32 Nucleo-L031K6** was configured and implemented successfully, and the transmitted data was observed on the **Wokwi Serial Monitor**.
