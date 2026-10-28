# SY0-701 study guide and practice questions

CompTIA Security+ covers the core skills for security work and suits people in, or moving into, roles such as security administrator, systems administrator, and junior security analyst. SY0-701 is the current exam (version V7) and certifies that you can assess an environment's security, put basic controls in place, monitor and respond to incidents, and work within governance, risk, and compliance rules. CompTIA has announced the next version, SY0-801, for November 2026. This repository holds a study guide built from CompTIA's published objectives, a cheat sheet linked to NIST, IETF, OWASP, and vendor documentation, an eight week study plan, and 15 original practice questions.

> Unofficial study notes by [Examice](https://examice.com/exams/comptia/sy0-701?utm_source=github&utm_medium=social&utm_campaign=sy0-701-study-guide-and-practice-questions&utm_content=link_1). Not affiliated with or endorsed by CompTIA. The practice questions are original and not taken from the exam.

## Contents

- [Exam at a glance](#exam-at-a-glance)
- [What the exam covers](#what-the-exam-covers)
- [Study plan](#study-plan)
- [Cheat sheet](#cheat-sheet)
- [Free official resources](#free-official-resources)
- [Practice questions](#practice-questions)
- [Exam day tips](#exam-day-tips)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)

## Exam at a glance

| Fact | Detail |
| --- | --- |
| Certification | CompTIA Security+ |
| Exam code | SY0-701 (version V7) |
| Launch date | November 7, 2023 |
| Retirement | English: June 11, 2027. Japanese, Portuguese, Spanish, and Thai: August 13, 2027 |
| Questions | Up to 90, a mix of multiple choice and performance-based |
| Time limit | 90 minutes |
| Passing score | 750 on a scale of 100–900 |
| Languages | English, Japanese, Portuguese, Spanish, and Thai |
| Recommended experience | CompTIA Network+ and two years in a security or systems administrator role |
| DoD 8140 | Listed for work roles including cyber defense analyst, incident responder, vulnerability analyst, and system administrator |
| Validity | 3 years from the date you pass |
| Renewal | 50 continuing education units (CEUs) in the three year cycle and a $150 CE fee for the cycle, or another route such as CertMaster CE or a higher certification |
| Retakes | No wait before a second attempt; at least 14 calendar days before a third or later attempt; full price every attempt |

Source: [Security+ V7 page](https://www.comptia.org/en-us/certifications/security/v7/), [Security+ renewal requirements](https://www.comptia.org/en-us/resources/ce/renew-options/renewing-security-single/), [CE renewal cycle](https://www.comptia.org/en-us/resources/ce/learn/how-to-renew/ce-renewal-cycle/), [CE renewal fees](https://www.comptia.org/en-us/resources/ce/learn/continuing-education-renewal-fees/), [How long Security+ lasts](https://www.comptia.org/en-us/blog/how-long-does-the-comptia-security-certification-last/), and the [retake policy](https://www.comptia.org/en-us/resources/test-policies/comptia-certification-retake-policy/), checked October 28, 2026.

### The next version: SY0-801

| Fact | SY0-701 (V7) | SY0-801 (V8) |
| --- | --- | --- |
| Launch | November 7, 2023 | On or around November 17, 2026 |
| Retirement | English: June 11, 2027 | Estimated 3 years after launch |
| Questions and time | Up to 90 in 90 minutes | Up to 90 in 90 minutes |
| Passing score | 750 on a scale of 100–900 | 750 on a scale of 100–900 |
| Languages | English, Japanese, Portuguese, Spanish, Thai | English |
| General security concepts | 12% | 16% |
| Threats, vulnerabilities, and mitigations (V8: attacks) | 22% | 24% |
| Security architecture | 18% | 19% |
| Security operations | 28% | 27% |
| Security program management and oversight | 20% | 14% |

The V8 objectives add an objective on threats and vulnerabilities tied to AI use. Source: [Security+ V8 page](https://www.comptia.org/en-us/certifications/security/v8/) and the [SY0-801 objectives preview (PDF)](https://lecbyo.files.cmp.optimizely.com/download/77f3bd3223ac11f180820e495f189928), checked October 28, 2026.

## What the exam covers

| Domain | Weight |
| --- | --- |
| 1.0 General Security Concepts | 12% |
| 2.0 Threats, Vulnerabilities, and Mitigations | 22% |
| 3.0 Security Architecture | 18% |
| 4.0 Security Operations | 28% |
| 5.0 Security Program Management and Oversight | 20% |

The full objectives summary is on the [Security+ V7 page](https://www.comptia.org/en-us/certifications/security/v7/). Below is what each domain asks you to do, in plain terms.

### Domain 1: General security concepts (12%)

- Sort controls by category (technical, managerial, operational, physical) and by what they do (prevent, deter, detect, correct, compensate, direct). [NIST SP 800-53 Rev. 5](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final), [NIST glossary: compensating controls](https://csrc.nist.gov/glossary/term/compensating_controls)
- Explain confidentiality, integrity, and availability, non-repudiation, and authentication, authorization, and accounting. Describe zero trust, where every request is checked by a policy decision point and enforced at a policy enforcement point, plus physical security and deception tools such as honeypots. [NIST SP 800-207](https://csrc.nist.gov/pubs/sp/800/207/final)
- Show why change management matters for security: approval, impact analysis, a backout plan, maintenance windows, and updated documentation. [NIST SP 800-128](https://csrc.nist.gov/pubs/sp/800/128/upd1/final)
- Choose cryptographic tools: symmetric and asymmetric encryption, hashing and salting, digital signatures, key management, certificates, and hardware such as a TPM or HSM. [FIPS 186-5](https://csrc.nist.gov/pubs/fips/186-5/final), [NIST SP 800-57 Part 1](https://csrc.nist.gov/pubs/sp/800/57/pt1/r5/final), [RFC 5280](https://www.rfc-editor.org/rfc/rfc5280)

### Domain 2: Threats, vulnerabilities, and mitigations (22%)

- Compare threat actors (nation states, unskilled attackers, hacktivists, insiders, organized crime, shadow IT) by resources, skill, and motive.
- Name the ways attacks arrive: email, text, and voice lures, removable media, unsecured networks, vulnerable software, and the supply chain. [CISA: social engineering and phishing](https://www.cisa.gov/news-events/news/avoiding-social-engineering-and-phishing-attacks), [IC3: business email compromise](https://www.ic3.gov/CrimeInfo/BEC)
- Explain vulnerability classes in applications, operating systems, web apps, hardware, virtualization, cloud, mobile devices, and suppliers. [OWASP Top 10](https://owasp.org/Top10/)
- Read indicators of malware, password attacks, application attacks, network attacks, and cryptographic attacks in a scenario. [MITRE ATT&CK](https://attack.mitre.org/)
- Pick mitigations: segmentation, access control, allow lists, isolation, patching, hardening, and least privilege. [NIST SP 800-40 Rev. 4](https://csrc.nist.gov/pubs/sp/800/40/r4/final)

### Domain 3: Security architecture (18%)

- Weigh the security tradeoffs of on premises, cloud, virtualization, containers, infrastructure as code, IoT, and industrial control systems. [NIST SP 800-145](https://csrc.nist.gov/pubs/sp/800/145/final), [NIST SP 800-82 Rev. 3](https://csrc.nist.gov/pubs/sp/800/82/r3/final)
- Design a secure network: security zones, device placement, firewalls, IDS and IPS, proxies, jump servers, VPNs, and port security.
- Protect data according to its type, classification, and state (at rest, in transit, in use) with encryption, hashing, masking, tokenization, and segmentation. [Microsoft: shared responsibility in the cloud](https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility)
- Plan for resilience: high availability, alternate sites, backups, power, platform diversity, and recovery testing. [NIST SP 800-34 Rev. 1](https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final)

### Domain 4: Security operations (28%)

- Apply secure baselines and hardening to servers, endpoints, mobile devices, network gear, and wireless. [CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks)
- Track assets from purchase to disposal, and sanitize media correctly before reuse or disposal. [NIST SP 800-88 Rev. 2](https://csrc.nist.gov/pubs/sp/800/88/r2/final)
- Run vulnerability management: find, score, prioritize, fix, confirm, and report. [NIST SP 800-40 Rev. 4](https://csrc.nist.gov/pubs/sp/800/40/r4/final), [CVSS](https://www.first.org/cvss/)
- Monitor with logs, a SIEM, and alerts, and tune the tools that enforce policy: firewalls, IDS and IPS, web and DNS filtering, email security, DLP, NAC, and EDR or XDR. [NIST SP 800-92](https://csrc.nist.gov/pubs/sp/800/92/final), [RFC 9989 (DMARC)](https://www.rfc-editor.org/rfc/rfc9989)
- Manage identity and access: provisioning, single sign-on, federation, access control models, MFA, password policy, and privileged access. [NIST SP 800-63B-4](https://pages.nist.gov/800-63-4/sp800-63b.html), [NIST SP 800-162](https://csrc.nist.gov/pubs/sp/800/162/upd2/final)
- Explain where automation and scripting help and what they cost.
- Handle incidents: preparation, detection and analysis, containment, eradication, recovery, and lessons learned, plus threat hunting and forensics with chain of custody. Use logs, scans, dashboards, and packet captures as evidence. [NIST SP 800-61 Rev. 3](https://csrc.nist.gov/pubs/sp/800/61/r3/final), [RFC 3227](https://www.rfc-editor.org/rfc/rfc3227)

### Domain 5: Security program management and oversight (20%)

- Explain how policies, standards, procedures, and guidelines fit together, and who owns, controls, processes, and keeps data. [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
- Run risk management: identify, assess, and record risks, compare qualitative and quantitative analysis, set appetite and tolerance, choose a response, and do a business impact analysis. [NIST SP 800-30 Rev. 1](https://csrc.nist.gov/pubs/sp/800/30/r1/final), [NISTIR 8286A](https://csrc.nist.gov/pubs/ir/8286/a/final)
- Manage third parties: vendor assessment, due diligence, contracts and agreements, and ongoing monitoring. [NIST SP 800-161 Rev. 1](https://csrc.nist.gov/pubs/sp/800/161/r1/upd1/final), [NIST SP 800-47 Rev. 1](https://csrc.nist.gov/pubs/sp/800/47/r1/final)
- Meet compliance and privacy duties, including reporting, the consequences of failing, and the roles of data controller and processor. [EDPB guidelines on controller and processor](https://www.edpb.europa.eu/documents/guideline/guidelines-072020-on-the-concepts-of-controller-and-processor-in-the-gdpr_en)
- Explain audits, attestation, and penetration tests, including how much the tester knows in advance. [NIST SP 800-115](https://csrc.nist.gov/pubs/sp/800/115/final)
- Run security awareness: phishing exercises, recognizing unusual behavior, and clear reporting paths.

## Study plan

Eight weeks at about 8–10 hours a week, roughly 70 hours. If you already work in IT operations, you can compress weeks 4–6.

| Week | Focus | Tasks | Hours |
| --- | --- | --- | --- |
| 1 | Domain 1 | Read the V7 objectives summary. Make a control matrix: one example per category and type. Learn what a hash, a salt, a signature, and a certificate each prove. | 8 |
| 2 | Domain 2, actors and vectors | Read CISA's social engineering guide and the IC3 BEC page. Write one line per threat actor on motive and skill. List the vulnerability classes with one example each from the OWASP Top 10. | 8 |
| 3 | Domain 2, attacks and mitigations | Browse MITRE ATT&CK techniques for password attacks and phishing. Map each attack type to its log evidence and its main mitigation. | 9 |
| 4 | Domain 3 | Draw a small network with a DMZ, an internal zone, and a jump server, and place a firewall, an IPS, and a proxy. Fill in the cloud responsibility table. Learn the alternate site types, RTO, and RPO from NIST SP 800-34. | 9 |
| 5 | Domain 4, hardening to monitoring | Compare one CIS Benchmark section against a machine you use. Score two CVEs with the CVSS calculator. Read NIST SP 800-88 on clear, purge, and destroy. | 10 |
| 6 | Domain 4, IAM and response | Memorize the port table below. Look up your own domain's SPF and DMARC records. Walk a ransomware case through each incident response step, and list evidence in order of volatility. | 10 |
| 7 | Domain 5 | Work three quantitative risk problems (SLE, ARO, ALE). Write a one page risk register. Match each contract type to the problem it solves. Read the EDPB definitions of controller and processor. | 9 |
| 8 | Review | Do the [practice questions](practice-questions.md) and CompTIA's free sample questions. Practice performance-based tasks: read firewall rules and logs, then reorder steps. Restudy the weakest domain. | 8 |

## Cheat sheet

### Domain 1: Controls and cryptography

| Control type | Purpose | Example |
| --- | --- | --- |
| Preventive | Stops an event | Firewall rule, door lock |
| Deterrent | Discourages an attempt | Warning sign, login banner |
| Detective | Finds an event in progress or after | IDS alert, log review |
| Corrective | Restores after an event | Restore from backup, reimage a host |
| Compensating | Stands in when the normal control is not possible | Isolate a system that cannot be patched |
| Directive | Tells people what to do | Acceptable use policy |

Each type can be technical, managerial, operational, or physical. Source: [Security+ V7 objectives summary](https://www.comptia.org/en-us/certifications/security/v7/), [NIST glossary: compensating controls](https://csrc.nist.gov/glossary/term/compensating_controls).

| Tool | What it gives you | Key point |
| --- | --- | --- |
| Symmetric encryption (AES) | Confidentiality, fast | One shared secret key |
| Asymmetric encryption | Key exchange, signatures | Public and private key pair |
| Hash (SHA-256) | Integrity | One way; the output has a fixed length |
| Digital signature | Integrity, authenticity, non-repudiation | Sign with the private key, verify with the public key |
| Salted password hash | Safe password storage | A unique salt per password, a password hashing scheme with a cost factor |

Source: [FIPS 197](https://csrc.nist.gov/pubs/fips/197/final), [FIPS 180-4](https://csrc.nist.gov/pubs/fips/180-4/upd1/final), [FIPS 186-5](https://csrc.nist.gov/pubs/fips/186-5/final), [NIST SP 800-63B-4](https://pages.nist.gov/800-63-4/sp800-63b.html).

### Domain 2: Attacks and defenses

| Password attack | Pattern | ATT&CK |
| --- | --- | --- |
| Guessing (brute force) | Many passwords against one account | [T1110.001](https://attack.mitre.org/techniques/T1110/001/) |
| Cracking | Offline guessing against stolen hashes | [T1110.002](https://attack.mitre.org/techniques/T1110/002/) |
| Spraying | One or a few common passwords against many accounts | [T1110.003](https://attack.mitre.org/techniques/T1110/003/) |
| Credential stuffing | Username and password pairs leaked from another site | [T1110.004](https://attack.mitre.org/techniques/T1110/004/) |

| Application attack | Primary defense |
| --- | --- |
| SQL injection | Prepared statements with parameterized queries |
| Cross-site scripting (XSS) | Encode output for the context it lands in |
| Cross-site request forgery (CSRF) | Synchronizer tokens or framework CSRF protection |

Source: [OWASP SQL Injection Prevention](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html), [OWASP XSS Prevention](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html), [OWASP CSRF Prevention](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html).

| Lure | Channel |
| --- | --- |
| Phishing | Email or a fake website |
| Vishing | Voice calls, often with a spoofed caller ID |
| Smishing | SMS text messages |
| Business email compromise | A real or lookalike business mailbox asking for a payment or account change |

Verify unusual requests through a channel you already trust, never through contact details in the message. Source: [CISA](https://www.cisa.gov/news-events/news/avoiding-social-engineering-and-phishing-attacks), [IC3](https://www.ic3.gov/CrimeInfo/BEC).

### Domain 3: Architecture and resilience

| Area | IaaS | PaaS | SaaS |
| --- | --- | --- | --- |
| Data, identities, configuration | Customer | Customer | Customer |
| Applications | Customer | Shared | Shared |
| Operating system | Customer | Provider | Provider |
| Physical hosts, network, datacenter | Provider | Provider | Provider |

Source: [Microsoft: shared responsibility in the cloud](https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility), [AWS shared responsibility model](https://aws.amazon.com/compliance/shared-responsibility-model/).

| Term | Meaning |
| --- | --- |
| RPO | The point in time to which data must be recovered: the most data you can afford to lose |
| RTO | The longest a system can stay down before the impact becomes unacceptable |
| MTD | The total outage the system owner will accept for the business process; RTO must be shorter |
| Hot site | Hardware, supporting infrastructure, and staff in place; ready to take over quickly |
| Warm site | Partly equipped with some hardware, software, and connectivity; needs setup |
| Cold site | Space, power, and connectivity only; the cheapest and slowest |

Source: [NIST SP 800-34 Rev. 1](https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final), [NIST glossary: RPO](https://csrc.nist.gov/glossary/term/recovery_point_objective), [RTO](https://csrc.nist.gov/glossary/term/recovery_time_objective), [MTD](https://csrc.nist.gov/glossary/term/maximum_tolerable_downtime).

| Sanitization method | What it does | Example |
| --- | --- | --- |
| Clear | Overwrites through the normal interface; protects against simple recovery tools | Overwrite all user storage, factory reset |
| Purge | Makes recovery infeasible even with lab techniques, and the media can be reused | Cryptographic erase, device sanitize command, degaussing for magnetic media only |
| Destroy | Makes recovery infeasible and the media unusable | Disintegrate, incinerate, melt |

Source: [NIST SP 800-88 Rev. 2](https://csrc.nist.gov/pubs/sp/800/88/r2/final).

### Domain 4: Operations

| Port | Protocol | Port | Protocol |
| --- | --- | --- | --- |
| 20, 21 | FTP | 143 | IMAP |
| 22 | SSH, SFTP, SCP | 161, 162 | SNMP, SNMP traps |
| 23 | Telnet | 389 | LDAP |
| 25 | SMTP | 443 | HTTPS |
| 53 | DNS | 445 | SMB |
| 67, 68 | DHCP | 514 | Syslog |
| 69 | TFTP | 587 | SMTP submission |
| 80 | HTTP | 636 | LDAPS |
| 88 | Kerberos | 993, 995 | IMAPS, POP3S |
| 110 | POP3 | 1812, 1813 | RADIUS |
| 123 | NTP | 3389 | RDP |

Source: [IANA service name and port number registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml).

| Email control | What it does | Standard |
| --- | --- | --- |
| SPF | A DNS record listing the hosts allowed to send mail for a domain | [RFC 7208](https://www.rfc-editor.org/rfc/rfc7208) |
| DKIM | A signature on each message, checked with a public key published in DNS | [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376) |
| DMARC | The domain's policy for mail that fails aligned SPF or DKIM (`none`, `quarantine`, `reject`), plus reports | [RFC 9989](https://www.rfc-editor.org/rfc/rfc9989), which replaced RFC 7489 in May 2026 |

| Access control model | Who decides |
| --- | --- |
| Discretionary (DAC) | The resource owner grants access |
| Mandatory (MAC) | The system enforces labels and clearances; users cannot change them |
| Role based (RBAC) | Access follows the user's job role |
| Attribute based (ABAC) | Rules evaluate attributes of the user, resource, action, and environment |

Source: [NIST glossary: DAC](https://csrc.nist.gov/glossary/term/discretionary_access_control), [MAC](https://csrc.nist.gov/glossary/term/mandatory_access_control), [RBAC](https://csrc.nist.gov/glossary/term/role_based_access_control), [ABAC](https://csrc.nist.gov/glossary/term/attribute_based_access_control).

Evidence order of volatility, most volatile first: CPU registers and cache; routing table, ARP cache, process table, and memory; temporary file systems; disk; remote logs; physical configuration and network topology; archival media. Source: [RFC 3227](https://www.rfc-editor.org/rfc/rfc3227).

Password policy in NIST SP 800-63B-4: no composition rules such as "one symbol", no forced periodic changes, a change when there is evidence of compromise, and storage as salted hashes. Source: [NIST SP 800-63B-4](https://pages.nist.gov/800-63-4/sp800-63b.html).

### Domain 5: Risk and governance

| Term | Formula or meaning |
| --- | --- |
| SLE (single loss expectancy) | Loss from one occurrence: asset value × exposure factor |
| ARO (annualized rate of occurrence) | Expected occurrences per year |
| ALE (annualized loss expectancy) | Expected loss per year: SLE × ARO |
| Risk responses | Accept, avoid, mitigate, share, or transfer (insurance is a transfer) |

Source: [NISTIR 8286A](https://csrc.nist.gov/pubs/ir/8286/a/final), [NIST glossary: risk response](https://csrc.nist.gov/glossary/term/risk_response).

| Privacy role | Meaning under the GDPR |
| --- | --- |
| Controller | Decides why and how personal data is processed |
| Processor | Processes personal data on the controller's behalf |
| Data subject | The person the data is about |

Source: [EDPB guidelines on controller and processor](https://www.edpb.europa.eu/documents/guideline/guidelines-072020-on-the-concepts-of-controller-and-processor-in-the-gdpr_en).

## Free official resources

- [Security+ V7 exam page](https://www.comptia.org/en-us/certifications/security/v7/): exam details and the objectives summary
- [Security+ V7 sample questions](https://www.comptia.org/en-us/certifications/security/v7/practice-questions/): 10 questions from CompTIA with an answer key
- [Security+ V8 page](https://www.comptia.org/en-us/certifications/security/v8/) and the [SY0-801 objectives preview (PDF)](https://lecbyo.files.cmp.optimizely.com/download/77f3bd3223ac11f180820e495f189928)
- [CompTIA exam policies](https://www.comptia.org/en-us/resources/test-policies/), including the [retake policy](https://www.comptia.org/en-us/resources/test-policies/comptia-certification-retake-policy/) and the [candidate agreement](https://www.comptia.org/en-us/resources/test-policies/comptia-candidate-agreement/)
- [CompTIA continuing education](https://www.comptia.org/en-us/certifications/continuing-education/) for renewal after you pass
- Public references the objectives draw on: [NIST Computer Security Resource Center](https://csrc.nist.gov/), [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework), [CISA #StopRansomware Guide](https://www.cisa.gov/stopransomware/ransomware-guide), [MITRE ATT&CK](https://attack.mitre.org/), and the [OWASP Top 10](https://owasp.org/Top10/)

CompTIA's full courseware and CertMaster practice tests are paid products and not listed here.

## Practice questions

[practice-questions.md](practice-questions.md) has 15 original questions in the exam's style, weighted by domain, each with an explanation and a link to the source. For more, the [Examice SY0-701 practice bank](https://examice.com/exams/comptia/sy0-701?utm_source=github&utm_medium=social&utm_campaign=sy0-701-study-guide-and-practice-questions&utm_content=link_2) has 600+ questions with a written explanation and a discussion under each, and the first 5 questions are free, explanations included.

## Exam day tips

- You get up to 90 questions in 90 minutes. Performance-based questions take longer than multiple choice, so do not let one eat 15 minutes; answer what you can and keep moving.
- In performance-based questions, read every log line and rule before you act. Rule order matters on firewalls: the first match wins on most platforms.
- Watch qualifiers such as BEST, FIRST, and MOST. Several options can be true; the question wants the one that fits the scenario's constraint (cost, speed, least privilege).
- In incident questions, the first step after confirming an incident is usually containment, and evidence is collected from most volatile to least.
- When a question asks for a control type, decide what the control does (prevent, detect, correct) before you decide its category (technical, managerial, operational, physical).
- The 750 pass mark is a scaled score, not a percentage. Leave no question blank.

## FAQ

### How hard is SY0-701?

CompTIA recommends Network+ and two years in a security or systems administrator role before you sit it. The exam mixes multiple choice with performance-based tasks, so you need to apply concepts to logs, rules, and scenarios, not only define them. The pass mark is 750 on a scale of 100–900. Source: [Security+ V7 page](https://www.comptia.org/en-us/certifications/security/v7/).

### How long should I study?

With a year or two of IT work, about 70 hours over eight weeks, as in the plan above, is a reasonable target. Without networking experience, add two to four weeks of networking basics first, since the exam assumes knowledge at the Network+ level.

### Should I take SY0-701 or wait for SY0-801?

SY0-801 is expected on or around November 17, 2026, in English only at launch. SY0-701 in English stays available until June 11, 2027. CompTIA's Security+ page says V7 remains a strong option if you are ready now, while V8 adds coverage such as risks tied to AI. Source: [Security+ V8 page](https://www.comptia.org/en-us/certifications/security/v8/), [Security+ V7 page](https://www.comptia.org/en-us/certifications/security/v7/).

### Does Security+ expire?

Yes, after 3 years. You renew by earning 50 CEUs in the cycle and paying the $150 CE fee, or through another route such as CertMaster CE, passing a newer Security+ exam, or earning a higher certification. If it expires, you must pass the exam again. Source: [Security+ renewal requirements](https://www.comptia.org/en-us/resources/ce/renew-options/renewing-security-single/), [CE renewal fees](https://www.comptia.org/en-us/resources/ce/learn/continuing-education-renewal-fees/), [How long Security+ lasts](https://www.comptia.org/en-us/blog/how-long-does-the-comptia-security-certification-last/).

### What is the retake policy?

There is no waiting period between your first and second attempt. Before a third or later attempt, you wait at least 14 calendar days after the last one. Every attempt costs the full price, and once you pass you cannot retake the same exam code without CompTIA's consent. Source: [CompTIA retake policy](https://www.comptia.org/en-us/resources/test-policies/comptia-certification-retake-policy/).

### Does Security+ meet DoD 8140 requirements?

CompTIA's V7 page lists Security+ against DoD 8140 work roles, including cyber defense analyst, incident responder, vulnerability analyst, security control assessor, and system administrator. Check your role's requirements with your employer. Source: [Security+ V7 page](https://www.comptia.org/en-us/certifications/security/v7/).

## Contributing

Found an error or an outdated fact? Open an issue or a pull request with a link to the official source.

## License

Text and questions © Examice, licensed under [CC BY 4.0](LICENSE).

CompTIA and Security+ are trademarks or registered trademarks of CompTIA, Inc. This guide is not affiliated with or endorsed by CompTIA.
