# Setup-and-Use-a-Firewall-on-Windows

Author: Rajeev More  
Date: October 25,2025

## Objective
Create and test inbound firewall rules using Windows Defender Firewall with Advanced Security to block specific TCP ports (Telnet — 23, HTTP Web — 80).

## Tool Used
- Tool: Windows Defender Firewall with Advanced Security
- OS: Windows 10 
- Command Prompt 

## Steps to do the procedure
1. Open Windows Defender Firewall with Advanced Security
 - Press Win + R → type wf.msc → Enter

2. Create a new inbound rule (block Telnet — port 23)
 - In the left pane click Inbound Rules.
 - On the right pane click New Rule...
 - Select Port → Click Next.
 - Select TCP and Specific local ports: 23 → Click Next.
 - Select Block the connection → Click Next.
 - Apply to Domain, Private, Public (choose as required) → Click Next.
 - Name the rule: Block Telnet Port 23 → (optionally) add a description → Click Finish.

3. Create a second inbound rule (Block HTTP Web — port 80)
 - Repeat the steps above, using local port 80 and name it Block HTTP Web Port 80.
## Verification via Command Prompt
Run all commands in an elevated Command Prompt (Run as Administrator).

- Test Telnet (port 23):
  - telnet localhost 23 [ if the block worked you will get the following output ]
  - Connecting To localhost...Could not open connection to the host, on port 23: Connect failed
- Test HTTP Web (port 80):
  - telnet localhost 80 [ if the block worked you will get the following output ]
  - Connecting To localhost...Could not open connection to the host, on port 80: Connect failed

Once Testing is Done 
- In the left pane, click Inbound Rules.
- In the middle pane, scroll through the list and find your rules:
  - Block Telnet Port 23
  - Block HTTP Web Port 80
- Right-click the rule you want to remove → Click Delete.
- Confirm the deletion when prompted.

## Observations
- Windows Firewall successfully blocked inbound traffic for both Telnet (23) and HTTP (80).
- When rules were active, Telnet returned “Connect failed”.
- After deleting the rules, both ports became reachable again.

## Repository contents
Phishing-Email-Analysis/ 
├── README.md ← (this report) 
├── screenshots 
