# VIA_FreeRTOS_Windows
FreeRTOS for Windows x86.

It is based on **FreeRTOS version 202012.00**.

### Project Setup
Be sure the project you want to add FreeRTOS to is under git control!

Open a command prompt in your projects root folder.

Add this repository in to your project as a git-submodule - by executing this command in the command prompt:

`git submodule add https://github.com/ihavn/VIA_FreeRTOS_Windows FreeRTOS`

Add `$(ProjectDir)/FreeRTOS/Source` as include path under the projects `Properties->VC++ Directories->Include Directories`.

Take a look at the `main.c`in the `Example` folder to get started. It is recommended that you create your own `main.c` in the projects root, and add seperate modules source (.c) and header files (.h) for each task, and give them meaningful names.

### FreeRTOS Configuration
Configuration of FreeRTOS must be done in `$(ProjectDir)\FreeRTOS\Source\FreeRTOSConfig.h` see details in the free RTOS documentation. **Be sure you know what you are doing before you configure anything!**


### FreeRTOS Heap Memory
This repository uses heap_4.c to handle dynamic memory/heap therefore it is **required to define how much RAM we will allocate for heap use**. This is done by defining
`#define configTOTAL_HEAP_SIZE 52k` in the configuration file `\FreeRTOS\Source\FreeRTOSConfig.h`. In this example it is defined to 4000 bytes.
