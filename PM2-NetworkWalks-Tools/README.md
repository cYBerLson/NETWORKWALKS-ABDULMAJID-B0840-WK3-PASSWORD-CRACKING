# Week 3 — PM2: Password Cracking with NetworkWalks Tools

**NetworkWalks Cybersecurity Internship | Password Security Assessment**

## Overview

This project demonstrates offline password recovery using the NetworkWalks Hash Calculator and Password Cracker.

The assessment involved extracting a password-verification hash from an encrypted PDF, performing a dictionary-based attack, recovering the password, and validating the result against the original document.

Having previously worked with John the Ripper through Kali Linux and Johnny GUI on Windows, I used this module to examine an alternative browser-based workflow for PDF password recovery.

## Tools and Environment

| Tool | Purpose |
|---|---|
| NetworkWalks Hash Calculator | Extraction of PDF password hashes |
| NetworkWalks Password Cracker | Dictionary-based password recovery |
| Google Chrome | Access to the browser-based security tools |
| Adobe Acrobat Reader | Validation of the recovered password |
| Windows | Host operating system |

## Methodology

### 1. Target File Preparation

Obtained the password-protected PDF supplied for the NetworkWalks practical assessment.

**Target:** `My-Locked-PDF1.pdf`

The objective was to recover the document password and confirm successful access to its encrypted contents.

### 2. PDF Hash Extraction

Accessed the NetworkWalks Hash Calculator:

https://networkwalks.com/hash-calculator/

Selected the PDF analysis option and loaded the encrypted document.

The tool successfully extracted a password hash in a format compatible with common password-recovery utilities.

**Extracted hash characteristics:**

- Format: `$pdf$`
- PDF revision: R4
- PDF version: V4
- Encryption key length: 128 bits

The extracted hash was used as the input for the password-recovery stage.

### 3. Dictionary-Based Password Recovery

Accessed the NetworkWalks Password Cracker:

https://networkwalks.com/password-cracker/

Submitted the extracted PDF hash and executed the dictionary attack.

The utility tested password candidates against the extracted hash until a matching candidate was identified.

**Observed results:**

| Metric | Result |
|---|---|
| Attack technique | Dictionary attack |
| Password candidates tested | 91 |
| Dictionary size | 100 candidates |
| Recovery status | Successful |
| Recovered password | `password1` |

The password was recovered after testing 91 candidates from the available dictionary.

### 4. Password Verification

Opened the original encrypted PDF in Adobe Acrobat Reader and supplied the recovered password:

`password1`

The document opened successfully, confirming that the recovered credential was valid.

### 5. Flag Capture

After successfully accessing the protected document, I located the NetworkWalks verification flag displayed inside the PDF.

This confirmed successful completion of the practical password-recovery exercise.

## Evidence and Screenshots

### Evidence 1 — PDF Hash Extraction

![PDF Hash Extraction](screenshots/W3-PM2-PDF-Hash-Extracted.png)

*Figure 1: Extracting the encrypted PDF's password hash using the NetworkWalks Hash Calculator.*

### Evidence 2 — Successful Dictionary Attack

![Password Cracked](screenshots/W3-PM2-Password-Cracked.png)

*Figure 2: NetworkWalks Password Cracker identifying a matching password candidate through a dictionary attack.*

### Evidence 3 — PDF Verification and Flag Capture

![PDF Flag Captured](screenshots/W3-PM2-PDF-Flag-Captured.png)

*Figure 3: Verification of the recovered password and successful access to the protected PDF.*

## Project Structure

```text
PM2-NetworkWalks-Tools/
├── README.md
└── screenshots/
    ├── W3-PM2-PDF-Hash-Extracted.png
    ├── W3-PM2-Password-Cracked.png
    └── W3-PM2-PDF-Flag-Captured.png
```

## Technical Analysis

### Offline Password Recovery

The assessment demonstrates how extracted password-verification material can be tested against candidate passwords without requiring repeated authentication attempts against the original document.

This is a relevant consideration when assessing the security of encrypted files that may be exposed or obtained by an unauthorized party.

### Dictionary Attack Effectiveness

The recovered password, `password1`, demonstrates the weakness of predictable credentials.

The successful recovery within a relatively small dictionary highlights the importance of password unpredictability, rather than relying solely on file encryption.

### Hash Extraction and Password Recovery

Hash extraction and password cracking are distinct stages of the assessment.

The Hash Calculator extracted the PDF's password-verification data, while the Password Cracker tested candidate passwords against that data.

Successful extraction alone does not mean that the password has been recovered.

### Verification

The final validation against the original encrypted PDF was important because it confirmed that the recovered candidate could actually unlock the target document.

## Security Recommendations

- Use long, unique and randomly generated passwords for sensitive documents.
- Avoid common passwords and predictable variations.
- Prefer current, robust document encryption standards.
- Restrict access to encrypted documents and their extracted password hashes.
- Perform authorized password-security assessments to identify weak credentials.
- Avoid submitting confidential documents or sensitive hashes to untrusted online services.

## Conclusion

Successfully completed the NetworkWalks Week 3 Project Module 2 password-security assessment.

The exercise covered PDF hash extraction, dictionary-based password recovery, credential verification and successful access to the protected document.

The practical also provided an opportunity to compare browser-based password-recovery utilities with my previous experience using John the Ripper in Linux and Windows environments.

All testing was performed against the authorized training document provided for the internship.

---

**Program:** NetworkWalks Cybersecurity Internship  
**Module:** Week 3 — Project Module 2  
**Category:** Ethical Hacking / Password Security Assessment  
**Environment:** Windows  
**Status:** Completed