# XEPackage0::XE_ETWTarget::FindOrCreateETWSession(XE_ErrorContext *)

- ea: `0x1005c1ea0`
- end: `0x1005c24de`
- name: `?FindOrCreateETWSession@XE_ETWTarget@XEPackage0@@AEAAHPEAVXE_ErrorContext@@@Z`
- size: `1598`
- prototype: `__int64 __fastcall(XEPackage0::XE_ETWTarget *__hidden this, struct XE_ErrorContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1005c24f0`

## callees

- `0x100403070`
- `0x100404bf2`
- `0x100411fb0`
- `0x100442a60`
- `0x10044acd0`
- `0x1005c1ea0`
- `0x1005c2a70`
- `0x1005c2b70`
- `0x1005c4930`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1005c23eb`
- `KERNEL32!LocalFree` at `0x1005c23eb`
- `KERNEL32!GetLastError` at `0x1005c2336`
- `KERNEL32!GetLastError` at `0x1005c2336`
- `KERNEL32!FormatMessageW` at `0x1005c232c`
- `KERNEL32!FormatMessageW` at `0x1005c2363`
- `KERNEL32!FormatMessageW` at `0x1005c232c`
- `KERNEL32!FormatMessageW` at `0x1005c2363`
- `ADVAPI32!ControlTraceW` at `0x1005c1f46`
- `ADVAPI32!ControlTraceW` at `0x1005c2000`
- `ADVAPI32!ControlTraceW` at `0x1005c2140`
- `ADVAPI32!ControlTraceW` at `0x1005c215e`
- `ADVAPI32!ControlTraceW` at `0x1005c1f46`
- `ADVAPI32!ControlTraceW` at `0x1005c2000`
- `ADVAPI32!ControlTraceW` at `0x1005c2140`
- `ADVAPI32!ControlTraceW` at `0x1005c215e`
- `ADVAPI32!StartTraceW` at `0x1005c2271`
- `ADVAPI32!StartTraceW` at `0x1005c2271`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x1005c201c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x1005c201c`

## string_xrefs

- `0x1005c248d`: `The operating system returned error 5 (ACCESS_DENIED) while creating an ETW tracing session. ErrorFormat: Ensure that the SQL Server startup account is a member of the 'Performance Log Users' group and then retry your command.`

## pseudocode

```c

```
