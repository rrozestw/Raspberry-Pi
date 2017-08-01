# MULTICORE
>
>The smartstart assembler boot was extended to setup cores 1,2,3 for hyperthreading. A new spinlock was created which mimics the bootloaders but is C compiler safe. To do that registers R0-R3 need to be able to be trashed when the core process is called. The demo uses printf to screen which is very dangerous because printf is not re-entrant so I took a bit of care to avoid clashes using it. Please don't try and take using printf too far what is expected is you setup proper thread safe C code. The stacks for the 4 cores are controlled by the linker file. So you can vary stack sizes by simply changing the linker file and recompiling. The random core hyperthread calls are cause by the interrupt timer.
>
![](https://github.com/LdB-ECM/Raspberry-Pi/blob/master/Images/Multicore.jpg)
