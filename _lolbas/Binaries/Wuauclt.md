---
Name: wuauclt.exe
Description: Windows Update Client
Author: 'David Middlehurst'
Created: 2020-09-23
Commands:
  - Command: wuauclt.exe /UpdateDeploymentProvider Full_Path_To_DLL /RunHandlerComServer
    Description: Full_Path_To_DLL would be the absolute path to .DLL file and would execute code on attach.
    Usecase: Execute dll via attach/detach methods
    Category: Execute
    Privileges: User
    MitreID: T1218
    OperatingSystem: Windows 10
    Tags:
      - Execute: DLL
Full_Path:
  - Path: C:\Windows\System32\wuauclt.exe
  - Path: C:\Windows\UUS\amd64\wuauclt.exe
Detection:
  - Sigma: https://github.com/SigmaHQ/sigma/blob/683b63f8184b93c9564c4310d10c571cbe367e1e/rules/windows/network_connection/net_connection_win_wuauclt_network_connection.yml
  - Sigma: https://github.com/SigmaHQ/sigma/blob/683b63f8184b93c9564c4310d10c571cbe367e1e/rules/windows/process_creation/proc_creation_win_lolbin_wuauclt.yml
  - Sigma: https://github.com/SigmaHQ/sigma/blob/683b63f8184b93c9564c4310d10c571cbe367e1e/rules/windows/process_creation/proc_creation_win_wuauclt_execution.yml
  - IOC: wuauclt run with a parameter of a DLL path
  - IOC: Suspicious wuauclt Internet/network connections
Resources:
  - Link: https://dtm.uk/wuauclt/
Acknowledgement:
  - Person: David Middlehurst
    Handle: '@dtmsecurity'
---
