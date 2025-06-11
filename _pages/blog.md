---
layout: single
title: "Insights"
permalink: /blog/
header:
  overlay_color: "#1a2d4f"
  overlay_image: /assets/images/blog.jpg  # Suggested: abstract data visualization or secure server image
excerpt: "Welcome to my lab challenges section! Here you'll find detailed writeups of networking and cybersecurity challenges I've completed during my studies. Each post includes the problem statement, my approach, tools used, and key lessons learned."
---

## Week 1: Examining TCP/IP and OSI Models in Action

**Category:** Network Protocols, Packet Analysis  
**Difficulty:** Beginner  

### Problem Statement

The challenge was to examine HTTP web traffic using Packet Tracer's simulation mode to understand how data moves through network layers. The objective was to map real network communication to both the TCP/IP and OSI models, observing the encapsulation and decapsulation processes at each protocol layer.

### Approach

I approached this challenge by:

1. **Switching to Simulation Mode**: Used Packet Tracer's simulation capabilities to slow down and visualize network traffic
2. **Generating HTTP Traffic**: Initiated a web request from a client PC to observe the complete communication flow
3. **Analyzing PDUs**: Examined Protocol Data Units at each layer to understand encapsulation
4. **Layer-by-Layer Analysis**: Mapped observed traffic to both OSI and TCP/IP model layers

### Tools Used

- **Cisco Packet Tracer**: For network simulation and traffic visualization

### Key Lessons Learned

1. **Layered Architecture Importance**: Understanding how each layer has specific responsibilities makes troubleshooting more systematic
2. **Protocol Interaction**: Seeing how HTTP, TCP, IP, and Ethernet work together reinforced the importance of the protocol stack
3. **Encapsulation Process**: Visualizing how data gets wrapped with headers at each layer clarified the theoretical concepts
4. **Real-World Application**: Connecting classroom theory to actual network behavior bridges the gap between learning and practice

### Challenges Faced

- Initially struggled with interpreting PDU information across different tabs
- Understanding the direction of data flow during request/response cycles
- Correlating theoretical layer functions with actual protocol operations

### Conclusion

This lab successfully demonstrated the practical application of networking fundamentals. By observing actual HTTP traffic through the lens of both OSI and TCP/IP models, I gained a deeper appreciation for how modern internet communication works. The visualization capabilities of Packet Tracer made abstract concepts tangible and reinforced the importance of understanding layered network architectures.

[View Full Writeup](/assets/images/Week One Assignment 1-Examine TCP_IP and OSI Models in Action.pdf){: .btn .btn--info target="_blank"}
---

## Week 2: Building a Switch and Router Network

**Category:** Network Configuration, Cisco IOS  
**Difficulty:** Intermediate  

### Problem Statement

Configure a complete network topology from scratch using Cisco routers and switches. The challenge required setting up devices without step-by-step instructions, relying on independent knowledge of IOS commands to establish connectivity between multiple subnets. The network needed to support both IPv4 and IPv6 protocols with proper security configurations.

### Network Topology

The lab involved:
- **1 Cisco 4221 Router (R1)** running IOS XE Release 16.9.4
- **1 Catalyst 2960 Switch (S1)** with IOS Release 15.2(2)
- **2 PCs** on different subnets requiring inter-VLAN communication
- **Multiple interfaces** requiring configuration and verification

### Tools Used

- **Cisco Packet Tracer**: For network simulation and device configuration

### Troubleshooting Insights

1. **First Ping Failure**: Normal behavior due to ARP resolution process
2. **Administrative Down**: Would require `no shutdown` command to resolve
3. **Incorrect Gateway**: Misconfigured default gateway would break inter-subnet communication

### Key Lessons Learned

1. **Systematic Configuration**: Following a logical sequence prevents configuration errors
2. **Security Best Practices**: Password encryption and banner warnings are essential
3. **Verification Importance**: Using show commands to verify each step prevents issues
4. **Layer 3 Routing**: Understanding how routers enable communication between subnets
5. **Default Gateway Significance**: Proper gateway configuration is critical for network connectivity

