# Enumeration


Enumeration
Enumeration allows you to establish an active connection with a target. Your intent is to extract different types of information from the target. Some of the information that you can extract is:

-Usernames
-Group Names
-Hostnames
-Network Shares and Services
-Routing Tables
-Web Application
-Web Servers
-SNMP Information
-DNS Information

Various types of enumerations can be performed. Some of these are:

Windows Enumeration
-Linux Enumeration
-NetBIOS Enumeration
-SNMP Enumeration
-LDAP Enumeration
-NTP Enumeration
-SMTP Enumeration
-DNS Enumeration

In this exercise, you will learn to use some of the enumeration techniques using Windows-based tools.

### Learning Outcome

-Use Nmap
-Use the Hping Command
-Understand Active vs. Passive Enumeration
-Use the Responder

## Task 1 - Nmap
Network Mapper, known as Nmap, is a network and host discovery tool. It is one of the most widely used tools for various activities, such as:

Discovering hosts, services, and ports
Fingerprinting operating systems
Enumeration
Discovering vulnerabilities on the local and remote host
Finding the IP address of a remote system
Using Nmap, you can scan for targets by:

Scanning for a single IP: nmap 192.168.0.1
Scanning for a host by using its name: nmap host1.plab.com
Scanning an entire subnet: nmap plab.com/24, nmap 192.168.0.0/24, nmap 192.168.0.*
Scanning for a range of IP addresses: nmap 192.168.0.1-10
Scanning for a range and a system outside the range: nmap 192.168.0.1, 1.10

## Task 2 Infrastructure Security 
Learning Outcomes
In this module, you will complete the following exercises:

Exercise 1 - Set up a Honeypot with Pentbox
Exercise 2 - Data Collector Sets
Exercise 3 - Configuring Alerts for Data Collector Sets
Exercise 4 - Enable EFS on Standalone Windows Computer
After completing this lab, you will be able to:

Download and Install Pentbox
Modify Proxy Server Exceptions in PLABWIN10
Test Honeypot Functionality
Create Data Collector Sets
Create a Schedule
Configure Alerts
Remove Windows Computer from the Domain
Create a Local User for Testing Local EFS
Allow Log on to the System via Remote Desktop
Create Folder, File, and Enable EFS
View EFS Permission
View the Effect of Copying or Moving Files on Encryption
Decrypt Files
Exam Objectives
The following exam objectives are covered in this lab:

2.1 Given a scenario, apply security solutions for infrastructure management.

Exercise 1 - Set up a Honeypot with Pentbox
A honey pot is a decoy, or a trap created by organizations to attract hackers into a computer system. One of the main objectives of using a honeypot is to monitor the hacker exploit the vulnerabilities of the system, then subsequently learn the weaknesses of the system and apply the necessary security measures to strengthen it from future attacks.

In this lab, you will learn how to use a program called Pentbox to create a basic honeypot system and test it using a standard web browser to detect an intrusion.

Learning Outcomes
After completing this exercise, you will be able to:

Download and Install Pentbox
Modify Proxy Server Exceptions in PLABWIN10
Test Honeypot Functionality

Task 1 - Download and Install Pentbox
Pentbox is a suite that has various security tools to streamline the security activities in your network. You can use it for various purposes, such as setting up a honeypot. In this task, you will download and install a program called Pentbox then set up a basic honeypot in a Kali Linux device. To do this, perform the following steps:



1. On the desktop, in the left pane, click the Terminal icon.
2. The terminal window is displayed. Before installing anything, we need to make sure that the keyring is added.

