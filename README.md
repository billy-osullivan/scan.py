# scan.py
Code for dissertation program scan.py

This program has 2 main modes of operation - an internal and external scan.
Each mode is selectable using buttons displayed in the GUI.

The internal scan mode operates as follows - 
    1. It scans the internal network for devices (assumes a /24 network). 
    2. Next a portscan is initiated for any found devices (port 1-6000).
    3. If port 23 responds to the portscan, an attempt is made to brute force access to the device using a list of credentials
       obtained from Qbot and Mirai source code.
    4. Once completed a report is displayed on the screen presenting all the details found during the internal scan,
       including IP addresses found, ports open and weather or not a device is vulnerable to Qbot or Mirai brute force attempts
       (including the credentials used to gain access).
   
The external scan mode operates as follows -
    1. The Shodan API is used to get the external IP address of the network.
    2. The Shodan API next checks the Shodan database for any information relating to the external IP address.
    3. Next the external IP address is scanned over port 23 for the same credentials used in the internal scan.
    4. Once completed all results are displayed in the results section on screen.
    
This program was designed on Windows 10 with python 2.7. It also requires that the Shodan API is installed  and the user gets a
Shodan API key from https://developer.shodan.io/ (A link in the program will take you to the Shodan site, use 'pip install shodan' 
to install the shodan API library).
    
Note - this program is a proof of concept application designed to find vulnerabilities on devices for Mirai and Qbot.
