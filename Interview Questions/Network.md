# TCP vs UDP
Transmission Control Protocol (TCP) is connection-oriented, meaning once a connection has been established, data can be transmitted in two directions. TCP has built-in systems to check for errors and to guarantee data will be delivered in the order it was sent, making it the perfect protocol for transferring information like still images, data files, and web pages.

User Datagram Protocol (UDP) is a simpler, connectionless Internet protocol wherein error-checking and recovery services are not required. With UDP, there is no overhead for opening a connection, maintaining a connection, or terminating a connection; data is continuously sent to the recipient, whether or not they receive it. 

## Connection status
TCP: Requires an established connection to transmit data (connection should be closed once transmission is complete)
UDP: Connectionless protocol with no requirements for opening, maintaining, or terminating a connection

## Data sequencing
TCP:Able to sequence
UDP: Unable to sequence

## Guaranteed delivery
TCP: Can guarantee delivery of data to the destination router
UDP: Cannot guarantee delivery of data to the destination

## Retransmission of data
TCP: Retransmission of lost packets is possible
UDP: No retransmission of lost packets

## Error checking
TCP: Extensive error checking and acknowledgment of data
UDP: Basic error checking mechanism using checksums

## Method of transfer
TCP: Data is read as a byte stream; messages are transmitted to segment boundaries
UDP: UDP packets with defined boundaries; sent individually and checked for integrity on arrival

## Speed
TCP: All the guarentees makes it have overhead hence slower
UDP: faster

## Broadcasting
TCP: Not supported
UDP: Supports broadcasting

## Optimal use
TCP: Used by HTTPS, HTTP, SMTP, POP, FTP, etc
UDP: Video conferencing, streaming, DNS, VoIP, etc

# HTTP Status codes