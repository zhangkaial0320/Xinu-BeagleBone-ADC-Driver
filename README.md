# Xinu-BeagleBone-ADC-Driver
Simple ADC Driver on Xinu Platform

Compile Instruction:

1. In ' <Your xinu root folder>/device ' ,  ' mkdir -p adc '
2. Copy all these source files into adc/ folder
3. move adc.h into <Your xinu root folder>/include folder
4. add #include <adc.h> in xinu.h
5. Modify the <Your xinu root folder>/config/Configure file by adding

    adc:
        on top
            -i adcinit  -o ionull   -c ionull
            -r adcread  -g ionull   -p ionull
            -w ionull   -s ionull   -n ionull
            -intr adchandler

    ADC  is adc on top csr 0x44e0d000 -irq 16

6. go to <Your xinu root folder>/compile, do:
	make clean
	make

NOTE:
	This simple dirver is just for test, you can modify to fit your own application,
	and this driver just juse AIN0 for input, if you want to use other pins (AIN1~AIN7),
	you have to modify the code.

Contact: zhangkai6@ufl.edu