To add the keyring, type the following command: wget -q -O - archive.kali.org/archive-key.asc | apt-key add
![image](https://github.com/kalejcamto/Enumeration/assets/101201140/ce5722f2-5185-4b0d-aa9b-268dacb03152)


Once complete and back on the root@kali prompt, type the following command: wget http://downloads.sourceforge.net/project/pentbox18realised/pentbox-1.8.tar.gz

![image](https://github.com/kalejcamto/Enumeration/assets/101201140/21af8b69-32a3-4a90-a70e-1633a3618115)
A confirmation will be displayed to indicate a successful download of the pentbox.
![image](https://github.com/kalejcamto/Enumeration/assets/101201140/1079a308-8f71-4e11-be7b-22555e2d9a36)

Clear the screen by entering the following command: clear

![image](https://github.com/kalejcamto/Enumeration/assets/101201140/3fd1ab1a-7e67-47bc-8951-dca78313a29f)
On the next prompt, to uncompress the pentbox files, type: tar -zxvf pentbox-1.8.tar.gz
![image](https://github.com/kalejcamto/Enumeration/assets/101201140/b7bb4e22-e6af-4d87-a4fa-c393a1f219cd)


The pentbox files will be extracted in its folder. On the next prompt, type the following to change to the pentbox folder:  cd pentbox-1.8/
On the next prompt, to run pentbox type the following: ./pentbox.rb
  ![image](https://github.com/kalejcamto/Enumeration/assets/101201140/2b60b507-8795-494e-b2d6-e0673b28667b)

From the Pentbox menu, type:  2


![image](https://github.com/kalejcamto/Enumeration/assets/101201140/3af7f011-1ddb-416d-a057-90401f32b9d0)

On the next menu screen, type the following:  3

![image](https://github.com/kalejcamto/Enumeration/assets/101201140/c13f694d-999f-459b-ab0a-a7a8023e29f0)

On the run Pentbox screen, type the following:  1

I get a notification that the *HONEYPOT ACTIVATED ON PORT 80*.  

Keep the terminal window running the Pentbox tool open.


Connected to .WINDOWS 10  VM Server In the Type here to search textbox, type the following: Internet Explorer
From the search results, select Internet Explorer.

![image](https://github.com/kalejcamto/Enumeration/assets/101201140/b12c375a-9001-465c-a82b-0f50b8da02c0)

On the Internet Options dialog box, click the Connections tab.

![image](https://github.com/kalejcamto/Enumeration/assets/101201140/b9f01564-6293-4b39-85ae-ca16e3cfbaab)

Under the Connections tab, next to Local Area Network (LAN) settings, click LAN settings.

On the Local Area Network (LAN) Settings, ensure that the Bypass proxy server for local address checkbox is ticked.

Click Advanced.


![image](https://github.com/kalejcamto/Enumeration/assets/101201140/898f7007-a1a7-4dd7-b746-79267b7168fb)

On the Proxy Settings dialog box, click on the provided text box and type: ;192*  then, ok.

![image](https://github.com/kalejcamto/Enumeration/assets/101201140/786aea55-aa6a-4909-a989-722d09b4e4e8)

![image](https://github.com/kalejcamto/Enumeration/assets/101201140/9fe4c51d-c712-459c-b3dc-c9c94e33947d)

Similarly, click OK on Local Area Network (LAN) Settings and Internet Options dialog boxes.


## Test Honeypot Functionality
After you have configured the honeypot, you need to test its functionality. One of the simplest methods could be attempting to access the Webserver that it is running. In this task, you will test the functionality of the Pentbox honeypot. To do this, perform the following steps:


WIN 10 SERVER the Internet Explorer window is open.

Click on the address bar and type: http://192.168.0.3


![image](https://github.com/kalejcamto/Enumeration/assets/101201140/daab283e-c26b-4de1-bcf6-c0df79e09116)

going back to Kali: Connect to KALILINUX. Ensure that the terminal window is still open, and the pentbox is running.

The terminal window displays INTRUSION ATTEMPT DETECTED from 192.168.0.4:XXXXX.
Using the Pentbox application, you have learned how honeypot systems work.

The administrator of the system where the honeypot is deployed can take the appropriate measures to strengthen the defenses of a computer system.


![image](https://github.com/kalejcamto/Enumeration/assets/101201140/909d9003-92c8-4321-a5c3-de314285b93b)



END OF LAB
