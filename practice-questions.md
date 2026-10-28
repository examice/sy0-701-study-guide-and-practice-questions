# SY0-701 practice questions

Fifteen original practice questions for CompTIA Security+ SY0-701, spread across the five domains by their weight in the [exam objectives](https://www.comptia.org/en-us/certifications/security/v7/): 2 on general security concepts, 3 on threats, vulnerabilities, and mitigations, 3 on security architecture, 4 on security operations, and 3 on program management and oversight. Each answer explains why the right option is right, why the others are wrong, and links the NIST, IETF, OWASP, MITRE, CISA, or vendor source behind it.

> Unofficial study notes by Examice. Not affiliated with or endorsed by CompTIA. The practice questions are original and not taken from the exam.

### Question 1

*Domain 1: General security concepts*

A plant runs a production controller on an operating system the vendor no longer patches. Replacing it would halt production for months. The security team moves the controller to its own network segment and allows traffic only from one engineering workstation. How is this control best classified?

- A. Corrective
- B. Deterrent
- C. Compensating
- D. Directive

<details><summary>Show answer</summary>

**C.** A compensating control is an alternative that gives comparable protection when the normal control (here, patching) is not possible. Isolating the system and limiting who can reach it reduces the risk the missing patches create.

- A is wrong because a corrective control restores things after an event, such as restoring from backup.
- B is wrong because a deterrent discourages an attacker, such as a warning banner; segmentation blocks traffic rather than discouraging it.
- D is wrong because a directive control tells people what to do, such as a policy.

Source: [NIST glossary: compensating controls](https://csrc.nist.gov/glossary/term/compensating_controls)

</details>

### Question 2

*Domain 1: General security concepts*

Your company publishes installer packages for download. Customers must be able to confirm that a package came from your company and was not changed after release. Which approach meets both needs?

- A. Encrypt each package with the customers' public keys.
- B. Publish a SHA-256 hash of each package on the download page.
- C. Encrypt each package with a symmetric key and email the key to customers.
- D. Sign each package with the company's private key, and let customers verify it with the public key in the company's certificate.

<details><summary>Show answer</summary>

**D.** A digital signature proves both integrity and origin: only the holder of the private key can produce it, and anyone with the matching public key can check it. If a single byte changes, verification fails.

- A protects confidentiality for each customer and proves nothing about who built the package; it also does not scale to public downloads.
- B shows integrity only if the page itself is trusted. An attacker who can replace the package on the same site can usually replace the hash too, and a hash does not identify the publisher.
- C is about confidentiality, and anyone with the emailed key could alter and encrypt a package.

Source: [FIPS 186-5, Digital Signature Standard](https://csrc.nist.gov/pubs/fips/186-5/final)

</details>

### Question 3

*Domain 2: Threats, vulnerabilities, and mitigations*

Over two hours, the SIEM shows one external IP address trying to sign in to 600 different accounts. Most accounts see a single attempt, almost all with the password `Autumn2026`, and few accounts lock out. Which attack is this?

- A. Brute force against individual accounts
- B. Password spraying
- C. Credential stuffing
- D. Offline cracking with rainbow tables

<details><summary>Show answer</summary>

**B.** Password spraying tries one or a few common passwords across many accounts, staying under the lockout threshold of each one. One password, hundreds of accounts, and few lockouts is the pattern.

- A is wrong because brute force tries many passwords against one account, which would trigger lockouts quickly.
- C is wrong because credential stuffing uses username and password pairs leaked from another breach, so the password would differ from account to account.
- D is wrong because offline cracking runs against stolen hashes and produces no sign-in attempts at all.

Source: [MITRE ATT&CK T1110.003, Password Spraying](https://attack.mitre.org/techniques/T1110/003/)

</details>

### Question 4

*Domain 2: Threats, vulnerabilities, and mitigations*

A penetration test finds that entering `' OR '1'='1` in a login form returns every row of the users table. The developers want to fix the root cause. What should they do?

- A. Add a web application firewall rule that blocks single quotes.
- B. Hide database error messages from users.
- C. Rewrite the queries as prepared statements with parameterized queries.
- D. Write a function that escapes quotes in the input before it is concatenated into the query.

<details><summary>Show answer</summary>

**C.** OWASP lists prepared statements with parameterized queries as the first primary defense against SQL injection. The database receives the query structure and the user's data separately, so input can never change the meaning of the query.

- A blocks one pattern at the edge and leaves the flaw in the code; a firewall is a useful extra layer, not a fix.
- B removes a clue for the attacker but leaves the injection fully working.
- D is the approach OWASP strongly discourages: escaping rules differ by database and context, and one missed case reopens the hole.

Source: [OWASP SQL Injection Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html)

</details>

### Question 5

*Domain 2: Threats, vulnerabilities, and mitigations*

Accounts payable receives an email from the real email address of a supplier it has paid for years. It asks to change the supplier's bank account before Friday's payment run. You suspect the supplier's mailbox has been compromised. What should the clerk do?

- A. Reply to the email and ask the supplier to confirm the change.
- B. Call the phone number in the email's signature to confirm.
- C. Make the change so the payment is on time, then confirm with the supplier next week.
- D. Call the supplier at the phone number already on file in the vendor record, and change nothing until they confirm.

<details><summary>Show answer</summary>

**D.** This is the classic business email compromise pattern: an account change request, urgency, and a message from a mailbox that may be in the attacker's hands. Both CISA and the FBI's IC3 advise confirming through a separate channel, using contact details you already trust rather than any in the message.

- A sends the confirmation request to the mailbox the attacker may control.
- B uses contact details supplied by the suspicious message itself, which the attacker can change.
- C pays first and checks later, which is exactly how BEC losses happen.

Source: [IC3: business email compromise](https://www.ic3.gov/CrimeInfo/BEC), [CISA: avoiding social engineering and phishing attacks](https://www.cisa.gov/news-events/news/avoiding-social-engineering-and-phishing-attacks)

</details>

### Question 6

*Domain 3: Security architecture*

Your company runs a web application on virtual machines from an IaaS provider. An audit finds that the guest operating systems are months behind on security patches. Who is responsible for patching them?

- A. The provider, because it runs the hypervisor
- B. The customer, because in IaaS the customer manages the operating system
- C. Both parties equally, so whoever notices first
- D. The provider, as part of physical host maintenance

<details><summary>Show answer</summary>

**B.** In the shared responsibility model, IaaS moves the physical datacenter, network, hosts, and hypervisor to the provider, while the customer keeps the operating system, applications, data, and identities. Guest OS patching is the customer's job.

- A confuses the hypervisor, which the provider runs, with the guest OS inside the VM, which the customer runs.
- C is wrong because the operating system is not a shared area in IaaS; the matrix assigns it to the customer.
- D is wrong because physical host maintenance stops at the hardware and hypervisor.

Source: [Microsoft: shared responsibility in the cloud](https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility), [AWS shared responsibility model](https://aws.amazon.com/compliance/shared-responsibility-model/)

</details>

### Question 7

*Domain 3: Security architecture*

A business impact analysis for the order database finds that the company can lose at most 15 minutes of orders, and the database must be back in service within 4 hours of an outage. Which pair of values does this set?

- A. RTO of 15 minutes and RPO of 4 hours
- B. MTBF of 15 minutes and MTTR of 4 hours
- C. RPO of 15 minutes and RTO of 4 hours
- D. MTD of 15 minutes and RPO of 4 hours

<details><summary>Show answer</summary>

**C.** The recovery point objective is how far back you can afford to restore, which sets how much data you can lose: 15 minutes. The recovery time objective is how long the system can stay down: 4 hours. In practice, backups or replication must run at least every 15 minutes.

- A swaps the two terms.
- B uses reliability metrics: MTBF measures average time between failures and MTTR the average repair time; neither is a business requirement for data loss.
- D misuses both terms: MTD is the total outage the business will accept, which must be longer than the RTO, and RPO is about data, not time to restore.

Source: [NIST glossary: recovery point objective](https://csrc.nist.gov/glossary/term/recovery_point_objective), [recovery time objective](https://csrc.nist.gov/glossary/term/recovery_time_objective), [NIST SP 800-34 Rev. 1](https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final)

</details>

### Question 8

*Domain 3: Security architecture*

Your company will donate 200 laptops whose SSDs encrypt all data in hardware. The data must be unrecoverable even with laboratory techniques, and the drives must stay usable for the charity. Which method fits?

- A. Purge with cryptographic erase or the drive's built-in sanitize command
- B. Degauss the drives
- C. Run a quick format
- D. Shred the drives

<details><summary>Show answer</summary>

**A.** NIST SP 800-88 defines purge as making recovery infeasible with state-of-the-art laboratory techniques while leaving the media reusable. Cryptographic erase destroys the encryption key, so the stored data becomes unreadable at once; standard device sanitize commands are also purge techniques.

- B is wrong because degaussing works only on magnetic media; NIST says it should not be used on flash storage such as SSDs.
- C leaves the data on the drive; a quick format rewrites file system structures and does not overwrite user data.
- D destroys the drive, which fails the requirement that the charity can use it.

Source: [NIST SP 800-88 Rev. 2](https://csrc.nist.gov/pubs/sp/800/88/r2/final)

</details>

### Question 9

*Domain 4: Security operations*

A firewall between the admin network and the server network must allow only two things: encrypted remote shell access to Linux servers, and directory queries using LDAP over TLS on its dedicated port. Which two ports should the rule allow? Choose two.

- A. 23
- B. 22
- C. 389
- D. 636

<details><summary>Show answer</summary>

**B and D.** SSH, the encrypted remote shell, uses port 22. LDAP over TLS on its own port (LDAPS) uses 636.

- A is Telnet, a remote shell that sends everything, passwords included, in clear text.
- C is plain LDAP. It can be upgraded with StartTLS, but the question asks for the dedicated TLS port, which is 636.

Source: [IANA service name and port number registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)

</details>

### Question 10

*Domain 4: Security operations*

A developer building a new login service asks how to store user passwords. Which option follows NIST SP 800-63B-4?

- A. Store a salted hash made with a password hashing scheme that has a cost factor.
- B. Store an unsalted SHA-256 hash of each password.
- C. Encrypt each password with AES-256 and keep the key in the application's configuration file.
- D. Store the passwords in plain text in a column only database administrators can read.

<details><summary>Show answer</summary>

**A.** NIST requires that passwords be salted and hashed with a suitable password hashing scheme, which takes the password, a salt, and a cost factor. The salt defeats precomputed tables, and the cost factor makes each guess expensive for an attacker who steals the hashes.

- B is fast to compute and has no salt, so identical passwords produce identical hashes and precomputed tables work.
- C is reversible: anyone who gets the server, and with it the key, gets every password.
- D relies only on access control; one breach or one rogue administrator exposes every password.

Source: [NIST SP 800-63B-4](https://pages.nist.gov/800-63-4/sp800-63b.html)

</details>

### Question 11

*Domain 4: Security operations*

A Linux server is suspected of running malware that lives only in memory. You have authorization to collect evidence. What should you do first?

- A. Capture a memory image, then image the disk.
- B. Power off the server to preserve the disk.
- C. Image the disk, then reboot the server to collect its logs.
- D. Copy the server's data from the remote syslog server.

<details><summary>Show answer</summary>

**A.** Evidence should be collected from most volatile to least volatile. Memory, with its running processes and network state, disappears at shutdown, so it comes before the disk. Malware that lives only in memory leaves little or nothing on disk.

- B destroys the memory contents, which is where the evidence is.
- C reboots the server, which also wipes memory.
- D collects remote logs, which RFC 3227 places well down the list; they will still be there after you capture memory.

Source: [RFC 3227, Guidelines for Evidence Collection and Archiving](https://www.rfc-editor.org/rfc/rfc3227)

</details>

### Question 12

*Domain 4: Security operations*

Attackers are sending fake invoices that put your domain in the From address. You publish SPF and sign outgoing mail with DKIM, yet some receiving servers still deliver the fakes to inboxes. What should you publish so receivers reject messages that fail authentication and send you reports?

- A. More IP addresses in the SPF record
- B. New DKIM keys
- C. A requirement for TLS on outbound SMTP
- D. A DMARC record with `p=reject` and a `rua` address for aggregate reports

<details><summary>Show answer</summary>

**D.** DMARC ties SPF and DKIM results to the domain in the From address and lets the domain owner state a policy (`none`, `quarantine`, or `reject`) for mail that fails, plus where to send reports. Without it, each receiver decides on its own what to do with a failure.

- A authorizes more senders; it does nothing about mail from senders that are not authorized.
- B refreshes your signing keys, but spoofed mail is not signed with your key at all, and receivers still lack a policy for it.
- C encrypts mail in transit and does not authenticate who sent it.

Source: [RFC 9989, DMARC](https://www.rfc-editor.org/rfc/rfc9989), [RFC 7208, SPF](https://www.rfc-editor.org/rfc/rfc7208), [RFC 6376, DKIM](https://www.rfc-editor.org/rfc/rfc6376)

</details>

### Question 13

*Domain 5: Security program management and oversight*

After a ransomware tabletop exercise, the board buys a cyber insurance policy that covers recovery costs and lost revenue, rather than funding more controls for now. Which risk response is this?

- A. Acceptance
- B. Avoidance
- C. Transfer
- D. Mitigation

<details><summary>Show answer</summary>

**C.** Buying insurance shifts the financial impact of the risk to another party. NIST lists the risk responses as accepting, avoiding, mitigating, sharing, or transferring the risk.

- A means taking on the risk knowingly with no further action, but the board did act by buying a policy.
- B means stopping the activity that creates the risk, such as shutting down the exposed system.
- D means adding controls to reduce likelihood or impact, which the board chose not to fund.

Source: [NIST glossary: risk response](https://csrc.nist.gov/glossary/term/risk_response)

</details>

### Question 14

*Domain 5: Security program management and oversight*

A warehouse system is valued at $400,000. A flood would destroy 25% of its value, and the site expects one flood every 4 years. What is the annualized loss expectancy (ALE)?

- A. $100,000
- B. $25,000
- C. $400,000
- D. $50,000

<details><summary>Show answer</summary>

**B.** The single loss expectancy is the asset value times the exposure factor: $400,000 × 0.25 = $100,000. One flood every 4 years is an annualized rate of occurrence of 0.25. ALE = SLE × ARO = $100,000 × 0.25 = $25,000.

- A is the SLE, the loss from one flood, not the loss per year.
- C is the full asset value.
- D uses an ARO of 0.5, one flood every 2 years.

Source: [NISTIR 8286A](https://csrc.nist.gov/pubs/ir/8286/a/final), which defines SLE as the loss per occurrence and ALE as the loss over a year

</details>

### Question 15

*Domain 5: Security program management and oversight*

A retailer hires a payroll company to calculate and pay employee salaries. The payroll company processes the employees' personal data only on the retailer's instructions and for that purpose. Under the GDPR, what are their roles?

- A. The retailer is the controller, and the payroll company is the processor.
- B. The retailer is the processor, and the payroll company is the controller.
- C. Both are joint controllers by default.
- D. The payroll company is the data subject.

<details><summary>Show answer</summary>

**A.** The controller decides why and how personal data is processed; the processor handles it on the controller's behalf. The retailer set the purpose (paying its staff), and the payroll company acts on its instructions.

- B reverses the roles.
- C would apply only if both parties decided the purposes and means together, which the scenario rules out.
- D is wrong because the data subjects are the employees whose data is processed.

Source: [EDPB guidelines 07/2020 on controller and processor](https://www.edpb.europa.eu/documents/guideline/guidelines-072020-on-the-concepts-of-controller-and-processor-in-the-gdpr_en)

</details>

## More practice

The [Examice SY0-701 practice bank](https://examice.com/exams/comptia/sy0-701?utm_source=github&utm_medium=social&utm_campaign=sy0-701-study-guide-and-practice-questions&utm_content=link_3) has 600+ questions in this style, each with a written explanation and a discussion. The first 5 questions are free, explanations included.
