# Week 3 — Password Security Assessment & AI-Assisted Security Testing

**NetworkWalks Cybersecurity Internship | Ethical Hacking & Password Recovery**

## Overview

Week 3 focused on practical password-security assessments across Windows, Kali Linux and AI-integrated security tooling.

I completed both compulsory project modules and an additional AI-assisted password-recovery exercise. The assessments involved extracting password-verification hashes from encrypted PDF documents, performing dictionary-based recovery, validating recovered credentials and capturing verification flags.

The work covered three approaches:

- **PM1:** John the Ripper using Johnny GUI on Windows.
- **PM2:** Browser-based hash extraction and password recovery using NetworkWalks tools.
- **Optional Project 1:** AI-assisted password recovery through Claude Desktop, HexStrike MCP and John the Ripper on Kali Linux.

## Completed Projects

| Module | Tools / Environment | Status |
|---|---|---|
| [PM1 — John the Ripper](PM1-John-the-Ripper/) | Windows, JTR, Johnny GUI | Completed |
| [PM2 — NetworkWalks Tools](PM2-NetworkWalks-Tools/) | Windows, Hash Calculator, Password Cracker | Completed |
| [Optional 1 — HexStrike AI + JTR](Optional1-HexStrike-AI-JTR/) | Kali Linux, Claude Desktop, HexStrike MCP, JTR | Completed |

## Technical Highlights

### PM1 — John the Ripper on Windows

Configured John the Ripper with Johnny GUI and performed an offline password-recovery assessment against the supplied encrypted PDF.

Extracted the PDF hash, recovered the password and verified the result by opening the protected document.

**Result:** 1 of 1 hashes cracked successfully.

**Recovered password:** `good-luck`

**Captured flag:** `nw{cybersecurity_flag_captured_2608}`

[View PM1 methodology and evidence](PM1-John-the-Ripper/README.md)

### PM2 — Password Cracking with NetworkWalks Tools

Used the NetworkWalks Hash Calculator to extract the PDF password hash, followed by the browser-based Password Cracker to perform a dictionary attack.

The recovered credential was validated against the original PDF.

**Result:** Password recovered after testing 91 candidates from a 100-entry dictionary.

**Recovered password:** `password1`

**Verification:** Protected PDF successfully opened and flag captured.

[View PM2 methodology and evidence](PM2-NetworkWalks-Tools/README.md)

### Optional 1 — AI-Assisted Password Recovery with HexStrike MCP

Deployed an AI-integrated security assessment environment using Claude Desktop, HexStrike AI and John the Ripper on Kali Linux.

Configured the HexStrike API server to listen on `127.0.0.1:8888`, connected it to Claude Desktop through MCP and verified access to John the Ripper.

Extracted the password hash from the authorized training PDF and performed dictionary-based recovery using RockYou.

**Result:** 1 of 1 hashes successfully cracked.

**Recovered password:** `1qaz2wsx`

**Captured flag:** `nw{networkwalks_flag_260821_1}`

[View AI-assisted assessment methodology and evidence](Optional1-HexStrike-AI-JTR/README.md)

## Tools and Technologies

| Category | Tools |
|---|---|
| Operating systems | Windows, Kali Linux |
| Virtualization | Oracle VirtualBox |
| Password recovery | John the Ripper, Johnny GUI |
| Hash extraction | PDF Hash Extractor, NetworkWalks Hash Calculator |
| Dictionary attacks | RockYou, NetworkWalks Password Cracker |
| AI integration | Claude Desktop, HexStrike AI |
| Communication | Model Context Protocol (MCP) |
| Supporting technologies | Python, Git, Linux CLI |

## Security Findings

The assessments demonstrated several important password-security considerations.

**Predictable credentials:** Common passwords such as `password1` and keyboard patterns such as `1qaz2wsx` can be vulnerable to dictionary-based attacks.

**Offline recovery risks:** Once password-verification data is extracted from a protected document, candidates can be tested locally without repeatedly accessing the original file.

**Tool orchestration:** MCP integration allows an AI interface to coordinate existing security utilities while preserving the underlying role of those tools.

**Validation:** Successful password recovery should be confirmed against the original encrypted file, rather than relying solely on the cracking tool's reported output.

**Environment security:** Locally deployed security APIs should be restricted to necessary interfaces and used only within authorized assessment environments.

## Repository Structure

```text
WEEK3/
├── README.md
│
├── PM1-John-the-Ripper/
│   ├── README.md
│   ├── hash1.txt
│   └── screenshots/
│       ├── W3-PM1-Johnny-Password-Cracked.png
│       └── W3-PM1-PDF-Flag-Captured.png
│
├── PM2-NetworkWalks-Tools/
│   ├── README.md
│   └── screenshots/
│       ├── W3-PM2-PDF-Hash-Extracted.png
│       ├── W3-PM2-Password-Cracked.png
│       └── W3-PM2-PDF-Flag-Captured.png
│
└── Optional1-HexStrike-AI-JTR/
    ├── README.md
    └── screenshots/
        ├── W3-Optional1-HexStrike-MCP-Running.png
        ├── W3-Optional1-JTR-Verification.png
        ├── W3-Optional1-PDF-Hash-Extracted.png
        ├── W3-Optional1-JTR-Password-Cracked.png
        └── W3-Optional1-PDF-Flag-Captured.png
```

## Security Recommendations

- Use long, unique and unpredictable passwords.
- Avoid common dictionary entries and recognizable keyboard patterns.
- Prefer strong, modern document encryption methods.
- Protect encrypted files and extracted password-verification material.
- Restrict local security tooling and API services to authorized access.
- Validate security assessment findings with reproducible evidence.

## Conclusion

Week 3 provided practical experience across command-line, graphical, browser-based and AI-assisted password-security workflows.

By combining established password-recovery techniques with MCP-enabled tool orchestration, the projects demonstrated both the security implications of weak document passwords and the potential of AI integration in controlled cybersecurity assessments.

All exercises were conducted using authorized NetworkWalks internship training materials.

---

**Program:** NetworkWalks Cybersecurity Internship  
**Week:** 3  
**Focus:** Password Security, Ethical Hacking & AI-Assisted Security Testing  
**Completed:** 2 Compulsory Modules + 1 Optional Project  
**Status:** Completed