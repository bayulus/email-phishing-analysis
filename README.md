# Investigating Phishing Email Analysis

<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/phi.png?raw=true" >

<p>Welcome to my Phishing Email Analysis Project! In this repository, I take a deep dive into the analysis of a suspicious phishing email to unravel its intricacies and pinpoint potential threats. Phishing attacks persist as significant cybersecurity threats, making it crucial for me to understand the tactics employed by malicious actors. My primary goal with this project is to meticulously document the various components of the phishing email, ranging from its header information to the content and any associated indicators of compromise (IOCs). By sharing my analysis, I aim to contribute to the collective knowledge, empowering users and organizations to recognize and effectively mitigate phishing threats. <b>Feel free to explore, contribute, or use the insights gained here to enhance your cybersecurity knowledge</b>.</p>

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

<p>Examining the "From,"  and "Return-Path" fields to identify the sender of the email. Verify the legitimacy of the sender's domain and cross-reference it with known information. <b>The result  raises a red flag because important updates from Adobe are typically delivered through official channels, and the use of a Gmail address typically indicates potential phishing</b></p>
<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/1.PNG?raw=true" >


<p>In my analysis to trace any email's origin, I first check the "X-Sender-IP" header. I extract and validate the IP address, making sure it aligns with the expected sources in  the first "Received" header from the bottom. Alternatively, I also use <b>CyberChef</b> to easily extract IPs and URLs in the received header and then cross-check.</p>
<img src="https://github.com/bayulus/phishing-email-analysis/blob/main/images/3.PNG?raw=true" >





