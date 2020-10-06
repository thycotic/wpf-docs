[title]: # (Checkmarx Results)
[tags]: # (WPF)
[priority]: # (101)
# Checkmarx Results

![logo](images/checkmarx-brand.png "Checkmarx Company Logo")

Based on the report results there are no Medium/High issues found, and nothing confirmed as valid issues.

>**Note**: The output file was edited to remove any unconfirmed and non-exploitable issues.

## Thycotic Integrations Web Password Filler Scan Report

* Project Name: Thycotic.Integrations.WebPasswordFiller
* Scan Start: Tuesday, September 15, 2020 1:36:52 AM
* Preset: Checkmarx Default
* Scan Time: 00h:09m:34s
* Lines Of Code Scanned: 112606
* Files Scanned: 212
* Report Creation Time Tuesday, September 15, 2020 1:53:44 AM 
* Online Results: [http://WIN-282IB73823V/CxWebClient/ViewerMain.aspx?scanid=1096154&projectid=128](http://win-282ib73823v/CxWebClient/ViewerMain.aspx?scanid=1096154&projectid=128)
* Team: CxServer
* Checkmarx Version: 8.8.0.72 HF9
* Scan Type: Full
* Source Origin: GIT
* Density: 0/100 (Vulnerabilities/LOC)
* Visibility: Public

### Filter Settings

#### Severity

* Included: High, Medium 
* Excluded: Low, Information

#### Result State

* Included: Confirmed
* Excluded: Not Exploitable, To Verify, Urgent, Proposed Not Exploitable

#### Assigned to

* Included: All

#### Categories

* Included:
  * Uncategorized: All
  * Custom: All
  * PCI DSS v3.2: All
  * OWASP Top 10 2013: All
  * FISMA 2014:  All
  * NIST SP 800-53:  All
  * OWASP Top 10 2017:  All
  * OWASP Mobile Top 10 2016: All

* Excluded:
  * Uncategorized: None
  * Custom: None
  * PCI DSS v3.2: None
  * OWASP Top 10 2013: None
  * FISMA 2014: None
  * NIST SP 800-53: None
  * OWASP Top 10 2017: None
  * OWASP Mobile Top 10 2016: None

#### Results Limit

Results limit per query was set to 500.

### Selected Queries

Queries cannot be displayed because the report contains no results.

| Category | Threat Agent  | Exploitability | Weakness Prevalence | Weakness Detectability | Technical Impact | Business Impact | Issues Found | Best Fix Locations [^1] |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| A1-Injection [^2] | App. Specific | EASY    | COMMON   | EASY | SEVERE    | App. Specific   | 0 | 0 |
| A2-Broken Authentication [^2]  | App. Specific | EASY    | COMMON   | AVERAGE | SEVERE    | App. Specific   | 0 | 0 |
| A3-Sensitive Data Exposure [^2]   | App. Specific | AVERAGE | WIDESPREAD   | AVERAGE | SEVERE    | App. Specific   | 0 | 0 |
| A4-XML External Entities (XXE)  | App. Specific | AVERAGE | COMMON   | EASY | SEVERE    | App. Specific   | 0 | 0 |
| A5-Broken Access Control [^2]  | App. Specific | AVERAGE | COMMON   | AVERAGE | SEVERE    | App. Specific   | 0 | 0 |
| A6-Security Misconfiguration | App. Specific | EASY    | WIDESPREAD   | EASY | MODERATE  | App. Specific   | 0 | 0 |
| A7-Cross-Site Scripting (XSS) [^2]| App. Specific | EASY    | WIDESPREAD   | EASY | MODERATE  | App. Specific   | 0 | 0 |
| A8-Insecure Deserialization  | App. Specific | DIFFICULT   | COMMON   | AVERAGE | SEVERE    | App. Specific   | 0 | 0 |
| A9-Using Components with Known Vulnerabilities [^2] | App. Specific | AVERAGE | WIDESPREAD   | AVERAGE | MODERATE  | App. Specific   | 0 | 0 |
| A10-Insufficient Logging & Monitoring| App. Specific | AVERAGE | WIDESPREAD   | DIFFICULT   | MODERATE  | App. Specific   | 0 | 0 |

[^1] Best fix location values are absolute values derived from the entire vulnerabilities detected.

[^2] Project scan results do not include all relevant queries. Presets and\\or Filters should be changed to include all relevant standard queries.

| Category | Threat Agent  | Attack Vectors | Weakness Prevalence | Weakness Detectability | Technical Impact | Business Impact  | Issues Found | Best Fix Locations [^1] |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| A1-Injection [^2] | EXTERNAL, INTERNAL, ADMIN USERS | EASY | COMMON | AVERAGE | SEVERE | ALL DATA | 0 | 0 |
| A2-Broken Authentication and Session Management [^2] | EXTERNAL, INTERNAL USERS | AVERAGE | WIDESPREAD   | AVERAGE | SEVERE    | AFFECTED DATA AND FUNCTIONS | 0 | 0 |
| A3-Cross-Site Scripting (XSS) [^2] | EXTERNAL, INTERNAL, ADMIN USERS  | AVERAGE | VERY WIDESPREAD  | EASY | MODERATE  | AFFECTED DATA AND SYSTEM | 0 | 0 |
| A4-Insecure Direct Object References [^2] | SYSTEM USERS  | EASY    | COMMON   | EASY | MODERATE  | EXPOSED DATA | 0 | 0 |
| A5-Security Misconfiguration  | EXTERNAL, INTERNAL, ADMIN USERS  | EASY    | COMMON   | EASY | MODERATE  | ALL DATA AND SYSTEM  | 0 | 0 |
| A6-Sensitive Data Exposure [^2] | EXTERNAL, INTERNAL, ADMIN USERS, USERS BROWSERS | DIFFICULT   | UNCOMMON | AVERAGE | SEVERE    | EXPOSED DATA | 0 | 0 |
| A7-Missing Function Level Access Control | EXTERNAL, INTERNAL USERS | EASY    | COMMON   | AVERAGE | MODERATE  | EXPOSED DATA AND FUNCTIONS  | 0 | 0 |
| A8-Cross-Site Request Forgery (CSRF)  | USERS BROWSERS    | AVERAGE | COMMON   | EASY | MODERATE  | AFFECTED DATA AND FUNCTIONS | 0 | 0 |
| A9-Using Components with Known Vulnerabilities   | EXTERNAL USERS, AUTOMATED TOOLS  | AVERAGE | WIDESPREAD   | DIFFICULT   | MODERATE  | AFFECTED DATA AND FUNCTIONS | 0 | 0 |
| A10-Unvalidated Redirects and Forwards| USERS BROWSERS    | AVERAGE | WIDESPREAD   | DIFFICULT   | MODERATE  | AFFECTED DATA AND FUNCTIONS | 0 | 0 |

[^1] Best fix location values are absolute values derived from the entire vulnerabilities detected.

[^2] Project scan results do not include all relevant queries. Presets and\\or Filters should be changed to include all relevant standard queries.

| Category  | Issues Found | Best Fix Locations [^1] |
| ----- ----------------------|--------------|--------------------------|
| PCI DSS (3.2) - 6.5.1 - Injection flaws - particularly SQL injection [^2]  | 0 | 0 |
| PCI DSS (3.2) - 6.5.2 - Buffer overflows    | 0 | 0 |
| PCI DSS (3.2) - 6.5.3 - Insecure cryptographic storage [^2] | 0 | 0 |
| PCI DSS (3.2) - 6.5.4 - Insecure communications [^2]  | 0 | 0 |
| PCI DSS (3.2) - 6.5.5 - Improper error handling | 0 | 0 |
| PCI DSS (3.2) - 6.5.7 - Cross-site scripting (XSS) [^2]  | 0 | 0 |
| PCI DSS (3.2) - 6.5.8 - Improper access control | 0 | 0 |
| PCI DSS (3.2) - 6.5.9 - Cross-site request forgery  | 0 | 0 |
| PCI DSS (3.2) - 6.5.10 - Broken authentication and session management [^2] | 0 | 0 |

* [^1] Best fix location values are absolute values derived from the entire vulnerabilities detected.
* [^2] Project scan results do not include all relevant queries. Presets and\\or Filters should be changed to include all relevant standard queries.

### Scan Summary - FISMA 2014

| Category | Description | Issues Found | Best Fix Locations [^1] |
| ----- | ----- | ----- | ----- |
| Access Control [^2] | Organizations must limit information system access to authorized users, processes acting on behalf of authorized users, or devices (including other information systems) and to the types of transactions and functions that authorized users are permitted to exercise. | 0 | 0 |
| Audit And Accountability | Organizations must: (i) create, protect, and retain information system audit records to the extent needed to enable the monitoring, analysis, investigation, and reporting of unlawful, unauthorized, or inappropriate information system activity; and (ii) ensure that the actions of individual information system users can be uniquely traced to those users so they can be held accountable for their actions. | 0 | 0 |
| Configuration Management [^2] | Organizations must: (i) establish and maintain baseline configurations and inventories of organizational information systems (including hardware, software, firmware, and documentation) throughout the respective system development life cycles; and (ii) establish and enforce security configuration settings for information technology products employed in organizational information systems. | 0 | 0 |
| Identification And Authentication [^2] | Organizations must identify information system users, processes acting on behalf of users, or devices and authenticate (or verify) the identities of those users, processes, or devices, as a prerequisite to allowing access to organizational information systems. | 0 | 0 |
| Media Protection [^2] | Organizations must: (i) protect information system media, both paper and digital; (ii) limit access to information on information system media to authorized users; and (iii) sanitize or destroy information system media before disposal or release for reuse. | 0 | 0 |
| System And Communications Protection [^2] | Organizations must: (i) monitor, control, and protect organizational communications (i.e., information transmitted or received by organizational information systems) at the external boundaries and key internal boundaries of the information systems; and (ii) employ architectural designs, software development techniques, and systems engineering principles that promote effective information security within organizational information systems. | 0 | 0 |
| System And Information Integrity [^2] | Organizations must: (i) identify, report, and correct information and information system flaws in a timely manner; (ii) provide protection from malicious code at appropriate locations within organizational information systems; and (iii) monitor information system security alerts and advisories and take appropriate actions in response. | 0 | 0 |

* [^1] Best fix location values are absolute values derived from the entire  vulnerabilities detected.
* [^2] Project scan results do not include all relevant queries. Presets and\\or Filters should be changed to include all relevant standard queries.

### Scan Summary - NIST SP 800-53

| Category | Issues Found | Best Fix Locations [^1] |
| ----- | ----- | ----- |
| AC-12 Session Termination (P2) | 0 | 0 |
| AC-3 Access Enforcement (P1) | 0 | 0 |
| AC-4 Information Flow Enforcement (P1) | 0 | 0 |
| AC-6 Least Privilege (P1) | 0 | 0 |
| AU-9 Protection of Audit Information (P1) | 0 | 0 |
| CM-6 Configuration Settings (P2) | 0 | 0 |
| IA-5 Authenticator Management (P1) | 0 | 0 |
| IA-6 Authenticator Feedback (P2) | 0 | 0 |
| IA-8 Identification and Authentication (Non-Organizational Users) (P1) | 0 | 0 |
| SC-12 Cryptographic Key Establishment and Management (P1) | 0 | 0 |
| SC-13 Cryptographic Protection (P1) | 0 | 0 |
| SC-17 Public Key Infrastructure Certificates (P1) | 0 | 0 |
| SC-18 Mobile Code (P2) [^2] | 0 | 0 |
| SC-23 Session Authenticity (P1) | 0 | 0 |
| SC-28 Protection of Information at Rest (P1) [^2] | 0 | 0 |
| SC-4 Information in Shared Resources (P1) | 0 | 0 |
| SC-5 Denial of Service Protection (P1) | 0 | 0 |
| SC-8 Transmission Confidentiality and Integrity (P1) [^2] | 0 | 0 |
| SI-10 Information Input Validation (P1) [^2] | 0 | 0 |
| SI-11 Error Handling (P2) | 0 | 0 |
| SI-15 Information Output Filtering (P0) [^2] | 0 | 0 |
| SI-16 Memory Protection (P1) | 0 | 0 |

* [^1] Best fix location values are absolute values derived from the entire vulnerabilities detected.
* [^2] Project scan results do not include all relevant queries. Presets and\\or Filters should be changed to include all relevant standard queries.

### Scan Summary - OWASP Mobile Top 10 2016

| Category | Description  | Issues Found | Best Fix Locations [^1] |
| ----- | ----- | ----- | ----- |
| M1-Improper Platform Usage | This category covers misuse of a platform feature or failure to use platform security controls. It might include Android intents, platform permissions, misuse of TouchID, the Keychain, or some other security control that is part of the mobile operating system. There are several ways that mobile apps can experience this risk. | 0 | 0 |
| M2-Insecure Data Storage [^2] | This category covers insecure data storage and unintended data leakage.   | 0 | 0 |
| M3-Insecure Communication  | This category covers poor handshaking, incorrect SSL versions, weak negotiation, cleartext communication of sensitive assets, etc. | 0 | 0 |
| M4-Insecure Authentication [^2] | This category captures notions of authenticating the end user or bad session management. This can include: a. Failing to identify the user at all when that should be required, b. Failure to maintain the user's identity when it is required, c. Weaknesses in session management | 0 | 0 |
| M5-Insufficient Cryptography | The code applies cryptography to a sensitive information asset. However, the cryptography is insufficient in some way. Note that anything and everything related to TLS or SSL goes in M3. Also, if the app fails to use cryptography at all when it should, that probably belongs in M2. This category is for issues where cryptography was attempted, but it wasn't done correctly. | 0 | 0 |
| M6-Insecure Authorization | This is a category to capture any failures in authorization (e.g., authorization decisions in the client side, forced browsing, etc.). It is distinct from authentication issues (e.g., device enrolment, user identification, etc.). If the app does not authenticate users at all in a situation where it should (e.g., granting anonymous access to some resource or service when authenticated and authorized access is required), then that is an authentication failure not an authorization failure. | 0 | 0 |
| M7-Client Code Quality [^2] | This category is the catch-all for code-level implementation problems in the mobile client. That's distinct from server-side coding mistakes. This would capture things like buffer overflows, format string vulnerabilities, and various other code- level mistakes where the solution is to rewrite some code that's running on the mobile device. | 0 | 0 |
| M8-Code Tampering [^2] | This category covers binary patching, local resource modification, method hooking, method swizzling, and dynamic memory modification. Once the application is delivered to the mobile device, the code and data resources are resident there. An attacker can either directly modify the code, change the contents of memory dynamically, change or replace the system APIs that the application uses, or modify the application's data and resources. This can provide the attacker a direct method of subverting the intended use of the software for personal or monetary gain. | 0 | 0 |
| M9-Reverse Engineering [^2] | This category includes analysis of the final core binary to determine its source code, libraries, algorithms, and other assets. Software such as IDA Pro, Hopper, otool, and other binary inspection tools give the attacker insight into the inner workings of the application. This may be used to exploit other nascent vulnerabilities in the application, as well as revealing information about back end servers, cryptographic constants and ciphers, and intellectual property. | 0 | 0 |
| M10-Extraneous Functionality | Often, developers include hidden backdoor functionality or other internal development security controls that are not intended to be released into a production environment. For example, a developer may accidentally include a password as a comment in a hybrid app. Another example includes disabling of 2-factor authentication during testing. | 0 | 0 |

* [^1] Best fix location values are absolute values derived from the entire vulnerabilities detected.
* [^2] Project scan results do not include all relevant queries. Presets and\\or Filters should be changed to include all relevant standard queries.

### Scan Summary - Custom

| Category   | Issues Found | Best Fix Locations [^1] |
| ----- | ----- | ----- |
| Must audit | 0 | 0 |
| Check   | 0 | 0 |
| Optional   | 0 | 0 |

[^1]: Best fix location values are absolute values derived from the entire vulnerabilities detected.
