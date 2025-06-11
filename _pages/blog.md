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

**Date:** February 2025  
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

### Key Findings

During the analysis, I discovered several important networking concepts:

**HTTP Request Flow:**
- Client initiates request to `www.osi.local`
- DNS resolution maps domain to IP `192.168.1.254`
- TCP connection established on port 80
- HTTP GET request sent for root path `/`
- Server responds with HTML content and status code 200 OK

**Layer Mapping Observations:**
- **Layer 7 (Application)**: HTTP request/response with host information
- **Layer 4 (Transport)**: TCP with source port 1025 and destination port 80
- **Layer 3 (Network)**: IP headers with source `192.168.1.1` and destination `192.168.1.254`
- **Layer 2 (Data Link)**: Ethernet II frames with MAC addresses
- **Layer 1 (Physical)**: Frame transmission over network medium

**PDU Encapsulation Process:**
- Each layer adds its own header information
- Data is encapsulated as it moves down the stack
- Decapsulation occurs in reverse order at the destination

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

**Date:** February 2025  
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

### Approach

My systematic approach included:

1. **Physical Setup**: Properly cabled the network according to topology requirements
2. **Device Initialization**: Cleared all previous configurations to start fresh
3. **Security Configuration**: Implemented passwords, banners, and access controls
4. **Interface Configuration**: Assigned IP addresses and activated interfaces
5. **Routing Setup**: Enabled IPv6 routing and configured default gateways
6. **Connectivity Testing**: Verified end-to-end communication between subnets

### Tools Used

- **Cisco Packet Tracer**: For network simulation and device configuration

### Configuration Details

**Router R1 Configuration:**
```cisco
Router> enable
Router# configure terminal
Router(config)# hostname R1
Router(config)# no ip domain-lookup
Router(config)# enable secret class
Router(config)# line console 0
Router(config-line)# password cisco
Router(config-line)# login
Router(config)# line vty 0 4
Router(config-line)# password cisco
Router(config-line)# login
Router(config)# service password-encryption
Router(config)# banner motd "Unauthorized access is prohibited!"
Router(config)# ipv6 unicast-routing
```

**Interface Configuration:**
```cisco
Router(config)# interface g0/0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# description "Connected to PC-A"
Router(config-if)# no shutdown
Router(config)# interface g0/0/1
Router(config-if)# ip address 192.168.2.1 255.255.255.0
Router(config-if)# description "Connected to S1"
Router(config-if)# no shutdown
```

**Switch S1 Configuration:**
```cisco
Switch(config)# hostname S1
Switch(config)# no ip domain-lookup
Switch(config)# interface vlan 1
Switch(config-if)# ip address 192.168.2.2 255.255.255.0
Switch(config-if)# no shutdown
Switch(config)# ip default-gateway 192.168.2.1
```

### Key Findings

**Routing Table Analysis:**
- Two directly connected networks (C code) in routing table
- GigabitEthernet interfaces properly configured and operational
- IPv6 routing enabled for dual-stack capability

**Interface Status Verification:**
- All interfaces showing "up/up" status
- Correct IP addressing assigned per topology
- MAC addresses properly displayed in interface information

**Connectivity Results:**
- Initial ping failures before router configuration (expected)
- Successful inter-subnet communication after configuration
- ARP resolution working correctly on first successful ping

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

**Date:** February 2025  
**Category:** Web Security, HTTP/HTTPS Protocols, API Testing  
**Difficulty:** Intermediate-Advanced  

### Problem Statement

Analyze and understand web application communication protocols through hands-on exploration of HTTP/HTTPS traffic. The challenge involved mastering web request methods, understanding protocol security mechanisms, and learning to manipulate web traffic for security testing purposes. This included working with authentication mechanisms, API interactions, and various HTTP methods.

### Learning Objectives

The lab focused on several key areas:
- HTTP/HTTPS protocol fundamentals and security differences
- URL structure and component analysis
- Request/response lifecycle and status codes
- HTTP headers and their security implications
- Authentication mechanisms and session management
- API testing with CRUD operations
- Command-line tools for web security testing

### Approach

My methodology included:

1. **Protocol Analysis**: Deep dive into HTTP vs HTTPS differences
2. **Tool Mastery**: Learning cURL command-line options and browser DevTools
3. **Traffic Inspection**: Analyzing request/response headers and body content
4. **Authentication Testing**: Working with basic auth and session cookies
5. **API Interaction**: Performing CRUD operations on test endpoints
6. **Security Assessment**: Understanding common web vulnerabilities

