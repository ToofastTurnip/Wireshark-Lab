# Wireshark-Lab
By the end of this short lab, you should be very disappointed when you see this string of characters: `cGFzc3dvcmQ=`  
<br/>
## What's a Wireshark?
Wireshark is a packet sniffer used by many network technicians to help them easily identify issues in their network.  It provides a wealth of information on all packets it analyzes and includes a powerful filter feature so you can find exactly what you are looking for by filtering out certain traffic or protocols.  

## Let's get started
First, you'll need to download Wireshark.  
  
https://www.wireshark.org/#download  
  
Make sure you get the most recent stable version for whatever operating system you're using.  The installer may not look the same on different platforms.  On the most recent Mac stable build you will not be prompted for any extra utilities, but on Windows you will want to install all utilities besides Wireshark 1 (an old version of the software).  You will also be prompted to install WinPcap, leave this checked as it is the driver for capturing on Windows.  It will next ask if you want to install USBPcap.  This is the driver for capturing traffic on a USB device, which is fun if you want to plug your phone into your computer to see what it's up to.  However, you will not need that in this lab, and installing USBPcap will require you to reboot your computer.  

## Your first capture
Now that you have Wireshark installed, go ahead and open it up.  At the home screen, you will see a few options that you can capture from.  Unles you have multiple wifi cards and/or ethernet connections, there should be only one bar with activity.  That is your Network Interface Card.  
  
![HomeScreenScreenshot](/screenshots/homeScreen.png?raw=true "Yeah that purple one")  
  
Double click it and capture some packets for a few seconds.  Try different things like logging into your social media or watching a video so you can get a variety of packets.  You can click the stop button in the top left when you are ready to move on.  

## What in tarnation am I looking at here
There should be several packets on your screen now that we can experiment with.  Because of how much traffic there can be on networks, if you ever want to find what you're looking for here you will need to use filters.  In the filter bar at the top, try entering different things like `TCP` or `HTTP` and see what happens.  What if you want to be able to see everything, but you just want to highlight what you're looking for?  Then coloring rules are your friend!  Check out view -> coloring rules to see what all the colors the packets have been highlighted as mean.  This is also a great place to get an example of the syntax for the filter bar, as the logic behind every coloring rule is simply a filter.  You will see that filters can be made to be as specific as you want them to be for whatever you need to do.  
  
![ColoringRulesScreenshot](/screenshots/coloringRules.png?raw=true "Coloring rulez!")  

There should be three different sections at your main screen.  When you click on a packet, it will display readable information about that packet in the second section and not-so-readable information in the third section (which you can close by dragging it down to the bottom of the screen as you will not need that).  Try finding an HTTP request and expanding some sections.

## Let's hack
Every packet you capture contains an immense amount of information.  For this demo, we are going to capture a packet that contains an encrypted username and password, then decrypt it.  First, we will need a form to submit data to that will encrypt said data before sending it out.  Luckily we don't need to make this, as one already exists for testing purposes.  
  
**MAKE SURE YOU BEGIN A NEW CAPTURE BEFORE PROCEEDING**  

Follow this link:  
  
http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wiresharkfile-5.html  
  
You will be met with a prompt to enter a username and password.  
  
![GaiaLoginScreenshot](/screenshots/gaiaLogin.png?raw=true "Login prompt")  
  
The credentials for this server are:  
Username: `wireshark-students`  
Password: `network`  
  
**AFTER SUBMITTING THE FORM, END THE CAPTURE**  
  
Now let's find the packet with the information we just sent.  Once you have located it, check out that string of text following the “Authorization: Basic” part of the HTTP GET message.  If you have a basic understanding of encryption, this format may look familiar to you (and you probably know where we're going with this).  Why don't we drop that text into a Base64 decoder and see what we get?  You can use this one:  
  
https://www.base64decode.org/  

<details>
<summary>If you need help finding the packet, click here</summary>
<br>
Hint will go here eventually lol
</details>

  
## Use your powers for good, not evil
As you can see, Wireshark is a very powerful network analysis tool.  However, you should only use this software to analyze your own networks and package captures.  Using Wireshark to sniff packets on a public/business network is completely illegal, and I do not condone it.  I hope you enjoyed this quick look into networks and analyzing them!
