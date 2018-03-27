## Concept - Unclassified

- what will happen after you enter url in browser and press enter



### what will happen after you enter url in browser and press enter



- 1 browser checks the cache for a DNS record to find the corresponding IP address of target url
  - browser cache
  - OS cache
  - router cache
  - IPS cache
- 2 if the requested URL is not in the cache, IPS's DNS server initiate a DNS query to find IP address of the server
- 3 browser initializes a TCP connection with the server
  - connection is established using a process called TCP/IP three way handshake
    - client sends a SYN packet to server
    - server response with an ACKnowlegement of the SYN packet using SYN/ACK
    - client receive SYN/ACK and acknowlege it by sending ACK package
- 4 browser sends an HTTP request to the web server
- 5 server handler the request and sends back a response
- 6 server sends out an http response
- 7 browser display HTML content





