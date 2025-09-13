# Network-Analysis-Dashboard
When I first set out to get hands on with Splunk, I had no idea what to expect. As a cybersecurity intern, I kept hearing how critical it is for SOC analysts, and I even came across another internship centered almost entirely on Splunk. That made me curious about why it is seen as a must-know tool for analyzing logs, monitoring traffic, and spotting anomalies. I wanted to see for myself how professionals use it to uncover threats across systems and networks. 



<img width="1918" height="971" alt="Screenshot 2025-09-09 at 10 53 32 PM" src="https://github.com/user-attachments/assets/55efaaf6-ab22-4f4c-bdf2-d057550e61a6" /> <br><br>





Opening Splunk for the first time was overwhelming, with dashboards, search bars, and menus I didn’t understand. I remember staring at the home screen thinking, “Okay, now what?” A YouTube walkthrough finally made it clear: Splunk Enterprise is the brain of the operation, the central hub where data is indexed, stored, and made searchable, while everything else depends on feeding it fresh data to analyze.

Setting up Splunk Enterprise was simple with the GUI; no terminal was needed. After creating my admin account, I watched a YouTube walkthrough to learn the basics like building dashboards, working with indexes, and filtering by IPs, MAC addresses, and geolocation. Once I got comfortable, I started wondering if I could bring in external datasets, such as those from Kaggle, to experiment with creating dashboards and applications. <br><br>


<img width="1916" height="970" alt="Screenshot 2025-09-12 at 2 17 38 PM" src="https://github.com/user-attachments/assets/bc87501c-2899-4bda-8127-ffce4f1dd451" /> <br><br>



That curiosity led me to the free BOTS v3 dataset, which contains public AWS-sourced data with multiple sourcetypes. I tried importing it into Splunk, but soon realized it was not that simple. Splunk Enterprise acts as the hub for indexing and analysis, but it needs an agent to bring in data. That is where the Universal Forwarder comes in, a lightweight tool that collects and sends logs to Enterprise.  <br><br>

<img width="970" height="966" alt="Screenshot 2025-09-12 at 2 23 18 PM" src="https://github.com/user-attachments/assets/6aaef024-c7fd-4da7-b29d-4170db2ea600" /> <br><br>

This step was more challenging since it required configuring ports and ensuring they were available. Fortunately, the Universal Forwarder defaults to port 9997, which was open on my system. After enabling it in Splunk Enterprise, the forwarder connected successfully and began transmitting data, completing the pipeline for analysis. <br><br>

After inserting the dataset into Splunk under /Applications/Splunk/etc/apps and restarting to ensure it was integrated, I logged into Splunk Enterprise and opened the Search & Reporting app. This is the hub for querying data with SPL, where you can filter logs, run stats, and build charts. 


From a video I watched about the basics of Splunk, I learned that an index is where you tell Splunk what to search. Since my dataset was called botsv3, I tried using the command index=botsv3, but nothing happened. At first, I was skeptical about why it did not work, and I figured I was missing something. Later, I found on a Splunk guide that you also need to add earliest=0, which tells Splunk to include the very first available event in the dataset. Put together, index=botsv3 earliest=0 means Splunk will search all events in the dataset starting from the very beginning. /> <br><br>


 
<img width="1914" height="969" alt="Screenshot 2025-09-13 at 7 23 36 PM" src="https://github.com/user-attachments/assets/f115573d-5a6b-419a-855b-7f95de5fb776" />/> <br><br>


After running the command, I saw a huge number of events that spanned about a year’s worth of logs from the dataset. These events represented different kinds of network activity. Some showed failed services or errors between connection endpoints, while others captured detailed records of network traffic. Each log contained valuable fields such as src_ip and dest_ip to identify endpoints, src_mac and dest_mac for hardware identifiers, and protocol_stack to show which communication protocols were used, such as TCP. I also recognized fields like bytes_in and bytes_out, which represent the amount of data transferred between endpoints. Many of these concepts were already familiar to me from my summer internship, which made it easier to connect the raw data with real-world networking and security practices.



