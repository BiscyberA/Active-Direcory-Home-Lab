 <h1>Detection Engineering Homelab</h1>
 - [Creating,Validating,Deploying and Monitoring Threat Detection Rules]

<h2>Description</h2>
In this lab, we will focus on the core principles of detection engineering by designing, validating, and monitoring threat detection rules to identify and mitigate potential cybersecurity threats. The lab environment includes configuring a Kali Linux,Windows 11, Ubuntu(Zeek) virtual machine, Nmap,Nikto,Elastic Siem and Atomic Red Team to simulate malicious activity, ingesting log data, and analyzing system behavior to create actionable detection rules.
<br />

<h2>Tools Used</h2>

- <b>Elastic SIEM</b> 
- <b>Kali Linux (Attacker)</b> 
- <b>Ubuntu (Zeek) VM</b> 
- <b>Atomic Red Team</b>
- <b>Nmap</b>
- <b>Nikto</b>



<h2>Environments Used </h2>

- <b>Windows 11 VM</b>
  

<h2>Lab walk-through:</h2>
<p align="center">
<br/>
Here is the Lab Overveiw<br/>
<img src="https://i.postimg.cc/qR84jBzL/Screenshot-2024-12-11-200416.png" />
<br />
<br />
I installed Windows 11, Ubuntu, Kali Linux,on VirtualBox and they are up and Running<br/>
<img src="https://i.postimg.cc/G2LkzzY0/Screenshot-2024-12-13-231314.png"/>
<br />
<br />
I created a small NatNetwork to have all three VMs connected to it and be able to talk to each other<br/>
<img src="https://i.postimg.cc/VNQh4qMx/Screenshot-2024-12-11-152317.png"/>
<br />
<br />
I connected Windows 11 VM to the Natnetwork<br/>
<img src="https://i.postimg.cc/MTZdrdGF/Screenshot-2024-12-13-234149.png" />
<br />
<br />
I connected Ubuntu VM to the Natnetwork<br/>
<img src="https://i.postimg.cc/Kjd3X5K8/Screenshot-2024-12-11-152424.png" />
<br />
<br />
I connected Kali VM to the Natnetwork<br/>
<img src="https://i.postimg.cc/gkmnhrv5/Screenshot-2024-12-11-152445.png" />
<br />
<br />
I tested connectivity between the VMs by pinging the Kali VM with the Ubuntu VM. Connection successfully reached <br/>
<img src="https://i.postimg.cc/FsTsJpFd/Screenshot-2024-12-11-152553.png" />
<br />
<br />
I ping Ubuntu VM with Windows 11 VM and connection was successful<br/>
<img src="https://i.postimg.cc/1X9s8nLr/Screenshot-2024-12-11-153837.png" /> 
<br />
<br />
I ping Ubuntu VM with Kali VM and connection was sucessful<br/>
<img src="https://i.postimg.cc/1X9s8nLr/Screenshot-2024-12-11-153837.png" />
<br />
<br />
I installed and deployed Zeek network monitoring and analyzer tool on Ubuntu and had it up and running <br/>
<img src="https://i.postimg.cc/qRCSG1ZH/Screenshot-2024-12-11-190957.png" />
<br />
<br />
I navigated to Zeek connection log directory to verify if its receiving logs. This output shows logs successfully been received<br/>
<img src="https://i.postimg.cc/wjNZdxrq/Screenshot-2024-12-14-135740.png" />
<br />
<br />
I signed up and deployed ElastiC SIEM instance  <br/>
<img src="https://i.postimg.cc/28HGV42Q/Screenshot-2024-12-11-192543.png" />
<br />
<br />
I added built-in Elastic Defend integration to Elastic which provides prevention, detection and response capabilities<br/> 
<img src="https://i.postimg.cc/gj5Sf1qL/Screenshot-2024-12-11-193851.png" />
<br />
<br />
 I clicked insatll Elastic agent to beggin the installation<br />
