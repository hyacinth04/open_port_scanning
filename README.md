# Internship Task 1: Network Reconnaissance

**Day 1: Local Network Port Scanning**

* **Author**: Miraclin Akshaya
* **Date**: 22-09-2025
* **Tools**: Nmap, Terminal / Command Prompt
* **Objective**: Learn basic network reconnaissance, identify open ports, and document findings to understand network service exposure.

### Process & Lessons Learned

To complete this task, I performed a hands-on network scan. I started by using online tutorials to understand the core concepts of Nmap, TCP SYN scans, and how to interpret the results. This self-guided research was crucial for my understanding.

1.  **Network Discovery**: I first used `ipconfig` to find my local IP address (`192.168.1.9`) and determine my network range (`192.168.1.0/24`).

2.  **Performing a Scan**: I executed a TCP SYN scan using the command `nmap -sS 192.168.1.0/24` to stealthily identify open ports on my network.

3.  **Analyzing the Results**: The scan revealed several active devices. I focused on documenting the open ports, the services running on them, and the potential security implications.

4.  **Documentation**: I saved the Nmap scan output to a text file for future reference using the command `nmap -sS 192.168.1.0/24 -oN results.txt`.

### Key Findings & Analysis

| IP Address | Open Ports | Common Services | Potential Security Risks |
| :--- | :--- | :--- | :--- |
| **192.168.1.1** | 53/tcp, 80/tcp, 443/tcp | DNS, HTTP, HTTPS | Standard ports for a router's web administration and DNS service. The primary risk is a weak admin password. |
| **192.168.1.3** | 8001/tcp, 8002/tcp, 8080/tcp, 9080/tcp | `vcom-tunnel`, `teradataordbms`, `http-proxy`, `glrpc` | Non-standard ports that could be used by various applications. They are potential entry points for an attacker if the services are unpatched or misconfigured. |
| **192.168.1.9** | 135/tcp, 139/tcp, 445/tcp | `msrpc`, `netbios-ssn`, `microsoft-ds` | Common Windows ports for remote procedure calls and file sharing. If exposed to the internet, they could be vulnerable to exploits. |

### Devices with No Open Ports

The following IP addresses were found to be up, but all of their scanned ports were either closed or filtered, indicating they are not immediately accessible for direct network connections.

* `192.168.1.4`
* `192.168.1.5`
* `192.168.1.6`

### Conclusion

This task provided valuable hands-on experience in network reconnaissance. I learned to use Nmap effectively, interpret scan results, and understand the security implications of network services. I also learned the importance of clear documentation for my findings.

---

### File Attachments

This repository includes:

* `results.txt`: The raw output from the Nmap scan.
* Screenshots of the `ipconfig` and Nmap command results.
