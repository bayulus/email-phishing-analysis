# Investigating Phishing Email Analysis

<img src="https://github.com/bayulus/azure-honeynet-livetraffic/blob/main/Blue%20Minimalist%20Profesional%20Personal%20Linkedln%20Banner.png?raw=true" >

<p>Welcome to my Phishing Email Analysis Project! In this repository, I take a deep dive into the analysis of a suspicious phishing email to unravel its intricacies and pinpoint potential threats. Phishing attacks persist as significant cybersecurity threats, making it crucial for me to understand the tactics employed by malicious actors. My primary goal with this project is to meticulously document the various components of the phishing email, ranging from its header information to the content and any associated indicators of compromise (IOCs). By sharing my analysis, I aim to contribute to the collective knowledge, empowering users and organizations to recognize and effectively mitigate phishing threats. <b>Feel free to explore, contribute, or use the insights gained here to enhance your cybersecurity knowledge</b>.</p>

<h2>Steps Taken: Investigating a Suspicious Email</h2>
<p>A user reported receiving a suspicious email that raised concerns about a potential phishing attempt. This case study documents the step-by-step analysis of the email to uncover its details and identify indicators of compromise (IOCs). Various tools were employed to dissect the email and assess potential threats.</p>

  - Extracted and analyzed the email header to understand its origin.
  - To further dissect and decode data, I leverage the capabilities of CyberChef. This powerful tool aids in the analysis and interpretation of encoded content, making it easier to uncover hidden information or malicious intent within the email.
  - I use MxLookup to verify Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM). This step ensures the authenticity of the sender and guards against phishing attempts by confirming that the email originates from an authorized source.
  - Looking at the email's subject, when it was sent, and where it came from helps me figure out who it's meant for, what it's about, whether it might be harmful, when it happened, and where it originated for further checking.
  - Cross-verified the originating IP address on AbuseIPDB to scrutinize any reported incidents or suspicious activities associated with it.
If the IP address has not been reported and exhibits malicious behavior, a detailed report is submitted to AbuseIPDB to contribute to the community's collective awareness and aid in the prevention of potential cyber threats.
- Examining the email's subject, timestamp, and sender details, including the return-path or reply-to in the header, allows me to deduce its intended recipient, purpose, potential harm, time of occurrence, and origin for further verification.
- Conducting a reverse DNS lookup on the originating IP address, we utilize whois.domaintools.com to identify the resolved host. This step helps in associating the IP with a specific domain, providing valuable information for tracing the email's origin.
- To visualize the content of webpages linked within the email, I used URL2PNG. This allows us to preview potentially harmful websites without directly accessing them, enhancing safety measures during the investigation.
