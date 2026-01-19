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
  - CPU utilization and load averages

- **Trigger Logic**
  - Five-minute rolling average evaluation
  - Sustained-condition detection (not spike-based)

- **Alerting**
  - High-severity alert generation
  - Visual evidence via graphs

- **Recovery**
  - Automatic alert resolution once conditions normalize

---

## Trigger Definition


**Name:**  
Linux: High CPU utilization (avg >80% for 5m)


**Expression:**
```text
avg(system.cpu.util[,system],5m) > 80
```


This trigger evaluates sustained system-level CPU utilization using a
five-minute rolling window, ensuring alerts represent real performance
pressure rather than transient bursts.

---

## Demo Flow

### 1. Baseline Verification
- Zabbix Problems view shows no active CPU alerts
- Confirms normal operating conditions before load is introduced

### 2. Load Generation
- Sustained CPU load is generated on the monitored Linux VM
- Simulates a runaway process or production workload

### 3. Detection
- Zabbix continuously evaluates CPU utilization via the agent
- Alert fires only after the five-minute average exceeds threshold

### 4. Evidence
- CPU utilization graph shows sustained elevation
- Alert threshold crossing is visually confirmed

### 5. Recovery
- Load is terminated
- CPU usage returns to normal
- Alert automatically resolves without manual intervention

---

## Demo Video

🎥 **Loom Walkthrough:**  
(Add Loom link here)

This video demonstrates how the monitoring architecture reacts to
sustained CPU pressure in real time.
