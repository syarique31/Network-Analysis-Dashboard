# Network-Analysis-Dashboard
When I first set out to get hands-on experience with Splunk, I didn’t quite know what I was getting myself into. As a cybersecurity intern, I’ve always been curious about the tools that SOC analysts rely on day to day, and Splunk consistently came up in conversations. Around that time, I was even considering another internship opportunity that focused almost entirely on Splunk. That made me even more curious about what made this platform such a big deal in the security world. Everyone described it as a “must-know” tool for analyzing logs, monitoring network traffic, and spotting anomalies that could indicate malicious activity. To me, that sounded like the perfect opportunity to learn how professionals actually dig into data to detect threats across systems, networks, and servers.



<img width="1918" height="971" alt="Screenshot 2025-09-09 at 10 53 32 PM" src="https://github.com/user-attachments/assets/55efaaf6-ab22-4f4c-bdf2-d057550e61a6" />





But opening Splunk for the first time was… overwhelming. The interface was full of dashboards, search bars, and menus I didn’t understand. I remember staring at the home screen and thinking, “Okay soo, now what?” That’s when I turned to YouTube. I found an introductory walkthrough that explained Splunk in a way that finally clicked: Splunk Enterprise is essentially the brain of the operation and central hub where all your data gets indexed, stored, and made searchable. Everything else revolves around feeding that brain with fresh data so it can be analyzed.

The process of setting up Splunk Enterprise wasn’t difficult; everything was provided through the GUI, without me having to touch the terminal (which I initially assumed would be the same experience with the Universal Forwarder). Once installed, I created my own admin account and password, and had Splunk Enterprise fully up and running. To get more familiar, I watched another YouTube walkthrough that explained the core features, such as building security dashboards, learning about indexes, and filtering different elements like IP addresses, source and destination MAC addresses, and even geolocation data. After exploring these features, I started wondering if I could import external datasets, such as those from Kaggle, to experiment with creating dashboards and applications.


<img width="1916" height="970" alt="Screenshot 2025-09-12 at 2 17 38 PM" src="https://github.com/user-attachments/assets/bc87501c-2899-4bda-8127-ffce4f1dd451" />



That curiosity led me to the free BOTS v3 dataset, which provides public AWS-sourced data with multiple sourcetypes. I downloaded it and tried importing it directly into Splunk, but quickly realized it wasn’t that simple. Splunk Enterprise acts as the central hub for indexing and analyzing data, but to get data into it, you usually need an agent that retrieves and forwards logs to the hub. That’s where the Universal Forwarder comes in — a lightweight agent that collects and transmits data to Splunk Enterprise.



<img width="1919" height="972" alt="Screenshot 2025-09-12 at 2 18 17 PM" src="https://github.com/user-attachments/assets/5e68d364-a0fd-48b9-9152-7bec4a0752e2" />





This part was a bit more challenging, since it required configuring ports and making sure they were available. Fortunately, the Universal Forwarder defaults to port 9997, which was free on my system. In Splunk Enterprise, I configured a new receiving port on 9997, set its status to enabled, and successfully established the connection. With that setup, the Universal Forwarder began transmitting data to Enterprise, completing the pipeline for collection and analysis.


 
