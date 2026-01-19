\## CPU Pressure Alert Action



\### Trigger

\- Name: Sustained CPU Pressure Detected

\- Condition: CPU pressure state = 1 for defined duration



\### Action

\- Execute auto-remediation script on affected host:

&nbsp; - cpu\_pressure\_remediation.sh



\### Execution Method

\- Zabbix agent executes the script locally on the affected host

\- Script execution is logged on the host for auditability



\### Failure Handling

\- If CPU pressure persists after remediation, escalation policies apply



\### Rationale

Attempting safe, automated remediation before alerting humans reduces alert fatigue and improves operational efficiency.

> Note: Automated remediation is documented here but was not executed
> during the demo walkthrough to avoid disruptive behavior.

