# CSEC Web Exploitation Workshop

A hands-on introduction to web application security testing using DVWA and OWASP Juice Shop.

## Prerequisites

- Computer with minimum 4GB RAM
- Docker installed (recommended) or VirtualBox/VMware
- Web browser with developer tools
- Burp Suite Community Edition or OWASP ZAP
- Basic understanding of HTTP and web technologies

## Workshop Structure

This workshop consists of two parts: DVWA for learning fundamental web vulnerabilities, and OWASP Juice Shop for modern application security challenges. Topics covered include IDOR, XXE injection, XSS, and SQL injection.

## Workshop Workflow
The workflow for this workshop is straightforward: install either DVWA or OWASP Juice Shop using the Docker commands provided (if these don't work for you for some reason, use the official installation instructions from the links below), then follow the built-in tutorials and challenges within each application. Both platforms include comprehensive instructions, hints, and documentation created by their developers.

---

## Part 1: DVWA Workshop

**Damn Vulnerable Web Application** (PHP/MySQL - Traditional vulnerabilities)
- Repository: https://github.com/digininja/DVWA
- Perfect for beginners learning OWASP Top 10 basics
- Security levels: Low, Medium, High, Impossible

**Quick Setup with Docker**:
```bash
docker pull vulnerables/web-dvwa
docker run -d -p 80:80 vulnerables/web-dvwa
```
Access at http://localhost
- Default login: admin / password

**Topics to explore**:
- SQL Injection (both blind and union-based)
- XSS (Reflected, Stored, DOM)
- CSRF
- File Inclusion
- Command Injection
- File Upload bypass

---

## Part 2: OWASP Juice Shop Workshop

**OWASP Juice Shop** (Node.js/Angular - Modern web application)
- Repository: https://github.com/juice-shop/juice-shop
- Modern vulnerabilities in a realistic e-commerce application
- Built-in CTF scoreboard with 100+ challenges

**Quick Setup with Docker**:
```bash
docker pull bkimminich/juice-shop
docker run -d -p 3000:3000 bkimminich/juice-shop
```
Access at http://localhost:3000

**Topics to explore**:
- REST API vulnerabilities
- JWT manipulation
- NoSQL injection
- XXE in file uploads
- IDOR in shopping baskets
- Client-side security bypasses

**Finding the Score Board**: Part of the challenge - explore the application or check the JavaScript source! =)

---

## Basic Linux Commands Reference

### Navigation
```bash
# Print current directory
pwd

# List files in current directory
ls

# List with details (size, permissions, dates)
ls -la

# Change directory
cd path/to/directory

# Go to home directory
cd ~
cd $HOME

# Go up one directory
cd ..

# Go to previous directory
cd -
```

### File Operations
```bash
# Create directory
mkdir directory_name

# Remove file
rm filename

# Remove directory and contents
rm -rf directory_name

# Copy file
cp source.txt destination.txt

# Move/rename file
mv oldname.txt newname.txt

# View file contents
cat file.txt

# View file with paging
less file.txt
# (press 'q' to quit)

# Edit file
vim file.txt
nano file.txt
```

### Process Management
```bash
# List running processes
ps aux

# Find specific process
ps aux | grep process_name

# Kill process by PID
kill <PID>

# Kill process by name
pkill process_name

# Stop running command
Ctrl+C
```

### System Information
```bash
# Check disk space
df -h

# Check memory usage
free -h

# Check CPU/memory usage (live)
top
# (press 'q' to quit)

# Download file from URL
wget https://example.com/file.tar.gz

# Extract tar.gz archive
tar -xvzf file.tar.gz
```

### Environment Variables
```bash
# Set variable for current session
export YOUR_VARIABLE=yourvalue

# View variable
echo $YOUR_VARIABLE

# View all environment variables
env
```

### Permissions
```bash
# Make script executable
chmod +x script.sh

# Run executable
./script.sh

# Run with sudo (root privileges)
sudo command
```

---

## Disclaimer

**Educational Purpose**: This workshop teaches security testing techniques for authorized environments only. Use these skills exclusively on systems you own or have explicit written permission to test.

**Legal Responsibility**: You are solely responsible for your actions. The instructor and organizers accept no responsibility for:
- Unauthorized access to systems
- Data loss or system damage
- Legal consequences of misuse
- Any malicious use of techniques learned

**Ethical Guidelines**:
- Never test systems without explicit authorization
- Report vulnerabilities responsibly
- Respect privacy and confidentiality
- Use knowledge to improve security, not exploit it

By participating, you acknowledge understanding these terms and agree to use this knowledge ethically and legally.

---

## Additional Resources
Beginner resources:
- PwnFunction's YT video on IDOR: https://www.acunetix.com/blog/articles/dom-xss-explained/
- OWASP Unrestricted File Upload Guide: https://owasp.org/www-community/vulnerabilities/Unrestricted_File_Upload
- OWASP Cross Site Scripting (XSS) Guide: https://owasp.org/www-community/attacks/xss/
- Acutenix DOM XSS Guide (very easy to understand!): https://www.acunetix.com/blog/articles/dom-xss-explained/
- OWASP SQL Injection Guide: https://owasp.org/www-community/attacks/SQL_Injection
- OWASP Top Ten Web Attack Types (2025 verision set to release next month): https://owasp.org/www-project-top-ten/

Advanced resources:

### Advanced

- [Hakuin - ML-Optimized Blind SQL Injection](https://github.com/pruzko/hakuin) - 6x faster than sqlmap using machine learning, this is the cutting-edge for blind SQLi research (Black Hat MEA 2024)
- [SQL Injection at Protocol Level](https://simonwillison.net/2024/Aug/12/smuggling-queries-at-the-protocol-level/) - Mind-blowing DEF CON 32 talk showing how to bypass app-layer defenses by exploiting PostgreSQL/MongoDB binary protocols
- [PHP Filter Chains: LFI to RCE](https://www.synacktiv.com/en/publications/php-filters-chain-what-is-it-and-how-to-use-it) - Transform any LFI into RCE using encoding transformations, includes practical exploitation tool
- [Bypassing DOMPurify with Mutation XSS](https://portswigger.net/research/bypassing-dompurify-again-with-mutation-xss) - Fresh 2024 techniques for XSS, shows why sanitizers still fail through browser parsing tricks
- [The State of GraphQL Security 2024](https://escape.tech/blog/the-state-of-graphql-security-2024/) - Scanned 160 real APIs and found 69% vulnerable to DoS, super informative for modern API research
- [JWT Algorithm Confusion Attacks](https://portswigger.net/web-security/jwt/algorithm-confusion) - Clear explanation of how to forge JWTs, still working in 2024 (CVE-2024-54150), great for understanding auth bypasses
- [OWASP API Security Top 10 2023](https://owasp.org/API-Security/) - BOLA is still #1 affecting 40% of APIs, must-read for API security projects
- [NoSQL Injection Guide](https://portswigger.net/web-security/nosql-injection) - Best comprehensive guide for MongoDB/Neo4j attacks with hands-on labs, very practical
- [IDOR Detection with AI](https://zeropath.com/blog/idor-crisis-2025) - LLMs find authorization bugs in minutes vs. hours manually, 53% critical vuln discovery rate
- [Command Injection ML Detection](https://www.nature.com/articles/s41598-024-74350-3) - Solid paper on deep learning for detecting command injection, great if you want to build detection tools (2024)

---

Author: Sasha Zyuzin, Santiago Castro-Luna
