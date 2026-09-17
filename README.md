# 🔎 FOOTPRINTING & NETWORK SCANNING REPORT

> Cybersecurity Internship – Networkwalks Week 2 Practical Project

| Field | Details |
| :--- | :--- |
| **Pentester Name (Cybersecurity Professional)** | **Parthasaradhi Reddy** |
| **Program/Batch** | `B083-Networkwalks` |
| **Date** | 16 September 2026 |
| **Modules completed** | • `W2-PM1` (Multiple Kali Tools)<br>• `W2-PM5` (Zenmap Scanning) <br>• `W2-PM-Final` (Report Writing) |
| **Client/Target** | 1. Networkwalks (*secured written permission already*)<br>2. My own local LAN Network |
| **Permission secured from client?** | **Yes** |
| **Phases covered** | • **Phase 1:** Reconnaissance & Footprinting<br>• **Phase 2:** Scanning & Network Discovery<br>• **Phase 3-5:** In Progress |


---

## Liability Disclaimer

I have performed these activities only on the systems & devices where I had secured written permission or the devices/systems that I own myself. All these materials are for education and research purpose only. Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most countries unauthorised access is a crime even when nothing is damaged.

---

## 📌 Project Overview

As part of my week2 cybersecurity internship with Networkwalks, I completed practical exercises covering:

1. **Footprinting & Reconnaissance**
2. **Network Discovery & Scanning**

The first activity focused on passive and active reconnaissance of the authorized
`networkwalks.com` domain using multiple Kali Linux tools.

The second activity focused on network discovery and scanning using **Zenmap**
against my own local LAN environment.

These exercises helped me understand how security professionals gather information
about a target and identify hosts, services, and potential attack surfaces during
the initial phases of a security assessment.

---

# 🎯 Objectives

The main objectives of this project were:

- Understand the footprinting and reconnaissance phase of penetration testing.
- Gather publicly available information about an authorized target.
- Understand how different reconnaissance tools provide different types of information.
- Perform DNS and domain enumeration.
- Identify web technologies and security mechanisms.
- Understand HTTP responses and headers.
- Perform network discovery using Zenmap.
- Identify active hosts within my local LAN.
- Understand basic port and service scanning concepts.
- Document the methodology and observations.

---

# 🧰 Tools Used

Footprinting & Reconnaissance

| Tool     | Purpose                                       |
| -------- | --------------------------------------------- |
| WHOIS    | Domain registration and ownership information |
| WhatWeb  | Web technology identification                 |
| Nslookup | DNS queries and record lookup                 |
| cURL     | HTTP/HTTPS requests and response inspection   |
| Wafw00f  | Web Application Firewall detection            |
| DNSRecon | DNS enumeration and reconnaissance            |

---

# 🧭 Activity 1 – Footprinting & Reconnaissance

```text
Target:networkwalks.com
```

The target domain was assessed using six Kali Linux reconnaissance tools. Each tool was used for a specific information-gathering purpose.

The reconnaissance activities against networkwalks.com were performed only
within the scope of the written authorization provided for this internship exercise.

## WHOIS

First, I used Whois to retrieve public available registration details of a domain, including registrar information, registration dates and authoritative name servers.

Command: whois networkwalks.com

Evidence collection:

## WhatWeb

Next, I Used WhatWeb to identify technologies used by websites, including web servers, CMS platforms, frameworks and security solutions.

Command: whatWeb networkwalks.com

Evidence collection:

## Nslookup

Next, I Used Nslookup to perform DNS queries against the target domain.

Command: nslookup networkwalks.com

Evidence collection:

## CURL
Next, I used to send HTTP/HTTPS requests and inspect the web server response. Used Curl with the -I option to inspect the HTTP response headers. This provided additional information about the web application and exposed the WordPress REST API endpoint /wp-json/.

Command: curl -I https://networkwalks.com

Evidence collection:

## Wafw00f

Next, I Used Wafw00f to determine whether a Web Application Firewall was protecting the website. The result identified ModSecurity (SpiderLabs).

