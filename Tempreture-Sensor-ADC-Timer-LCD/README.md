# Temperature Sensor ADC With Timer And LCD
In this example, `ADC1` is used to calculate the temperature using the on-chip temperature sensor. `TIM2` timer is used to trigger the `ADC1` every one second. Each time the timer has reached it `Counter Period`, it triggers the ADC to do a conversion. Once the conversion is completed, the temperature is calculated and showed on LCD.
Some LCD functions are written using this link: http://www.microdigitaled.com/ARM/STM_ARM/Code/Ver1/Chapter03/Program3-1.txt (HAL alternatives are replaced instead of CMSIS structures.)
Some LCD functions added to make things easier.
- **LCD Data Pins (PC0 - PC7) and LCD Control Pins (PB5 - PB7)** are set on `GPIO Output Push-Pull` Mode with `no pull-up and no pull-down`.
- `HAL_ADC_ConvCpltCallback()` function is called when the conversion is completed. in this function, ADC value is read and the temperature is calculated and showed on LCD.
- `ADC1` Temperature Channel Active and ADC is Configuration is: Clock Prescaler is set on `PCLK2 divided by 2`, `12bit` Resolution, `Right Alignment` data, `Continuous Conversion` Enabled, External Conversion Source on `Timer2 Trigger Out event`, External Trigger Conversion edge on `Rising edge`. Note that there is no difference in End Of Conversion Selection because there is only one conversion done.
- `TIM2` clock is prescaled by 1000, on `Up Counter` Mode, with 16000 `Counter Period` and auto-reload preload enabled. Note that Trigger Event Selection must be on `Update Event`, else the ADC is not triggered.
