Copyright 2022 - Paul McCarty

# AppSec training
This playbook will help you introduce effective DevSecOps practices in your company, regardless of size. We provide explicit guidance and actionable steps to introduce security controls, measure their effectiveness, and demonstrate value for money to your business leaders. Following this playbook will help teams build materially more secure applications, and that in the end, is the intent.


## Sponsors 
Sponsored with 💜  by

<a href="https://securestack.com" target=”_blank” rel="noopener noreferrer"><center><img src="https://securestack.com/wp-content/uploads/2021/09/securestack-horizontal.png" width="500"/></center></a>


## Tools

# SAST
Semgrep - https://github.com/returntocorp/semgrep

# SCA
NPM - Build in
Dependency Check - https://github.com/jeremylong/DependencyCheck


# Secret/Credential Scanning

Trufflehog - https://github.com/trufflesecurity/trufflehog

Scan a local filesystem: ``` trufflehog filesystem --directory=./ ```

Scan a remote git repo: ``` trufflehog git https://github.com/securestack-training/juiceshop ```

Gitleaks 8 - https://github.com/zricethezav/gitleaks

``` gitleaks detect -v ```

Gitleaks 7 - https://github.com/zricethezav/gitleaks/releases/tag/v7.6.1

``` gitleaks7 -v -r https://github.com/securestack-training/juiceshop ```

# Vulnerability Scanning
Nuclei - https://github.com/projectdiscovery/nuclei
Nikto - https://github.com/sullo/nikto
Nmap - https://github.com/vulnersCom/nmap-vulners
Nmap - https://github.com/scipag/vulscan

# Cloud security
Prowler - https://github.com/prowler-cloud/prowler

# DAST
Zed Attack Proxy (ZAP) - https://www.zaproxy.org/
Burp Suite - https://portswigger.net/burp

# SBOM
Sift - https://github.com/anchore/syft


# SecureStack


## What's been mapped so far?

- [x] mapped all of ISM GSD
- [x] mapped all of SSDF
- [x] mapped CIS section 16

## What's left to do?

- [ ] map CIS section other than 16 to all items
- [ ] map remaining ISO 27001 Annex 14
- [ ] create compliance section for ISO 27002
- [ ] map brand new ISO 27002 controls
- [ ] map remaining NIST 800-53
- [ ] map remaining ISM infrastructure

## About the author

My name is Paul McCarty and I'm the founder of [SecureStack](https://securestack.com). I created this document as a way to capture in one place the steps I took to implement DevSecOps functions into my team. If you have any questions you can contact me at hello@securestack.com or on twitter [@eastside-mccarty](https://twitter.com/eastsidemccarty) 


