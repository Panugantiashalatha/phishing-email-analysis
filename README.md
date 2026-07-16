# Phishing Email Analysis

## Project Overview

This project demonstrates the analysis of a suspected phishing email using industry-standard email investigation techniques. The objective was to identify indicators of phishing by examining the sender's identity, email authentication records, message headers, embedded hyperlinks, and social engineering techniques.

The investigation followed a structured methodology to determine whether the email was legitimate or malicious and to document the evidence supporting the final assessment.

---

# Objectives

* Analyse a suspected phishing email
* Verify the sender's authenticity
* Examine email authentication mechanisms (SPF, DKIM and DMARC)
* Identify malicious or suspicious hyperlinks
* Detect social engineering techniques
* Assess the overall risk presented by the email

---

# Tools Used

* MXToolbox (Email Header Analyzer)
* Email Header Analysis
* Web Browser (URL Inspection)
* Manual Threat Analysis

---

# Investigation Methodology

The following investigation process was used:

1. Obtained a phishing email sample.
2. Reviewed the sender's email address.
3. Analysed the complete email header.
4. Examined embedded hyperlinks.
5. Checked for attachments.
6. Identified persuasive or urgent language.
7. Compared displayed hyperlinks with their actual destinations.
8. Documented the findings and assessed the overall risk.

---

# Findings

## Email Subject

```
are you in the mood XGHTMTGGC
```

The subject line appears random and unrelated to any legitimate business communication, which is a common characteristic of spam and phishing campaigns.

---

## Sender Analysis

**Claimed Sender**

```
svzss@wanadoo.fr
```

Although the sender appeared to originate from the *wanadoo.fr* domain, examination of the delivery path showed the message travelled through unrelated mail servers.

### Security Observation

This behaviour suggests that the sender address was spoofed and cannot be trusted.

---

## Email Authentication Analysis

The email headers were analysed using MXToolbox.

| Authentication Check | Result |
| -------------------- | ------ |
| SPF                  | Failed |
| SPF Alignment        | Failed |
| DKIM                 | Failed |
| DKIM Alignment       | Failed |
| DMARC                | Failed |

### Security Observation

Authentication failures across SPF, DKIM and DMARC indicate that the message was not authorised by the legitimate domain owner.

This is a strong indicator of email spoofing.

---

## Embedded Links

The investigation identified two URLs:

```
http://www.great-meds.com/main2.php?nc=3D18148
```

```
http://greenzer.com/remove.php
```

### Analysis

The first link directs users to an online pharmaceutical website promoting discounted medication.

The second link is presented as an unsubscribe option. In phishing and spam campaigns, unsubscribe links are often used to confirm that an email address is active, increasing the likelihood of future spam.

No attachments were present within the email.

---

## Social Engineering Techniques

The email attempted to persuade recipients by advertising:

* Reduced prices
* Special offers
* Fast delivery
* Discreet purchasing

Rather than using threats, the attacker relied on persuasive marketing language designed to encourage immediate interaction with embedded links.

---

## URL Verification

Comparison between the visible hyperlinks and their actual destinations showed that the URLs redirected users to domains unrelated to the claimed sender.

### Security Observation

Mismatched or unrelated domains are a common phishing indicator and should always be treated as suspicious.

---

# Indicators of Compromise (IOCs)

| Indicator         | Value                                       |
| ----------------- | ------------------------------------------- |
| Subject           | are you in the mood XGHTMTGGC               |
| Claimed Sender    | [svzss@wanadoo.fr](mailto:svzss@wanadoo.fr) |
| Suspicious Domain | great-meds.com                              |
| Suspicious Domain | greenzer.com                                |
| Authentication    | SPF Failed                                  |
| Authentication    | DKIM Failed                                 |
| Authentication    | DMARC Failed                                |

---

# Risk Assessment

| Category             | Assessment  |
| -------------------- | ----------- |
| Sender Authenticity  | High Risk   |
| Email Authentication | High Risk   |
| Embedded Links       | High Risk   |
| Social Engineering   | Medium Risk |
| Overall Risk         | High        |

---

# Skills Demonstrated

* Phishing Email Analysis
* Email Header Investigation
* Email Authentication Validation
* SPF Analysis
* DKIM Analysis
* DMARC Analysis
* URL Inspection
* Threat Identification
* Security Documentation
* Technical Report Writing

---

# Key Learning Outcomes

This investigation reinforced the importance of validating sender identity using email authentication mechanisms rather than relying solely on the displayed email address.

The project also demonstrated how phishing campaigns combine spoofed identities, malicious hyperlinks and persuasive language to increase the likelihood of user interaction.

Analysing multiple indicators together provides greater confidence when determining whether an email is malicious.

---

# Conclusion

The analysed email was identified as a phishing and spam campaign based on multiple indicators, including sender spoofing, failed SPF, DKIM and DMARC authentication, suspicious external links and social engineering techniques.

The investigation demonstrates a structured approach to phishing analysis and highlights the importance of validating email authenticity before interacting with embedded content. Users should avoid clicking suspicious links, refrain from replying to the message and report the email through the appropriate security channels before deleting it.
