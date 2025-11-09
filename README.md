# TOGGLE-AN-LED-ON-OFF-BY-USING-AN-EXTERNAL-INTERRUPT-IN-ARM-CONTROLLER

**Aim:**

To Interface a Digital Input (user push button ) to ARM development board and write a program to obtain the data and flash the led.

**Components required:** 

1.	STM32 CUBE IDE
2.	ARM IOT development board
3.	STM programmer tool. Theory

The full form of an ARM is an advanced reduced instruction set computer (RISC) machine, and it is a 32-bit processor architecture expanded by ARM holdings. The applications of an ARM processor include several microcontrollers as well as processors. The architecture of an ARM processor was licensed by many corporations for designing ARM processor-based SoC products and CPUs. This allows the corporations to manufacture their products using ARM architecture. Likewise, all main semiconductor companies will make ARM-based SOCs such as Samsung, Atmel, TI etc.

**Procedure:**

1.	Click on STM 32 CUBE IDE.
2.	Click on FILE, click on new stm 32 project.
3.	Select the target to be programmed as shown below and click on next.
4.	Select the program name and save it.
5.	Corresponding ioc file will be generated automatically.
6.	Select the appropriate pins as gipo, in or out, USART or required options and configure.
7.	click on cntrl+S , automaticall C program will be generated.
8.	Edit the program and as per required.
9.	Use project and build all.
10.	Once the project is build link the hexfile build in stm32cube ide using post processor build.
11.	Click on debug option.
12.	Connect the stm nucleo board and click on run.

**STM 32 CUBE PROGRAM** : https://www.youtube.com/watch?v=oJc0seuBbzI

#include "main.h" 

#include "stdbool.h"

bool buttonstatus; 


void pushbutton();

void SystemClock_Config(void);

static void MX_GPIO_Init(void); 

int main(void)

{

HAL_Init();

SystemClock_Config(); 

MX_GPIO_Init();

while (1)

{

pushbutton();

}

}

void pushbutton()

{

buttonstatus=HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_13); 

if(buttonstatus==0)

{

HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);

HAL_Delay(200);

HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);

HAL_Delay(200);

}

else

{

HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);

}

}

**OUTPUT:**

<img width="692" height="432" alt="506904210-a17f388d-a405-469d-9e7d-851d794f5993" src="https://github.com/user-attachments/assets/3e6f7f87-af2d-46af-8f8c-b950d99efeb9" />

CASE 1: LED ON

<img width="603" height="432" alt="506904504-5ba60f1c-042f-4303-8c0b-89cb3d02f359" src="https://github.com/user-attachments/assets/2ec4d617-f9b0-4c3c-8206-25940fd9b0d3" />

CASE 2:LED OFF

<img width="596" height="416" alt="506904450-7d4d9587-3a41-413f-a5a1-5c49a7154c97" src="https://github.com/user-attachments/assets/b8f149d4-ab57-4b48-8659-00cafcc61081" />


**Result :**

Interfacing a digital Input (Pushbutton ) with ARM microcontroller based IOT development is executed and the results are verified.

