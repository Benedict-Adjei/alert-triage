# SOC Alert Triage and Phishing Investigation

## Project Overview

I worked on this project to get practical experience with the daily responsibilities of a Security Operations Center (SOC) analyst. I used TryHackMe's SOC Simulator and Splunk SIEM to investigate 5 security alerts involving suspicious emails and network connections.

The simulation included five security alerts: four phishing-related alerts and one firewall alert. My task was to review the alerts, write out indicators of compromise (IoCs), investigate the available evidence, and determine whether the alerts was either a true positive or a false positive.

During the investigation, I reviewed email information, searched email and firewall logs in Splunk, checked suspicious IP addresses using TryDetectThis, and examined firewall logs to understand whether network connections were allowed or blocked.

I also followed a phishing investigation playbook to guide my investigation and wrote an incidence report.

The main goal of this project was to improve my alert triage, log analysis, threat investigation, and incident reporting skills.

## Tools Used

- **TryHackMe SOC Simulator:** Used to review and investigate simulated security alerts.
- **Splunk Enterprise:** Used to search and analyze email and firewall logs.
- **TryDetectThis:** Used to check suspicious URLs, file hashes, and IP addresses.
- **Phishing Investigation Playbook:** Used as a guide for investigating suspicious emails.

## Investigation Environment

The SOC dashboard displayed five alerts:

- Four phishing-related alerts.
- One firewall alert involving a blocked connection.

The alerts had different severity levels, which helped me understand why SOC analysts need to prioritize investigations based on the potential risk.

![SOC Dashboard](screenshots/01-soc-dashboard.png)

## Investigation Process

### 1. Reviewing the Security Alerts

I started by reviewing the alerts displayed on the TryHackMe SOC Simulator dashboard. There were five alerts in total, including four phishing-related alerts and one firewall alert.

Before investigating, I looked at the alert descriptions, severity levels, and available information to understand what might have triggered each alert.

This helped me decide what evidence I needed to examine during the investigation.

![SOC Alert Queue](screenshots/02-alert-queue.png)

### 2. Following the Phishing Investigation Playbook

For the phishing alerts, I used the phishing investigation playbook provided in the simulation.

The playbook helped me understand the steps involved in investigating a suspicious email. These included reviewing the sender's email address, checking links in the message, and looking for evidence of suspicious network activity.

I learned that an email should not be classified as phishing simply because it contains an external link. It is important to investigate the sender, the purpose of the email, and any related activity before making a decision.

![Phishing Investigation Playbook](screenshots/03-phishing-playbook.png)

### 3. Investigating an Email Using Splunk

One of the alerts involved an onboarding email sent from HRCONNEX, a third-party recruitment organization.

I used Splunk to search for information related to the email. During my investigation, I found an internal communication between the Human Resources department and IT Support confirming that HRCONNEX was involved in the employee onboarding process.

This evidence helped me understand that the email was expected rather than an unexpected phishing attempt.

Based on the available evidence, I classified the alert as a false positive.

![Splunk Email Investigation](screenshots/04-splunk-email-search.png)

### 4. Investigating a Blocked Firewall Connection

I also reviewed a firewall event involving a device with the source IP address `10.20.2.17`.

The device attempted to connect to the destination IP address `67.199.248.11` using TCP port 80.

After reviewing the firewall log in Splunk, I found that the connection had been blocked by a firewall rule named `Blocked Websites`.

This showed that the firewall had prevented the recorded connection from going through.

I also checked the destination IP using TryDetectThis, which identified it as malicious.

The investigation helped me understand how firewall logs and threat intelligence can be used together to investigate suspicious network connections.

![Blocked Firewall Connection](screenshots/05-blocked-firewall-event.png)

### 5. Investigating an Allowed Firewall Connection

Another firewall event showed a connection from the source IP address `10.20.2.25` to the destination IP address `45.148.10.131` over TCP port 443.

Unlike the previous event, this connection was allowed by the firewall.

The event was associated with a suspicious Microsoft-themed URL.

This caught my attention because a connection being allowed does not automatically mean it is safe.

I learned that when investigating allowed connections, it is important to check the destination, review the related activity, and determine whether there is evidence of malicious behavior.

![Allowed Firewall Connection](screenshots/06-allowed-firewall-event.png)

### 6. Checking Suspicious IP Addresses

As part of the investigation, I used TryDetectThis to check an IP address associated with suspicious network activity.

The tool flagged the IP address as malicious, which gave me additional information to consider alongside the firewall logs.

I learned that threat intelligence results can help analysts understand the potential risk of an IP address, but they should not be the only evidence used to make a final decision.

![Threat Intelligence Analysis](screenshots/07-url-analysis.png)

### 7. Closing the Security Alert

After completing an investigation and reviewing the available evidence, I documented my findings and closed the alert in the SOC Simulator.

This helped me practice the final stage of alert triage, where analysts record their conclusions and explain why an alert was classified as a true positive or false positive.

![Alert Closure](screenshots/08-alert-closed.png)
