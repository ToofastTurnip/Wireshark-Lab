# Wireshark-Lab
By the end of this short lab, you should be very disappointed when you see this string of characters: `cGFzc3dvcmQ=`  
<br/>
<br/>
## What's a Wireshark?
Wireshark is a packet sniffer used by many a network technician to help them easily identify issues in their network.  It provides a wealth of information on all packets it analyzes and includes a powerful filter feature so you can find exactly what you are looking for by filtering out certain traffic or protocols.  

## Let's get started
First, you'll need to download Wireshark.  
  
https://www.wireshark.org/download.html  
  
Make sure you get the most recent stable version for whatever operating system you're using.  The installer may not look the same on different platforms, but generally you will want to intall all the utilities besides Wireshark 1 (an old version of the software).  If you are on a Windows machine, it will prompt you to install winpcap.  You will need this, as it is the driver for capturing on Windows.  It will next ask if you want to install USBPcap.  This is the driver for capturing traffic on a USB device, which is fun if you want to plug your phone into your computer to see what it's up to.  However, you will not need that in this lab, and installing USBPcap will require you to reboot your computer.  

## Your first capture


## Let's hack
Every packet you capture contains a stupid big amount of information.  For this demo, we are going to capture a packet that contains an encrypted username and password, then decrypt it.  First, we will need a form to submit data to that will encrypt said data before sending it out.  Luckily we don't need to make this, as one already exists for testing purposes.  
  
*MAKE SURE YOU BEGIN A NEW CAPTURE BEFORE PROCEEDING*  

Follow this link:  
  
http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wiresharkfile-5.html  
  
You will be met with a prompt to enter a username and password.  The credentials for this server are:  
Username: `wireshark-students`  
Password: `network`  
  
*AFTER SUBMITTING THE FORM, END THE CAPTURE*  
  
Now let's find the packet with the information we just sent.  Once you have located it, check out that string of text following the “Authorization: Basic” header in the client’s HTTP GET message.  If you have a basic understanding of encryption, this format may look familiar to you (and you probably know where we're going with this).  Why don't we drop that text into a Base64 decoder and see what we get?  You can use this one:  
  
https://www.base64decode.org/
  
## Use your powers for good, not evil
As you can see, Wireshark is a very powerful network analysis tool.  However, you should only use this software to analyze your own networks and package captures.  Using Wireshark to sniff packets on a public/business network is completely illegal, and I do not condone it.  I hope you enjoyed this quick look into networks and analyzing them!
