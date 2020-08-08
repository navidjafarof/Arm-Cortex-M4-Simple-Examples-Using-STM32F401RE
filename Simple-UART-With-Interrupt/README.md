# Simple UART With Interrupt
In this example, `USART1` is set to exchange data in asynchronous mode. `USART1` is waiting to receive data and then transmits the received data. `USART1` is configured on asynchronous mode, 9600 bits/sec Baud Rate, 8bit Word Length (including parity), None parity, 1 Stop Bit, Recieve And Transmit Data Direction and 16 Samples Over Sampling.
- **USART1 TX Pin (_PA9_) and RX Pin (_PA10_)** are set on appropriate `Alternative Function` with `no pull-up and no pull-down` and maximum output speed on `Very High`.
- `HAL_UART_Receive_IT()` function is called in infinite loop. `HAL_UART_RxCpltCallback()` function is called every time USART receives data. In this function, received data transmits through UART using the `HAL_UART_Transmit()` function.
- This program can be tested using **serial port terminal applications** such as CoolTerm.
