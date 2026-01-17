# Zabbix Linux Monitoring with Auto‑Remediation

This repository demonstrates a production‑style Linux monitoring setup using Zabbix,
focused on detecting sustained CPU pressure and responding intelligently through
automation and escalation.

## 📌 Overview

The system follows a layered monitoring approach:

1. **Detection** – Identify sustained CPU pressure using Zabbix triggers  
2. **Auto‑Remediation** – Attempt safe, automated recovery on the host  
3. **Alert Actions** – Execute remediation before notifying humans  
4. **Escalation** – Notify engineers only if the issue persists  

This design reduces alert fatigue while ensuring real problems receive attention.

---

## 🧱 Repository Structure

architecture/ # High‑level system design
dashboards/ # Zabbix dashboard definitions
triggers/ # CPU pressure trigger definitions
scripts/ # Monitoring helper scripts
remediation/ # Auto‑remediation scripts
actions/ # Zabbix alert action documentation
escalation/ # Alert escalation policies

---

## ⚙️ CPU Pressure Workflow

1. Zabbix detects sustained CPU pressure  
2. Auto‑remediation script is executed on the host  
3. System state is re‑evaluated after remediation  
4. If pressure persists, escalation policies apply  

---

## 🧠 Design Principles

- Automate before escalating  
- Separate policy from implementation  
- Minimize alert noise  
- Favor safe, reversible remediation  

---

## ✅ Use Case

This project reflects real‑world SRE and DevOps monitoring practices and is suitable
as a reference implementation or portfolio example.
