# Secure Software Development

## **What Developers Do (Baseline Expectations)**

If you’re building or changing production code, this is the baseline.

---

## 1. Own What You Build

* Every repo, service, and app has an owner
* You’re responsible for security findings in your code
* If a security issue is assigned to your team, it gets attention like any other bug

---

## 2. Work Through Pull Requests

* All production changes go through a pull request
* Main and release branches are protected
* CI runs automatically on PRs
* If a required check fails, the PR doesn’t merge

---

## 3. Let Security Run in CI

* Security scans run automatically on PRs
* You review security findings during code review
* New high-risk issues are fixed before merge
* If something can’t be fixed immediately, it’s documented and time-boxed

---

## 4. Keep Dependencies Clean

* Dependency files and lockfiles stay committed
* You update dependencies regularly
* You review dependency upgrades like any other code change
* High-risk dependency issues don’t ship unnoticed

---

## 5. Never Commit Secrets

* Secrets live in approved secret managers
* No API keys, tokens, or passwords in repos
* If a secret leaks, it gets rotated immediately
* Treat leaked secrets as incidents, not TODOs

---

## 6. Use Infrastructure as Code

* Infrastructure changes go through code and PRs
* Infrastructure is scanned before deploy
* You know what’s public and why
* No surprise public endpoints or storage

---

## 7. Build Secure Containers

* Use approved base images
* Scan images before they’re deployed
* Fix or replace images with serious vulnerabilities
* Rebuild images when base images change

---

## 8. Test What’s Exposed

* If an app is internet-facing, it gets security tested
* Auth is included in testing when possible
* Critical issues get fixed before release
* Major changes get retested

---

## 9. Track and Fix Security Issues

* Every finding has an owner
* You prioritize by risk, not noise
* You don’t ignore issues forever
* Accepted risk has a reason and an expiration

---

## 10. Ship Securely

* Security checks are complete before release
* Known high-risk issues aren’t shipped by accident
* If you need an exception, you involve security early

---

### The One Rule to Remember

> **If it reaches production, it’s been scanned, reviewed, and owned.**
