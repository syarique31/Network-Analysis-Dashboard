# Network-Analysis-Dashboard
When I first set out to get hands-on experience with Splunk, I wasn’t sure what to expect. As a cybersecurity intern, I often heard how essential it is for SOC analysts, and even came across another internship focused almost entirely on Splunk. That made me curious about why it’s considered a “must-know” tool for analyzing logs, monitoring traffic, and spotting anomalies — and I wanted to see firsthand how professionals use it to detect threats across systems and networks.



<img width="1918" height="971" alt="Screenshot 2025-09-09 at 10 53 32 PM" src="https://github.com/user-attachments/assets/55efaaf6-ab22-4f4c-bdf2-d057550e61a6" />





Opening Splunk for the first time was overwhelming — the interface was full of dashboards, search bars, and menus I didn’t understand. I remember staring at the home screen thinking, “Okay, now what?” A YouTube walkthrough finally made it click: Splunk Enterprise is the brain of the operation — the central hub where data is indexed, stored, and made searchable, while everything else revolves around feeding it fresh data to analyze.

Setting up Splunk Enterprise was simple with the GUI — no terminal required. After creating my admin account, I watched a YouTube walkthrough to learn the basics: building dashboards, working with indexes, and filtering by IPs, MAC addresses, and geolocation. Once I got comfortable, I began wondering if I could import external datasets, like those from Kaggle, to experiment with creating dashboards and applications.


<img width="1916" height="970" alt="Screenshot 2025-09-12 at 2 17 38 PM" src="https://github.com/user-attachments/assets/bc87501c-2899-4bda-8127-ffce4f1dd451" />



That curiosity led me to the free BOTS v3 dataset, which provides public AWS-sourced data with multiple sourcetypes. I tried importing it into Splunk but quickly realized it wasn’t that simple. Splunk Enterprise is the hub for indexing and analysis, but it needs an agent to bring in data — that’s where the Universal Forwarder comes in, a lightweight tool that collects and sends logs to Enterprise.




<img width="970" height="966" alt="Screenshot 2025-09-12 at 2 23 18 PM" src="https://github.com/user-attachments/assets/6aaef024-c7fd-4da7-b29d-4170db2ea600" />


This part was more challenging, as it meant configuring ports and ensuring they were available. Luckily, the Universal Forwarder defaults to port 9997, which was free on my system. After enabling that port in Splunk Enterprise, the forwarder connected successfully and began transmitting data, completing the pipeline for analysis.


 
