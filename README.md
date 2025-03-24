
**🛡️ Creating a Honeypot using Pentbox on Kali Linux (VMware)**
**📌 Honeypot**
Simulating a Network Honeypot to Detect Unauthorized Access

**🎯 Objective**
The goal of this project is to set up a honeypot using Pentbox on a Kali Linux virtual machine to simulate a web server and observe how unauthorized connection attempts are logged. This serves as a basic example of cybersecurity threat detection and monitoring.

**🧰 Materials & Tools**
VMware Workstation Pro

Kali Linux 2024.4 ISO

Pentbox v1.8

Host Computer (Windows/macOS)

Internet Browser (for simulating access attempts)

**🧪 Procedure**
**1. Creating the Virtual Machine**
I used VMware Workstation Pro to create a new virtual machine.

Installed Kali Linux 2024.4 as the guest operating system.

**2. Installing Pentbox**

Opened the terminal inside Kali Linux.

Ran the following command to download Pentbox:

wget https://downloads.sourceforge.net/project/pentbox18realised/pentbox-1.8.tar.gz

Extracted the .tar.gz archive:

tar -xvzf pentbox-1.8.tar.gz

Created a dedicated directory for organization:

mkdir pentbox

mv pentbox-1.8/* pentbox/

cd pentbox

**3. Running Pentbox**
   
Started the tool by running:

ruby pentbox.rb
Navigated through the Pentbox menu:

Network Tools → Honeypot → Fast Auto Configuration
Selected port 80, the default HTTP port, to simulate a web server.

Pentbox launched the honeypot and began listening for incoming connections.


Honeypot activated on port 80.

![image](https://github.com/user-attachments/assets/9a6df9f0-69b6-430a-9939-62ef2e6b76bd)


**4. Simulating an Intrusion Attempt**
On my host machine (outside the virtual machine), I opened a browser.

Typed the IP address of the virtual machine in the URL bar:

http://<your-vm-ip-address>

The honeypot responded with an "Access Denied" page.


Browser shows an "Access Denied" message.

![image](https://github.com/user-attachments/assets/65ddbeb9-aa9f-48e1-ab30-16ec51b40c77)


**5. Logging and Detection**
Back on the Kali Linux VM terminal, Pentbox detected the attempt.

It logged information such as:

The IP address of the request

User-Agent (browser/device info)

Timestamp of the event


Pentbox logs the intrusion attempt with detailed request info.

![image](https://github.com/user-attachments/assets/38c88f92-8961-46db-9ab0-8f6b698764ac)


**📝 Summary**
This project demonstrates how to set up a basic honeypot using Pentbox v1.8 in a Kali Linux virtual machine. The honeypot listens on port 80 and logs unauthorized HTTP requests as potential intrusion attempts. This setup provides a simple, controlled environment for understanding how attackers probe network services and how such activities can be monitored. While not a production-grade security solution, it's a great introduction to cybersecurity monitoring, network awareness, and the concept of trap-based defense mechanisms.
