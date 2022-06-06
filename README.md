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
Microsoft Windows [Version 10.0.17763.737]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\Users\Administrator>dir
 Volume in drive C has no label.
 Volume Serial Number is F0DC-5D15

 Directory of C:\Users\Administrator

05/11/2021  08:29 AM    <DIR>          .
05/11/2021  08:29 AM    <DIR>          ..
12/04/2020  05:55 PM    <DIR>          3D Objects
12/04/2020  05:55 PM    <DIR>          Contacts
12/18/2020  11:45 AM    <DIR>          Desktop
06/06/2022  07:15 AM    <DIR>          Documents
12/04/2020  05:55 PM    <DIR>          Downloads
12/04/2020  05:55 PM    <DIR>          Favorites
12/04/2020  05:55 PM    <DIR>          Links
12/04/2020  05:55 PM    <DIR>          Music
12/04/2020  05:55 PM    <DIR>          Pictures
12/04/2020  05:55 PM    <DIR>          Saved Games
12/04/2020  05:55 PM    <DIR>          Searches
12/04/2020  05:55 PM    <DIR>          Videos
               0 File(s)              0 bytes
              14 Dir(s)   4,412,194,816 bytes free

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
```
C:\Users\Administrator>wevtutil
Command is not specified.
Windows Events Command Line Utility.

Enables you to retrieve information about event logs and publishers, install
and uninstall event manifests, run queries, and export, archive, and clear logs.

Usage:

You can use either the short (for example, ep /uni) or long (for example,
enum-publishers /unicode) version of the command and option names. Commands,
options and option values are not case-sensitive.

Variables are noted in all upper-case.

wevtutil COMMAND [ARGUMENT [ARGUMENT] ...] [/OPTION:VALUE [/OPTION:VALUE] ...]

Commands:

el | enum-logs          List log names.
gl | get-log            Get log configuration information.
sl | set-log            Modify configuration of a log.
ep | enum-publishers    List event publishers.
gp | get-publisher      Get publisher configuration information.
im | install-manifest   Install event publishers and logs from manifest.
um | uninstall-manifest Uninstall event publishers and logs from manifest.
qe | query-events       Query events from a log or log file.
gli | get-log-info      Get log status information.
epl | export-log        Export a log.
al | archive-log        Archive an exported log.
cl | clear-log          Clear a log.

Common options:

/{r | remote}:VALUE
If specified, run the command on a remote computer. VALUE is the remote computer
name. Options /im and /um do not support remote operations.

/{u | username}:VALUE
Specify a different user to log on to the remote computer. VALUE is a user name
in the form domain\user or user. Only applicable when option /r is specified.

/{p | password}:VALUE
Password for the specified user. If not specified, or if VALUE is "*", the user
will be prompted to enter a password. Only applicable when the /u option is
specified.

/{a | authentication}:[Default|Negotiate|Kerberos|NTLM]
Authentication type for connecting to remote computer. The default is Negotiate.

/{uni | unicode}:[true|false]
Display output in Unicode. If true, then output is in Unicode.

To learn more about a specific command, type the following:

wevtutil COMMAND /?

C:\Users\Administrator>
```
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
