# STM32 Slide Switch Mode Controller (State Machine)

## Demo Video
https://www.youtube.com/watch?v=dyYU6o39anU&list=PLWeYcGhnIKbg&index=4

---

## Hardware
- STM32F103C8T6 (Blue Pill)
- 2 Slide Switch (Mode Select)
- 4 LEDs
- ST-LINK V2

---

## GPIO Configuration

| Device | Pin | Mode |
|--------|-----|------|
| LED1 | PA4 | GPIO Output |
| LED2 | PA5 | GPIO Output |
| LED3 | PA6 | GPIO Output |
| LED4 | PA7 | GPIO Output |
| SW1 | PB0 | GPIO Input (Pull-down) |
| SW2 | PB1 | GPIO Input (Pull-down) |

---

## Features

- GPIO Input (Slide Switch)
- GPIO Output (LED Control)
- State Machine (Mode Control)
- Non-blocking Timing using HAL_GetTick()
- Running LED Effect
- Blink LED Effect
- Independent Mode Switching
- EXTI Button Mode Reuse (Project02)

---

## Operation

### Mode Selection

| SW2 | SW1 | Mode | Behavior |
|-----|-----|------|----------|
| 0 | 0 | Mode 0 | All LEDs OFF |
| 0 | 1 | Mode 1 | Running LED |
| 1 | 0 | Mode 2 | Blink LED |
| 1 | 1 | Mode 3 | EXTI Button Control (Project02 Reuse) |

---

### Mode Behavior

**Mode 0**
- All LEDs OFF
- Idle state

**Mode 1**
- Running LED
- One LED moves sequentially (PA4 → PA7)

**Mode 2**
- Blink LED
- All LEDs toggle ON/OFF every 500ms

**Mode 3**
- External Interrupt (EXTI) Button Mode
- Each button toggles corresponding LED (Project02 logic reused)

---

## Software Structure


Slide Switch Input
│
▼
Mode Selection (State Machine)
│
▼
┌───────────────┬───────────────┬───────────────┐
│ Mode 0 │ Mode 1 │ Mode 2 │
│ All OFF │ Running LED │ Blink LED │
└───────────────┴───────────────┴───────────────┘
│
▼
Mode 3 (EXTI Mode)
Button Interrupt Control (Project02)
