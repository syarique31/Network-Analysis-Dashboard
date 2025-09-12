# Network-Analysis-Dashboard
When I first set out to get hands on with Splunk, I had no idea what to expect. As a cybersecurity intern, I kept hearing how critical it is for SOC analysts, and I even came across another internship centered almost entirely on Splunk. That made me curious about why it is seen as a must-know tool for analyzing logs, monitoring traffic, and spotting anomalies. I wanted to see for myself how professionals use it to uncover threats across systems and networks. 



<img width="1918" height="971" alt="Screenshot 2025-09-09 at 10 53 32 PM" src="https://github.com/user-attachments/assets/55efaaf6-ab22-4f4c-bdf2-d057550e61a6" /> <br><br>





Opening Splunk for the first time was overwhelming, with dashboards, search bars, and menus I didn’t understand. I remember staring at the home screen thinking, “Okay, now what?” A YouTube walkthrough finally made it clear: Splunk Enterprise is the brain of the operation, the central hub where data is indexed, stored, and made searchable, while everything else depends on feeding it fresh data to analyze.

Setting up Splunk Enterprise was simple with the GUI; no terminal was needed. After creating my admin account, I watched a YouTube walkthrough to learn the basics like building dashboards, working with indexes, and filtering by IPs, MAC addresses, and geolocation. Once I got comfortable, I started wondering if I could bring in external datasets, such as those from Kaggle, to experiment with creating dashboards and applications. <br><br>


<img width="1916" height="970" alt="Screenshot 2025-09-12 at 2 17 38 PM" src="https://github.com/user-attachments/assets/bc87501c-2899-4bda-8127-ffce4f1dd451" /> <br><br>



That curiosity led me to the free BOTS v3 dataset, which contains public AWS-sourced data with multiple sourcetypes. I tried importing it into Splunk but soon realized it was not that simple. Splunk Enterprise acts as the hub for indexing and analysis, but it needs an agent to bring in data. That is where the Universal Forwarder comes in, a lightweight tool that collects and sends logs to Enterprise.  <br><br>

<img width="970" height="966" alt="Screenshot 2025-09-12 at 2 23 18 PM" src="https://github.com/user-attachments/assets/6aaef024-c7fd-4da7-b29d-4170db2ea600" /> <br><br>

This step was more challenging since it required configuring ports and ensuring they were available. Fortunately, the Universal Forwarder defaults to port 9997, which was open on my system. After enabling it in Splunk Enterprise, the forwarder connected successfully and began transmitting data, completing the pipeline for analysis. <br><br>

After inserting the dataset into Splunk under /Applications/Splunk/etc/apps and restarting to ensure it was integrated, I logged into Splunk Enterprise and opened the Search & Reporting app. This is the hub for querying data with SPL, where you can filter logs, run stats, and build charts. For me, it became the starting point for exploring the BOTS v3 dataset and creating dashboards.


 
