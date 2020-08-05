# Turning LED On/Off Using Pushbutton
In this example, the on-chip LED turns on/off using the on-chip pushbutton. Each time the pushbutton is pressed the LED pin toggles using an external interrupt. The interrupt is set on `rising edge trigger detection`. In `HAL_GPIO_EXTI_Callback()` Function, `HAL_GPIO_TogglePin()` is called and the LED pin toggles.
- **LED Pin (_PA5_)** is set on `GPIO_Output (Output Push-Pull)` with `no pull-up and no pull-down`.
- **Pushbutton Pin (_PC13_)** is set on `GPIO_EXTI13 (External Interrupt Mode with Rising edge trigger detection)` with `pull-up`. Pull-up is set because the on-chip pushbutton is connected to the ground.
This Project Is Done By STMCubeMX 6.0.
