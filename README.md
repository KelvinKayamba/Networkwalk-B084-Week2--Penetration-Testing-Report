# 🔐 Networkwalk-B084-Week2--Penetration-Testing-Report

### Footprinting & Network Scanning Phases
**W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS**

---

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="left">Details</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><b>Pentester Name</b></td>
<td align="left">Kelvin Kayamba (Cybersecurity Professional)</td>
</tr>
<tr>
<td align="left"><b>Program/Batch</b></td>
<td align="left">B084-Networkwalks</td>
</tr>
<tr>
<td align="left"><b>Date</b></td>
<td align="left">10 November 2026</td>
</tr>
<tr>
<td align="left"><b>Client/Target</b></td>
<td align="left">1. Networkwalks (secured written permission already)<br>2. My own local LAN Network</td>
</tr>
<tr>
<td align="left"><b>Permission secured from client?</b></td>
<td align="left">Yes</td>
</tr>
</tbody>
</table>


### Modules Completed

- W2-PM5: Network Scanning with Zenmap
- W2-PM4: Footprinting with theHarvester
- W2-PM3: Footprinting with Maltego
- W2-PM2: Google Hacking Database (GHDB)
- W2-PM1: Footprinting with Multiple Kali Tools

### Phases Covered

- **Phase 1:** Reconnaissance & Footprinting
- **Phase 2:** Scanning & Network Discovery
- **Phase 3-5:** In Progress

---

## 📑 Table of Contents