### Challenges Faced

- **Command Syntax**: Remembering exact IOS command syntax without references
- **Interface Naming**: Understanding Cisco's interface naming conventions
- **IPv6 Configuration**: Enabling IPv6 routing for dual-stack functionality
- **Troubleshooting**: Systematically diagnosing connectivity issues

### Conclusion

This hands-on lab successfully tested my ability to configure Cisco networking equipment independently. By building the network from scratch without step-by-step guidance, I demonstrated proficiency in IOS commands, network design principles, and systematic troubleshooting. The experience reinforced the importance of proper planning, security implementation, and thorough verification in network deployments.

The lab particularly strengthened my understanding of inter-VLAN routing, default gateway configuration, and the critical role routers play in enabling communication between different network segments.

[View Full Writeup](/assets/images/Week Two Assignment 1-Packet Tracer - Build a Switch and Router Network.pdf){: .btn .btn--info target="_blank"}
---

## Week 3: Web Requests and HTTP Protocol Analysis

**Category:** Web Security, HTTP/HTTPS Protocols, API Testing  
**Difficulty:** Intermediate-Advanced  

### Problem Statement

Analyze and understand web application communication protocols through hands-on exploration of HTTP/HTTPS traffic. The challenge involved mastering web request methods, understanding protocol security mechanisms, and learning to manipulate web traffic for security testing purposes. This included working with authentication mechanisms, API interactions, and various HTTP methods.

### Tools Used

- **cURL**: Command-line tool for making HTTP requests
- **Browser DevTools**: Chrome/Firefox developer tools for traffic analysis
- **HTB Academy Platform**: Hands-on learning environment
- **VMWare Kali Linux**: Hands on environment to practice and answer questions

### Challenges Faced

1. **Certificate Issues**: Learning to handle SSL certificate warnings appropriately
2. **Session Management**: Understanding how authentication persists across requests
3. **API Design**: Grasping RESTful principles and proper HTTP method usage
4. **Header Complexity**: Managing multiple headers for complex requests

### Real-World Applications

This knowledge directly applies to:
- **Web Penetration Testing**: Understanding how to manipulate and analyze web traffic
- **API Security Assessment**: Testing authentication and authorization mechanisms
- **Network Security**: Analyzing encrypted vs unencrypted communications
- **Incident Response**: Interpreting web server logs and traffic patterns

### Key Lessons Learned

1. **Protocol Fundamentals**: HTTP/HTTPS differences are crucial for security assessment
2. **Tool Mastery**: Command-line tools like cURL are essential for automation and scripting
3. **Security Awareness**: Understanding common web vulnerabilities through protocol analysis
4. **Systematic Testing**: Following methodical approaches for comprehensive security testing
5. **Documentation Skills**: Proper logging and documentation of testing procedures

### Future Applications

This foundation prepares me for:
- **Advanced Web Application Security Testing**
- **API Penetration Testing Certification**
- **CREST Certification Pathways**
- **Bug Bounty Hunting**
- **Security Research and Development**

### Conclusion

This comprehensive web requests module provided essential foundation knowledge for web application security testing. By mastering HTTP/HTTPS protocols, learning command-line tools, and understanding API interactions, I've built the groundwork for advanced cybersecurity skills.

The hands-on approach of analyzing real traffic, manipulating requests, and understanding authentication mechanisms has given me practical experience that bridges theoretical knowledge with real-world application. This knowledge forms the cornerstone of web application security assessment and will be invaluable for future penetration testing engagements.

The progression from basic HTTP concepts to complex API interactions demonstrates the depth of understanding required for effective cybersecurity work, and I'm confident this foundation will support continued growth in the field.

[View Full Writeup](/assets/images/Week Three Assignment 2-HTB Academy - Web Requests.pdf){: .btn .btn--info target="_blank"}
---

*These lab challenges represent my ongoing journey in cybersecurity education, demonstrating both technical proficiency and analytical thinking in network security and web application testing.*