<img src="https://i.postimg.cc/4NK7QVXb/Screenshot-2024-12-11-194031.png" />
<br />
<br />
I used this command to install the Elastic Agent on Windows 11 <br/> 
<img src="https://i.postimg.cc/wjYFLXWz/Screenshot-2024-12-11-194405.png"/>
<br />
<br />
I run the installation and it was successfully installed <br/> 
<img src="https://i.postimg.cc/C5R1JppL/Screenshot-2024-12-12-111637.png"/>
<br />
<br />
Result of Elastic Agent enrolled on Windows 11<br/>
<img src="https://i.postimg.cc/nzzccfzY/Screenshot-2024-12-12-112010.png" />
<br />
<br />
A preview in Elastic Siem shows logs coming in from the Windows 11 VM after the Agent installed. <br/>
<img src="https://i.postimg.cc/1R8wJLHq/Screenshot-2024-12-12-114339.png" />
<br />
<br />
I run a few commands again on the Windows 11 VM to verify if it will be pickup by Elastic <br/>
<img src="https://i.postimg.cc/3NnYpLcC/Screenshot-2024-12-12-150440.png" />
<br />
<br />
I query the logs in Elastic for the Command Whoami and it was pickup by Elastic<br/>
<img src="https://i.postimg.cc/9Q2YzLjN/Screenshot-2024-12-12-151024.png" />
<br />
<br />
I also added Zeek integration to Elastic since I have Zeek running on Ubuntu VM for network monitoring.
<img src="https://i.postimg.cc/ZnN94z7s/Screenshot-2024-12-12-114804.png" />
<br />
<br />
Zeek integration added to Elastic <br/>
<img src="https://i.postimg.cc/WzrYcX99/Screenshot-2024-12-12-130920.png" />
<br />
<br />
I run this command to install Elastic agent on Ubuntu where zeek is running<br/>
<img src="https://i.postimg.cc/kg71LNWc/Screenshot-2024-12-12-130947.png" />
<br />
<br />
Elastic agent successfully installed on Ubuntu <br/>
<img src="https://i.postimg.cc/N0XZ6Nnq/Screenshot-2024-12-12-131233.png" />
<br />
<br />
Zeek logs successfully been ingested into Elastic<br/>
<img src="https://i.postimg.cc/RZqf3Nmm/Screenshot-2024-12-12-135059.png" />
<br />
<br />
An overveiw of web scans againts a simple webserver<br/>
<img src="https://i.postimg.cc/gJb6BsZc/Screenshot-2024-12-12-164810.png" />
<br />
<br />
I created a simple web server on windows 11 VM <br/>
<img src="https://i.postimg.cc/zf719XLL/Screenshot-2024-12-12-170102.png" />
<br />
<br />
I tested the webserver on a web browser and it was successfully up and running<br/>
<img src="https://i.postimg.cc/6qywVJp8/Screenshot-2024-12-12-173516.png" />
<br />
<br />
I run an Nmap scan against the webserver and we can see the request coming in on the webserver<br/>
<img src="https://i.postimg.cc/g0YCqFMG/Screenshot-2024-12-13-015514.png" />
<br />
<br />
I also run an Nikto scan against the webserver and we can see the request coming in on the webserver<br/>
<img src="https://i.postimg.cc/t432yb39/Screenshot-2024-12-13-021655.png" />
<br />
<br />
We can see zeek logs coming into Elastic after running the scans<br/>
<img src="https://i.postimg.cc/DfR9w2XG/Screenshot-2024-12-12-135111.png" />
<br />
<br />
We can see the logs in Elastic and based on the event.dataset, I am interested in zeek.http data since our scan was hitting the http server<br/>
<img src="https://i.postimg.cc/0y9BGQLB/Screenshot-2024-12-12-235010.png" />
<br />
<br />
I filtered the logs to make it looks more readable and organize<br/>
<img src="https://i.postimg.cc/SNy7ZFFm/Screenshot-2024-12-13-001211.png" />
<br />
<br />
I queried the logs for the string Nmap and got these results<br/>
<img src="https://i.postimg.cc/gkQ2dFYt/Screenshot-2024-12-15-233043.png" />
<br />
<br />
I was also queried the logs for Nikto and got these results <br/>
<img src="https://i.postimg.cc/zvMzRYTT/Screenshot-2024-12-13-010902.png" />
<br />
<br />
I wrote a single query to filter namp and nikto strings in the logs. The idea here is to use this query to create a detection rule that will alert on Nmap and Nikto scans  <br/>
<img src="https://i.postimg.cc/tTWwzQ0h/Screenshot-2024-12-15-000525.png" />
<br />
<br />
I am going to create a customer rule to alert on Nmap and Nikto scans <br/>
<img src="https://i.postimg.cc/Bb3yYYsR/Screenshot-2024-12-13-012448.png" />
<br />
<br />
I added the query in the custom query field, suppressed alert by destination.ip and runs every 5mins.<br/>
<img src="https://i.postimg.cc/mgkCpGmd/Screenshot-2024-12-13-012709.png" />
<br />
<br />
I named the rule, gave a description and severity level<br/>
<img src="https://i.postimg.cc/3RZhB6tX/Screenshot-2024-12-13-012941.png" />
<br />
<br />
I added Mitre Att&ck information based on the activity performed<br/>
<img src="https://i.postimg.cc/jSJr9C8d/Screenshot-2024-12-13-013747.png" />
<br />
<br />
The rule shown been added to the Elastic buit-in rules list<br/>
<img src="https://i.postimg.cc/4d05r42s/Screenshot-2024-12-15-002827.png" />
<br />
<br />
I run the Nmap scan again against the web server to test on the detection rule created if it will be alerted in Elastic <br/>
<img src="https://i.postimg.cc/FHYkgVK8/Screenshot-2024-12-13-015514.png" />
<br />
<br />
I verified in Elastic and the Nmap scan was alert on the detection rule created <br/>
<img src="https://i.postimg.cc/Z5N1H2RW/Screenshot-2024-12-13-020636.png" />
<br />
<br />
 I installed Atomic Redteam on the Windows 11 VM to simulate an attack,create detection rule of the attack and use the rule to alert on activities in our environment <br/>
