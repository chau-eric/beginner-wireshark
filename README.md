<h1>Capturing Packets with Wireshark</h1>

<h2>Description</h2>
This project consists of using Wireshark to capture packets, save them, and use filters to display certain HTTP and HTTPS packets
<br />

<h2>Tools Used</h2>

- <b>Wireshark</b>

<h2>Environment</h2>

- <b>Ubuntu 18.04.4 LTS</b>

<h2>Scenario</h2>
You are working for a company that wants to detect certain TCP/IP network traffic on their server; specifically web traffic. Your task is to set up and demonstrate Wireshark's packet capture capabilities.<br/>
The IT manager wants to be able to capture ethernet network web traffic on the server and be able to detect certain IP addresses as well.

<h2>Project walk-through:</h2>

<h4>Detect a web page's IP address using a display filter</h4>
I am going to start a packet capture in Wireshark on my device's ethernet interface. While Wireshark is capturing packets, I am going to open the target web page (I am using google.com for this project).
<p align="center">
<img width="570" alt="Untitled" src="https://github.com/chau-eric/beginner-wireshark/assets/76719902/9254201c-9e74-4b0c-b6dd-ae903e7acfa7"><br/>
</p>
After stopping the packet capture, I used the display filter "tcp.port==443" to display only the traffic that used port 443, or HTTPS traffic. Here, I can locate the Client Hello packet to google.com in the HTTPS handshake process.
<p align="center">
<img width="570" alt="Untitled" src="https://github.com/chau-eric/beginner-wireshark/assets/76719902/48fc4c4e-180b-405b-be70-bacfa3e9968d"><br/>
</p>
If I wanted to find only the Client Hellos, I could use the display filter "tls.handshake.type==1."
<p align="center"><img width="564" alt="Untitled" src="https://github.com/chau-eric/beginner-wireshark/assets/76719902/02f667d3-5ec4-484b-8005-823ddeaffefc"><br/>
</p>
Regardless of which of the two filters I used, I was able to detect google.com's IP address 172.253.62.105, which is listed as the destination IP in the packet capture. Now I can use that destination IP in a new display filter "ip.addr==172.253.62.105" to find all the network traffic between google.com.
<p align="center"><img width="564" alt="Untitled" src="https://github.com/chau-eric/beginner-wireshark/assets/76719902/cccd3143-d392-4e07-9c4a-80b7cd1c652c"><br/></p>
Notice how all the packets have either a destination IP address of 172.253.62.105 (packets sent TO google.com) or a source IP address of 172.253.62.105 (packets sent FROM google.com). If I wanted just the packets FROM google.com, I can change the display filter to "ip.src==172.253.62.105."
<p align="center"><img width="564" alt="Untitled" src="https://github.com/chau-eric/beginner-wireshark/assets/76719902/f78d7856-5061-49e4-94d2-ee2f3a76ad1d"><br/></p>
Likewise, I can get just the packets TO google.com using the filter "ip.dst==172.253.62.105."