### Tools Used

- **cURL**: Command-line tool for making HTTP requests
- **Browser DevTools**: Chrome/Firefox developer tools for traffic analysis
- **HTB Academy Platform**: Hands-on learning environment
- **VMWare Kali Linux**: Hands on environment to practice and answer questions

### Key Technical Concepts Explored

**HTTP vs HTTPS:**
- Plain text vs encrypted communication
- SSL/TLS handshake process
- Certificate validation and security warnings
- Port differences (80 vs 443)

**URL Structure Analysis:**
```
http://admin:password@inlanefreight.com:80/dashboard.php?login=true#status
```
- Scheme: `http://`
- User Info: `admin:password@`
- Host: `inlanefreight.com`
- Port: `:80`
- Path: `/dashboard.php`
- Query String: `?login=true`
- Fragment: `#status`

**HTTP Request Methods:**
- **GET**: Retrieving resources and data
- **POST**: Submitting forms and uploading data
- **PUT**: Creating or updating resources
- **DELETE**: Removing resources
- **HEAD**: Getting headers without body
- **OPTIONS**: Discovering available methods

### Practical Exercises Completed

**cURL Command Examples:**
```bash
# Basic GET request
curl http://inlanefreight.com

# Download file with custom name
curl -o index.html http://inlanefreight.com

# Silent mode
curl -s http://inlanefreight.com

# View headers only
curl -I http://inlanefreight.com

# Include headers in output
curl -i http://inlanefreight.com

# Verbose output
curl -v http://inlanefreight.com

# Custom User-Agent
curl -A "CustomBot/1.0" http://inlanefreight.com

# Skip SSL certificate verification
curl -k https://inlanefreight.com
```

**HTTP Headers Analysis:**
```
# Request Headers
Host: www.inlanefreight.com
User-Agent: curl/7.77.0
Accept: */*
Cookie: PHPSESSID=b4e4fbd93540
Authorization: BASIC cGFzc3dvcmQK

# Response Headers
Server: Apache/2.2.14 (Win32)
Set-Cookie: PHPSESSID=b4e4fbd93540
Content-Type: text/html
Content-Length: 385
```

### Authentication and Session Management

**Basic Authentication:**
```bash
# Using cURL with basic auth
curl -u admin:password http://inlanefreight.com/admin

# Base64 encoded credentials
curl -H "Authorization: Basic YWRtaW46cGFzc3dvcmQ=" http://inlanefreight.com/admin
```

**Session Cookie Management:**
```bash
# Login and save cookies
curl -c cookies.txt -d "username=admin&password=password" http://inlanefreight.com/login

# Use saved cookies for authenticated requests
curl -b cookies.txt http://inlanefreight.com/admin
```

### API Testing with CRUD Operations

**CRUD API Interactions:**
```bash
# CREATE - Add new user
curl -X POST -H "Content-Type: application/json" -d '{"name":"john","email":"john@example.com"}' http://api.inlanefreight.com/users

# READ - Get user information
curl http://api.inlanefreight.com/users/1

# UPDATE - Modify user data
curl -X PUT -H "Content-Type: application/json" -d '{"name":"john updated"}' http://api.inlanefreight.com/users/1

# DELETE - Remove user
curl -X DELETE http://api.inlanefreight.com/users/1
```

### Security Insights Discovered

**HTTPS Security Benefits:**
- Encryption prevents eavesdropping on sensitive data
- Certificate validation ensures server authenticity
- Prevents man-in-the-middle attacks
- Protects user credentials and session tokens

**Common Security Headers:**
- `Content-Security-Policy`: Prevents XSS attacks
- `Strict-Transport-Security`: Enforces HTTPS usage
- `X-Frame-Options`: Prevents clickjacking
- `X-Content-Type-Options`: Prevents MIME sniffing

### Key Findings

**Protocol Behavior:**
- HTTP requests are stateless by nature
- HTTPS adds significant security but requires proper certificate management
- Session management through cookies maintains state across requests
- API design follows RESTful principles for predictable interactions

**Tool Effectiveness:**
- cURL provides powerful command-line flexibility for automation
- Browser DevTools offer visual inspection capabilities
- Verbose flags reveal detailed protocol communications
- Header manipulation enables advanced testing scenarios

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
