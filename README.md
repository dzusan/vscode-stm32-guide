## This guide for Windows 10 for now. Example for NUCLEO-L053R8
Special thanks to [GREGOR_812's note](https://habr.com/ru/post/437760/)

### 1. [Install Chocolatey](https://chocolatey.org/install) then run
```
choco install gcc-arm-embedded make
```
Or instal packages manually

### 2. Download OpenOCD and add to 'Path'
[OpenOCD](http://www.freddiechopin.info/en/download/category/4-openocd) or [Download OpenOCD for Windows](https://gnutoolchains.com/arm-eabi/openocd/)

### 3. Check connection (for NUCLEO-L053R8)
```
openocd -f interface/stlink-v2-1.cfg -f target/stm32l0.cfg
```

### 4. Generate STM32CubeMX project where `Toolchain/IDE` config is `Makefile`
My STM32 Cube Repository directory is `c:\STM32CubeRepository` and I check in project manager:
* Add necessary library files as reference in the toolchain project configuration file
* Generate peripheral initialization as a pair of .c / .h files per peripheral

### 5. Find and copy `.svd`-file into root of your project directory
MCU page on st.com -> Resources -> HW Model, CAD Libraries & SVD -> download System View Description

### 6. Copy `.vscode` from this repository into root of your project directory and improve it depend on your own configurations

### 7. Install vscode extentions:
* Cortex-Debug from marus25.
* С/С++ from Microsoft

### 8. Press `F5` and enjoy

************************************************************************
I'm not sure that really must done, but it helped me.
First run VS code as administrator. Next you can start it as commim user.
