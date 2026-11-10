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
