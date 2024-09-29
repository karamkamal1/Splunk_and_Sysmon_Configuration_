# SPLUNK & SYSMON CONFIGURATION

## Splunk Summary
In this lab, I successfully installed Ubuntu 24.04.1 as a dedicated Splunk server. It involved installing Splunk Enterprise on the Ubuntu server via the command line, configuring a static IP address through the netplan utility, and ensuring connection with the Domain Controller for DNS and routing. I also demonstrated how to secure access by changing user permissions and utilized the web interface for Splunk to confirm the installation was succesful.

Once the Splunk server was running, I configured the Domain Controller with the Splunk Universal Forwarder to collect logs and send them to the Splunk server. This setup is ideal for real-time log analysis and monitoring. I ensured all configurations followed best practices, including static IP assignment, proper account privileges, and user authentication. This lab provided a hands-on demonstration of setting up a SIEM tool, showcasing my abilities to work with Splunk, Linux server environments, and network configuration.

## Sysmon Summary
In this lab, I successfully installed Sysmon on a Domain Controller. The lab began with downloading Sysmon from the internet, extracting the files, and preparing for installation. I was able to install a prebuilt configuration file (Olaf Sysmon Configuration) alongside syslog. I used PowerShell as an administrator to execute commands to install and configure both. This task not reinforced my understanding of how Sysmon can be installed and configured. 


### Skills Learned
- Understanding of Splunk concepts and Deployment.
- Installation and configuration of Sysmon.
- Ability to use Powershell.
- Advanced ability to use Linux CLI.

### Tools Used

- Linux CLI
- PowerShell
- Splunk
- Notepad(inputs.conf)

## Step By Step

<a href="https://github.com/karamkamal1/Splunk_and_Sysmon_Configuration_/blob/cb72125f31c23e9d35888fa55200732d19dbb7c0/step_by-step_splunk_configuration.md">SPLUNK LAB</a>

<a href="https://github.com/karamkamal1/Splunk_and_Sysmon_Configuration_/blob/cb72125f31c23e9d35888fa55200732d19dbb7c0/step_by_step_sysmon_configuration.md">SYSMON LAB</a>
