# VAPT Week 5 – Practical Learning

## Overview

This repository contains the practical work completed during **Week 5 of the Cyber Security Internship**. The main focus was on **Vulnerability Assessment and Penetration Testing (VAPT)** fundamentals, including network scanning, basic vulnerability assessment, and HTTP request analysis.

The practical activities were performed only against authorized systems and lab environments.

## Objectives

* Understand the basic VAPT workflow.
* Perform network and service discovery using Nmap.
* Learn basic web vulnerability scanning using Nikto.
* Understand HTTP requests, headers, cookies, and proxy interception using Burp Suite.
* Analyze scan results instead of simply running security tools.
* Document observations and limitations during security testing.

## Tools Used

* **Nmap** – Network and service discovery
* **Nikto** – Web server security assessment
* **Burp Suite** – HTTP/HTTPS request interception and analysis
* **Kali Linux** – Security testing environment
* **Ubuntu Apache Lab** – Authorized local testing environment

## Task 1 – Nmap Scanning

The following Nmap scans were performed against the authorized training target:

### Basic Scan

```bash
nmap testphp.vulnweb.com
```

This scan was used to identify available ports on the target.

### Service Detection

```bash
nmap -sV testphp.vulnweb.com
```

This scan attempts to identify the services and their versions running on discovered ports.

### Aggressive Scan

```bash
nmap -A testphp.vulnweb.com
```

The aggressive scan combines several Nmap detection techniques to collect additional information about the target.

### Nmap Version

```bash
nmap --version
```

This command was used to verify the installed Nmap version.

## Task 2 – Nikto

The following command was attempted:

```bash
nikto -h http://testphp.vulnweb.com
```

The target hostname was reachable by ping, but the Kali system could not establish an HTTP/HTTPS connection to the target during the testing session.

A connectivity check using `curl` also failed to establish a connection to the web server.

Therefore, **no Nikto vulnerability findings are claimed from this scan**. The result was documented as a testing limitation rather than inventing or assuming vulnerabilities.

## Task 3 – Burp Suite

Burp Suite was configured with the local proxy:

```text
127.0.0.1:8080
```

Burp Proxy was used to capture and inspect HTTP requests.

Because the training website could not be reached over HTTP/HTTPS from the Kali environment, Burp Suite was demonstrated using the **authorized local Ubuntu Apache lab**.

The captured requests were used to understand:

* HTTP request methods
* Request URLs
* HTTP headers
* Cookies
* Host information
* Client-server communication

Two HTTP requests were captured and documented in the `Burp-Suite` directory.

## Mini VAPT Activity

The three security tools were studied as part of a basic VAPT workflow:

```text
Target
   ↓
Nmap
   ↓
Service Discovery
   ↓
Nikto
   ↓
Web Security Assessment
   ↓
Burp Suite
   ↓
HTTP Request Analysis
   ↓
Documentation
```

The practical exercise focused on understanding what each tool reveals and recognizing testing limitations.

## Security Observations

### 1. Network and Service Discovery

Nmap demonstrated how an assessor can identify exposed ports and services on a target system.

### 2. Web Server Assessment

Nikto is intended to identify common web server configuration issues and potentially interesting security observations. In this exercise, the target could not be reached over HTTP/HTTPS, so no vulnerability result was reported.

### 3. HTTP Traffic Analysis

Burp Suite demonstrated how HTTP requests can be intercepted and inspected through a local proxy. This helped in understanding headers, cookies, request methods, and client-server communication.

## Screenshots

Screenshots from the practical work are stored in the `Screenshots` directory.

They include:

* Nmap version
* Nmap basic scan
* Nmap service detection
* Nmap aggressive scan
* Nikto connectivity limitation
* Burp Suite proxy configuration
* Burp Suite HTTP request
* Burp Suite second request

## Repository Structure

```text
vapt-week-5-practical/
│
├── Nmap/
│   ├── nmap_basic.txt
│   ├── nmap_service.txt
│   └── nmap_aggressive.txt
│
├── Nikto/
│   └── nikto_notes.txt
│
├── Burp-Suite/
│   ├── request-1.txt
│   └── request-2.txt
│
├── Screenshots/
│   ├── Week5_Nmap_01_Version.png
│   ├── Week5_Nmap_02_Basic_Scan.png
│   ├── Week5_Nmap_03_Service_Detection.png
│   ├── Week5_Nmap_04_Aggressive_Scan.png
│   ├── Week5_Nikto_Scan_Limitation.png
│   ├── Week5_Burp_01_Proxy_Settings.png
│   ├── Week5_Burp_02_HTTP_Request.png
│   └── Week5_Burp_03_Second_Request.png
│
└── README.md
```

## Learning Outcomes

After completing this practical, I gained hands-on experience with:

* Basic VAPT methodology
* Nmap network scanning
* Service and version detection
* Aggressive Nmap scanning
* Nikto web security assessment
* Burp Suite proxy configuration
* HTTP request interception
* Header and cookie analysis
* Security testing documentation
* Recognizing and documenting connectivity limitations

## Authorization and Safety

All security testing was performed only against authorized training targets and my own local laboratory environment.

Security tools should not be used against systems or websites without explicit permission.

## Author

**Varsha Kammari**

Cyber Security Intern
DG Interns Hub
