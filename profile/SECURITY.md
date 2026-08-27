# 🛡️ AirBorne Enterprise Security Policy & Disclosure Program

**Classification:** Public Enterprise Standard  
**Effective Date:** 2026  
**Security Governance:** AirBorne Product Security Incident Response Team (AirBorne PSIRT)  
**Primary Security Contact:** [suryaansh@airbornehrs.in](mailto:suryaansh@airbornehrs.in)

---

## 🏛️ 1. Security Philosophy & Commitment

At **AirBorne**, security and data integrity are foundational architectural pillars. Our machine intelligence, autonomous systems, and enterprise HRMS platforms are built upon a **Zero-Trust Security Model** incorporating end-to-end cryptography, continuous vulnerability management, and rigid supply chain assurance.

We welcome and value the contributions of independent security researchers, ethical hackers, and academic institutions who assist us in maintaining the highest standards of safety and compliance.

---

## 📊 2. Supported Versions & Security Maintenance Windows

Security patches, CVE advisories, and critical updates are actively provided for the following version streams:

| Product / Framework | Branch / Stream | Security Maintenance Status | EOL Date |
| :--- | :---: | :---: | :---: |
| **Airborne-Antara (V8.x / V9.x)** | `main` | :white_check_mark: **Active Full Support** | 2028-12-31 |
| **AirBorne Core HRMS Engine (V2.x)** | `v2.x` | :white_check_mark: **Active Full Support** | 2027-12-31 |
| **AirBorne Enterprise API (V1.x)** | `v1.x` | :warning: **Critical Security Patches Only** | 2026-12-31 |
| **Legacy Proof-of-Concepts** | `< 1.0.0` | :x: **End of Life (Unsupported)** | Immediate |

*If you are running an unsupported version, we strongly recommend upgrading to the latest stable release immediately.*

---

## 🚨 3. Responsible Vulnerability Disclosure Program

If you discover a potential vulnerability, bug, data leakage vector, or architectural flaw in any AirBorne repository, service, or API, please report it following our coordinated vulnerability disclosure process.

### 🔒 Reporting Procedure

> [!CAUTION]
> **DO NOT** open public GitHub issues, discussions, pull requests, or tweet about potential security findings before responsible coordination is complete.

1. **Email Contact:** Send your confidential report directly to **[suryaansh@airbornehrs.in](mailto:suryaansh@airbornehrs.in)**.
2. **Subject Convention:** `[SECURITY-DISCLOSURE] <Severity: Low/Med/High/Critical> - <Brief Component Description>`
3. **Mandatory Report Contents:**
   - **Target Component:** Repository name, branch/commit SHA, API endpoint, or Docker image tag.
   - **Vulnerability Classification:** CWE identifier, OWASP category (e.g., Auth Bypass, RCE, IDOR, Prompt Injection, Memory Leak).
   - **Step-by-Step Reproduction:** Comprehensive, deterministic reproduction steps or Proof-of-Concept (PoC) script.
   - **Threat Impact Assessment:** Realistic evaluation of the risk to confidentiality, integrity, or system availability.
   - **Proposed Remediation:** Suggested code patch, config fix, or architectural mitigation (optional but appreciated).

---

## ⏱️ 4. Security Incident Response SLA

The AirBorne PSIRT commits to the following strict response milestones for all reported vulnerabilities:

```
[ Day 0: Submission ] ──▶ [ < 24 Hours: Acknowledgement ] ──▶ [ < 72 Hours: Severity Triage & CVE Assignment ]
                                                                       │
[ Public Coordinated Disclosure ] ◀── [ < 30 Days: Full Deployment ] ◀──┘
```

| Phase | Target SLA | Action Taken |
| :--- | :---: | :--- |
| **Initial Acknowledgment** | **< 24 Hours** | Automated & human confirmation of report receipt with assigned Tracking ID. |
| **Technical Triage & Severity Scoping** | **< 72 Hours** | Reproduction of finding, CVSS v3.1 calculation, and engineering notification. |
| **Remediation & Patch Development** | **< 14 Days** | Patch authoring, regression validation, and internal staging testing. |
| **Production Deployment & Release** | **< 30 Days** | Production release, GitHub Advisory creation, and CVE assignment. |

---

## 🎯 5. Scope Matrix

### ✅ In-Scope (Eligible for Recognition)

- **Authentication & Authorization Flaws:** Privilege escalation, session hijacking, JWT forge, SSO bypass.
- **Remote Code Execution (RCE):** Arbitrary code injection, unsafe deserialization, pickle exploits.
- **Sensitive Data & PII Exposure:** Unauthenticated exposure of employee salaries, personal data, or API secret keys.
- **Model Inversion & Weight Extraction:** Unauthorized extraction of private model weights or training embeddings.
- **Supply Chain Vulnerabilities:** Malicious dependency injection, pipeline compromise, unpinned mutable actions.
- **Zero-Trust Boundary Bypasses:** Circumventing Level 1–Level 6 authorization matrix rules.

### ❌ Out-of-Scope (Ineligible)

- Distributed Denial of Service (DDoS) or high-volume load testing against infrastructure.
- Social engineering, phishing, or physical attacks against AirBorne employees or facilities.
- Theoretical vulnerabilities without practical PoC demonstrations.
- Scanner-generated boilerplate reports without manual validation or actionable findings.
- Missing HTTP security headers (e.g., CSP, HSTS) unless directly chainable into an exploitable attack vector.
- Issues in third-party dependencies unless an active, zero-day exploit path in AirBorne's code is demonstrated.

---

## 🤝 6. Safe Harbor & Researcher Protection

AirBorne considers security research conducted under this policy to be **authorized, legal, and in good faith**. 

If you adhere to the following principles:
- You make a good-faith effort to avoid privacy violations, destruction of data, and service disruption.
- You do not retain, copy, or distribute any proprietary data or employee PII obtained during research.
- You give us reasonable time to remediate the vulnerability before public disclosure.

**AirBorne guarantees that:**
- We will **not** initiate or pursue legal action against you.
- We will **not** request law enforcement investigations for authorized research.
- We will collaborate openly with you to understand and resolve the issue.
- You will be eligible for formal recognition in the **AirBorne Security Hall of Fame**.

---

## 🔒 7. Secure Development Lifecycle (SDLC) Standards

All software produced by the AirBorne organization must pass rigorous automated security gates prior to production deployment:

1. **Static Application Security Testing (SAST):** Automated CodeQL and Bandit scans integrated into every pull request.
2. **Software Composition Analysis (SCA):** Automated Dependabot and pip-audit vulnerability monitoring.
3. **Secret Scanning:** Automated pre-commit hooks and GitHub push protection blocking hardcoded credentials.
4. **Cryptographic Integrity:** Cryptographically verified GPG commit signing and container signature verification (Cosign/Sigstore).

---

```
AIRBORNE PVT. LTD. • PRODUCT SECURITY INCIDENT RESPONSE
CONFIDENTIALITY & TRUST GUARANTEED
For questions: suryaansh@airbornehrs.in
```
