# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/b4c38aa2-531d-4c94-b85c-d87cc1d735bf" />

2. Click **File → New STM32 Project**.
  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/5e426cd2-5067-41e5-9047-e76ba6412c00" />
  <img width="1912" height="1078" alt="image" src="https://github.com/user-attachments/assets/6306fa05-4bdf-404f-89b4-aeeb2ef4c931" />


3. Select the **target microcontroller** or board and click **Next**.
   <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/9a259954-b4d5-4f7d-99c9-49e72c557838" />



4. Name the project.
   <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/cc0a11a3-b1a9-43ac-bc4f-80d93b4b3816" />



5. The corresponding `.ioc` file will be generated automatically.
     <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/f8bed8e7-7075-423d-a979-f9a950e25348" />


6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.
      <img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/d4593d26-1c64-4216-9f85-99d01c5827b7" />
      <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/766ed252-983a-447d-81e7-febfe8b966c1" />

7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
   <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/df0372cc-a176-472f-96f8-ce706e6bffd0" />

 
8. Edit the generated main program as required.
   <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/67b8bdc4-cd7d-4005-9970-6f0480390dee" />


9. Click **Project → Build All**.
    <img width="1907" height="1078" alt="image" src="https://github.com/user-attachments/assets/35a13740-7cc1-4000-b7d4-a9ac36c5d047" />


10. Link the **HEX file** using the post-build process.
    <img width="663" height="205" alt="image" src="https://github.com/user-attachments/assets/abc8abc6-8dad-425f-a091-1635c7dbe567" />


11. Click **Debug** and connect the **STM Nucleo Board**.
    <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/584b00fa-002e-4f07-a4ae-00ee11a6de06" />

13. Click **Run** to execute the program.
    
---

### 💻 **Program**


```
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/6c582ce2-0372-48df-9f2b-dfa8a720b8da" />


CASE 2: LED OFF
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/0829ccbc-c9fe-4e58-b739-b4e3065449a0" />

---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
