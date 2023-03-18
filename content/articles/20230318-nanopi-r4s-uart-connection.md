---
title: UART Connection to NanoPi R4S
date: 2023-03-18T01:15:59-06:00
type: page
description: When things go wrong and you need console access
image: /images/nanopi-r4s.jpg
topic: systems
---
![How Daemons Work](/images/nanopi-r4s.jpg)
# UART Connection to NanoPi R4S: When things go wrong and you need console access
The NanoPi R4S a great little board that's awesome as a home gateway. But let's be real - sometimes things go wrong. Maybe your NanoPi R4S won't boot up, or it keeps crashing. Whatever the issue is, there's one trick up your sleeve that can help you troubleshoot and fix it: connecting to the UART pinout.

The UART pinout is a 3-pin header on the NanoPi R4S that provides a serial communication interface for sending and receiving data between devices. By connecting to the UART pinout using a UART cable, you can access the NanoPi R4S's boot log, debug messages, and more.

To connect to the UART pinout on a NanoPi R4S, you'll need a few things:

1. A [NanoPi R4S](https://wiki.friendlyelec.com/wiki/index.php/NanoPi_R4S) board that's giving you grief
2. A [UART cable](https://www.adafruit.com/product/954)
3. A command line with [`screen`](https://www.gnu.org/software/screen/manual/screen.html) installed

To connect to the NanoPi R4S's UART pinout using screen on Linux, follow these steps:

1. Connect your UART cable to the NanoPi R4S's UART header (use the above image as a reference).

2. Open a terminal window on your Linux machine.

3. Find the device file associated with the UART interface. This is typically something like /dev/ttyUSB0 or /dev/ttyS0, depending on your system configuration. You can use the dmesg command to find the device file that corresponds to your UART adapter. For example, if your adapter is connected to /dev/ttyUSB0, you can use the following command:

```
dmesg | grep ttyUSB
```

4. Once you have identified the device file, use the screen command to connect to the UART interface. For example, if your device file is /dev/ttyUSB0 (baud rate is 1500000bps), you can use the following command:

```
screen /dev/ttyUSB0 1500000
```

5. Power on the NanoPi R4S (don't forget to make sure the SD card is inserted).

If everything is set up correctly, you should see the output from the NanoPi R4S in your terminal window. You can then use the terminal to communicate with the NanoPi R4S and troubleshoot any issues.

## Conclusion
Connecting to the UART pinout on a NanoPi R4S can be a powerful tool for troubleshooting and fixing issues. By following the steps outlined above, you can easily connect to the NanoPi R4S's UART interface and diagnose and fix issues with the board.