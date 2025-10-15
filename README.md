# SOC Fundamentals - Port Scanning Detection Lab

## Objective

This project focused on investigating a high-severity port scanning alert using SIEM analysis. The goal was to analyze network logs, identify attack patterns, and classify the incident as either a true positive or false positive, demonstrating practical SOC analyst skills.

### Skills Learned

- Understanding of SOC analyst workflows and alert triage procedures
- Proficiency in analyzing and interpreting SIEM logs and network traffic
- Ability to recognize port scanning patterns and attack signatures
- Enhanced knowledge of incident response and decision-making processes
- Understanding of legitimate security tools vs. malicious activity
- Development of critical thinking and problem-solving skills in security operations

### Tools Used

- TryHackMe - Hands-on cybersecurity training platform
- SIEM system for log ingestion and security event analysis
- Network traffic analysis tools for examining connection patterns
- Alert management dashboard for incident tracking and response

## Steps

### Step 1: Initial Alert Detection

<img width="927" height="962" alt="Screenshot 1" src="https://github.com/user-attachments/assets/30b4c4a1-dc90-4548-9ecc-3f8338314566" />

*Ref 1: SIEM Alerts Dashboard - Alert #167 Port Scanning Activity from IP 10.0.0.8*

Identified high-severity alert indicating port scanning from internal IP 10.0.0.8. Clicked ACKNOWLEDGE to take ownership of the investigation.

---

### Step 2: Alert Acknowledgment
<img width="730" height="153" alt="Screenshot 2" src="https://github.com/user-attachments/assets/838b2a91-f89e-42dd-b336-007e6e178d91" />


*Ref 2: Alert status changed to "Investigate in SIEM"*

Alert acknowledged and transitioned to investigation phase for detailed SIEM analysis.

---

### Step 3: SIEM Investigation
<img width="997" height="711" alt="Screenshot 3" src="https://github.com/user-attachments/assets/8e4b6943-d878-4f71-b9b3-d86af7cb6201" />


*Ref 3: SIEM showing 4,300 events from IP 10.0.0.8 to 10.0.0.3*

Analysis revealed:
- **Total Events:** 4,300 hits over 5 hours
- **Source:** 10.0.0.8 (NESSUS)
- **Destination:** 10.0.0.3 (JOE PC)
- **Ports:** 443, 53, 22
- **Time:** June 12-13, 2024

Multiple peaks indicated automated scanning behavior.

---

### Step 4: Traffic Pattern Analysis
<img width="1004" height="651" alt="Screenshot 4" src="https://github.com/user-attachments/assets/240a2e0e-1bd5-4117-a3dd-72268b1ce775" />


*Ref 4: Traffic pattern analysis confirming automated scanning*

All 4,300 connections from single source (10.0.0.8) targeting multiple ports. Source hostname "NESSUS" identified as legitimate vulnerability scanner.

---

### Step 5: Incident Classification Decision
<img width="980" height="591" alt="Screenshot 5" src="https://github.com/user-attachments/assets/b18e5bdf-b58d-4120-925b-b600ec412efe" />


*Ref 5: Classification decision point*

Determined classification:
- **Option A:** True Positive (malicious)
- **Option B:** False Positive (authorized)

**Decision:** False Positive - authorized internal vulnerability assessment by security team using Nessus scanner.

---

### Step 6: Investigation Resolution
<img width="992" height="516" alt="Screenshot 6" src="https://github.com/user-attachments/assets/ba1855d0-1f81-4e52-aeed-4e4c1338ea2b" />


*Ref 6: Investigation resolution confirmation*

Confirmed authorized Nessus scan from 10.0.0.8 to JOE PC by internal security team.

**Flag Captured:** THM{000_INTRO_TO_SOC}

---

### Step 7: Alert Closure
<img width="988" height="250" alt="Screenshot 7" src="https://github.com/user-attachments/assets/efd98adf-61ea-4f51-a1cf-8187a660e0c6" />


*Ref 7: Alert closed with RESOLVED status*

Alert #167 closed and marked as RESOLVED - authorized activity documented.

---

### Step 8: Challenge Completion
<img width="1512" height="712" alt="Screenshot 8" src="https://github.com/user-attachments/assets/3a482cb2-2ff5-4627-b020-558a44e41d44" />


*Ref 8: TryHackMe completion*

Completed with 128 points, 7/7 tasks, Easy difficulty.

---

## Key Takeaways

- Triaged and investigated high-severity SIEM alert
- Analyzed 4,300+ network events to identify patterns
- Distinguished authorized scanning from malicious activity
- Applied proper incident response procedures
- Documented findings with appropriate alert disposition

### Lessons Learned
1. Context is critical - recognizing legitimate security tools prevents false escalations
2. Internal IP scanning requires different analysis than external threats
3. Coordination with security teams reduces alert fatigue
4. Proper documentation is essential for SOC operations

---

## Project Information

**Platform:** TryHackMe - SOC Fundamentals Room  
**Completion Date:** June 2024  
**Course:** ITECH1502 Cybersecurity Fundamentals  
**Institution:** Federation University Australia  
**Flag Achieved:** THM{000_INTRO_TO_SOC}

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| TryHackMe | Hands-on cybersecurity training platform |
| SIEM System | Security event log aggregation and analysis |
| Network Analysis | Traffic pattern examination and investigation |
| Alert Management | Incident tracking and response workflow |

---

## Repository Structure

```
soc-fundamentals-investigation/
│
├── README.md                          # Project documentation
├── screenshots/                       # Investigation screenshots
│   ├── 01-alert-dashboard.png
│   ├── 02-alert-acknowledged.png
│   ├── 03-siem-analysis.png
│   ├── 04-traffic-patterns.png
│   ├── 05-decision-point.png
│   ├── 06-investigation-result.png
│   ├── 07-alert-closed.png
│   └── 08-challenge-complete.png
│
└── documentation/
    └── project-report.pdf             # Full project report (5 pages)
```

---

## How to Use This Repository

This repository documents practical SOC operations and incident response skills:
- Alert investigation methodology
- SIEM log analysis
- Network traffic pattern recognition
- Incident classification

---

## Additional Projects

For more cybersecurity projects and demonstrations, please visit my complete portfolio:

- [GitHub Portfolio](https://modassar-islam.github.io/Cybersecurity-Portfolio/)
- [TryHackMe Profile](https://tryhackme.com/p/modassari)

---

## Acknowledgments

- **TryHackMe** for providing excellent hands-on cybersecurity training
- **Federation University Australia** for the ITECH1502 Cybersecurity Fundamentals course

---

## License

This project is part of academic coursework for ITECH1502 Cybersecurity Fundamentals at Federation University Australia.

---

*Last Updated: October 2025*
