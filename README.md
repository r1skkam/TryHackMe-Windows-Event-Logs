[TryHackMe | Windows Event Logs](https://tryhackme.com/room/windowseventlogs)

# TryHackMe-Windows-Event-Logs
`Introduction to Windows Event Logs and the tools to query them.`
## Task 1 What are event logs?
## Task 2 Event Viewer
`C:\Windows\System32\winevt\Logs`

There are 3 main ways of accessing these event logs within a Windows system:
1. Event Viewer (GUI-based application)
2. Wevtutil.exe (command-line tool)
3. Get-WinEvent (PowerShell cmdlet)

[Event Types - Win32 apps | Microsoft Docs](https://docs.microsoft.com/en-us/windows/win32/eventlog/event-types)

## Task 3 wevtutil.exe
[wevtutil | Microsoft Docs](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/wevtutil)

```


C:\Users\Administrator>whoami
win-1o0ujbnp9g7\administrator

C:\Users\Administrator>whoami /priv

PRIVILEGES INFORMATION
----------------------

Privilege Name                            Description                                                        State
========================================= ================================================================== ========
SeIncreaseQuotaPrivilege                  Adjust memory quotas for a process                                 Disabled
SeSecurityPrivilege                       Manage auditing and security log                                   Disabled
SeTakeOwnershipPrivilege                  Take ownership of files or other objects                           Disabled
SeLoadDriverPrivilege                     Load and unload device drivers                                     Disabled
SeSystemProfilePrivilege                  Profile system performance                                         Disabled
SeSystemtimePrivilege                     Change the system time                                             Disabled
SeProfileSingleProcessPrivilege           Profile single process                                             Disabled
SeIncreaseBasePriorityPrivilege           Increase scheduling priority                                       Disabled
SeCreatePagefilePrivilege                 Create a pagefile                                                  Disabled
SeBackupPrivilege                         Back up files and directories                                      Disabled
SeRestorePrivilege                        Restore files and directories                                      Disabled
SeShutdownPrivilege                       Shut down the system                                               Disabled
SeDebugPrivilege                          Debug programs                                                     Disabled
SeSystemEnvironmentPrivilege              Modify firmware environment values                                 Disabled
SeChangeNotifyPrivilege                   Bypass traverse checking                                           Enabled
SeRemoteShutdownPrivilege                 Force shutdown from a remote system                                Disabled
SeUndockPrivilege                         Remove computer from docking station                               Disabled
SeManageVolumePrivilege                   Perform volume maintenance tasks                                   Disabled
SeImpersonatePrivilege                    Impersonate a client after authentication                          Enabled
SeCreateGlobalPrivilege                   Create global objects                                              Enabled
SeIncreaseWorkingSetPrivilege             Increase a process working set                                     Disabled
SeTimeZonePrivilege                       Change the time zone                                               Disabled
SeCreateSymbolicLinkPrivilege             Create symbolic links                                              Disabled
SeDelegateSessionUserImpersonatePrivilege Obtain an impersonation token for another user in the same session Disabled

C:\Users\Administrator>
```
[wevtutil](https://github.com/r1skkam/TryHackMe-Windows-Event-Logs/blob/main/wevtutil)

[wevtutil el](https://github.com/r1skkam/TryHackMe-Windows-Event-Logs/blob/main/wevtutil%20el)

[Measure-Object (Microsoft.PowerShell.Utility) - PowerShell | Microsoft Docs](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-7.2)

```
PS C:\Users\Administrator> wevtutil el |Measure-Object


Count    : 1071
Average  :
Sum      :
Maximum  :
Minimum  :
Property :



PS C:\Users\Administrator>
```
