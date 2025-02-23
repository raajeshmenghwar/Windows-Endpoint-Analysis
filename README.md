# Windows Endpoint Analysis  

## Overview  
This project documents the analysis of a suspicious binary (`challenge.exe`) discovered during an investigation. The analysis includes process behavior, network connections, persistence mechanisms, and system modifications.  

### Key Findings:  
1️. **Malicious Process Identification** – Detected the running `challenge.exe` process and its network connection using `tasklist` and `netstat`.  
2️. **Persistence Mechanisms** – Identified registry entries, scheduled tasks, and services used for maintaining persistence.  
3️. **Shared Resources & Exfiltration** – Analyzed shared folders (`xkalibur`, `Exfil`) for potential data theft.  
4️. **Scheduled Task & Backdoor** – Investigated a malicious task (`ayttpnzc`) and backdoor service (`WindowsActiveService`).  

## Important Commands  

This guide provides essential **commands and techniques** to analyze an endpoint, detect anomalies, and investigate malicious activities.

## Network Analysis

- `net share` – Displays shared resources on the local system.
- `net view` – Lists shared resources on a remote or local system.
- `net sessions` – Shows active SMB sessions on the system.
- `net use` – Displays and manages network connections and mapped drives.
- `netstat` – Displays active network connections and listening ports.
- `netstat -anob` – Shows active connections with associated processes and executables.

## Process Analysis

- `tasklist` – Lists all running processes.
- `tasklist /v` – Displays detailed information about each process.
- `tasklist /M` – Shows processes using specific DLLs.
- `tasklist /M /FI "PID eq 123"` – Filters processes by PID to list associated modules.
- `wmic` – Windows Management Instrumentation command-line utility.
- `wmic process where processid=123 get name, parentprocessid` – Retrieves process name and parent process ID.

## Services Analysis

- `sc` – Command-line tool for managing Windows services.
- `sc create <ServiceName> binpath=<Path> start=auto` – Creates a new service.
- `net start <ServiceName>` – Starts a service.
- `sc query` – Queries the status of a service.
- `sc query state=all` – Displays all services and their statuses.
- `sc qc <ServiceName>` – Displays service configuration details.

## Scheduled Task Analysis

- `schtasks /create /tn <TaskName> /tr <TaskPath> /sc <Schedule> /st <Time> /ru <User>` – Creates a scheduled task.

## Sysmon Event Analysis

- `Get-WinEvent -LogName "Microsoft-Windows-Sysmon/Operational"` – Retrieves Sysmon logs for detailed process and network event monitoring.

## Additional Commands for Investigation

- `whoami` – Displays the current user’s information.
- `ipconfig /all` – Shows detailed network adapter configurations.
- `get-process` – Lists active processes (alternative to `tasklist`).
- `net localgroup administrators` – Lists local administrator accounts.

🔍 **Use these commands to investigate suspicious activities and detect threats effectively.**


Follow for more updates and insights:

- **[LinkedIn](https://www.linkedin.com/in/raajeshmenghwar)**
- **[Medium](https://raajeshmenghwar.medium.com)**

**Keep hacking and stay curious!**

