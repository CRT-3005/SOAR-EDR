# SOAR-EDR

## Objective

This Project aimed to create a basic AD environment, utilise the user accounts to perform attacks on from Kali and have Splunk configured to generate telemetry from the target machines. 
In total there were 4 VMs. A VM running Windows 10 with Splunk forwarding and Sysmon configured on. A VM running Windows Server machine running AD which also had Splunk forwarding and Sysmon configured on. A VM running Ubunutu which was configured for Splunk. Finally a VM running Kali Linux.

## Skills Learned

- How to create a SOAR EDR playbook.
- How to add LimaCharlie endpoint onto Windows Server.
- How to inspect events generated from the server in LimaCharlie.
- How to install LaZagne and then creating a specific rule to check processes relating to LaZagne.
- Using Tines to create links between LimaCharlie and Slack.
- How to generate alerts on Slack.
- Setting up trigger links on Tines.
  
## Tools Used

- LimaCharlie
- Virtual Box with Windows Server 2022
- LaZagne
- Slack
- Tines

## Steps