1. [Liability Disclaimer](#1-liability-disclaimer)
2. [Introduction](#2-introduction)
3. [Tools Used](#3-tools-used)
4. [Activities Performed](#4-activities-performed)
   - [4.1 W2-PM5 – Network Scanning with Zenmap](#41-w2-pm5--network-scanning-with-zenmap)
   - [4.2 W2-PM4 – Footprinting with theHarvester](#42-w2-pm4--footprinting--reconnaissance-with-theharvester)
   - [4.3 W2-PM3 – Footprinting with Maltego](#43-w2-pm3--footprinting--reconnaissance-with-maltego)
   - [4.4 W2-PM2 – Google Hacking Database (GHDB)](#44-w2-pm2--footprinting--reconnaissance-using-google-hacking-database-ghdb)
   - [4.5 W2-PM1 – Multiple Kali Tools](#45-w2-pm1--footprinting--reconnaissance-with-multiple-kali-tools)
5. [Risk Analysis / Impact](#5-risk-analysis--impact)
6. [Recommendations](#6-recommendations)
7. [Conclusion](#7-conclusion)
8. [Evidences Collected](#8-evidences-collected)

---

## 1. Liability Disclaimer

This report has been prepared by me, Kelvin Kayamba, as part of the NetworkWalks Cybersecurity & Ethical Hacking Programme (Batch B084). The activities documented were carried out for educational purposes and within the authorized scope of the assessment. The findings in this report are based on the results obtained during the exercises using the tools and techniques described. They reflect only what I was able to identify within the scope of the assessment and should not be considered a complete security audit or a guarantee that all vulnerabilities have been discovered. The information provided is intended for learning, documentation, and security awareness purposes. I accept no liability, to the extent permitted by applicable law, for any loss, damage, or disruption resulting from the use of or reliance on this report. Any further testing or access to the systems discussed must have separate authorization from the relevant owners. This report is intended for NetworkWalks and other authorized reviewers and should not be shared, reproduced, or used for purposes outside its intended scope without appropriate permission.

---

## 2. Introduction

This report presents the activities, findings, and observations from the Week 2 Cybersecurity & Ethical Hacking practical assessment conducted as part of the NetworkWalks training programme (Batch B084).

The assessment focused on two key areas: reconnaissance and footprinting, and network scanning and discovery. These activities involved gathering publicly available information about the designated target, identifying potential information exposures, examining domain-related details, and discovering active devices within a local network environment.

A range of cybersecurity tools and techniques was used to carry out the exercises, including Nmap, Zenmap, Maltego, theHarvester, GHDB, and other reconnaissance utilities. The practical exercises provided an opportunity to apply theoretical cybersecurity concepts, interpret technical results, and document findings in a structured manner.

The primary objective of this assessment was to develop practical skills in identifying information that may be relevant to an organization's security posture, understanding network visibility, and recognizing potential areas requiring further security review.

This report documents the procedures performed, tools used, results obtained, and key observations for each project module. It also outlines the limitations of the assessment and provides recommendations based on the findings.

---

## 3. Tools Used

The table below lists each tool used in this report and its purpose.

<table>
<thead>
<tr>
<th align="left">Tool</th>
<th align="left">Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Kali Linux</td>
<td align="left">Operating system used for reconnaissance and footprinting activities.</td>
</tr>
<tr>
<td align="left">Windows</td>
<td align="left">Operating system used for Maltego and Zenmap activities.</td>
</tr>
<tr>
<td align="left">WHOIS</td>
<td align="left">Retrieve publicly available domain registration information.</td>
</tr>
<tr>
<td align="left">whatweb</td>
<td align="left">Identify website technologies, web servers and CMS platforms.</td>
</tr>
<tr>
<td align="left">nslookup</td>
<td align="left">Resolve domain names to IP addresses through DNS.</td>
</tr>
<tr>
<td align="left">curl -I</td>
<td align="left">Retrieve and examine HTTP response headers.</td>
</tr>
<tr>
<td align="left">wafw00f</td>
<td align="left">Identify Web Application Firewall technologies.</td>
</tr>
<tr>
<td align="left">dnsrecon</td>
<td align="left">Enumerate DNS records and identify DNS infrastructure information.</td>
</tr>
<tr>
<td align="left">Google Search</td>
<td align="left">Search for publicly indexed information using specialized search queries.</td>
</tr>
<tr>
<td align="left">Google Hacking Database (GHDB)</td>
<td align="left">Identify search operators and queries used to discover publicly indexed resources.</td>
</tr>
<tr>
<td align="left">Maltego CE</td>
<td align="left">Perform OSINT investigations and visualize relationships between domain and email entities.</td>
</tr>
<tr>
<td align="left">theHarvester</td>
<td align="left">Collect publicly available email addresses, subdomains and host information.</td>
</tr>
<tr>
<td align="left">Zenmap (Nmap GUI)</td>
<td align="left">Perform network discovery and identify active hosts on a local subnet.</td>
</tr>
<tr>
<td align="left">Windows CMD</td>
<td align="left">Identify local IP configuration, subnet masks and MAC addresses.</td>
</tr>
</tbody>
</table>


---

## 4. Activities Performed

### 4.1 W2-PM5 – Network Scanning with Zenmap

> **Project Objective:** Identify active devices on my local network, retrieve their IP and MAC addresses, and generate a network topology diagram.

I used Zenmap, the graphical interface for Nmap, to perform network discovery on my local LAN.

First, I opened Windows Command Prompt and executed the `ipconfig` command to identify my computer's local IP address, subnet mask and default gateway.

The network configuration identified the following:

<table>
<thead>
<tr>
<th align="left">Network Information</th>
<th align="left">Result</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Local IP address</td>
<td align="left">172.20.10.2</td>
</tr>
<tr>
<td align="left">Subnet mask</td>
<td align="left">255.255.255.240</td>
</tr>
<tr>
<td align="left">Default gateway</td>
<td align="left">172.20.10.1</td>
</tr>
<tr>
<td align="left">LAN subnet</td>
<td align="left">172.20.10.0/24</td>
</tr>
</tbody>
</table>


I then opened Zenmap, entered the network subnet as the scan target and selected the **Ping Scan** profile to identify active devices.

The scan identified **three live hosts** on the network.

**Discovered IP Addresses:**

1. `172.20.10.1`
2. `172.20.10.2`
3. `172.20.10.13`

The scan results also provided MAC address information for discovered devices.

<table>
<thead>
<tr>
<th align="left">IP Address</th>
<th align="left">MAC Address</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">172.20.10.1</td>
<td align="left">76:9E:AF:81:6A:64</td>
</tr>
<tr>
<td align="left">72.20.10.13</td>
<td align="left">D0:31:69:F8:6B:8E</td>
</tr>
<tr>
<td align="left">172.20.10.2</td>
<td align="left">Local computer; MAC address not displayed in the scan screenshot</td>
</tr>
</tbody>
</table>


After completing the scan, I accessed the Topology feature in Zenmap, enabled the legend and generated a network topology visualization. I saved the topology output in PDF format.

#### ✅ Results and Achievements

- Successfully identified my local IP address and LAN configuration.
- Discovered three active hosts on my local network.
- Identified the IP addresses of the discovered devices.
- Retrieved MAC address information for two discovered hosts.
- Generated and saved a network topology diagram in PDF format.
- Gained practical experience in network discovery, host identification and network visualization.

---

### 4.2 W2-PM4 – Footprinting & Reconnaissance with theHarvester

> **Project Objective:** Identify publicly available email addresses, subdomains and host information associated with Microsoft using theHarvester in Kali Linux.

I used theHarvester, an OSINT reconnaissance tool available in Kali Linux, to collect publicly available information associated with `microsoft.com`.

I first opened the tool and reviewed its usage instructions and supported data sources.

#### Task 1: Reconnaissance Using Baidu

I executed the following command:

```bash
theHarvester -d microsoft.com -l 1000 -b baidu
```

This command specified Microsoft as the target domain, set the results limit to 1,000 and selected Baidu as the information source.

I examined the returned information, including email addresses and discovered hosts.

#### Task 2: Reconnaissance Using All Sources

I opened another terminal window and executed:

```bash
theHarvester -d microsoft.com -l 50 -b all
```

This command targeted the same domain, set the results limit to 50 and instructed the tool to use all supported data sources.

I examined the results and documented the information returned by the tool.

#### ✅ Results and Achievements

- Successfully executed two theHarvester reconnaissance exercises.
- Used Baidu as an individual search source.
- Performed a second search using all supported sources.
- Practiced identifying publicly available email addresses and subdomains.
- Gained experience comparing reconnaissance results from different information sources.
- Learned how publicly exposed email addresses and subdomains can contribute to an organization's digital attack surface.

---

### 4.3 W2-PM3 – Footprinting & Reconnaissance with Maltego

> **Project Objective:** Install and configure Maltego Community Edition and perform domain-to-email reconnaissance on `networkwalks.com`.

I downloaded Maltego from its official website and installed the application on my Windows computer.

After installation, I launched Maltego and completed the initial configuration process.

I registered for a free Maltego Community Edition account, obtained my Maltego ID and completed authentication through the browser. The authentication process redirected me to the desktop application.

I completed the remaining setup using the default configuration settings and selected **Normal Privacy Mode**.

#### Email Harvesting on networkwalks.com

After configuring Maltego, I opened the graph workspace and searched the entity palette for a **Domain** entity.

I dragged the Domain entity onto the graph canvas and changed its value to:

```
networkwalks.com
```

I then right-clicked the domain entity, searched the available transforms for email-related options and executed the relevant transforms.

Maltego queried its available data sources and returned associated email addresses as linked entities on the graph.

#### ✅ Results and Achievements

- Successfully installed and configured Maltego Community Edition.
- Created a Maltego account and completed application authentication.
- Established a working OSINT and link-analysis environment.
- Created a domain entity for networkwalks.com.
- Executed email-related transforms against the domain.
- Retrieved associated email information returned by the available data sources.
- Visualized the relationship between the domain and discovered email entities.
- Gained practical experience with Maltego's entity, transform and graph-analysis workflow.

---

### 4.4 W2-PM2 – Footprinting & Reconnaissance Using Google Hacking Database (GHDB)

> **Project Objective:** Use Google Hacking Database search queries to identify publicly indexed camera interfaces and open directories containing downloadable mathematics PDF documents.

I used Exploit-DB's Google Hacking Database to explore specialized Google search queries, commonly known as Google dorks.

The exercise involved two activities.

#### Task 1: Identifying Publicly Indexed Security Camera Interfaces

I accessed the Google Hacking Database section of Exploit-DB and searched for camera-related queries using the keyword `cam`.

I selected relevant search queries and executed them individually through Google Search.

I reviewed the resulting search listings and checked the returned pages to determine whether they contained accessible camera interfaces.

I repeated the process using different camera-related search queries, including those associated with:

- webcamXP
- NoVus
- Device (IP CAMERA)
- Index of /cam/
- Generic IP camera login pages
- Multi.html webcam pages
- Cambium top.cgi
- ContaCam
- HD IP Camera

I documented the relevant search queries and corresponding publicly indexed results.

#### Task 2: Identifying Open Directories Containing Mathematics PDFs

For the second activity, I used the following Google dork:

```
intitle:index.of "parent directory" mathematics pdf
```

I examined the search results and reviewed directory listings to identify pages containing downloadable mathematics eBooks in PDF format.

I documented the relevant directory links and the search query used to identify them.

#### ✅ Results and Achievements

- Successfully used Exploit-DB's Google Hacking Database to identify relevant search queries.
- Identified and documented 10 publicly indexed camera interfaces or endpoints.
- Identified and documented 10 open-directory listings containing downloadable mathematics PDF resources.
- Practised using specialized Google search operators to identify publicly indexed information.
- Gained practical understanding of how search engines can expose information that organizations may not intend to make publicly discoverable.
- Learned how exposed camera interfaces and open directory listings can increase an organization's information exposure and potential attack surface.

> ⚠️ No camera credentials are reproduced in this report.

---

### 4.5 W2-PM1 – Footprinting & Reconnaissance with Multiple Kali Tools

> **Project Objective:** Perform domain footprinting and reconnaissance against `networkwalks.com` using six Kali Linux tools.

I used six different Kali Linux tools to gather publicly available information about the target domain. Each tool was used to identify a different aspect of the domain's registration, hosting infrastructure, website technologies and DNS configuration.

#### Task 1: WHOIS – Domain Registration Information

```bash
whois networkwalks.com
```

The command retrieved publicly available domain registration information, including registrar details, registration information and name server records.

The results provided information about the domain's registration and hosting infrastructure.

#### Task 2: WhatWeb – Website Technology Fingerprinting

```bash
whatweb networkwalks.com
```

WhatWeb was used to identify the technologies running on the website.

The results identified **WordPress 7.0.4** and **WP Download Manager 3.3.58**, alongside other website technology information.

#### Task 3: NSLookup – DNS Resolution

```bash
nslookup networkwalks.com
```

This command resolved the domain name to its associated IP address.

The result identified: `192.232.216.135`

#### Task 4: cURL – HTTP Response Headers

```bash
curl -I https://networkwalks.com
```

This command retrieved the website's HTTP response headers.

I examined the returned information, including server details, HTTP response information and references to the WordPress REST API endpoint: `/wp-json/`

#### Task 5: WAFW00F – Web Application Firewall Detection

```bash
wafw00f networkwalks.com
```

The tool was used to determine whether a Web Application Firewall was protecting the website.

The result identified: **ModSecurity (SpiderLabs)**

#### Task 6: DNSRecon – DNS Enumeration

```bash
dnsrecon -d networkwalks.com
```

DNSRecon was used to enumerate publicly available DNS records and identify information relating to name servers, mail servers, SPF, TXT and service records.

The results provided additional information about the domain's DNS and hosting configuration.

#### ✅ Results and Achievements

- Successfully used six Kali Linux tools for domain footprinting.
- Retrieved publicly available domain registration information using WHOIS.
- Identified website technologies using WhatWeb.
- Resolved the target domain to its IP address using NSLookup.
- Retrieved HTTP response headers using cURL.
- Identified ModSecurity (SpiderLabs) using WAFW00F.
- Enumerated DNS records using DNSRecon.
- Gained practical experience combining multiple reconnaissance tools to develop a broader profile of a website's digital infrastructure.

---

## 5. Risk Analysis / Impact

The following table summarizes potential security risks associated with the information identified during the five practical exercises.

> These observations represent potential exposure and security considerations. They are **not** confirmed vulnerabilities unless independently validated through authorized testing.

<table>
<thead>
<tr>
<th align="center">#</th>
<th align="left">Risk / Finding</th>
<th align="left">Evidence / Observation</th>
<th align="left">Potential Impact</th>
<th align="center">Risk Level</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center">1</td>
<td align="left">Website technology information exposed</td>
<td align="left">WhatWeb identified WordPress and WP Download Manager.</td>
<td align="left">Technology and version information may help attackers identify software requiring security review.</td>
<td align="center">🟡 Medium</td>
</tr>
<tr>
<td align="center">2</td>
<td align="left">Server IP address identifiable</td>
<td align="left">NSLookup resolved networkwalks.com to 192.232.216.135.</td>
<td align="left">Provides information that may assist further infrastructure reconnaissance.</td>
<td align="center">🟢 Low</td>
</tr>
<tr>
<td align="center">3</td>
<td align="left">HTTP technical information exposed</td>
<td align="left">cURL retrieved HTTP headers and identified a WordPress REST API reference.</td>
<td align="left">May assist technology fingerprinting and further enumeration.</td>
<td align="center">🟢 Low</td>
</tr>
<tr>
<td align="center">4</td>
<td align="left">WAF technology identifiable</td>
<td align="left">Wafw00f identified ModSecurity (SpiderLabs).</td>
<td align="left">Reveals information about the website's security architecture.</td>
<td align="center">🟢 Low</td>
</tr>
<tr>
<td align="center">5</td>
<td align="left">DNS infrastructure information exposed</td>
<td align="left">DNSRecon identified DNS, mail and service-related records.</td>
<td align="left">May help attackers understand the organization's hosting and email infrastructure.</td>
<td align="center">🟡 Medium</td>
</tr>
<tr>
<td align="center">6</td>
<td align="left">Publicly exposed email information</td>
<td align="left">Maltego and theHarvester demonstrated the collection of email-related information from public sources.</td>
<td align="left">Publicly available email addresses may be used in phishing and social engineering attempts.</td>
<td align="center">🟡 Medium</td>
</tr>
<tr>
<td align="center">7</td>
<td align="left">Publicly indexed camera interfaces</td>
<td align="left">GHDB searches identified publicly indexed camera interfaces and endpoints.</td>
<td align="left">Exposed interfaces may create privacy and unauthorized-access risks.</td>
<td align="center">🔴 High</td>
</tr>
<tr>
<td align="center">8</td>
<td align="left">Open directory listings</td>
<td align="left">Identified 10 directory listings containing downloadable mathematics PDF resources.</td>
<td align="left">Open directories may expose files that an organization did not intend to make publicly accessible.</td>
<td align="center">🟡 Medium</td>
</tr>
<tr>
<td align="center">9</td>
<td align="left">Multiple live hosts on local network</td>
<td align="left">Zenmap identified three live hosts on my local LAN.</td>
<td align="left">Unknown or unauthorized devices may potentially exist on a network.</td>
<td align="center">🟡 Medium</td>
</tr>
<tr>
<td align="center">10</td>
<td align="left">Network device information identifiable</td>
<td align="left">Zenmap provided IP addresses and MAC address information for discovered hosts.</td>
<td align="left">Device information may assist network mapping and further reconnaissance.</td>
<td align="center">🟢 Low</td>
</tr>
</tbody>
</table>


### Risk Level Key

- 🟣 **Critical** – Severe security exposure requiring immediate attention.
- 🔴 **High** – Significant potential security exposure.
- 🟡 **Medium** – Security concern requiring review and appropriate controls.
- 🟢 **Low** – Limited information exposure that should be monitored.

The risk classifications above are preliminary assessments based on the observations from the practical exercises. They do not represent the results of a formal vulnerability assessment.

The exercises primarily involved reconnaissance, information gathering and network discovery. No exploitation or formal vulnerability validation was performed.

---

## 6. Recommendations

Based on the observations and practical activities completed, I recommend the following security improvements:

1. **Review Publicly Exposed Website Information**
   Organizations should regularly review publicly accessible information about their web technologies, CMS platforms, plugins and hosting infrastructure.

2. **Keep Website Technologies Updated**
   WordPress, plugins, frameworks and other web technologies should be updated regularly to address known security weaknesses.

3. **Review HTTP Response Headers**
   Organizations should review HTTP response headers and avoid unnecessarily exposing technical information that could assist attackers during reconnaissance.

4. **Monitor and Review DNS Records**
   DNS records should be reviewed periodically to ensure that only required information and services are publicly exposed.

5. **Maintain Proper WAF Configuration**
   Web Application Firewalls should remain enabled, properly configured and regularly monitored to help detect and prevent malicious web requests.

6. **Monitor Publicly Exposed Email Information**
   Organizations should educate employees about phishing, social engineering and other attacks that may use publicly available email addresses.

7. **Secure Internet-Connected Cameras**
   Security cameras should use strong, unique authentication credentials, updated firmware and appropriate network access restrictions. Camera interfaces should not be publicly accessible unless there is a legitimate business requirement and adequate protection.

8. **Review Public Directory Listings**
   Organizations should regularly inspect web servers and file repositories to ensure that sensitive information and unnecessary directory listings are not publicly accessible.

9. **Perform Regular Internal Network Discovery**
   Organizations should periodically scan their own networks to identify active devices and maintain an accurate inventory of connected systems.

10. **Investigate Unknown Network Devices**
    Any unexpected devices discovered during network scanning should be investigated and verified to ensure they are authorized.

11. **Maintain Network Documentation**
    Network topology diagrams, device IP addresses and other infrastructure information should be documented and updated regularly.

12. **Conduct Authorized Security Testing**
    Reconnaissance, scanning and penetration testing should always be conducted within an approved scope and with appropriate authorization.

---

## 7. Conclusion

During Week 2 of my Cybersecurity & Ethical Hacking internship at NetworkWalks, I completed five practical project modules covering footprinting, reconnaissance, OSINT and network scanning.

The exercises provided practical experience using different cybersecurity tools and techniques to gather information about digital environments.

- **W2-PM5:** I used Zenmap to perform network discovery on my local network. I identified my local IP configuration, discovered three live hosts, retrieved available MAC address information and generated a network topology diagram.
- **W2-PM4:** I used theHarvester to perform reconnaissance against microsoft.com using Baidu and all supported data sources. This helped me understand how publicly available information can be collected from different sources to identify email addresses, subdomains and hosts.
- **W2-PM3:** I installed and configured Maltego Community Edition. I created a domain entity for networkwalks.com and executed email-related transforms to identify associated email information and visualize the relationships through a graph.
- **W2-PM2:** I used Exploit-DB's Google Hacking Database and Google search operators to identify publicly indexed camera interfaces and open directory listings containing mathematics PDF resources. This demonstrated how search engines can reveal information that may increase an organization's security exposure.
- **W2-PM1:** I used six Kali Linux tools: WHOIS, WhatWeb, NSLookup, cURL, WAFW00F and DNSRecon. These tools helped me collect information about domain registration, website technologies, IP addresses, HTTP headers, firewall protection and DNS infrastructure.

Overall, the five projects strengthened my understanding of the reconnaissance and footprinting stages of ethical hacking. I learned how different tools can be combined to gather information, identify relationships between digital assets, examine publicly exposed information and discover active network devices.

I also gained experience documenting technical findings, interpreting scan results, identifying potential security risks and developing recommendations.

One of the most important lessons from these exercises is that information gathering is a critical part of cybersecurity. Before conducting more advanced security assessments, professionals need to understand the target environment, identify exposed information and determine which areas may require further investigation.

All practical activities were undertaken for educational purposes within the stated scope of each exercise. Further penetration testing, exploitation and vulnerability validation will be covered in subsequent phases of the internship.

---

## 8. Evidences Collected

The following evidence supports the activities documented in this report.

### W2-PM5: Zenmap Network Scanning

### Screenshot 1: Network Scan
![W2-PM5 Network Scan 1](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM5%20-1.png)

### Screenshot 2: Network Scan
![W2-PM5 Network Scan 2](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM5%20-2.png)

### Screenshot 3: Network Scan
![W2-PM5 Network Scan 3](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM5%20-3.png)

### Screenshot 4: Network Topology
![W2-PM5 Network Topology](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM5%20-4.png)
---

### W2-PM4: TheHarvester 

### Screenshot 1: TheHarvester Results
![W2-PM4 TheHarvester Results 1](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM4%20-1.png)

### Screenshot 2: TheHarvester Results
![W2-PM4 TheHarvester Results 2](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM4%20-%202.png)

---

### W2-PM3: Maltego – Domain Footprinting

### Screenshot 1: Maltego Domain Analysis
![W2-PM3 Maltego Domain Analysis 1](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM3%20-%201.png)

### Screenshot 2: Maltego Graph Results
![W2-PM3 Maltego Graph Results 2](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM3%20-2.png)
---

### W2-PM2: Google Hacking Database (GHDB) 

### Screenshot 1: Google Dorking Results
![W2-PM2 Screenshot 1](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM2%20-1.png)

### Screenshot 2: Indexed Camera Interfaces
![W2-PM2 Screenshot 2](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM2%20-2.png)

### Screenshot 3: Camera Search Results
![W2-PM2 Screenshot 3](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM2%20-3.png)

### Screenshot 4: Publicly Indexed Resources
![W2-PM2 Screenshot 4](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM2%20-4.png)

### Screenshot 5: Open Directory Listings
![W2-PM2 Screenshot 5](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM2%20-5.png)

### Screenshot 6: Indexed PDF Documents
![W2-PM2 Screenshot 6](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM2%20-6.png)

### Screenshot 7: Additional Search Evidence
![W2-PM2 Screenshot 7](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM2%20-7.png)

### W2-PM1: Website Footprinting and Information Gathering

### Screenshot 1: WHOIS Domain Information
![W2-PM1 WHOIS Results](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM1%20-1.png)

### Screenshot 2: WhatWeb Technology Identification
![W2-PM1 WhatWeb Results](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM1%20-2.png)

### Screenshot 3: DNS Lookup Results
![W2-PM1 DNS Lookup](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM1%20-3.png)

### Screenshot 4: HTTP Header Analysis
![W2-PM1 HTTP Headers](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM1%20-4.png)

### Screenshot 5: Web Application Firewall Detection
![W2-PM1 WAF Detection](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM1%20-5.png)

### Screenshot 6: DNS Enumeration
![W2-PM1 DNS Enumeration](https://raw.githubusercontent.com/KelvinKayamba/Networkwalk-B084-Week2--Penetration-Testing-Report/main/W2-PM1%20-6.png)

---

## 👤 Author

**Kelvin Kayamba** – Cybersecurity Professional, Batch B084
LinkedIn: https://www.linkedin.com/in/kelvin-kayamba-792881184
