Copyright 2022 - Paul McCarty

# AppSec training
This playbook will help you introduce effective DevSecOps practices in your company, regardless of size. We provide explicit guidance and actionable steps to introduce security controls, measure their effectiveness, and demonstrate value for money to your business leaders. Following this playbook will help teams build materially more secure applications, and that in the end, is the intent.

![DIY-Application-Security-Program](https://github.com/securestack-training/AppSec-Training/assets/7798480/885c47cc-dbc8-4e5f-a661-420fb58be4cd)

# Tools

## SAST

### Semgrep 

https://github.com/returntocorp/semgrep

Simple auto scan: ``` semgrep --config auto ```

CI/CD scan: ``` semgrep --config "p/r2c-ci" ```

OWASP Top Ten scan: ``` semgrep --config "p/owasp-top-ten" ```

Generic security scan: ``` semgrep --config "p/r2c-security-audit" ```

### Bearer 

https://github.com/bearer/bearer

Simple auto scan: ``` bearer scan ./ --scanner=sast ```

### Bandit (Python only)

https://github.com/PyCQA/bandit

Simple auto scan: ``` bandit -r ./myproject ```

## SCA

### Scancode Toolkit

https://github.com/nexB/scancode-toolkit

Simple scan: ``` scancode --license --copyright --json-pp scancode_result.json ./ ```

### OWASP Dependency Check

https://github.com/jeremylong/DependencyCheck

Simple auto scan: ``` dependency-check --out . --scan ./  -f JSON ```

### NPM

https://docs.npmjs.com/cli/v9/commands/npm-audit

Simple auto scan: ``` npm audit ```

Forced fix scan: ``` npm audit fix ```


### Trivy SCA

https://github.com/aquasecurity/trivy

Simple auto scan: ``` trivy fs --scanners vuln myproject/ ```

## Container Vulnerability Scanning

### Trivy container scanning

https://github.com/aquasecurity/trivy

Simple auto scan: ``` trivy image python:3.4-alpine ```

## Secret/Credential Scanning

### Trufflehog

https://github.com/trufflesecurity/trufflehog

Scan a local filesystem: ``` trufflehog filesystem --directory=./ ```

Scan a remote git repo: ``` trufflehog git https://github.com/securestack-training/juiceshop ```

### Gitleaks 8

https://github.com/zricethezav/gitleaks

``` gitleaks detect -v ```

### Gitleaks 7 

https://github.com/zricethezav/gitleaks/releases/tag/v7.6.1

``` gitleaks7 -v -r https://github.com/securestack-training/juiceshop ```

### Trivy Secret Scanning

https://github.com/aquasecurity/trivy

Simple auto scan: ``` trivy fs --scanners secret myproject/ ```

## Vulnerability Scanning

### Nuclei

https://github.com/projectdiscovery/nuclei

Run kitchen sink nuclei scan: ``` nuclei -u https://app.niftybank.org ```

Run faster nuclei scan: ``` nuclei -silent -eid http-missing-security-headers -u https://app.niftybank.org ```

Find only criticals and highs: ``` nuclei -silent -eid http-missing-security-headers -u https://app.niftybank.org ```

### Nikto 

https://github.com/sullo/nikto

Simple Nikto scan: ``` nikto -host  app.niftybank.org ```

### Nmap

https://github.com/vulnersCom/nmap-vulners

Simple vulners scan: ``` nmap -sV --script=nmap-vulners app.niftybank.org ```

Nmap - https://github.com/scipag/vulscan

Nmap NTLM scan: ``` nmap -p 80 --script http-ntlm-info --script-args http-ntlm-info.root=/root/ cifs.niftybank.org ```

## Infrastructure as Code

### Trivy Config

https://github.com/aquasecurity/trivy

Simple auto scan: ``` trivy fs --scanners config myproject/ ```

## CI/CD Pipeline Analysis

### Ghast

https://github.com/bin3xish477/ghast

Simple auto scan: ``` ghast -d directory-with-actions/ ```

## Cloud security

Prowler

https://github.com/prowler-cloud/prowler

## DAST

### Zed Attack Proxy (ZAP) 

https://www.zaproxy.org/

### Burp Suite 

https://portswigger.net/burp

### Caido

https://caido.io/

## SBOM

### Syft 

https://github.com/anchore/syft

Simple Syft scan: ``` syft packages file:./package-lock.json ```

### CycloneDX Node

Simple node scan: ``` cyclonedx-node --output bom.json ```

### CycloneDX NPM 

Simple npm scan: ``` cyclonedx-npm --output-file ./npm.json ```

### Microsoft Salus SBOM

https://github.com/microsoft/sbom-tool

Simple Salus scan: ``` microsoft-sbom-tool generate -bc ./  -b ./SPDX -pn app.niftybank.org -pv 1.0 -nsb https://app.niftybank.org -ps test ```

### OSS Review Toolkit (ORT)

https://github.com/oss-review-toolkit/ort

Simple ORT scan:

# Trivy All-in-One

https://github.com/aquasecurity/trivy

Simple auto scan: ``` trivy fs --scanners vuln,secret,config myproject/ ```

# SecureStack

### SCA

Single commit SCA scan: ``` bloodhound-cli code -t node -a <app_id> ```

### Secrets & Credentials

Secret scan: ``` bloodhound-cli code -s -a <app_id> ```

### Web vulnerability

Web vuln scan: ``` bloodhound-cli recon -a <app_id> ```

### SBOM generation

SecureStack SBOM Generation: ``` bloodhound-cli SBOM -r -a <app_id> ```

## What's left to do?

- [ ] map CIS section other than 16 to all items
- [ ] map remaining ISO 27001 Annex 14

## About the author

My name is Paul McCarty and I'm the founder of [SecureStack](https://securestack.com). I created this document as a way to capture in one place the steps I took to implement DevSecOps functions into my team. If you have any questions you can contact me at hello@securestack.com or on twitter [@eastside-mccarty](https://twitter.com/eastsidemccarty) 

## Sponsors 
Sponsored with 💜  by

<a href="https://securestack.com" target=”_blank” rel="noopener noreferrer"><center><img src="https://securestack.com/wp-content/uploads/2021/09/securestack-horizontal.png" width="500"/></center></a>
