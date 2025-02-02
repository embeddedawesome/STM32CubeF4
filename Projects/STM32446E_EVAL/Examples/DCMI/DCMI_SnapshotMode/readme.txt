/**
  @page DCMI_SnapshotMode DCMI Capture Mode example
  
  @verbatim
  ******************** (C) COPYRIGHT 2017 STMicroelectronics *******************
  * @file    DCMI/DCMI_SnapshotMode/readme.txt 
  * @author  MCD Application Team
  * @brief   Description of the STM32F4xx DCMI_SnapshotMode example.
  ******************************************************************************
  * @attention
  *
  * <h2><center>&copy; COPYRIGHT 2017 STMicroelectronics</center></h2>
  *
  * Copyright (c) 2017 STMicroelectronics. All rights reserved.
  *
  * This software component is licensed by ST under BSD 3-Clause license,
  * the "License"; You may not use this file except in compliance with the
  * License. You may obtain a copy of the License at:
  *                       opensource.org/licenses/BSD-3-Clause
  *
  ******************************************************************************
   @endverbatim

@par Example Description 

This example provides a short description of how to use the DCMI to interface with
a camera module and display in snapshot mode the picture on the LCD.

At the beginning of the main program the HAL_Init() function is called to reset 
all the peripherals, initialize the Flash interface and the systick.
Then the SystemClock_Config() function is used to configure the system
clock (SYSCLK) to run at 180 MHz.

The Digital camera interface is configured to receive the capture from
the camera module mounted on STM32446E-EVAL evaluation board.
The DMA is configured to transfer the picture from DCMI peripheral
to an external RAM used by the LCD as a frame buffer.   
When the frame event callback is raised the picture is transferred to the LCD frame buffer.   

The camera module is configured to generate QVGA (320x240) image resolution
and the LCD is configured to display QVGA image resolution.

@note The picture is displayed on the LCD screen about 4 seconds after reset.

@note Care must be taken when using HAL_Delay(), this function provides accurate delay (in milliseconds)
      based on variable incremented in SysTick ISR. This implies that if HAL_Delay() is called from
      a peripheral ISR process, then the SysTick interrupt must have higher priority (numerically lower)
      than the peripheral interrupt. Otherwise the caller ISR process will be blocked.
      To change the SysTick interrupt priority you have to use HAL_NVIC_SetPriority() function.
      
@note The application need to ensure that the SysTick time base is always set to 1 millisecond
      to have correct HAL operation.

@par Keywords

Display, DCMI, Camera, Snapshot, Frame Buffer, LCD, ARGB8888, DMA, RGB565, SDRAM, DMA2D, QQVGA

@par Directory contents 

  - DCMI/DCMI_SnapshotMode/Inc/stm32f4xx_hal_conf.h    HAL configuration file
  - DCMI/DCMI_SnapshotMode/Inc/stm32f4xx_it.h          Interrupt handlers header file
  - DCMI/DCMI_SnapshotMode/Inc/main.h                  Header for main.c module  
  - DCMI/DCMI_SnapshotMode/Src/stm32f4xx_it.c          Interrupt handlers
  - DCMI/DCMI_SnapshotMode/Src/main.c                  Main program
  - DCMI/DCMI_SnapshotMode/Src/system_stm32f4xx.c      STM32F4xx system source file


@par Hardware and Software environment

  - This example runs on STM32F446xx devices.
    
  - This example has been tested with STM32446E-EVAL board and can be
    easily tailored to any other supported device and development board.      

@par How to use it ? 

In order to make the program work, you must do the following :
 - Open your preferred toolchain
 - Rebuild all files: Project->Rebuild all
 - Load project image: Project->Download and Debug
 - Run program: Debug->Go(F5) 


 * <h3><center>&copy; COPYRIGHT STMicroelectronics</center></h3>
 */