Command: wafw00f networkwalks.com

Evidence Collection: 

## DNSRecon

Finally, I used DNSRecon to enumerate DNS records. The results provided information relating to name servers, mail servers, SPF/TXT records, service records and DNS software information.

Command: dnsrecon -d networkwalks.com

---

# 🖥️ Activity 2 – Network Scanning with Zenmap

```text
Target: My own local LAN network
```

For the second activity, I used Zenmap to perform network discovery on my local network. The practical required me to identify my local IP address and subnet, discover live hosts, identify their IP and MAC addresses, and generate a network topology.

I first used the Windows ipconfig command to identify my local IP address and LAN subnet. I then entered the subnet into Zenmap and selected Quick Scan to identify active hosts.

The example results provided in the practical identified four live hosts:
10.x.x.x
10.x.x.x

The example results also included four MAC addresses.

After completing the scan, I opened the Topology section in Zenmap, enabled the legend and saved the network topology in PDF format as required by the practical task.

Evidence Collection:

---

# ⚠️ Risk Analysis / Impact & Recommendations

| Activity / Information | Potential Risk | Potential Impact | Risk Level | Recommendation |
|------------------------|----------------|------------------|------------|----------------|
| WHOIS Information | Domain registration and infrastructure information may be publicly visible. | May assist attackers in understanding domain ownership and infrastructure. | Low | Minimize unnecessary publicly exposed registration and administrative information. |
| DNS Enumeration | DNS records may reveal hosts, mail servers, and other infrastructure details. | Can assist in external attack-surface mapping. | Medium | Remove unnecessary DNS records and regularly review publicly exposed DNS information. |
| WhatWeb Technology Detection | Web technologies and server components may be identifiable. | May help attackers identify technologies and research associated vulnerabilities. | Medium | Keep web technologies patched and avoid unnecessary technology/version disclosure. |
| HTTP Header Analysis | HTTP responses may disclose server information or missing security headers. | Weak configurations may increase exposure to certain web attacks. | Medium | Review and implement appropriate HTTP security headers and minimize unnecessary information disclosure. |
| WAF Detection | WAF presence may be identifiable. | May provide information about the organization's defensive architecture. | Low | Keep WAF rules updated and properly configure based on application requirements. |
| DNSRecon Enumeration | Additional DNS information may reveal infrastructure details. | Can assist attackers in identifying externally exposed services. | Medium | Regularly audit DNS records and remove obsolete or unnecessary entries. |
| Host Discovery | Active hosts on the local network can be identified. | Provides visibility into the available network attack surface. | Medium | Maintain an updated asset inventory and restrict unauthorized network access. |
| Open Port Identification | Open ports may expose network services. | Vulnerable or misconfigured services may become potential attack vectors. | Medium | Close unnecessary ports and restrict required services using firewall rules. |
| Service Identification | Running services and versions may be identifiable. | May help attackers target outdated or vulnerable services. | Medium | Keep services updated and disable unnecessary services. |
| Combined Reconnaissance | Multiple data points can be correlated to map the attack surface. | Provides a more detailed view of the target environment. | Medium | Perform regular attack-surface reviews and minimize unnecessary external exposure. |

> **Important:** The risk levels above represent potential security
> impact of the information exposed or identified during reconnaissance.
> They do not indicate that an exploitable vulnerability was confirmed.
> No exploitation or vulnerability validation was performed as part of these two modules.
Therefore, the presence of information such as a software version, IP address or DNS record does not by itself mean that the system is vulnerable. Further authorized security testing would be required to confirm any actual vulnerability.

---

# Conclusion

Through this activity, I learned how reconnaissance and scanning fit into the early stages of a security assessment.

By using multiple reconnaissance tools and Zenmap, I gained hands-on
experience in collecting target information, performing DNS and web
reconnaissance, discovering hosts, identifying open ports and
understanding the importance of scope and authorization in security
testing.

---

# 👨‍💻 Author

Nusi Parthasaradhi Reddy

Cybersecurity Trainee | LinkedIn: 
