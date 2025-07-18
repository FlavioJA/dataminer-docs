---
uid: Troubleshooting_SLSNMPManager_exe
---

# SLSNMPManager.exe

## About SLSNMPManager

SLSNMPManager controls all communication from and to devices using the SNMP protocol.

**Communication types**: SNMPv1, v2 & v3.

## SLSNMPManager troubleshooting flowchart

```mermaid
%%{init: { 'theme': 'base', 'themeVariables': { 'edgeLabelBackground':'#fff', 'fontFamily' : 'Segoe UI'}}}%%
flowchart TD
Title["SLSNMPManager"]:::Start
Title---L{{"Are RTEs present in the system?"}}:::Decision
L----|No|U{{"Is SNMP functionality broken?"}}:::Decision
U----|No|S{{"Does the device respond as expected?"}}:::Decision
S----|No|T["Fix device communication."]:::Start
S----|Yes|I
U----|Yes|M{{"Is 1 of the 3 SLSNMPManager<br>processes consuming more <br>CPU/memory than the others?"}}:::Decision
M----|Yes|V["Collect memory dump of that process only."]:::InfoAccNoClick
V----I
M----|No|W["Collect memory dump of all 3 processes."]:::InfoAccNoClick
W----I
L---|Yes|F["RTE troubleshooting:<br/>\- Verify RTE Count = 1.<br/>\- Check memory/CPU usage of SLPort.<br/>\- Run collector and<br>include memory dump."]:::InfoAccNoClick
F---G["Check SLErrors and SLErrorsInProtocol."]:::InfoAccNoClick
G---H{{"Can you link the issues with a connector? (Check for a new connector in the system.)"}}:::Decision
H---|Yes| K{{"Stop the element(s) using the connector. Has this solved the issue?"}}:::Decision
H---|No| J["\- Investigate the root cause<br> of the leak/RTE/crash.<br/>\- Check information events.<br/>\- Check the Recycle Bin.<br/>\- Check Event Viewer."]:::InfoAccNoClick
J---I
K---|Yes| Log["\- Add or update the Portlog.txt file in the Skyline DataMiner folder.<br/>\- Contact the connector developer to find the root cause in the protocol."]:::InfoAccNoClick
K---|No| I["Contact software team with the information and memory dump."]:::Start
XX([Start page]):::External
click XX "/dataminer/Troubleshooting/Troubleshooting_Flowcharts/Finding_a_Root_Cause.html" "Go to the start page"
linkStyle default stroke:#cccccc
classDef ExtRef fill:#9DDAF5,stroke:#000070,stroke-width:0px, color:#1E5179;
classDef Decision fill:#4BAEEA,stroke:#000070,stroke-width:0px, color:#FFFFFF;
classDef Start fill:#1E5179,stroke:#000070,stroke-width:0px, color:#FFFFFF;
classDef Solution fill:#58595B,stroke:#000070,stroke-width:0px, color:#FFFFFF;
classDef InfoAccClick fill:#999999,stroke:#000070,stroke-width:0px, color:#FFFFFF;
classDef InfoAccNoClick fill:#DDDDDD,stroke:#000070,stroke-width:0px, color:#1E5179;
classDef External fill:#9DDAF5,stroke:#000070,stroke-width:0px, color:#1E5179;
```

> [!NOTE]
>
> - Three SLSNMPManager processes will always run simultaneously, one for each version of SNMP.
> - In the *DataMiner.xml* file, you can customize which ports are used. For more information, see [Changing SNMP agent ports](xref:Changing_SNMP_agent_ports).
> - Ensure that the data source is **communicating as expected** and that all OIDs respond properly with the **expected data types**.
