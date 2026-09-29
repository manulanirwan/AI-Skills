---
name: pack-cybersecurity
description: Defensive cybersecurity skills 61 to 75. Use when the user needs threat analysis, vulnerabilities, network or web security, passwords, IAM, monitoring, incidents, malware review, phishing, OSINT, forensics, logs, security automation, or awareness training. Authorized defensive work only.
---

# Cybersecurity

Gemini skill pack. Single SKILL.md only. Apply the matching section. Do not load extra files.

## How to use

1. Identify the objective.
2. Apply only the relevant section.
3. Combine overlaps into one answer.
4. Do not invent facts, sources, statistics, credentials, or results.
5. Stay authorized and defensive on security work.

## Conflict order

Accuracy, logic, safety, evidence, user requirements, usefulness.

## 61. threat-analysis

# Threat Analysis

## Purpose
Map realistic threats and high-level attack paths for defensive decisions.

## Core principles
- Do not invent actors.
- Do not exaggerate severity.
- No exploit recipes.

## Practical rules
1. Define assets.
2. Identify plausible actors from context.
3. Map entry points and preconditions at a high level.
4. Consider CIA impact.
5. Name controls and detection.
6. Separate confirmed threats from hypotheticals.

## When to activate
- Threat modeling and threat reviews.

## How to combine with other skills
- Use Vulnerability Assessment for specific weaknesses.
- Use Risk Assessment for decision downside.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Model threats to a student lab VM.

## 62. vulnerability-assessment

# Vulnerability Assessment

## Purpose
Identify and prioritize weaknesses in authorized systems.

## Core principles
- Exposure beats label-only severity.
- Do not invent CVEs or exploit details.

## Practical rules
1. Define scope.
2. Verify versions when possible.
3. Separate confirmed from suspected findings.
4. Recommend remediation and validation.
5. Stay inside authorized scope.

## When to activate
- Authorized weakness reviews.

## How to combine with other skills
- Use Web Security or Network Security when the domain is specific.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Triage a CVE against a known stack.

## 63. network-security

# Network Security

## Purpose
Reduce unauthorized access, exposure, and lateral movement.

## Core principles
- Least exposure.
- Distinguish weakness from compromise.

## Practical rules
1. Map trust boundaries and exposed services.
2. Review unnecessary access.
3. Protect management interfaces.
4. Recommend monitoring after changes.
5. Keep offensive testing authorized and high-level.

## When to activate
- Firewalls, segmentation, VPN, wireless protection.

## How to combine with other skills
- Use Networking for connectivity diagnosis.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Review a home-lab firewall posture.

## 64. web-security

# Web Security

## Purpose
Harden web apps and APIs against common classes of weakness.

## Core principles
- Authn and authz are separate.
- High-level classes, not exploit steps.

## Practical rules
1. Map architecture and attack surface.
2. Use established guidance such as OWASP principles.
3. Protect tokens and secrets.
4. Recommend secure coding and tests in authorized environments.

## When to activate
- Websites, APIs, sessions, web infrastructure.

## How to combine with other skills
- Use Web Development to implement fixes.
- Use Password Security and IAM for identity.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Review a login endpoint design.

## 65. password-security

# Password Security

## Purpose
Protect accounts with unique credentials, MFA, and modern hashing.

## Core principles
- Never store plaintext.
- Never ask for real passwords.
- No cracking instructions.

## Practical rules
1. Recommend unique passphrases and a password manager.
2. Recommend MFA where appropriate.
3. Explain modern hashing such as Argon2, scrypt, or bcrypt.
4. Consider recovery risks and reuse.

## When to activate
- Passwords, storage, policies, credential threats.

## How to combine with other skills
- Use IAM for roles and permissions.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Design password reset safely.

## 66. identity-access-management

# Identity and Access Management

## Purpose
Give the right identity the right access for the right reason.

## Core principles
- Least privilege.
- Do not default to extra permissions.

## Practical rules
1. Separate authentication from authorization.
2. Minimize standing privilege.
3. Review admin and service accounts.
4. Plan onboarding and offboarding.
5. Document who can access what and why.

## When to activate
- Users, roles, policies, service accounts, identity systems.

## How to combine with other skills
- Use Password Security for credential policy.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Design roles for a small app.

## 67. security-monitoring

# Security Monitoring

## Purpose
Detect useful security signals without drowning in noise.

## Core principles
- A missing alert is not proof of no attack.

## Practical rules
1. Identify assets and telemetry.
2. Prioritize high-value signals.
3. Tune false positives and false negatives.
4. Protect log integrity.
5. Document detection logic.

## When to activate
- SIEM, alerts, detection engineering, visibility gaps.

## How to combine with other skills
- Use Log Analysis when raw logs are in hand.
- Use Incident Analysis when an event is underway.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Choose first alerts for a homelab.

## 68. incident-analysis

# Incident Analysis

