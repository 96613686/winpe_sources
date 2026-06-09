# CRemoteTerminal::getInitialCommandProcess(ushort *,ulong *)

- ea: `0x18005a320`
- end: `0x18005a56a`
- name: `?getInitialCommandProcess@CRemoteTerminal@@UEAAJPEAGPEAK@Z`
- size: `586`
- prototype: `int(CRemoteTerminal *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a210`
- `0x18000ef50`
- `0x180011f80`
- `0x180015ab0`
- `0x1800321f0`
- `0x18004f3fc`
- `0x18005a24c`
- `0x18005a320`
- `0x1800c4e00`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4da`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005a4ce`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005a4ce`

## string_xrefs

- `0x18005a36f`: `CRemoteTerminal::getInitialCommandProcess`
- `0x18005a3b1`: `CRemoteTerminal::getInitialCommandProcess`
- `0x18005a41c`: `%SYSTEMROOT%\System32\WinLogon.exe -type Debug`
- `0x18005a498`: `%%SYSTEMROOT%%\System32\WinLogon.exe -type Agent -parentSessionId %u`

## pseudocode

```c

```
