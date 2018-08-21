# Wireshark-Lab
By the end of this short lab, you should be very disappointed when you see this string of characters: `cGFzc3dvcmQ=`  
  
## What's a Wireshark?
Wireshark is a packet sniffer used by many a network technician to help them easily identify issues in their network.  It provides a wealth of information on all packets it analyzes and includes a powerful filter feature so you can find exactly what you are looking for by filtering out certain traffic or protocols.  

## Let's get it started
First, you'll need to download Wireshark.  
  
https://www.wireshark.org/download.html  
  
Make sure you get the most recent stable version for whatever operating system you're using.  The installer may not look the same on different platforms, but generally you will want to intall all the utilities besides Wireshark 1 (an old version of the software).  If you are on a Windows machine, it will prompt you to install winpcap.  You will need this, as it is the driver for capturing on Windows.  It will next ask if you want to install USBPcap.  This is the driver for capturing traffic on a USB device, which is fun if you want to plug your phone into your computer to see what it's up to.  However, you will not need that in this lab, and installing USBPcap will require you to reboot your computer.
