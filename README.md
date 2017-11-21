# Implementation of RED in ns-3 in line with Linux Kernel
## Course Code: CS822
## Assignment: #GP9
### Brief Description:
Modifying RED implementation of ns-3 to make it aligned with the implementation in Linux kernel
### Overview
RED is an AQM algorithm that is implemented in Linux kernel as a qdisc[1], and in ns-3 as a traffic control model[2]. But there exists some differences in the Linux implementation and the ns-3 implementation. This repository aims to align the ns-3 code for RED with the Linux one.  
### Changes Implemented
In Adaptive RED of Linux, the maximum probability is adapted   by a function which executes asynchronously when a timer interrupt occurs. In ns3 no such timer implementation exists for RED. The adapting function is called by the packet enqueue function by checking the current time against the last probability update time. This project implements the timer function in ns3 for RED, so that the adapting function is called asynchronously.
### References
[1]Linux source code for RED ( http://elixir.free-electrons.com/linux/latest/source/net/sched/sch_red.c )


[2]ns-3 source code for RED ( https://www.nsnam.org/doxygen/red-queue-disc_8cc_source.html )
