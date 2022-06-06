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

[dir](https://github.com/r1skkam/TryHackMe-Windows-Event-Logs/blob/main/dir)

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
