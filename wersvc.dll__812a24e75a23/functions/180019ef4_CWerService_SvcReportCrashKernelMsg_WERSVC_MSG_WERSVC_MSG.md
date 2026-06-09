# CWerService::SvcReportCrashKernelMsg(_WERSVC_MSG *,_WERSVC_MSG *)

- ea: `0x180019ef4`
- end: `0x180019fc0`
- name: `?SvcReportCrashKernelMsg@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z`
- size: `204`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180014fa4`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x180013df4`
- `0x180016ac0`
- `0x180019ef4`

## import_xrefs

- `ntdll!NtClose` at `0x180019f5c`
- `ntdll!NtClose` at `0x180019f5c`
- `wer!WerpAddTerminationReason` at `0x180019faf`
- `wer!WerpAddTerminationReason` at `0x180019faf`

## pseudocode

```c

```
