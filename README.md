# SPLUNK & SYSMON CONFIGURATION

## Summary
In this lab, I successfully set up an internal network using VirtualBox with a Domain Controller managing DHCP, and installed Ubuntu 24.04.1 Server as a dedicated Splunk server. The lab involved installing Splunk Enterprise on the Ubuntu server via the command line, configuring a static IP address through the netplan utility, and ensuring seamless communication with the Domain Controller for DNS and routing. I also demonstrated how to secure access by changing user permissions and utilized the web interface for Splunk to confirm the installation was operational. Additionally, OpenSSH was installed for future remote access purposes.

Once the Splunk server was operational, I configured a Windows machine with the Splunk Universal Forwarder to collect logs and send them to the Splunk server. This setup is ideal for real-time log analysis and monitoring. I ensured all configurations followed best practices, including static IP assignment, proper account privileges, and user authentication. This lab provided a hands-on demonstration of setting up a SIEM tool in a virtualized environment, showcasing my abilities to work with Splunk, Linux server environments, and network configuration.

### Skills Learned
[Bullet Points - Remove this afterwards]

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
[Bullet Points - Remove this afterwards]

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## 
drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*
