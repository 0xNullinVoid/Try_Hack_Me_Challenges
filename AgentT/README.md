# Agent T 

[Try Hack Me Room](https://tryhackme.com/room/agentt) 

# Room Details:
Agent T uncovered this website, which looks innocent enough, but something seems off about how the server responds...

After deploying the vulnerable machine attached to this task, please wait a couple of minutes for it to respond.

# Tools Used: 
  - nmap
  - exploitdb

# Analysis

1. We're given the IP address to view a website, nagivating to the website shows us a dashboard.
<img width="1267" height="762" alt="Screenshot from 2026-02-18 14-59-59" src="https://github.com/user-attachments/assets/d7e428a8-33ff-4652-8859-434bd03625a8" />

2. Navigating the website doesn't provide much information or potential exploits so we'll start a scan using nMap using the -A function which scans for OS and version detection. 
  <img width="815" height="413" alt="nMapScan" src="https://github.com/user-attachments/assets/63713516-9857-4267-9b5b-52a7c9f9b3ca" />

3. From the scan we can see that port 80 is opened and it's running PHP cli server 5.5 (PHP 9.1.0-dev). This servers is vulnerable to Remote Code Execution (RCE) where code can be ran remotely on a target system which can compromise the whole system. This vulnerability can be found on ExploitDB where the python code can be retrieved. 
   
<img width="1029" height="580" alt="ExploitDB" src="https://github.com/user-attachments/assets/60a42534-2211-4aa1-abdd-333961b4114f" />

4. Running the code will give us the option to enter the target IP address and once completed gives us shell access to the website. 
<img width="667" height="152" alt="python" src="https://github.com/user-attachments/assets/4f6eba92-e41d-4f1a-8473-aef0a8db8537" />

5. Once we gain access to the shell it's just a matter of finding the flag file using the find function and cat to display the file. 
<img width="435" height="115" alt="flag" src="https://github.com/user-attachments/assets/d5190f32-6117-4b52-8fb5-b4111668e297" />


