## DoS & DDoS Attacks

## Overview

**Denial-of-Service (DoS)** and **Distributed Denial-of-Service (DDoS)** attacks are malicious attempts to take a service offline by overwhelming it with a flood of traffic. While a DoS attack originates from a single source, a DDoS attack is launched from a network of compromised devices, known as a **botnet**, making it far more powerful and complex to mitigate. These attacks target a service's availability, a critical pillar of cybersecurity.

## Types of Attacks

DDoS attacks are often categorized by the layer of the network they exploit. Modern attacks frequently combine these vectors to be more effective.

### A. Volumetric Attacks

These attacks saturate the target's bandwidth with massive amounts of junk traffic.

- **Example:** A **UDP Flood** sends a large volume of User Datagram Protocol packets to random ports, consuming a target's resources as it attempts to respond.

### B. Protocol Attacks

These attacks exploit weaknesses in network protocols to consume server resources, such as its connection table.

- **Example:** A **SYN Flood** exploits the TCP handshake by sending a flood of SYN requests without completing the connection, tying up server resources and preventing legitimate connections.

### C. Application-Layer Attacks

These attacks are more sophisticated, targeting specific application vulnerabilities with seemingly legitimate requests that consume processing power and memory.

- **Example:** An **HTTP Flood** sends a high volume of HTTP GET or POST requests that appear normal but overload a web server's resources.

## Key Impacts

A successful DDoS attack can have significant consequences for an organization.

- **Service Outages:** The immediate and most visible impact is that websites or applications become unavailable to legitimate users.
- **Financial Loss:** For e-commerce or online services, downtime directly translates to lost sales and decreased productivity.
- **Reputational Damage:** Outages can erode customer trust and lead to negative publicity.
- **Security Smokescreen:** DDoS attacks are sometimes used to distract security teams while attackers perform other malicious activities, such as data exfiltration.

## Mitigation Strategies

Effective DDoS mitigation requires a multi-layered, proactive approach, often utilizing specialized services.

- **DDoS Protection Providers:** Companies like **DataDome** specialize in comprehensive protection services that can absorb and filter malicious traffic. Their solutions often employ techniques like scrubbing centers, which divert and clean traffic before forwarding it to your network.
- **Anycast Routing:** A routing technique that advertises the same IP address from multiple locations, distributing incoming traffic (including attack traffic) across a wider network and reducing the impact on a single location.
- **Traffic Scrubbing Centers:** Specialized data centers that an organization's traffic is diverted through during an attack. The center's systems analyze and filter out malicious traffic, forwarding only clean, legitimate traffic to the destination.
- **Content Delivery Networks (CDNs):** Using a CDN helps distribute content and traffic across a global network, which can help absorb the load of an attack and prevent it from overwhelming a single server.
- **Web Application Firewalls (WAFs):** WAFs are crucial for mitigating application-layer attacks by analyzing and filtering HTTP requests to block malicious bots and other threats.