<img src="https://i.postimg.cc/ydHJKqTC/Screenshot-2024-12-15-005711.png" />
<br />
<br />
The installation run, basically installed the Atomic Redteam framework,a module into powershell and also downloaded the Mitre Techniques <br/>
<img src="https://i.postimg.cc/23N89v4v/Screenshot-2024-12-14-220056.png" />
<br />
<br />
I simulated the attack based on the Mitre Tactics Collection and Audio Capture Technique with ID T1123 <br/>
<img src="https://i.postimg.cc/x81KTX8W/Screenshot-2024-12-15-011355.png" />
<br />
<br />
I run the simulation attack by running the invoke command on the technique T1123<br/>
<img src="https://i.postimg.cc/90SCWZjw/Screenshot-2024-12-13-154524.png" />
<br />
<br />
The invoke command run, will basically run the below powershell attack command <br/>
<img src="https://i.postimg.cc/L5jnSRBr/Screenshot-2024-12-15-013719.png" />
<br />
<br />
I verified the logs in Elastic,filter the windowsAudioDevice-Powershell-cmdlet and the logs successfully show in Elastic <br/>
<img src="https://i.postimg.cc/jdV7F3Qp/Screenshot-2024-12-13-190205.png" />
<br />
<br />
I filtered the logs with the necessary fields to get a better view <br/>
<img src="https://i.postimg.cc/VNRwJ388/Screenshot-2024-12-13-190608.png" />
<br />
<br />
I then save the search which can be later use to alert in activities based on the command <br/>
<img src="https://i.postimg.cc/5y8qRhHt/Screenshot-2024-12-15-015920.png" />
<br />
<br />
<h1>In Conclusion</h2>
As a Detection Engineer, when investigating alerts or incidents related to suspicious activity, it is crucial to leverage various tools to analyze the data and identify potential threats. For example, email-related alerts can be dissected to uncover malicious indicators such as suspicious IPs, URLs, or payloads. Additionally, sandbox environments can be used to analyze attachments or executables, providing insight into the behavior of potential malware. This approach ensures accurate detections and aids in developing effective threat detection rules to proactively identify and mitigate similar threats in the future.
</p>