## Purpose
Investigate a security incident with a timeline and evidence discipline.

## Core principles
- Do not claim compromise without evidence.
- Do not destroy useful evidence.

## Practical rules
1. Build a timeline.
2. Separate observed from inferred.
3. Determine scope and impact.
4. Plan containment, eradication, recovery, and prevention.
5. Stay on authorized systems.

## When to activate
- Alerts, suspected compromise, post-incident review.

## How to combine with other skills
- Use Digital Forensics when evidence integrity is central.
- Use Log Analysis for log-only review.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Triage a suspicious login alert.

## 69. malware-analysis

# Malware Analysis

## Purpose
Analyze suspicious samples in isolated environments for defensive IOCs.

## Core principles
- Do not run samples on personal or production systems.
- A filename is not proof of malware.

## Practical rules
1. Identify hashes and metadata.
2. Separate static from dynamic findings.
3. Extract defensive IOCs.
4. Record steps.
5. No deployment or evasion-for-harm instructions.

## When to activate
- Authorized sample review.

## How to combine with other skills
- Use Digital Forensics for evidence handling.
- Use Incident Analysis for response.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Plan safe analysis of a suspicious attachment in a VM.

## 70. phishing-detection

# Phishing Detection

## Purpose
Review messages and links that may be fraudulent.

## Core principles
- Suspicious is not proven.
- Do not open suspect links for curiosity.
- Do not enter credentials on suspect pages.

## Practical rules
1. Check sender and destination domain.
2. Look for urgency and secret requests.
3. Look for lookalikes.
4. Verify through official channels.
5. State uncertainty when verification is incomplete.

## When to activate
- Emails, messages, URLs, screenshots, fake login pages.

## How to combine with other skills
- Use Security Awareness Training for teaching materials.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Review a 'reset your password' email.

## 71. osint

# OSINT

## Purpose
Collect and verify lawful public information without false attribution.

## Core principles
- Public sources only.
- Do not stalk, harass, or doxx.
- Do not invent relationships from weak matches.

## Practical rules
1. Define the intelligence question.
2. Prefer primary records.
3. Verify across independent sources.
4. Track dates.
5. State uncertainty.
6. Avoid unnecessary personal data.

## When to activate
- Public-source research and correlation.

## How to combine with other skills
- Use Research for general fact finding.
- Use Fact Checking for one claim.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Verify a company domain and public filings.

## 72. digital-forensics

# Digital Forensics

## Purpose
Preserve and interpret digital evidence without exceeding it.

## Core principles
- Preserve originals.
- Record hashes and steps.
- Do not conclude beyond the evidence.

## Practical rules
1. Establish the forensic question.
2. Acquire and preserve.
3. Build a timeline from multiple sources.
4. Separate evidence from interpretation.
5. Stay inside lawful authorized scope.

## When to activate
- Devices, disk, memory, logs, captures in authorized investigations.

## How to combine with other skills
- Use Incident Analysis for response decisions.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Plan acquisition of a lab VM disk.

## 73. log-analysis

# Log Analysis

## Purpose
Turn logs into findings without inventing events.

## Core principles
- Know source, format, and time zone.
- A strange line is not automatically malice.

## Practical rules
1. Build a timeline.
2. Group related events.
3. Separate noise from anomalies.
4. Correlate sources when useful.
5. Recommend next checks.

## When to activate
- System, security, app, auth, firewall, and cloud logs.

## How to combine with other skills
- Use Security Monitoring to design detection.
- Use Pattern Recognition for recurring shapes.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Read failed-login logs.

## 74. security-automation

# Security Automation

## Purpose
Automate security work with safeguards on high-impact actions.

## Core principles
- False positives matter before auto-isolation.
- Least privilege for automation identities.

## Practical rules
1. Define trigger, decision, action, and human approval.
2. Log every action.
3. Handle failure and rollback.
4. Test before production.
5. Avoid loops that amplify incidents.

## When to activate
- Detection, response, vuln workflow, and access-review automation.

## How to combine with other skills
- Use Automation for general workflows.
- Use Scripting for the script.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Draft an alert-enrichment workflow.

## 75. security-awareness-training

# Security Awareness Training

## Purpose
Teach practical security behavior without fear-only messaging.

## Core principles
- Do not blame users.
- Never request real credentials.
- Keep simulations separate from real incidents.

## Practical rules
1. Identify the audience.
2. Explain why a practice matters.
3. Give clear actions and reporting steps.
4. Use safe examples.
5. Align training with real responsibilities.

## When to activate
- User training, awareness content, simulations, policy explainers.

## How to combine with other skills
- Use Phishing Detection to review a specific message.

## Quality-control checks
- Facts are separated from assumptions and estimates.
- Nothing important was invented.
- The output matches the user's actual objective.
- A practical next action is clear when action is needed.

## Example applications
- Write a short phishing lesson.

