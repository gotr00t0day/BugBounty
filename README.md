# 🎯 Bug Bounty Quick Start Guide

<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=F7F7F7&center=true&vCenter=true&width=435&lines=Bug+Bounty+Guide;Hacking+Resources;Security+Tools;Beginner+Friendly" alt="Typing SVG" />
</div>

## 📖 About This Guide

This comprehensive resource is designed to help beginners start their journey in bug bounty hunting. It provides a curated collection of tools, methodologies, and learning materials that are essential for identifying and reporting security vulnerabilities. Whether you're completely new to security research or transitioning from another field, this guide offers:

- 🎓 Structured learning paths and free educational resources
- 🛠️ Essential tools with practical usage examples
- 📝 Step-by-step methodology for hunting bugs
- 🔒 Best practices and safety guidelines
- 🌐 Recommended platforms and programs
- 📚 Valuable learning resources and practice environments

Perfect for: Security enthusiasts, aspiring bug hunters, and anyone interested in web security.

---

## 📚 Learning Resources

### Free Courses & Platforms
| Platform | Description | Link |
|----------|-------------|------|
| PortSwigger Web Security Academy | Interactive labs and learning materials | [Link](https://portswigger.net/web-security) |
| TryHackMe | Beginner-friendly rooms and paths | [Link](https://tryhackme.com) |
| HackerOne CTFs | Practice finding vulnerabilities | [Link](https://ctf.hacker101.com/) |
| PentesterLab | Hands-on web security exercises | [Link](https://pentesterlab.com/) |
| OWASP Top 10 | Essential vulnerabilities to understand | [Link](https://owasp.org/www-project-top-ten/) |

### YouTube Channels
| Channel | Focus | Link |
|---------|-------|------|
| InsiderPhD | Beginner tutorials | [Link](https://www.youtube.com/c/InsiderPhD) |
| NahamSec | Bug bounty tips | [Link](https://www.youtube.com/c/Nahamsec) |
| STöK | Vulnerability analysis | [Link](https://www.youtube.com/c/STOKfredrik) |
| Bug Bounty Reports Explained | Report breakdowns | [Link](https://www.youtube.com/c/BugBountyReportsExplained) |

## 🛠️ Essential Tools

### Reconnaissance Tools
```bash
# Subdomain Enumeration
subfinder -d target.com        # Fast subdomain discovery
amass enum -d target.com       # Comprehensive enumeration
assetfinder target.com        # Quick asset discovery

# Content Discovery
dirsearch -u https://target.com  # Directory enumeration
ffuf -w wordlist -u https://target.com/FUZZ  # Fast fuzzing
gobuster dir -u https://target.com -w wordlist  # Directory busting

# Visual Recon
aquatone -out ./aquatone targets.txt  # Screenshot and analysis
eyewitness --web -f urls.txt         # Visual reconnaissance
```

### Vulnerability Scanning
```bash
# Web Vulnerability Scanners
nuclei -l urls.txt -t nuclei-templates  # Template-based scanning
nikto -h https://target.com            # Classic web scanner
wpscan --url https://wordpress-site.com # WordPress scanning

# Specific Vulnerability Tools
xsstrike -u "https://target.com/?param=test"  # XSS testing
sqlmap -u "https://target.com/?id=1"         # SQL injection
jwt_tool decode [token]                      # JWT analysis
```

### Proxy Tools
| Tool | Type | Purpose |
|------|------|---------|
| Burp Suite Community | Proxy & Scanner | Web app testing |
| OWASP ZAP | Security Tool | Vulnerability scanning |
| Fiddler | Web Debugger | Traffic analysis |

### API Testing Tools
```bash
# API Reconnaissance & Testing
postman                     # API development and testing client
kiterunner scan https://target.com -w routes.txt  # API endpoint discovery
```

### Cloud Security Tools
```bash
# Cloud Misconfiguration Scanners
prowler aws --profile <profile_name>  # AWS security assessment
scoutsuite aws --profile <profile_name> # Multi-cloud security auditing
```

## 🎯 Getting Started

### Latest Bug Bounty Programs 
| Site | Description | Link |
|----------|-------|------|
| bbradar | Find the Latest Bug Bounty Programs. Programs auto-refresh every 7 mins. | [Link](https://bbradar.io/) |


### Bug Bounty Platforms
| Platform | Focus | Link |
|----------|-------|------|
| HackerOne | Wide range of programs | [Link](https://hackerone.com) |
| Bugcrowd | Managed programs | [Link](https://bugcrowd.com) |
| Intigriti | European programs | [Link](https://intigriti.com) |
| YesWeHack | Global programs | [Link](https://yeswehack.com) |

### Beginner-Friendly Programs
- GitHub Security Lab
- Department of Defense VDP
- Internet Bug Bounty
- Open-source projects

### Common Entry-Level Vulnerabilities
1. XSS (Cross-Site Scripting)
2. IDOR (Insecure Direct Object References)
3. Information Disclosure
4. Security Misconfiguration
5. Subdomain Takeover

## 📝 Basic Methodology

### 1. Reconnaissance
```bash
# Initial Enumeration
subfinder -d target.com > domains.txt
assetfinder target.com >> domains.txt
amass enum -d target.com >> domains.txt

# Live Host Discovery
cat domains.txt | httpx > live_domains.txt

# Screenshot
aquatone -out ./aquatone < live_domains.txt
```

### 2. Content Discovery
```bash
# Directory Enumeration
ffuf -w wordlist.txt -u https://target.com/FUZZ

# Parameter Discovery
arjun -u https://target.com/path

# JavaScript Analysis
subjs -i live_domains.txt
```

### 3. Vulnerability Assessment
```bash
# Automated Scanning
nuclei -l urls.txt -t nuclei-templates

# Manual Testing
# - Test input fields
# - Check file uploads
# - Analyze API endpoints
# - Review JavaScript files
```

## 📝 Reporting Vulnerabilities

Writing a clear, concise, and actionable bug report is crucial for getting your findings validated and rewarded. A good report demonstrates professionalism and makes the triage process easier for the security team.

### Key Components of a Good Report
- **Clear Title:** Summarize the vulnerability and its location (e.g., "Stored XSS in User Profile Name via POST /settings").
- **Vulnerability Details:** Explain the type of vulnerability, where it was found, and the technical details.
- **Steps to Reproduce (PoC):** Provide clear, step-by-step instructions that allow the team to reliably reproduce the issue. Include necessary code snippets, commands, or URLs. Screenshots or video recordings are often helpful.
- **Impact:** Describe the potential impact of the vulnerability. What could an attacker achieve? (e.g., steal user sessions, modify data, gain unauthorized access).
- **Remediation Suggestion (Optional but helpful):** Briefly suggest how the vulnerability might be fixed.

### Tips for Effective Reporting
- **Be Clear and Concise:** Avoid jargon where possible and get straight to the point.
- **Ensure Reproducibility:** Double-check your steps before submitting.
- **Demonstrate Impact:** Clearly explain why the vulnerability matters.
- **Stay Professional:** Maintain a respectful tone, even if discussing sensitive issues.
- **Check Scope:** Ensure the vulnerability is within the program's scope before reporting.
- **Proofread:** Check for typos and grammatical errors.

## 💡 Pro Tips

### Getting Started
1. Focus on one vulnerability type
2. Master one tool at a time
3. Read disclosed reports
4. Join bug bounty Discord communities
5. **Specialize:** Focus on specific vulnerability classes or target types (e.g., APIs, mobile).

### Documentation
- Take detailed notes
- Create reproducible steps
- Record proof-of-concept videos
- Use templates for reports
- **Be Patient:** Finding bugs takes time and persistence.

### Safety First
- Always read program policies
- Use VPN when testing
- Never test without authorization
- Respect scope and rules
- **Understand Safe Harbor:** Know the legal protections offered by the program policy.

### General Tips
- **Network:** Connect with other hunters and researchers.
- **Handle Duplicates/NA Gracefully:** Learn from them and move on. It's part of the process.
- **Don't Chase Leaderboards:** Focus on learning and quality reports over quantity.

## 📚 Must-Read Resources

### Books
| Title | Author | Focus |
|-------|--------|-------|
| Web Application Hacker's Handbook | Dafydd Stuttard | Web Security |
| Real-World Bug Hunting | Peter Yaworski | Bug Bounty Tips |
| Bug Bounty Bootcamp | Vickie Li | Methodology |

### Blogs and Write-ups
- [PortSwigger Research](https://portswigger.net/research)
- [HackerOne Hacktivity](https://hackerone.com/hacktivity)
- [Bug Bounty Write-ups](https://pentester.land/list-of-bug-bounty-writeups.html)

## 🎓 Practice Environments
| Platform | Type | Link |
|----------|------|------|
| DVWA | Vulnerable Web App | [Link](http://www.dvwa.co.uk/) |
| Juice Shop | OWASP Project | [Link](https://owasp.org/www-project-juice-shop/) |
| VulnHub | Vulnerable VMs | [Link](https://www.vulnhub.com/) |
| Hack The Box | CTF Platform | [Link](https://www.hackthebox.eu/) |

## 🔄 Continuous Learning

### Stay Updated
- Follow security researchers on Twitter
- Join bug bounty Discord servers
- Subscribe to security newsletters
- Participate in CTFs

### Build Your Brand
- Share your findings (after disclosure)
- Write blog posts
- Create YouTube content
- Help others learn

---

<div align="center">
  Remember:
  - Start with the basics
  - Practice regularly
  - Learn from others
  - Stay ethical
  - Document everything
  - Never stop learning
</div>

---

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=gotr00t0day&label=Guide+Views&color=brightgreen&style=flat" alt="Guide Views" />
</div> 
