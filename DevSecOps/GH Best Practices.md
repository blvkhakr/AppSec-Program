## Recommended GitHub Security Baseline (Non-Enterprise)

This document defines a recommended security baseline for organizations using GitHub
on the standard platform (Free or Team plans), focusing on controls available without GitHub Enterprise.


--

### 1. Identity & Access

* Mandatory **2FA for all users**
* Remove inactive users quarterly
* Use **least privilege**:

  * No blanket admin access
  * Limit who can manage settings, secrets, and Actions
* Enforce **SSO if available** (Team supports this)

---

### 2. Repository Protections

For **all production or customer-impacting repos**:

* Protect default branch:

  * PRs required
  * ≥1–2 reviews (risk-based)
  * Status checks required
  * Force-push & deletion blocked
* CODEOWNERS required
* No direct pushes to `main`


---

### 3. Secrets Management (Much higher risk in orgs)

* Enable:

  * Secret scanning
  * Push protection
* Centralize secrets:

  * GitHub Actions secrets only
  * No `.env` committed anywhere
* Enforce **pre-commit secret scanning** org-wide

> One leaked token can expose **customers, infrastructure, or revenue**.

---

### 4. Governance & Ownership

* Define repo ownership:

  * Product owner
  * Technical owner
  * Security contact

* Archive or delete:
  * Abandoned repos
  * POCs that turned into production “by accident”
        
* Standardize:
  * README security expectations
  * Contribution rules
  * Disclosure guidance

---

### 5. CI/CD & GitHub Actions

For orgs, Actions become a **supply-chain attack surface**.

**Required practices:**

* Pin actions by **commit SHA**
* Default workflow permissions = read-only
  
* Explicit approval for:
  * External actions
  * Forked PR workflows
    
* Disable Actions where not needed

> A compromised workflow can pivot across **multiple repos**.

---

### 6. Dependency & Supply Chain 

* Enable:
  * Dependency graph
  * Dependabot alerts & security updates
    
* Set org-wide expectations:
  * Patch SLAs (e.g., critical < 7 days)
    
* Ban:
  * Unmaintained dependencies
  * Random forks without review

> Vulnerabilities now translate to **compliance, contracts, and trust**.

---

### 7. Visibility & Exposure Control (Often overlooked)

* Default repos to **private**
* Require review before open-sourcing anything
  
* Scrub:
  * Internal domains
  * Architecture details
  * Debug logs
    
* Clear policy for:
  * What *can* be public
  * What *must not* be public

> Company GH must be **intentional**.

---

## What Companies **Lose** Without Enterprise

Without Enterprise, companies **do not get**:

* Org-wide policy enforcement
* Advanced audit logs
* Centralized rulesets
* Advanced secret scanning controls

**So the compensating controls are:**

* Process
* Documentation
* Periodic reviews
* Strong defaults
