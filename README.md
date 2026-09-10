# Interrupt-Based Digital Tachometer for Real-Time RPM Measurement

An embedded digital tachometer developed using the **PIC16F877A microcontroller** for non-contact real-time rotational speed measurement.

The system uses an **infrared sensor** to detect rotational pulses. Each detected pulse generates an external interrupt on the PIC16F877A. **Timer1** provides a precise 1-second measurement window, allowing the firmware to calculate and display the motor speed in RPM on a **16×2 LCD**.

An over-speed indication is also implemented using a GPIO-controlled LED.



## Features

- Real-time RPM measurement
- Non-contact speed sensing using an IR sensor
- External interrupt-based pulse detection
- Timer1-based measurement window
- 16×2 LCD RPM display
- Configurable pulses-per-revolution (PPR)
- Over-speed detection
- GPIO-based warning LED
- Interrupt-driven Embedded C firmware
- Designed for high-speed pulse detection

---

## System Overview


                 Rotating Object
                       │
                       ▼
                  IR Sensor
                       │
                 Pulse Signal
                       │
                       ▼
              RB0 / INT Pin
                       │
                       ▼
           External Interrupt ISR
                       │
                       ▼
                 Pulse Counter
                       │
                       │
                       ▼
                RPM Calculation
                       │
                       ▼
                  16×2 LCD
                       │
                       └──────► RPM Display


                 PIC16F877A
                     │
                   Timer1
                     │
             1-second time window
                     │
                     ▼
             Measurement Complete
