# Net User Detection

## Description

Detects execution of the Windows `net user` or `net1 user` command using Sysmon Process Create events.

## MITRE ATT&CK

- T1087.001 - Account Discovery: Local Account

## Detection Logic

The rule monitors Sysmon Event ID 1 (Process Create) and inspects the `CommandLine` field for execution of:

- net user
- net1 user

## Test

Run:

```cmd
net user
```

or

```cmd
net1 user
```

## Expected Result

Wazuh generates a high severity alert.

## False Positives

Low.

System administrators may legitimately use this command.
