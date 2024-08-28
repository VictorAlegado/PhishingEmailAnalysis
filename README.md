<h1>Phishing Email Investigation And Analysis</h1>

<h2>Description</h2>
In this project, I conduct a detailed analysis of a phishing email, identifying indicators of malicious activity. The email was retrieved from my personal spam inbox on Gmail, where it claimed that my system was infected with viruses. The email attempted to impersonate Google by using their logo and provided a link to supposedly remove the alleged threats.
<br />

<h2>Overview</h2>
To assess the authenticity of the email, I examined the sender details, subject line, and email body, and hovered over the embedded links to determine the address destination. Additionally, I utilized third-party tools such as MXToolbox, URLScan, and Browserling to further analyze the email's content and headers. Through this comprehensive analysis, I determined that the email was indeed a phishing attempt designed to deceive recipients into downloading a malicious payload disguised as a legitimate virus removal tool, falsely representing itself as Google.

<br />
<br />
<img src="https://i.imgur.com/5DwshVe.png" height="80%" width="80%" alt="EmailFull"/>
<br />
<h2>Key Findings and Recommendations</h2> 
<br />
<br />
<h2>Utilities Used</h2>

- <b>Gmail Client</b> 
- <b>MXtoolbox.com (Header Analyzation)</b>
- <b>URLscan.io (URL Threat analaysis tool)</b>
- <b>Browserling.com (Web browser sandbox testing tool)</b>
- <b>IPgeolocation.io</b>

<h2>Phishing Email Analysis walk-through:</h2>
<br/>
<p align="center">
<br/>
<br/>
Authentic Google Email Reference<br/>
<img src="https://i.imgur.com/WvPeCDH.png" height="80%" width="80%" alt="Real"/>
<br />
<br />
Phishing Email <br/>
-Sender details is not the official Google email/domain.<br />
-Sender Recipient "To" field is missing, possibly indicating bulk emailing or mass Phishing campaign.<br />
-SPF does not match google mail server.<br />
-DKIM is signed by yandex.ru, a Russian email domain not Google.<br />
-Email assumes use of a mobile device, whilst im on a laptop.

<img src="https://i.imgur.com/IDZ9KEm.png" height="80%" width="80%" alt="PhishinEmail"/>
<br />
<br />
Inside Honeynet Virtual Machine, Disabled Firewalls:  <br/>
<img src="https://i.imgur.com/hHjsiXE.png" height="80%" width="80%" alt="2. Windows firewall Virtual Machine"/>
<br />
<br />
