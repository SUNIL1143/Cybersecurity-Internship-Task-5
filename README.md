# Cybersecurity-Internship-Task-5
Submission for Task 5: Capturing and analyzing network traffic with Wireshark. Includes .pcap file and a report on identified protocols (DNS, TCP, TLS).

Wireshark Network Traffic Analysis Report
 
Objective: To capture live network packets and identify basic protocols and traffic types. 

# Summary of Activity
I used Wireshark to capture traffic on my active network interface while browsing the web. After stopping the capture, I analyzed the packets and successfully identified several key protocols. 



## Identified Protocols Analysis
I identified the following protocols as required by the task:

## 1. Protocol: DNS (Domain Name System)
Packet Example: Frame 93

Analysis: This was a 'Standard query' packet using the UDP (User Datagram Protocol). It was sent to Destination Port 53, which is the standard port for DNS servers.

Purpose: The packet's purpose was to ask for the IP address associated with the domain name clients4.google.com.

## 2. Protocol: TCP (Transmission Control Protocol)
Packet Example: Frame 1073

Analysis: This packet was part of the TCP 3-Way Handshake. It had the [SYN, ACK] flags (Flags: 0x012) set. It was sent from the server's Source Port 443 (HTTPS).

Purpose: This was the server's response, acknowledging the client's request and establishing a reliable connection.

## 3. Protocol: TLS (Transport Layer Security)
Packet Example: Frame 1091

Analysis: This packet contained a TLS payload running on top of TCP, as shown in the protocol frame details ([Protocols in frame: ...:tcp:tls]). It carried an encrypted TCP payload of 1220 bytes from the server's Port 443.

Purpose: This packet contained the actual application data (from the website), which was encrypted by TLS for security. This is the core protocol for HTTPS.

## 4. Protocol: UDP (User Datagram Protocol) & QUIC
Packet Example: Frame 480

Analysis: This was a UDP packet, but unlike the DNS query, this one was coming from the server's Source Port 443. Using UDP on Port 443 (instead of TCP) is the standard behavior for the QUIC protocol.

Purpose: QUIC is a modern protocol developed by Google to make web connections faster and more efficient than traditional TCP.

## Conclusion
This task provided hands-on experience in capturing and analyzing live network traffic using Wireshark. I successfully identified and understood the purpose of fundamental protocols like DNS, TCP, TLS, and UDP/QUIC, gaining practical skills in packet analysis.
