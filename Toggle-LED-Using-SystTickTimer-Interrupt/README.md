# Toggle LED On/Off Using SysTickTimer
In this example, the on-chip LED turns on/off using SysTickTimer Interrupt Every 200ms. Each time the interrupt is called, the LED pin toggles. In `HAL_SYSTICK_Callback()` Function, `HAL_GPIO_TogglePin()` is called and the LED pin toggles.
- **LED Pin (_PA5_)** is set on `GPIO_Output (Output Push-Pull)` with `no pull-up and no pull-down`.
- Before the infinite loop of the main program, `HAL_SYSTICK_Config()` is called with the value of **3200000**, because the system clock is set on 16MHz, so in order to toggle LED every 200ms, we need to toggle it every **3200000** ticks.
- ***Note that STMCubeMX does not call `HAL_SYSTICK_IRQHandler()` in function `SysTick_Handler()` and you have to add it manually, else your callback is never called. This issue can be found on https://community.st.com/s/question/0D50X00009yHWejSAG/halsystickirqhandler-call-is-missing-in-cubemx-v5-generated-systickhandler.***
