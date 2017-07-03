# scan.py
Code for dissertation program scan.py

This program was designed for Windows 10. 
It requires the following libraries to be installed - shodan api (pip install shodan).
It was designed on python 2.7.
It makes the following assumptions - internal network is a /24 network.

This program has 3 modes of operation, all available through the GUI interface - 

1.  Internal Scan:
This mode scans the internal network for devices responding to a PING.
Any device found is then scanned for open ports (in the range of 1 - 6000).
Next any device found to have port 23 open is scanned with a bruteforce attempt to check if they respond
to the credentials used by Mirai and Qbot.
Once completed the results are displayed in the result pannel on the GUI.

2. External Scan:
This mode uses the Shodan API to get the external IP address of the network.
Once found it will check the Shodan database for any information stored about the network.
Next it will scan the external IP address over port 23 for the same credentials used in the internal scan.
The results are then displayed in the result pannel on the GUI.

3. About
This section gives information about the program and also some tips for best operation.
