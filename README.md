# SPLUNK & SYSMON CONFIGURATION

This is an overview of my experience installing splunk on an ubuntu CLI server, Installing the SplunkUniversalForwarder on a Client, Using a custom inputs.conf file. Alongside this I also Installed and configured Sysmon using Powershell.

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

## Splunk Summary
In this lab, I successfully installed Ubuntu 24.04.1 as a dedicated Splunk server. This involved installing Splunk Enterprise on the Ubuntu Machine using a CLI (Command Line Interface) setting up a static IP address using the netplan utility and connecting it to the Domain Controller for DNS and routing. I then used the web interface for Splunk on my Windows Machine to ensure the installation was successful and the server was up on the network.

Once the Splunk server was up and running, I  configured the Domain Controller with the Splunk Universal Forwarder in order to collect logs and forward them to the Splunk server. This Lab also allowed me the opportunity to learn how to write an input.conf file allowing me to configire where I want real-time log analysis and monitoring to be done. All configurations were performed by following best practices: assignment of static IP, proper privileges of the account, and authentication of users. This lab provided hands on experience in the implementation and configuration of a SIEM tool and demonstrated how to use Splunk, Linux server environments, and network configuration.

## Sysmon Summary
In this lab, I successfully installed Sysmon on a Domain Controller. The lab began with downloading Sysmon from the internet, extracting the files, and preparing for installation. I was able to install a prebuilt configuration file (Olaf Sysmon Configuration) alongside syslog. I used PowerShell as an administrator to execute commands to install and configure both. This task reinforced my understanding of how Sysmon can be installed and configured. 

## Step By Step

<a href="https://github.com/karamkamal1/Splunk_and_Sysmon_Configuration_/blob/cb72125f31c23e9d35888fa55200732d19dbb7c0/step_by-step_splunk_configuration.md">SPLUNK LAB</a>

<a href="https://github.com/karamkamal1/Splunk_and_Sysmon_Configuration_/blob/cb72125f31c23e9d35888fa55200732d19dbb7c0/step_by_step_sysmon_configuration.md">SYSMON LAB</a>

<a href="https://github.com/karamkamal1/Splunk_and_Sysmon_Configuration_/blob/3b9534c8fe3334d8e153ddc89ee9a8453fbae61d/Splunk_inputs_conf">SPLUNK INPUTS.CONF</a>

