# scenario

- You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website.
- The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. 
- One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server.
- You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.
- You use a packet sniffer to capture data packets in transit to and from the web server.
- You notice a large number of TCP SYN requests coming from an unfamiliar IP address.
- The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests.
- You suspect the server is under attack by a malicious actor. 
- You take the server offline temporarily so that the machine can recover and return to a normal operating status.
- You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests.
- You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block.
# request
- You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again.
-  You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.

# Report
## Cybersecurity Incident Report


- One potential explanation for the website's connection timeout error message is: SYN DOS attack from ip = 203.0.113.0

- The logs show that: The ip 203.0.113.0 is flooding the web server with SYN request 

- This event could be: SYN DOS attack And the website is crashed and cannot accept any requisites any more
- This attack could lead to losing customer trust
- the admin must block this ip 203.0.113.0 and tries to reset the server and configure the firewall 





### Section 2: Explain how the attack is causing the website to malfunction
When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. Explain the three steps of the handshake:
User sends SYN request 

2. The web server respond with SYN/ACK that the server accepted the request

3.The user/browser send ACK showing the acknowledge of server acceptance 

Explain what happens when a malicious actor sends a large number of SYN packets all at once:if it is more than the server can handle the server crash and stop accepting any more requisites 

Explain what the logs indicate and how that affects the server:the loge indicates a SYN  DOS attack coming from this ip 203.0.113.0 and it is affecting the server and it cannot handle any requests 
