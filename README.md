# Investigating Phishing Email - Analysis

<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/phi.png?raw=true" >

<p>Welcome to my Phishing Email Analysis Project! In this repository, I take a deep dive into the analysis of a suspicious phishing email to unravel its intricacies and pinpoint potential threats. Phishing attacks persist as significant cybersecurity threats, making it crucial for me to understand the tactics employed by malicious actors. My primary goal with this project is to meticulously document the various components of the phishing email, ranging from its header information to the content and any associated indicators of compromise (IOCs). By sharing my analysis, I aim to contribute to the collective knowledge, empowering users and organizations to recognize and effectively mitigate phishing threats. <b>Feel free to explore, contribute, or use the insights gained here to enhance your cybersecurity knowledge</b>.</p>
<br>

💻 **Tools Used For This Project:** 🛠️

![Static Badge](https://img.shields.io/badge/CYBERCHEF-blue?style=flat-square)
![Static Badge](https://img.shields.io/badge/MXLOOKUP-blue?style=flat-square)
![Static Badge](https://img.shields.io/badge/VIRUSTOTAL-blue?style=flat-square)
![Static Badge](https://img.shields.io/badge/ABUSEIPDB-blue?style=flat-square)
![Static Badge](https://img.shields.io/badge/VISUAL%20STUDIO-blue?style=flat-square&logo=visualstudio)


# End-End Case Study of The Steps Taken
<p>A user reported receiving a suspicious email that raised concerns about a potential phishing attempt that poses as a communication from Adobe Support, urging the recipient to update their Adobe software.  This incident raises concerns of a potential phishing attempt targeting Adobe users. This case study documents the step-by-step analysis of the email to uncover its details and identify indicators of compromise (IOCs). Various tools were employed to dissect the email and assess potential threats.</p>

<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/lily_suspicious_report.png?raw=true" >

  - Extracted and analyzed the email header to understand its origin.
  - To further dissect and decode data, I leverage the capabilities of CyberChef. This powerful tool aids in the analysis and interpretation of encoded content, making it easier to uncover hidden information or malicious intent within the email.
  - I use MxLookup to verify Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM). This step ensures the authenticity of the sender and guards against phishing attempts by confirming that the email originates from an authorized source.
  - Looking at the email's subject, when it was sent, and where it came from helps me figure out who it's meant for, what it's about, whether it might be harmful, when it happened, and where it originated for further checking.
  - Cross-verified the originating IP address on AbuseIPDB to scrutinize any reported incidents or suspicious activities associated with it.
If the IP address has not been reported and exhibits malicious behavior, a detailed report is submitted to AbuseIPDB to contribute to the community's collective awareness and aid in the prevention of potential cyber threats.
- Examining the email's subject, timestamp, and sender details, including the return-path or reply-to in the header, allows me to deduce its intended recipient, purpose, potential harm, time of occurrence, and origin for further verification.
- Conducting a reverse DNS lookup on the originating IP address, we utilize whois.domaintools.com to identify the resolved host. This step helps in associating the IP with a specific domain, providing valuable information for tracing the email's origin.
- To visualize the content of webpages linked within the email, I used URL2PNG. This allows us to preview potentially harmful websites without directly accessing them, enhancing safety measures during the investigation.

# Analysis Details

<h2>1. Header Analysis</h2>
<p>Email headers contain crucial information about the origin and path of an email. Analyzing these headers can provide insights into the legitimacy and potential threats associated with the message. In summary, the email originated from a Google server, went through various authentication checks, and was routed through Outlook servers before reaching its final destination. The timestamps, protocols, and server details provide a detailed trace of the email's journey <b>as shown below. This information can help identify any unusual or suspicious patterns.</b></p>
<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/2.PNG?raw=true" >

<p>Examining the "From,"  and "Return-Path" fields to identify the sender of the email. Verify the legitimacy of the sender's domain and cross-reference it with known information. <b>The result  raises a red flag because important updates from Adobe are typically delivered through official channels, and the use of a public email domain(Gmail) typically indicates potential phishing</b></p>
<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/1.PNG?raw=true" >


<p>In my analysis to trace any email's origin, I first check the "X-Sender-IP" header. I extract and validate the IP address, making sure it aligns with the expected sources in  the first "Received" header from the bottom. Alternatively, I also use <b>CyberChef</b> to easily extract IPs and URLs in the received header and then cross-check.</p>
<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/3.PNG?raw=true" >

***Alternatively use CyberChef To extract all IPs present in the email header***

<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/4.PNG?raw=true">

***Using AbuseIPDB to scrutinize any reported incidents and also get more information from the originating IP Address***

<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/6.PNG?raw=true" >

<p>While it's evident that the email is not from a legitimate source due to its use of a public email address, let's consider this for demonstration purposes. To evaluate the email's legitimacy, it's crucial to assess the presence of key authentication mechanisms. Check for SPF (Sender Policy Framework), DKIM (DomainKeys Identified Mail), and DMARC (Domain-based Message Authentication, Reporting, and Conformance) records. These mechanisms play a vital role in enhancing email authentication, helping to verify the legitimacy of the email.</p>

***Using MxLookup for SPF/DKIM Check***

<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/5.PNG?raw=true" >

<h2>2. Content/Attachment/Link Analysis</h2>
<p>Phishing emails often employ social engineering techniques to deceive recipients. By scrutinizing the content, one can unveil hidden threats, malicious links, or attempts to manipulate users. Content analysis serves as a crucial step in identifying and mitigating potential risks, and safeguarding against unauthorized access, data breaches, or other security compromises.</p>

***As shown below, The email starts with a generic greeting ("Dear User") instead of addressing the user by name. Legitimate companies often personalize their communications with the recipient's name. The email creates a sense of urgency by stating that an "important update" has been released and emphasizes the need for immediate action. Phishing emails often use urgency and fear tactics to prompt quick responses. The displayed hyperlink text suggests it leads to "update.adobe.com/latest-security-updates," but the actual link points to a different domain (vmi1159541.contaboserver.net/payload.exe). This discrepancy is a red flag. The email requests users to follow a link to download an executable file ("payload.exe").***

**Using Virustotal To Check The Actual URL: This shows it's a malicious link which has also been reported many times by different security vendors**

<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/8.PNG?raw=true" >

***The email requests users to follow a link to download an executable file ("payload.exe"). By using URL2PNG.COM  I captured a visual representation of the content hosted on vmi1159541.contaboserver.net as shown below.***

<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/9.PNG?raw=true" >

<h2>3. Indicators of Compromise (IOCs) Found In This Analysis</h2>

  - **209.85.215.170**
  - **alfredegov@gmail.com**
  - **vmi1159541.contaboserver.net**
  - **Jason Conrad**

# Mitigation and Recommendations
<h2>For Users</h2>

  - Hover over hyperlinks to preview the actual URL before clicking. Ensure that the displayed link matches the expected destination.
  - Always verify the authenticity of emails, especially those urging immediate action. Contact the purported sender through official channels to confirm the legitimacy of requests
  - Refrain from opening attachments or downloading files from unknown or unexpected sources. If in doubt, contact the sender or your security team directly to confirm the legitimacy of the file.
  - Report any suspicious emails to your organization's IT or security team, helping to identify and mitigate potential threats.
  - Stay informed about common phishing tactics and attend security awareness training programs to recognize and avoid potential threats.

<h2>For Organizations</h2>

  - Conduct regular cybersecurity training for employees, emphasizing the importance of recognizing and reporting phishing attempts.
  - Implement robust email filtering systems, including advanced tools like **Proofpoint and Inky**, to automatically detect and quarantine suspicious emails before they reach users' inboxes.
  - Deploy Endpoint Detection and Response (EDR) solutions like **Crowdstrike** to monitor and respond to advanced threats on endpoints, providing real-time visibility into potential malicious activities.
  - Employ User Behavior Analytics solutions to detect anomalous behavior patterns that may indicate a security threat.
  - Utilize SIEM solutions to collect, analyze, and correlate log data from various sources, helping in the detection of security incidents and providing a centralized view of the organization's security posture.

<br>

[![Static Badge](https://img.shields.io/badge/Check%20Out%20Azure%20Sentinel%20Real%20Live%20Threat%20Detection%20Here-blue)](https://github.com/bayulus/azure-honeynet-livetraffic)





                                  








