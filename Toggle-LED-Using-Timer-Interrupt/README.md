# Toggle LED On/Off Using Timer
In this example, the on-chip LED turns on/off using Global Timer Interrupt Every 200ms. The timer used here is `TIM3`. Each time the interrupt is called, the LED pin toggles. In `HAL_TIM_PeriodElapsedCallback()` Function, `HAL_GPIO_TogglePin()` is called and the LED pin toggles.
- **LED Pin (_PA5_)** is set on `GPIO_Output (Output Push-Pull)` with `no pull-up and no pull-down`.
- The timer is prescaled by 1000 and the auto-reload register is initialized with 3200 and timer auto-reload preload is enabled, in order to call the interrupt every 200ms because the system clock is set 16MHz. There is no difference in counter mode (up-counter or down-counter). 
- This timer is used simply and non of the channels are used.
- ***Note that STMCubeMX does not call `HAL_TIM_Base_Start_IT()` in `main()` function and you have to add it manually, else your timer never starts and the callback is never called.***
