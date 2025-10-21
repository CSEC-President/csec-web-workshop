# CSEC Web Exploitation Workshop

A hands-on introduction to web application security testing using DVWA and OWASP Juice Shop.

## Prerequisites

- Computer with minimum 4GB RAM
- Docker installed (recommended) or VirtualBox/VMware
- Web browser with developer tools
- Burp Suite Community Edition or OWASP ZAP
- Basic understanding of HTTP and web technologies

## Workshop Structure

This workshop consists of two parts: DVWA for learning fundamental web vulnerabilities, and OWASP Juice Shop for modern application security challenges. Topics covered include IDOR, XXE injection, XSS, SQL injection, and HTTP verb tampering.

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

# TODO: Resources must be split into 2 sections: Beginner and Advanced. The Beginner section includes materials that elaborate on the session's content, while the Advanced section covers topics that are useful to read if a person wants to build something entirely new (such as research or advanced attacks that use variations of the methods you've covered). You can include the resources I gave you here as well. You probably have additional resources you've used while preparing the session.

---

Author: Sasha Zyuzin, Santiago Castro-Luna