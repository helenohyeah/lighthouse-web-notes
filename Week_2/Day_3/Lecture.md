# Week 2 Day 2 Lecture
Instructor: Travis Borsa

## Protocols
## Internet Protocol (IP)
* IP address recognizes your device
* Port recognizes the program or application on that device
  * common development ports are 3000 and up
  * some are [reserved](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers)
* both TCP and UDP use IP to communicate

### Transmission Control Protocol (TCP)
* used to establish networked communication between applications
* connection oriented protocol meaning both need to agree to establish communication (e.g. phone call)
* prioritizes accuracy over speed

### User Datagram Protocol (UDP)
* both parties do not need to agree (e.g. text message)
* prioritizes speed over accuracy (low-latency, loss-tolerating)
* usually used for live data transfer (e.g. FaceTime, online games)