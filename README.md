<h1>Phishing Email Forensics: Investigation And Analysis</h1>

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
<h4>Key Findings:</h4>
<b>1. Suspicious Sender Details:</b><br/>
- The email is not from the official Google domain.<br/>
- The "To" field is missing, indicating a potential mass phishing campaign.<br/>
- SPF, DKIM, and DMARC checks fail, showing the email is likely spoofed.<br/>
<b>2. Phishing Tactics:</b><br/>
- The phishing link uses Google Storage APIs to exploit trust in Google services.<br/>
- The URL uses redirection through 7 domains to obscure the final malicious site.<br/>
- The IP address associated with the email is blacklisted for malicious activity.<br/>
<b>3. Malicious Website Activity:</b><br/>
- The phishing URL contacted 6 IPs across 3 countries, showing distributed operations and redirect chain<br/>
- 31 HTTP transactions were made, indicating active communication and potential data gathering.<br/>
- Google Safe Browsing flagged the site as malicious.<br/>
<b>4. Landing Page Analysis:</b><br/>
- The landing page uses fear-inducing language to prompt quick action.<br/>
- A large "ACTIVATE" button encourages users to install malware or submit personal information decietfully.<br/>
<br/>
<h4>Recommendations:</h4>
1. Block the Sender: Prevent emails from the spoofed domain and similar unauthorized senders.<br/>
2. User Education: Inform users about the risks of clicking on suspicious links, especially those involving urgent or fear-inducing language.<br/>
3. IP Blacklisting: Update security systems to block the IP addresses associated with this phishing campaign.<br/>
4. Ongoing Monitoring: Continuously monitor for similar phishing tactics using trusted domains like Google APIs.<br/>
5. Report the Phishing Site: Report the malicious site to Google and relevant security teams to aid in takedown efforts.<br/>
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
Authentic Google Email Reference<br/>
<img src="https://i.imgur.com/WvPeCDH.png" height="80%" width="80%" alt="Real"/>
<br />
<br />
<b>Phishing Email</b> <br/>
-Sender details is not the official Google email/domain.<br />
-Sender Recipient "To" field is missing, possibly indicating bulk emailing or mass Phishing campaign.<br />
-SPF does not match google mail server.<br />
-DKIM is signed by yandex.ru, a Russian email domain not Google.<br />
-Email assumes use of a mobile device, whilst im on a laptop.
<img src="https://i.imgur.com/IDZ9KEm.png" height="80%" width="80%" alt="PhishinEmail"/>
<br />
<br />
<b>Hovering over embedded link:</b>  <br/>
-The phishing link uses Google Storage APIs which is designed to exploit the trust and legitimacy associated with Google services<br />
<img src="https://i.imgur.com/L4j0HAz.pngg" height="80%" width="80%" alt="link"/>
<br />
<br />
<b>Accessing email headers:</b> <br/>
<img src="https://i.imgur.com/DrSuoe4.png" height="80%" width="80%" alt="Headers"/>
<br />
<br />
<b>Analysing headers through MXtoolbox:</b> <br/>
-DMARC Non-Compliance: The email fails to comply with DMARC (Domain-based Message Authentication, Reporting, and Conformance), indicating it was likely not sent from an authorized source for the domain it claims to represent.<br/>
-SPF Misalignment: The email's SPF (Sender Policy Framework) record does not align, meaning the sending IP address is not authorized to send emails on behalf of the claimed domain.<br/>
-DKIM Authentication Failure: The email lacks DKIM (DomainKeys Identified Mail) authentication, suggesting the message was not properly signed by the domain, further pointing to possible spoofing or forgery.<br/>
<img src="https://i.imgur.com/4QjZx5F.png" height="80%" width="80%" alt="mx1"/>
<br />
<br />
<b>IP address is blacklisted:</b>  <br/>
-The IP address has been flagged for sending spam, phishing, or other malicious emails, and is listed on one or more public email blacklists<br />
<img src="https://i.imgur.com/q1NDIve.png" height="80%" width="80%" alt="mx2"/>
<br />
<br />
<b>IP Geo-Locator:</b>  <br/>
-Further investigation of the IP address from the email on IP geo-locator shows country of origin<br />
<img src="https://i.imgur.com/0yFnD2C.png" height="80%" width="80%" alt="ip"/>
<br />
<br />
<b>Safely accessing embedded link through Browserling sandbox:</b>  <br/>
-The phishing site is blocking access from certain IP addresses, including those used by Browserling, to avoid detection and analysis.<br />
<img src="https://i.imgur.com/eS8nGLm.png" height="80%" width="80%" alt="browser"/>
<br />
<br />
<b>Analyzing phishing URL through URLscan.io: </b>  <br/>
-The phishing URL contacted 6 IP addresses across 3 countries and 7 domains, indicating an effort to distribute its operations across multiple servers, potentially to evade detection and enhance resilience against takedowns.<br/>
-The website performed 31 HTTP transactions, suggesting it is actively communicating with various resources, possibly to load malicious content, track user interactions, or gather data.<br/>
-Google Safe Browsing flagged the site as malicious, confirming that reputable security services have identified the URL as a threat, reinforcing the need to avoid interaction.<br/>
<img src="https://i.imgur.com/EJsBw42.pngg" height="80%" width="80%" alt="url1"/>
<br />
<br />
<b>Viewing redirect chain from the initial embedded link on URLscan.io:</b>  <br/>
-The different landing page observed on URLScan.io, along with the redirection through 7 domains, indicates that the phishing campaign is using a redirection chain to obfuscate its final destination. This tactic enhances the attacker's ability to deceive users and security systems, increasing the chances of a successful phishing attempt
<img src="https://i.imgur.com/r0NG69g.png" height="80%" width="80%" alt="url2"/>
<br />
<br />
<b>Screenshot taken from URLscan.io of the embedded links final landing page:</b> <br/>
-The screenshot taken of the final landing page uses fear-inducing language to create a sense of urgency to take immediate action with a large green "ACTIVATE" button to prompt the user to act quickly, where the attacker will direct victim to install malware or submit personal information.<br/>
<img src="https://i.imgur.com/iabQIq4.png" height="80%" width="80%" alt="url3"/>
<br />
<br />
