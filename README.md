# Official [Cyber Range](http://joshmadakor.tech/cyber-range) Project

# Vulnerability Management Program Implementation

In this project, we simulate the implementation of a comprehensive vulnerability management program, from inception to completion.

_**Inception State:**_ the organization has no existing policy or vulnerability management practices in place.

_**Completion State:**_ a formal policy is enacted, stakeholder buy-in is secured, and a full cycle of organization-wide vulnerability remediation is successfully completed.

---

<img width="1000" alt="image" src="https://github.com/user-attachments/assets/cfc5dbcf-3fcb-4a71-9c13-2a49f8bab3e6">

# Technology Utilized
- Tenable (enterprise vulnerability management platform)
- Azure Virtual Machines (Nessus scan engine + scan targets)
- PowerShell & BASH (remediation scripts)

---


# Table of Contents

- [Vulnerability Management Policy Draft Creation](#vulnerability-management-policy-draft-creation)
- [Mock Meeting: Policy Buy-In (Stakeholders)](#step-2-mock-meeting-policy-buy-in-stakeholders)
- [Policy Finalization and Senior Leadership Sign-Off](#step-3-policy-finalization-and-senior-leadership-sign-off)
- [Mock Meeting: Initial Scan Permission (Server Team)](#step-4-mock-meeting-initial-scan-permission-server-team)
- [Initial Scan of Server Team Assets](#step-5-initial-scan-of-server-team-assets)
- [Vulnerability Assessment and Prioritization](#step-6-vulnerability-assessment-and-prioritization)
- [Distributing Remediations to Remediation Teams](#step-7-distributing-remediations-to-remediation-teams)
- [Mock Meeting: Post-Initial Discovery Scan (Server Team)](#step-8-mock-meeting-post-initial-discovery-scan-server-team)
- [Mock CAB Meeting: Implementing Remediations](#step-9-mock-cab-meeting-implementing-remediations)
- [Remediation Round 1: Outdated Wireshark Removal](#remediation-round-1-outdated-wireshark-removal)
- [Remediation Round 2: Insecure Protocols & Ciphers](#remediation-round-2-insecure-protocols--ciphers)
- [Remediation Round 3: Guest Account Group Membership](#remediation-round-3-guest-account-group-membership)
- [Remediation Round 4: Windows OS Updates](#remediation-round-4-windows-os-updates)
- [First Cycle Remediation Effort Summary](#first-cycle-remediation-effort-summary)

---

### Vulnerability Management Policy Draft Creation

This phase focuses on drafting a Vulnerability Management Policy as a starting point for stakeholder engagement. The initial draft outlines scope, responsibilities, and remediation timelines, and may be adjusted based on feedback from relevant departments to ensure practical implementation before final approval by upper management.  
[Draft Policy](https://docs.google.com/document/d/1CLSWm1_9JL1oUqgyNNwtPXW6FzXJ7ddVnSAUQTyqC8I/edit?usp=drive_link)

---

### Step 2) Mock Meeting: Policy Buy-In (Stakeholders)

In this phase, a meeting with the server team introduces the draft Vulnerability Management Policy and assesses their capability to meet remediation timelines. Feedback leads to adjustments, like extending the critical remediation window from 48 hours to one week, ensuring collaborative implementation.

### Vulnerability Remediation Policy Discussion

**Participants:** Bob, Sam  
**Topic:** Remediation timelines for vulnerability management policy

---

## Summary

Bob and Sam discussed the proposed vulnerability remediation policy, focusing on whether the current timelines are realistic given existing staffing levels. Bob raised concerns about the aggressive **48-hour remediation window for critical vulnerabilities**, noting that the current team may not be able to consistently meet that target.

Sam acknowledged the concern and suggested a compromise approach to allow teams time to adjust to the new policy.

---

## Key Decisions

- The **48-hour remediation window** may be too aggressive for normal operations.
- A **one-week remediation window for critical vulnerabilities** will be considered as a more practical starting point.
- The **48-hour timeline will be reserved for severe cases**, such as **zero-day vulnerabilities**.
- Departments will receive **approximately six months to adjust** after the policy is finalized.

---

## Action Items

- **Sam:** Update the policy draft to reflect the proposed remediation timeline adjustments.
- **Bob:** Begin preparing the team for the new remediation and patching process.
- **Both:** Continue collaboration during the policy rollout period.

---

## Conversation
**Sam:**  
Hey, morning Bob. How has everything been recently? I know everyone’s been busy these last few weeks.

**Bob:**  
Good morning, Sam. Yeah, it’s been a bit hectic, but we’re hanging in there. Thanks for asking.  

I had a chance to read through the policy draft, and overall it makes sense. However, with our current staffing, we can’t meet the aggressive remediation timelines—especially the **48-hour window for critical vulnerabilities**.

**Sam:**  
Yeah, I totally understand. It is a bit aggressive, especially to start. Perhaps we can extend the critical remediation window to **one week**. That might be a good compromise for now. Then we can reserve the **48-hour window** for truly severe cases, like **zero-day vulnerabilities**.

**Bob:**  
Yeah, that sounds reasonable. We appreciate the flexibility. Can we also have a bit of leeway in the beginning as we get used to the remediation and patching process—just for the first few months?

**Sam:**  
Absolutely. After the policy is finalized, we’ll officially start the program. We’re planning to give all departments about **six months to adjust** and get comfortable with the new process.

**Bob:**  
Thanks, Sam. We’ll do our best. I appreciate you including us in the decision-making process. It really helps us feel like we’re part of the solution.

**Sam:**  
Of course. We’re all in this together. Thanks for working with us.

**Bob:**  
No problem. Thanks for the short meeting.

**Sam:**  
Yeah, those are my favorite types.

**Bob:**  
Bye now.

**Sam:**  
See you later.

---

### Step 3) Policy Finalization and Senior Leadership Sign-Off

After gathering feedback from the server team, the policy is revised, addressing aggressive remediation timelines. With final approval from upper management, the policy now guides the program, ensuring compliance and reference for pushback resolution.  
[Finalized Policy](https://docs.google.com/document/d/1rvueLX_71pOR8ldN9zVW9r_zLzDQxVsnSUtNar8ftdg/edit?usp=drive_link)


---

### Step 4) Mock Meeting: Initial Scan Permission (Server Team)

The team collaborates with the server team to initiate scheduled credential scans. A compromise is reached to scan a single server first, monitoring resource impact, and using just-in-time Active Directory credentials for secure, controlled access.  

### Meeting Notes: Sam and Bob – Vulnerability Scanning Setup

**Participants:** Sam, Bob  
**Topic:** Planning and initiating credentialed vulnerability scans

---

## Summary

Sam and Bob discussed the next step in the vulnerability management program: conducting scheduled credentialed vulnerability scans across the server infrastructure. Sam explained how the scans work and why administrative credentials are required to properly assess systems.

Bob raised concerns about potential server performance impact and the security risks of providing administrative credentials for all machines. To address these concerns, they agreed to begin with a **single-server test scan** and monitor resource utilization.

They also discussed creating **temporary Active Directory credentials** that would only be enabled during scans to reduce security risk.

---

## Key Decisions

- Vulnerability scans will be conducted **weekly** across the server infrastructure.
- Initial scans will be **credentialed scans** to provide deeper vulnerability detection.
- A **test scan on a single server** will be performed first to monitor system impact.
- Administrative credentials will be handled using a **temporary Active Directory account**.
- The account will follow a **just-in-time access approach**:
  - Disabled by default  
  - Enabled only during scans  
  - Disabled or deprovisioned after scanning completes

---

## Action Items

- **Sam:** Prepare and schedule the initial vulnerability scan.
- **Bob:** Coordinate the creation of a temporary Active Directory account for scanning.
- **Susan:** Automate the provisioning and disabling of the scanning credentials.
- **Both:** Monitor server performance during the initial test scan.

---

## Conversation

**Bob:**  
Morning, Sam.

**Sam:**  
Good morning. I heard you're ready to conduct some scans.

**Bob:**  
Yep. Now that our vulnerability management policy is in place, I wanted to start conducting some scheduled credentialed scans of your environment.

**Sam:**  
Sounds good to me. What’s involved? How can we help?

**Bob:**  
We’re planning to schedule weekly scans of the server infrastructure. We estimate it will take about **4–6 hours to scan all 200 assets**.  

We’ll need you to provide some **administrative credentials** so the scan engine can remotely log into the targets and better assess them.

**Sam:**  
Whoa, hold on. What does scanning actually entail? I’m a bit worried about resource utilization. Also, you want admin credentials to all 200 machines? That doesn’t sound very safe.

**Bob:**  
Those are valid concerns. The scan engine sends various types of traffic to the servers to check for specific vulnerabilities.  

This includes things like:
- Checking the registry
- Identifying outdated software
- Detecting insecure protocols or cipher suites

That’s why credentials are required—it allows the scanner to perform deeper checks.

**Sam:**  
I see. Well, as long as it doesn’t bring the servers offline, we should be okay.

**Bob:**  
Absolutely. Let’s start by scanning **a single server** and monitor the resource utilization.

**Sam:**  
Not a bad idea.

**Bob:**  
Great. Also, for the credentials, could you set up something in **Active Directory** for us?  

You could leave the account disabled until we’re ready to scan. Then enable it during the scan and disable or deprovision it afterward—kind of like a **just-in-time access** setup.

**Sam:**  
That sounds good. I’ll ask Susan to start working on the automation for provisioning the account.

**Bob:**  
Awesome. Okay, talk soon.

**Sam:**  
Sounds good. I’ll get back to you once the credentials are set up.

**Bob:**  
See you later.

**Sam:**  
See you later.

---

### Step 5) Initial Scan of Server Team Assets

In this phase, an insecure Windows Server is provisioned to simulate the server team's environment. After creating vulnerabilities, an authenticated scan is performed, and the results are exported for future remediation steps.  

<img width="743" height="634" alt="Screen Shot 2026-03-08 at 5 17 23 PM" src="https://github.com/user-attachments/assets/dc51d035-f178-4388-93ff-8f60a2876ddd" />


[Scan 1 - Initial Scan](https://drive.google.com/file/d/1cAbKpe7dHbP_yywmFRq0RRYN0sn9YHUB/view)




---

### Step 6) Vulnerability Assessment and Prioritization

We assessed vulnerabilities and established a remediation prioritization strategy based on ease of remediation and impact. The following priorities were set:

1. Third Party Software Removal (Wireshark)
2. Windows OS Secure Configuration (Protocols & Ciphers)
3. Windows OS Secure Configuration (Guest Account Group Membership)
4. Windows OS Updates

---

### Step 7) Distributing Remediations to Remediation Teams

The server team received remediation scripts and scan reports to address key vulnerabilities. This streamlined their efforts and prepared them for a follow-up review.  

<img width="635" alt="image" src="https://github.com/user-attachments/assets/bbf9478f-e1d1-4898-846e-b510ec8c6f72">

[Remediation Email](https://github.com/inoyatovmanu/remediation-email/blob/main/README.md)

---

### Step 8) Mock Meeting: Post-Initial Discovery Scan (Server Team)

The server team reviewed vulnerability scan results, identifying outdated software, insecure accounts, and deprecated protocols. The remediation packages were prepared for submission to the Change Control Board (CAB). 

### Meeting Notes: Sam and Bob – Vulnerability Scan Results Review

**Participants:** Sam, Bob  
**Topic:** Review of vulnerability scan results and remediation planning

---

## Summary

Sam and Bob reviewed the results of the first vulnerability scan conducted on the server environment. The scan completed successfully with **no outages or resource utilization issues**, confirming that the scanning process does not significantly impact system performance.

Most identified vulnerabilities were related to **outdated software**, particularly an old installation of Wireshark. Additional findings included deprecated cryptographic protocols, weak cipher suites, and a misconfigured **guest account with administrative privileges**.

They discussed potential remediation strategies and confirmed that **Windows Update and existing patch management** should automatically resolve some vulnerabilities. Other issues will require manual remediation and change control approval.

---

## Key Decisions

- The vulnerability scan **did not negatively impact server performance**.
- Several vulnerabilities were caused by **outdated Wireshark installations**.
- The **local guest account belonging to the Administrators group** must be removed.
- Deprecated protocols **TLS 1.0 and TLS 1.1** and weak cipher suites should be disabled.
- Some vulnerabilities related to **Microsoft Edge and Windows components** may be resolved through the existing patch management system.
- Remediation tasks will be reviewed through the **Change Control Board** before deployment.

---

## Action Items

- **Bob:** Develop remediation packages for identified vulnerabilities.
- **Sam:** Coordinate remediation tasks through the Change Control Board.
- **Sam:** Investigate why Wireshark and the guest administrator configuration exist on servers.
- **Bob:** Research best practices for disabling weak cipher suites and deprecated TLS protocols.
- **Both:** Review remediation progress during the next meeting.

---

## Conversation

**Bob:**  
Morning, Sam. How are you doing?

**Sam:**  
Not bad for a Monday. How about you?

**Bob:**  
I’m still alive, so I can’t complain. Before we get into the vulnerabilities, how did the scan go on your end? Did you notice any outages or resource overutilization?

**Sam:**  
The scan went well. We monitored the servers during the process, and aside from seeing a large number of open connections, we wouldn’t have known a scan was taking place.

**Bob:**  
That’s good news. I expected it to run smoothly, but we can keep monitoring going forward. I don’t anticipate any resource utilization issues.

Do you mind if I walk through the vulnerability findings?

**Sam:**  
Absolutely.

**Bob:**  
Most of the vulnerabilities are related to **Wireshark being installed and severely outdated**. That accounts for the majority of these findings.

One interesting thing I noticed is that the **local guest account on the servers belongs to the Administrators group**. I’m not sure why that configuration exists.

Some other vulnerabilities might automatically resolve through **Windows Updates**, such as the Microsoft Edge Chromium findings. I’m not completely certain about all of them, but patch management may address some.

We don’t need to worry about the **self-signed certificate finding**, since it’s simply the system’s self-generated certificate.

However, the **medium-strength cipher suites and deprecated protocols like TLS 1.0 and TLS 1.1** should definitely be remediated.

So the primary issues we need to address are:
- Outdated Wireshark installations  
- Deprecated protocols and cipher suites  
- Removing the guest account from the Administrators group

**Sam:**  
That’s interesting. The good news is that most of our servers likely share the same configuration, so they probably have the same vulnerabilities. Hopefully that will make remediation easier.

**Bob:**  
Yes, that actually helps a lot. If the environment is consistent, remediation can be applied uniformly.

Do you foresee any issues with fixing the cipher suites or disabling the deprecated protocols?

**Sam:**  
I don’t expect any major issues. We’ll run the changes through the **Change Control Board** first.

Uninstalling Wireshark and correcting the guest account configuration should be straightforward since those shouldn’t be on production servers anyway. I’ll need to talk to our system administrators about that.

**Bob:**  
That’s good news. I’ll start building **remediation packages** to make deployment easier for your team.

**Sam:**  
That would be great.

Actually, I wanted to ask—do you already have something in place to handle vulnerabilities related to Windows updates? For example, a patch management system?

**Bob:**  
Yes, we do. Windows updates should be handled automatically by next week through our **patch management process**, so I’m not too concerned about those.

**Sam:**  
Excellent.

**Bob:**  
I’ll start researching the best ways to remediate these findings and get back to you before the next Change Control Board meeting.

**Sam:**  
Sounds good. Talk to you soon.

**Bob:**  
Talk to you soon.

---

### Step 9) Mock CAB Meeting: Implementing Remediations

The Change Control Board (CAB) reviewed and approved the plan to remove insecure protocols and cipher suites. The plan included a rollback script and a tiered deployment approach.  

### Meeting Notes: Vulnerability Remediation – Protocol and Cipher Updates

**Participants:** Sam, Bob, John, Fred  
**Topic:** Removal of insecure protocols and cipher suites on servers

---

## Summary

During the weekly change approval meeting, the team reviewed remediation actions related to **insecure protocols and cipher suites** discovered during vulnerability scanning.

Bob explained that older cryptographic protocols and cipher suites allow systems to negotiate deprecated encryption methods when communicating with other servers. To address this issue, a **PowerShell script** was developed to automatically disable insecure protocols and enable only modern, secure standards.

The team also discussed deployment safety. A **tiered deployment strategy** will be used, starting with a small pilot group before progressing to production systems. In addition, an **automated rollback script** has been created to restore the original configuration if issues arise.

---

## Key Decisions

- Insecure protocols and cipher suites will be **disabled via automated remediation scripts**.
- The remediation will be deployed using a **tiered rollout strategy**:
  - Pilot group
  - Pre-production environment
  - Full production deployment
- A **rollback script** is available to restore original registry settings if problems occur.
- Changes will be implemented using **Windows registry updates through PowerShell automation**.

---

## Action Items

- **Bob:** Finalize and validate the PowerShell remediation scripts.
- **Sam:** Coordinate the rollout through the change management process.
- **John:** Monitor pilot systems for potential compatibility issues.
- **Fred:** Verify rollback procedures and assist with deployment monitoring.

---

## Conversation

**Sam:**  
Okay, next on the list are a couple of vulnerability remediations for the server team: removal of insecure protocols and removal of insecure cipher suites.  

It looks like Bob from the risk team has been working with Sam from infrastructure on this. Sam, do you want to walk us through the technical aspects of the change?

**Sam:**  
Normally I would, but would you mind letting Bob explain this one? He actually built the solution for us, and we’re still getting used to the process.

**Bob:**  
Sure, I can explain.  

The presence of insecure cipher suites and protocols on a system means the machine is capable of negotiating deprecated encryption algorithms or communication protocols. If it connects to a server that only supports those older standards, the system could potentially use them.

These configurations are controlled through the **Windows registry**. The remediation is actually very straightforward. We created a **PowerShell script** that disables all insecure protocols and cipher suites while enabling only modern, secure standards.

**John:**  
That sounds good, but what happens if something goes wrong? Do we have a rollback plan?

**Bob:**  
Yes, absolutely. First, we’re using a **tiered deployment strategy**. That means we’ll start with a small **pilot group**, then move to **pre-production**, and finally to **full production deployment**.

In addition, we created a fully automated **rollback script** for each remediation. If any issues occur, the script restores the original protocol and cipher settings automatically.

**Fred:**  
That sounds reasonable. Since these fixes are simple registry updates, I’m not too concerned.

**Bob:**  
Exactly. It’s a straightforward change.

**Sam:**  
Any more questions from anyone?

Alright, that wraps things up for this week’s meeting. See you all next week.

**Everyone:**  
See you later.

---
### Step 10 ) Remediation Effort

#### Remediation Round 1: Outdated Wireshark Removal

The server team used a PowerShell script to remove outdated Wireshark. A follow-up scan confirmed successful remediation.  
[Wireshark Removal Script](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/remediation-wireshark-uninstall.ps1)  

<img width="634" alt="image" src="https://github.com/user-attachments/assets/7b4f9ab2-d230-4458-ac0f-c0ff070ae79a">

[Scan 2 - Third Party Software Removal](https://drive.google.com/file/d/1UiwPPTtuSZKk02hiMyXf31pXUIeC5EWt/view?usp=drive_link)


#### Remediation Round 2: Insecure Protocols & Ciphers

The server team used PowerShell scripts to remediate insecure protocols and cipher suites. A follow-up scan verified successful remediation, and the results were saved for reference.  
[PowerShell: Insecure Protocols Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-protocols.ps1)
[PowerShell: Insecure Ciphers Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-cipher-suites.ps1)

<img width="630" alt="image" src="https://github.com/user-attachments/assets/0e96120d-8ec9-4f76-8e42-79c752200010">

[Scan 3 - Ciphersuites and Protocols](https://drive.google.com/file/d/1Qc6-ezQvwReCGUZNtnva0kCZo_-zW-Sm/view?usp=drive_link)


#### Remediation Round 3: Guest Account Group Membership

The server team removed the guest account from the administrator group. A new scan confirmed remediation, and the results were exported for comparison.  
[PowerShell: Guest Account Group Membership Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-guest-local-administrators.ps1)  

<img width="627" alt="image" src="https://github.com/user-attachments/assets/870a3eac-3398-44fe-91c0-96f3c2578df4">

[Scan 4 - Guest Account Group Removal](https://drive.google.com/file/d/1jVgikjfrV1YjOcL3QRT_oUB0Y82w22V7/view?usp=drive_link)


#### Remediation Round 4: Windows OS Updates

Windows updates were re-enabled and applied until the system was fully up to date. A final scan verified the changes  

<img width="627" alt="image" src="https://github.com/user-attachments/assets/870a3eac-3398-44fe-91c0-96f3c2578df4">

[Scan 5 - Post Windows Updates](https://drive.google.com/file/d/1tmDjeHl5uiGitRwWy8kFRi33q-nGi1Zt/view?usp=drive_link)

---

### First Cycle Remediation Effort Summary

The remediation process reduced total vulnerabilities by 80%, from 30 to 6. Critical vulnerabilities were resolved by the second scan (100%), and high vulnerabilities dropped by 90%. Mediums were reduced by 76%. In an actual production environment, asset criticality would further guide future remediation efforts.  

<img width="1920" alt="image" src="https://github.com/user-attachments/assets/51f0aae8-7f36-4d90-b29f-5257e57155f9">

[Remediation Data](https://docs.google.com/spreadsheets/d/1FTtFfZYmFsNLU6pm8nTzsKyKE-d2ftXzX_DPwcnFNfA/edit?gid=0#gid=0)

---

### On-going Vulnerability Management (Maintenance Mode)

After completing the initial remediation cycle, the vulnerability management program transitions into **Maintenance Mode**. This phase ensures that vulnerabilities continue to be managed proactively, keeping systems secure over time. Regular scans, continuous monitoring, and timely remediation are crucial components of this phase. (See [Finalized Policy](https://docs.google.com/document/d/1rvueLX_71pOR8ldN9zVW9r_zLzDQxVsnSUtNar8ftdg/edit?usp=drive_link) for scanning and remediation cadence requirements.)

Key activities in Maintenance Mode include:
- **Scheduled Vulnerability Scans**: Perform regular scans (e.g., weekly or monthly) to detect new vulnerabilities as systems evolve.
- **Patch Management**: Continuously apply security patches and updates, ensuring no critical vulnerabilities remain unpatched.
- **Remediation Follow-ups**: Address newly identified vulnerabilities promptly, prioritizing based on risk and impact.
- **Policy Review and Updates**: Periodically review the Vulnerability Management Policy to ensure it aligns with the latest security best practices and organizational needs.
- **Audit and Compliance**: Conduct internal audits to ensure compliance with the vulnerability management policy and external regulations.
- **Ongoing Communication with Stakeholders**: Maintain open communication with teams responsible for remediation, ensuring efficient coordination.

By maintaining an active vulnerability management process, organizations can stay ahead of emerging threats and ensure long-term security resilience.
