# CMPE283 : Assignment 1 - VMX Features

# Assignment 1: Discovering VMX Features

Student names: Priya Gupta , Phani Sai Ram Munipalli

University Name: San Jose State University

# Prerequisites

You will need a machine capable of running Linux, with VMX virtualization features exposed.
You may be able to do this inside a VM, or maybe not, depending on your hardware and software configuration. • You will need at least one github account (create one at github.com if you don’t already have one)

# Assignment Details

We studied Intel SDM provided by professor and listened to the lecture provided on this assignment.

Team Member: Phani Sai Ram Munipalli

1. Configuare a GCP vm and enable the nested virtualization settings

2. Create a directory for project and download the cmpe283-1.c source file and Makefile from canvas

3. Added the functionality for primary and secondary-based MSR controls in cmpe283.c file
   as explained by Prof in his assignment video lecture.

4. Added struct code by taking reference from Intel SDM volume 3 and modify the detect_vmx function to check the VMX capability by printing message in the log using the corresponding print function.

Team Member: Priya Gupta

5. Added the remaining functionality of the exit, entry, and tertiary-based MSR controls by using Intel SDM volume 3 as explained by Prof in his assignment video lecture.

6. make sure to have make tool and gcc compiler on your VM. For this install the required packages

run(all commands are run in terminal)
sudo apt install gcc make

There are 5 total features that we are trying to detect on our GCP VM.
Pinbased (provided by professor Mike as codebase)

7. Run under the same directory with MakeFile and cmpe283-1 file in terminal er_priyagupta123@vt-assignment1:~/cmpe283-1$ make
   After running the make command, a couple of files .o/.ko files will be generated

8. Use insmod/rmmod tool to insert and remove module

sudo insmod ./cmpe283-1.ko

sudo rmmod ./cmpe283-1.ko

er_priyagupta123@vt-assignment1:~/cmpe283-1$ sudo insmod ./cmpe283-1.ko

er_priyagupta123@vt-assignment1:~/cmpe283-1$ sudo dmesg

9. Use dmesg tool to print run

   sudo dmesg

By here we sould be able to see the message outputs for pinbased, procbased, procbased02, exit, entry, procbased03 features on terminal

    Below is the screenshot of output after executing commands:

![VT_Assignment](/images/screenshot3.png)

![VT_Assignment](/images/screenshot5.png)

![VT_Assignment](/images/screenshot4.png)

![VT_Assignment](/images/screenshot1.png)

![VT_Assignment](/images/screenshot2.png)
