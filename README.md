<h1>Capturing Packets with Wireshark</h1>

<h2>Description</h2>
This project consists of using Wireshark to capture packets, save them, and use filters to display certain HTTP and HTTPS packets
<br />

<h2>Tools Used</h2>

- <b>Wireshark</b>

<h2>Environment</h2>

- <b>Ubuntu 18.04.4 LTS</b>

<h2>Scenario</h2>
You are working for a company that wants to detect certain TCP/IP network traffic on their server; specifically web traffic. Your task is to set up and demonstrate Wireshark's packet capture capabilities.

<h2>Project walk-through:</h2>

<h4>Perform first tcpdump capture</h4>
<p align="center">
<img width="697" alt="Untitled" src="https://github.com/chau-eric/tcpdump-capture/assets/76719902/a881084b-5287-4a99-8e24-f7a8de461249"><br/>
</p>
This first capture is just to check that our network is up and running. By default you need to be a super user to use tcpdump, therefore the command "sudo" needs to be used. The -c option is used here so we don't infinitely capture traffic and overflow our screen with captures. 10 is being passed to -c to tell tcpdump that we only want to capture 10 packets.
<br />
<br />
