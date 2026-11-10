
# SOC Alert Triage - Investigation Summary

## Project Overview
This document contains my investigation findings from the TryHackMe SOC Simulator.

I investigated five security alerts involving suspicious emails and firewall activity. I used Splunk SIEM, firewall logs, and URL/IP analysis to review the evidence and make decisions.

## Alerts Investigated

- Alert 8814: Suspicious email
- Alert 8815: Suspicious email
- Alert 8816: Blocked external URL
- Alert 8817: Suspicious email
- Alert 8818: Suspicious email

## Investigation Findings

### Alert 8814 — Suspicious Onboarding Email

**Alert Type:** Inbound Email Containing Suspicious External Link

**Investigation:**

I investigated an onboarding email sent from HRCONNEX to a newly hired employee at TheTryDaily.

I used Splunk SIEM to search for `hrconnex.thm` and found three matching events.

During the investigation, I found an internal conversation between the HR and IT departments confirming that HRCONNEX was involved in the company's employee onboarding process.

This helped me understand why the email was sent and whether the recipient was expecting it.

**Final Decision:** False Positive

**Reason:** The available evidence showed that the email was part of a legitimate employee onboarding process rather than a phishing attempt.

### Alert 8816 — Blacklisted URL Blocked by Firewall

**Alert Type:** Access to Blacklisted External URL Blocked by Firewall

**Investigation:**

I investigated a high-severity firewall alert involving an internal device attempting to access a blacklisted external URL.

The firewall logs showed the following:

- Source IP: `10.20.2.17`
- Destination IP: `67.199.248.11`
- Destination Port: `80`
- Protocol: `TCP`
- Firewall Action: `Blocked`
- Firewall Rule: `Blocked Websites`

I also checked the destination IP address using TryDetectThis, which identified it as malicious.

The firewall log confirmed that the connection attempt was blocked.

**Final Decision:** True Positive

**Reason:** The logs confirm a blocked connection to a blacklisted destination. They do not, by themselves, prove that the endpoint was compromised.
