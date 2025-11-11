# Network-Analysis-Dashboard
When I first set out to get hands on with Splunk, I had no idea what to expect. As a cybersecurity intern, I kept hearing how critical it is for SOC analysts, and I even came across another internship centered almost entirely on Splunk. That made me curious about why it is seen as a must-know tool for analyzing logs, monitoring traffic, and spotting anomalies. I wanted to see for myself how professionals use it to uncover threats across systems and networks. 



<img width="1918" height="971" alt="Screenshot 2025-09-09 at 10 53 32 PM" src="https://github.com/user-attachments/assets/55efaaf6-ab22-4f4c-bdf2-d057550e61a6" /> <br><br>





Opening Splunk for the first time was overwhelming, with dashboards, search bars, and menus I didn’t understand. I remember staring at the home screen thinking, “Okay, now what?” A YouTube walkthrough finally made it clear: Splunk Enterprise is the brain of the operation, the central hub where data is indexed, stored, and made searchable, while everything else depends on feeding it fresh data to analyze.

Setting up Splunk Enterprise was simple with the GUI; no terminal was needed. After creating my admin account, I watched a YouTube walkthrough to learn the basics like building dashboards, working with indexes, and filtering by IPs, MAC addresses, and geolocation. Once I got comfortable, I started wondering if I could bring in external datasets, such as those from Kaggle, to experiment with creating dashboards and applications. <br><br>


<img width="1916" height="970" alt="Screenshot 2025-09-12 at 2 17 38 PM" src="https://github.com/user-attachments/assets/bc87501c-2899-4bda-8127-ffce4f1dd451" /> <br><br>


 
That curiosity led me to the free BOTS v3 dataset, which contains public AWS-sourced data with multiple source types. After inserting it into Splunk, I began to see how powerful the platform really was. Thousands of logs appeared showing real network traffic and system activity; it felt like being in a real SOC. Splunk instantly organized everything, letting me search and spot patterns using simple SPL queries. <br><br>



<img width="970" height="966" alt="Screenshot 2025-09-12 at 2 23 18 PM" src="https://github.com/user-attachments/assets/6aaef024-c7fd-4da7-b29d-4170db2ea600" /> <br><br>




From a video I watched about Splunk basics, I learned that an index tells Splunk where to search. Since my dataset was called botsv3, I tried index=botsv3, but nothing happened. I later found on a Splunk guide that adding earliest=0 includes the first available events. Together, index=botsv3 earliest=0 searches all events in the dataset from the very beginning. <br><br>


 <img width="1918" height="967" alt="Screenshot 2025-11-10 at 9 19 19 PM" src="https://github.com/user-attachments/assets/f2607a5f-7e73-4097-b485-509f67fd0afe" /> <br><br>



After successfully loading and exploring the BOTS v3 dataset, I wanted to take it a step further and build a Security Analysis Dashboard that looked like a real SOC view. My goal was to visualize security events, identify alert types, and see which hosts were the most active on the network. <br><br>



I created a new dashboard inside Splunk Enterprise called Security Dashboard. The first panel I built showed the total number of security alerts. It was rewarding to see a live counter that pulled data directly from the dataset, confirming everything was connected properly. <br><br>



Next, I added an Event Severity Breakdown pie chart to categorize alerts by severity level, such as critical, medium, or unknown. Most logs were labeled as unknown, but it helped me understand how severity tagging works and why it is important for prioritizing incidents. <br><br>
 



To make it more useful, I built two bar charts. One showed the Top 10 Alert Sources, and the other highlighted the Top Alerting Hosts. These panels made the dashboard more interactive. I could instantly see which devices triggered the most blocked or denied events, showing where most network noise came from. <br><br>


I also added an Alert Type Distribution panel to separate alerts into categories like Blocked, Denied, and Alert. This used a simple SPL command with conditions that grouped the event types. It felt similar to how SOC analysts filter data to focus on what really matters. <br><br>



By the end, my dashboard showed a full overview of the dataset with total alerts, severity breakdowns, top sources, and alert types. Each visualization helped me understand how raw log data can be turned into security insights. <br><br>

<img width="1723" height="968" alt="Screenshot 2025-11-10 at 9 20 23 PM" src="https://github.com/user-attachments/assets/96490241-2e69-4ae9-a78a-8ec5ffc296c0" /> <br><br> 



Building this taught me how Splunk can transform large amounts of data into clear, actionable information. What started as curiosity became a hands-on project that helped me think like a security analyst. <br><br>






