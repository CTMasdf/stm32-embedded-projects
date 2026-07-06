# STM32 FreeRTOS LED Multi-Task

## Demo Video

https://youtube.com/shorts/_bSGh-X4Ryw](https://www.youtube.com/watch?v=scLDuqXt2UU&list=PLWeYcGhnIKbg&index=2

## Hardware

- STM32F103C8T6 (Blue Pill)
- 4 External LEDs (Active Low)
- ST-LINK V2

## GPIO Configuration

| LED | Pin | Period |
|-----|-----|---------|
| LED1 | PB3 | 500 ms |
| LED2 | PB4 | 1000 ms |
| LED3 | PB5 | 1500 ms |
| LED4 | PB6 | 2000 ms |

## RTOS Structure

```text
FreeRTOS Scheduler
│
├── Led1Task (500 ms)
├── Led2Task (1000 ms)
├── Led3Task (1500 ms)
└── Led4Task (2000 ms)
