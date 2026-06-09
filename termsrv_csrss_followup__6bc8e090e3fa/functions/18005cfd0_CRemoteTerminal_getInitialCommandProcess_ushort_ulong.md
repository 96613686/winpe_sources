# CRemoteTerminal::getInitialCommandProcess(ushort *,ulong *)

- ea: `0x18005cfd0`
- end: `0x18005d227`
- name: `?getInitialCommandProcess@CRemoteTerminal@@UEAAJPEAGPEAK@Z`
- size: `599`
- prototype: `int(CRemoteTerminal *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009940`
- `0x18000f0d0`
- `0x180012750`
- `0x180016558`
- `0x180033f60`
- `0x180051aa4`
- `0x18005cef8`
- `0x18005cfd0`
- `0x1800caed0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d190`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005d17e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005d17e`

## string_xrefs

- `0x18005d01f`: `CRemoteTerminal::getInitialCommandProcess`
- `0x18005d061`: `CRemoteTerminal::getInitialCommandProcess`
- `0x18005d0cc`: `%SYSTEMROOT%\System32\WinLogon.exe -type Debug`
- `0x18005d148`: `%%SYSTEMROOT%%\System32\WinLogon.exe -type Agent -parentSessionId %u`

## pseudocode

```c

```
