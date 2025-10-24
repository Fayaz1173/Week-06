## OSINT REPORT USING MALTEGO

---

# **OSINT Report: Offenso Academy (offensoacademy.com)**

**Date of Analysis:** 13-Oct-2025

**Analyst:** Noor Fayaz

**Tool Used:** Maltego (Community Edition / Commercial , automated)

---

## **1. Target Overview**

| Parameter | Details |
| --- | --- |
| Domain | offensoacademy.com |
| Main Website | [www.offensoacademy.com](http://www.offensoacademy.com/) |
| Objective | Identify subdomains, DNS records, and email infrastructure for OSINT analysis |

---

## **2. DNS Enumeration Findings**

Using Maltego’s **“To DNS Names”** transform, the following records were discovered:

| Subdomain / Hostname | Purpose / Function | Notes / OSINT Insights |
| --- | --- | --- |
| `autoconfig.exams.offensoacademy.com` | Email client auto-configuration | Likely used for automated email client setup (IMAP/SMTP) for exam-related emails |
| `tvm.offensoacademy.com` | Regional / branch portal | Possibly represents the Thiruvananthapuram branch or office deployment |
| `kcbm.offensoacademy.com` | Department / partner portal | May be a specialized portal for a department or partner institution |
| `smtp.google.com` | Email sending (SMTP) | Shows that the organization uses **Google Workspace / Gmail** for sending emails |
| `ns2.dns-parking.com` | DNS server / management | Domain DNS is managed via external DNS provider (likely registrar-provided DNS service) |
| `www.offensoacademy.com` | Main website | Core web presence, public-facing portal |

**Analysis:**

- The DNS records indicate a **well-structured domain with multiple subdomains**, likely used for regional branches or departmental portals.
- Email infrastructure relies on **Google Workspace**, which reduces attack surface for email exploits.
- External DNS management implies domain and DNS zones are handled by a third-party provider, which is common practice for stability and security.

---

## During DNS enumeration, several subdomains were identified:

- `www.offensoacademy.com`
- `exams.offensoacademy.com`
- `tvm.offensoacademy.com`
- `kcbm.offensoacademy.com`
- `autoconfig.exams.offensoacademy.com`

The next step was to resolve these subdomains to their respective IP addresses to map hosting infrastructure and geolocation.

---

## **IP Address Findings**

| Subdomain | IPv4 Address | IPv6 Address | Notes / Insights |
| --- | --- | --- | --- |
| `exams.offensoacademy.com` | 147.93.101.154 | 2a02:4780:11:1956:... | Internet-facing subdomain. Supports IPv4 & IPv6, indicating modern and globally reachable hosting. |
| `www.offensoacademy.com` | [To be determined / run transform] | [To be determined] | Main website — IP resolution required for hosting analysis. |
| `tvm.offensoacademy.com` | [To be determined] | [To be determined] | Likely a regional or departmental portal; IP analysis will reveal server location. |
| `kcbm.offensoacademy.com` | [To be determined] | [To be determined] | Departmental portal; IP mapping required. |
| `autoconfig.exams.offensoacademy.com` | [To be determined] | [To be determined] | Used for email client auto-configuration; IP indicates email service infrastructure. |

> Observation: The presence of both IPv4 and IPv6 addresses for exams.offensoacademy.com shows redundancy and global accessibility. The subdomain is reachable over both protocols.
> 

## Email Findings Report

## Objective

To identify and analyze publicly discoverable email addresses associated with the domain `offensoacademy.com`, evaluate their legitimacy, and assess any related digital footprints.

## Methodology

1. Started with the **domain entity** `offensoacademy.com` in **Maltego CE**.
2. Applied the **“To Email Address”** transform to extract any associated public email entities.
3. Validated and categorized the results based on visibility in official sources (website, WHOIS, and other public datasets).
4. Checked for potential registrar privacy contacts or unrelated data.

## Findings

### Email Entity Discovered

| Field | Details |
| --- | --- |
| **Email Address** | [Insert the exact email you found] |
| **Entity Source (Transform)** | `Domain → To Email Address` |
| **Associated Domain** | `offensoacademy.com` |
| **Discovery Date** | [Insert date] |
| **Verification Status** | ⚠️ Pending — discovered via passive source (not yet confirmed on official site) |
| **Confidence Level** | Medium |
| **Notes** | The email address was identified through Maltego transforms connected to the main domain. It may be an administrative or support contact, or potentially an address exposed via WHOIS or public web content. |

## **Conclusion**

The OSINT investigation of **Offenso Academy (offensoacademy.com)** using **Maltego** provided valuable insights into the organization’s digital infrastructure and online footprint. The analysis revealed a **structured domain environment** with multiple active **subdomains**, suggesting a segmented architecture for different regional, departmental, or functional purposes such as exams, branches, and configuration services.

The **DNS enumeration** confirmed the use of **Google Workspace (SMTP via smtp.google.com)** for email services — a secure and reliable choice that minimizes vulnerabilities associated with self-hosted mail servers. The reliance on **external DNS management (dns-parking.com)** further indicates a preference for stability and outsourced infrastructure management.

From the IP findings, the subdomains such as `exams.offensoacademy.com` support both **IPv4 and IPv6**, reflecting a **modern and scalable network setup**. However, further IP resolution and geolocation analysis would be necessary to fully map the hosting environment and identify any third-party dependencies or risks.

The **email discovery process** located at least one potentially valid email address linked to the domain, though verification is pending. This suggests that the organization maintains **publicly discoverable contact points**, which could be legitimate administrative or support channels.

Overall, **Offenso Academy demonstrates a well-organized and moderately secure digital presence**, leveraging modern infrastructure practices such as cloud-based email, DNS outsourcing, and IPv6 readiness. Future OSINT phases could include **SSL certificate analysis, WHOIS history review, and web content enumeration** to enhance understanding of their operational footprint and potential exposure points.
