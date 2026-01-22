# Demo: Sustained CPU Pressure Detection and Recovery

This demo demonstrates how the monitoring architecture implemented in
this repository detects and handles sustained CPU pressure on a Linux
virtual machine.

The demo correlates directly with the layered monitoring and alerting
design documented in this repository.

---

## Architecture Components Demonstrated

This demo exercises the following components:

- **Linux Agent Monitoring**
  - Metric collection via Zabbix Agent
  - CPU idle time and load averages

- **Trigger Logic**
  - Two-minute rolling average evaluation of CPU idle time
  - Sustained-condition detection (not spike-based)

- **Alerting**
  - High-severity alert generation
  - Visual evidence via graphs

- **Recovery**
  - Automatic alert resolution once conditions normalize

---

## Trigger Definition

**Name:**  
Linux: Sustained CPU Pressure Detected

**Expression:**
```text
avg(system.cpu.idle[,system],2m) < 30
```

## Demo Video

🎥 **Loom Walkthrough:**  
https://www.loom.com/share/6601992579414afabdd73c092df7f84a

This walkthrough demonstrates the Zabbix server detecting sustained CPU
pressure on a Linux virtual machine using idle-based monitoring. The video
shows baseline conditions, sustained load introduction, trigger activation
after the defined rolling window, visual confirmation via graphs, and
automatic alert resolution once CPU pressure subsides.
Automated remediation behavior is documented separately and was not executed during this demo to avoid disruptive actions in a demonstration environment.

