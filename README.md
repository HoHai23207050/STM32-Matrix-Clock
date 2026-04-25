



# STM32 Multi-functional Real-Time Matrix Clock

## Overview
This project is a multi-functional smart clock built around the STM32F103C8T6 (BluePill) microcontroller. It features an 8x32 LED Matrix display to provide a clear, real-time readout of time and environmental temperature, along with a Pomodoro timer function designed to help students and professionals improve focus and productivity.

## Demo Video
*(If the video doesn't autoplay, please click the play button or unmute)*

<video src="[DemoClockMatrix.mp4](https://github.com/user-attachments/assets/41bd6e47-7a9f-49bd-901e-c7a29c76ba0b)" autoplay loop muted playsinline width="100%" controls></video>

## Features
* **Mode 1: Real-Time Clock:** Displays current hours and minutes accurately.
* **Mode 2: Temperature Display:** Shows the current ambient temperature in Celsius.
* **Mode 3: Pomodoro Timer (Alarm):** A 45-minute countdown timer with a buzzer alarm, ideal for structured study or work sessions.
* **Touch Interface:** Uses TTP223 capacitive touch sensors to easily switch between modes.

## Hardware Components
* **Microcontroller:** STM32F103C8T6 (BluePill)
* **RTC Module:** DS3231 (for precise timekeeping and temperature sensing)
* **Display:** MAX7219 8x32 LED Matrix
* **Input:** 3x TTP223 Touch Sensor Modules (for Mode selection)
* **Output:** 5V Active Buzzer (for the alarm)
* **Power:** 5V/3.3V power supply via breadboard/USB

## Pin Configuration (STM32 to Peripherals)

| Component | Pin | STM32 Pin |
| :--- | :--- | :--- |
| **Touch 0 (Mode 1)** | Out | PB3 |
| **Touch 1 (Mode 2)** | Out | PB4 |
| **Touch 2 (Mode 3)** | Out | PB5 |
| **DS3231 (RTC)** | SDA | PB7 |
| | SCL | PB6 |
| **MAX7219 (LED Matrix)** | DIN | PA7 |
| | CLK | PA5 |
| | CS | PA4 |
| **Buzzer** | VCC | PA0 |

*(Note: Ensure all VCC and GND pins are connected to appropriate 3.3V/5V and GND lines on the STM32/Breadboard)*

## How it Works
1.  The **DS3231** module keeps track of the time and temperature via the I2C protocol.
2.  The **STM32** processes this data and sends it to the **MAX7219** LED Matrix via the SPI protocol for display.
3.  The **TTP223 Touch Sensors** act as external interrupts. Touching sensor 1, 2, or 3 switches the device to Mode 1 (Time), Mode 2 (Temperature), or Mode 3 (Pomodoro Alarm), respectively.
4.  In Mode 3, after 45 minutes, a signal is sent to the **Buzzer** to sound the alarm.

## Project Files Included in this Repository
* **Source Code:** (Add the path/instructions for your code here, e.g., `Core/Src/main.c`)
* `Nhóm 7_BÁO CÁO ĐỒ ÁN VI ĐIỀU KHIỂN.pdf`: Detailed project report (Vietnamese).
* `Nhóm 7_BÁO CÁO ĐỒ ÁN VI ĐIỀU KHIỂN.pptx`: Presentation slides.

## Team Members (Nhóm 7 - HCMUS)
* Nguyễn Trần Quốc Bảo
* Hồ Trọng Hải
* Phạm Văn Phúc
* Lê Trần Viết Thịnh
