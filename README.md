# Temp-Measure-With-Heart-Beat-Count-

This program is designed to toggle an LED and trigger a temperature sensor readout based on specific conditions, using an STM32 microcontroller and FreeRTOS.

Heartbeat Task: The heartbeat task toggles a red LED every 500 milliseconds. The program counts the number of toggles, and each time the count is a multiple of 3, a semaphore is given, triggering a temperature sensor readout.

Temperature Readout Task: A second task waits for the semaphore. When received, the task reads the internal temperature sensor of the MCU, processes the ADC value, converts it to a temperature, and sends the result through a UART for display.

Synchronization: The two tasks are synchronized using a semaphore, ensuring that the temperature sensor readout is triggered only when the heartbeat task detects the condition (every 3rd LED toggle).
