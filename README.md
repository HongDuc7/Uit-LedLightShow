# 🎵 Sound-Reactive NeoPixel LED Strip with STM32

A **sound-reactive RGB LED system** built on the **STM32F411E-DISCO** board, capable of driving a **WS2812B (NeoPixel) LED strip** with multiple lighting effects — including **real-time audio-responsive modes** using a **MAX9814 microphone module**.

> 🎓 Course Project – *Microprocessor & Microcontroller (CE103)*
> 
> 📍 University of Information and Technology – VNU-HCM

---

## ✨ Project Overview

This project implements a **high-performance LED control system** using:

* **PWM (800 kHz)** for WS2812B protocol timing
* **DMA** for CPU-efficient data transfer
* **ADC** to process real-time audio input

The system supports **7 different lighting modes**, including **sound-reactive visualizations** such as volume bars and glow effects synchronized with ambient audio.

---

## 🚀 Features

### 🎨 Default LED Effects

* **COLOR_TRANSITION** – Smooth RGB color fading
* **STROBE** – Random color flashing
* **PIXEL** – Animated moving color bar
* **RAINBOW** – Dynamic rainbow gradient
* **ALL_OFF** – Turn off all LEDs

### 🎧 Sound-Reactive Effects

* **ADC_GLOW**

  * All LEDs glow in **magenta**
  * Brightness scales with audio intensity
* **ADC_VOLUME_BAR**

  * LED count represents sound level
  * Smooth rainbow gradient with dynamic motion

🎛️ **Single Button Control**
A push button cycles through all 7 modes with built-in debounce handling.

---

## 🧠 System Architecture

* **Timer (TIM4)**
  Generates 800 kHz PWM signal for WS2812B communication

* **DMA**
  Transfers LED bitstream directly to PWM register (low CPU load)

* **ADC (12-bit)**
  Reads analog signal from MAX9814 microphone
  → Converts sound intensity into lighting data

---

## 🔌 Hardware Setup

| Component  | Description             |
| ---------- | ----------------------- |
| MCU        | STM32F411E DISCO        |
| LED Strip  | WS2812B – 29 LEDs       |
| Microphone | MAX9814 (Analog Output) |
| Power      | 5V External Supply      |

### 🔗 Pin Mapping

| STM32 Pin | Connected To      |
| --------- | ----------------- |
| **PD12**  | WS2812B Data In   |
| **PA1**   | MAX9814 OUT (ADC) |
| **3V3**   | MAX9814 VDD       |
| **GND**   | Common Ground     |

---

## 🧮 Key Technical Specs

* PWM Frequency: **800 kHz**
* LED Data Format: **24-bit (GRB)**
* ADC Resolution: **12-bit (0–4095)**
* LED Buffer: **DMA-based**
* Max Brightness: **~10% (Power & Thermal Safe)**

---

## 📂 Software & Tools

* **STM32CubeIDE**
* **STM32F4 HAL Library**
* Language: **C**
* No RTOS (Bare-metal)

---

## 👨‍💻 Authors

| Name                 | Role                                   |
| -------------------- | -------------------------------------- |
| **Trần Lê Minh Đạt** | ADC Effects, Environment Setup         |
| **Võ Hồng Đức**      | Core LED Effects, Hardware Integration |

Instructor: **Trần Ngọc Đức**

✨ *If you like this project, give it a ⭐ on GitHub!*
