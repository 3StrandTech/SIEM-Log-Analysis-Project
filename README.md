<h1> SIEM Log Analysis Project </h1>

<h2> Project Overview </h2>

A SIEM setup using two virtual machines (VMs) (1 Ubuntu, 1 Linux Mint VM), a firewall (pfsense Community Edition), and an open source Extended Detection and Response (XDR) and Security Information and Event Management (SIEM) system called Wazuh. I built the project to practice my cybersecurity skills. 

Note: I do have a 10 part series on LinkedIn where I go into great detail about the entire setup. You can view Part 1 of that setup <a href="https://www.linkedin.com/pulse/siem-project-lab-setup-part-1-install-oracle-nicholas-piersimoni-puxte/?trackingId=%2Fq3V7dKkz2Gm6GlBAlkttQ%3D%3D">here</a>, at the bottom of each article is a link to the next article. 

<h2> Project Objective </h2>

Build a home lab to simulate the setup of a firewall and SIEM for the purposes of practicing various cybersecurity skills. In this lab, you will see:

1. The network diagram showing the setup of the devices involved and their subnets
2. The flow of data from each device to other devices
3. A simulation of a failed login and then the succeeding Wazuh event showing the failed login within Wazuh!

<h2> Network Diagram </h2>

Below you see the network diagram (made with draw.io). To summarize, the pfSense router/firewall is the DHCP server. The 172.16.0.1/24 network is for the LAN interface only. The WAN interface is active and only allows the two Linux machines to access the Internet. The two Linux VMs generate data and have Wazuh agents installed that forward logs to the Wazuh server. The pfSense device forwards syslogs to the Wazuh server. 

![1](https://github.com/user-attachments/assets/caf1f757-bab5-4bfe-b84a-dfa4b0e5adff)


<h2> Virtual Network Setup </h2>

The network was setup in Oracle Virtualbox and Wazuh Agents were installed on each VM as shown in the second screenshot (shows the terminal commands needed to install the Wazuh agents).

![VirtualBox Network Manager](https://github.com/user-attachments/assets/e397f62b-7754-4b78-a39a-f610da825067)

![Step 11](https://github.com/user-attachments/assets/9c4b26d8-75ef-428a-aff4-8c1853bddd68)

The pfSense router/firewall setup as DHCP server

![Step 4(c)](https://github.com/user-attachments/assets/584ef296-38b6-43e0-b70a-b4d8ef310663)

![Step 5](https://github.com/user-attachments/assets/6326339c-e49f-4fa3-b0d9-e86b609eb24d)

![Step 6](https://github.com/user-attachments/assets/80f98af9-2e54-400c-9a62-722a43f88dfa)

![Step 7](https://github.com/user-attachments/assets/67cebe96-98e4-4760-a841-0a71f1435528)

![Step 7(a)](https://github.com/user-attachments/assets/e12db965-0ae6-48ec-86d9-c18db733cdef)


<h2> Failed Login test </h2>

As you can see in the below screenshots, login attempts failed

![Step 3(a)](https://github.com/user-attachments/assets/6fd7041b-baba-4b15-a19e-e7d36fd32dee)

![Step 3](https://github.com/user-attachments/assets/a0d34914-7b36-49ea-8bae-4646912cff22)


<h2> Wazuh Logs showing failed logins </h2>

In the first image I used Dashboard Query Language (DQL) to search for the failed login records. The second image shows the specific failed login records. 

![Step 7(special)](https://github.com/user-attachments/assets/2fe641b5-e6fc-4275-8009-c60cfc3d7a1b)

![Step 8](https://github.com/user-attachments/assets/718c7c36-f25a-49aa-b602-832fcf3f6a30)

<h2> Lessons Learned </h2>

I learned how to install and configure a network virtually in Oracle VirtualBox including the PC endpoints, router/firewall, and Wazuh server. I was able to attempt to login which failed and was able to verify the failed login in the Wazuh logs. I gained an appreciation for the detail and planning involved in network setup and got experience with Dashboard Query Language (DQL) in searching for the failed authentication logs within Wazuh. I feel much more confident in log analysis as a result of this lab



