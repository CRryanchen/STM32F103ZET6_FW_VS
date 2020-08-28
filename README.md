# 说明

该工程是基于FW和STM32F103ZET6芯片的MDK使用VSCODE编辑的空工程，需要开发新项目时可以直接下载并更改芯片即可，免去重复新建空工程的时间。

关于固件库移植时的几个重要文件这里做一下说明：

**CMSIS**：移植固件库的CMSIS文件夹中的启动文件、stm32f10x.h等头文件

* 固件库 `Libraries->CMSIS->CM3->CoreSupport->core_cm3.c`
* 固件库 `Libraries->CMSIS->CM3->CoreSupport->core_cm3.h`
* 固件库 `Libraries->CMSIS->CM3->DeviceSupport->ST->STM32F10x->startup`中适合自己芯片的启动文件
* 固件库 `Libraries->CMSIS->CM3->DeviceSupport->ST->STM32F10x->stm32f10x.h、system_stm32f10x.c、system_stm32f10x.h`。

**FWLIB**：移植固件库中的外设驱动。

* 固件库 `Libraries->STM32F10x_StdPeriph_Driver->inc`文件夹
* 固件库 `Libraries->STM32F10x_StdPeriph_Driver->src`文件夹

**USER**：存放main.c、中断等用户自己编写的文件。

* 固件库 `PROJECT->STM32F10x_StdPeriph_Template->stm32f10x_conf.h、stm32f10x_it.h、stm32f103_it.c`
* 建立main.c和main.h，一般需要包含`stmf10x.h`，包含该头文件即包含了其他外设的头文件。