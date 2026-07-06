# STM32 Push Button Interrupt (EXTI)

## Demo Video
https://www.youtube.com/watch?v=UlzFuua7fBY&list=PLWeYcGhnIKbg

## Hardware
- STM32F103C8T6 (Blue Pill)
- 4 Push Buttons
- 4 LEDs
- ST-LINK V2

## GPIO Configuration

| Device | Pin | Mode |
|---------|-----|------|
| LED1 | PA4 | GPIO Output |
| LED2 | PA5 | GPIO Output |
| LED3 | PA6 | GPIO Output |
| LED4 | PA7 | GPIO Output |
| Button1 | PB4 | EXTI Falling Edge |
| Button2 | PB5 | EXTI Falling Edge |
| Button3 | PB6 | EXTI Falling Edge |
| Button4 | PB7 | EXTI Falling Edge |

## Features
- GPIO Output
- EXTI Interrupt
- NVIC
- Software Debounce (HAL_GetTick)
- Independent LED Control

## Operation

- Press Button1 → Toggle LED1
- Press Button2 → Toggle LED2
- Press Button3 → Toggle LED3
- Press Button4 → Toggle LED4

## Software Structure

```
Push Button
     │
     ▼
EXTI Interrupt
     │
     ▼
HAL_GPIO_EXTI_Callback()
     │
     ▼
Software Debounce
(HAL_GetTick)
     │
     ▼
HAL_GPIO_TogglePin()
     │
     ▼
LED Toggle
```

## Development Environment
- STM32CubeIDE
- STM32 HAL Driver
