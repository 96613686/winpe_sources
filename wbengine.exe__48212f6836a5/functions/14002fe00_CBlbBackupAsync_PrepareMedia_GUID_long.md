# CBlbBackupAsync::PrepareMedia(_GUID *,long *)

- ea: `0x14002fe00`
- end: `0x14003063b`
- name: `?PrepareMedia@CBlbBackupAsync@@AEAAJPEAU_GUID@@PEAJ@Z`
- size: `2107`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this, struct _GUID *, int *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, service_task`

## callers

- `0x140019fd0`

## callees

- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x1400202a4`
- `0x140024088`
- `0x140026060`
- `0x14002fe00`
- `0x140033b94`
- `0x14003a8f0`
- `0x14003b924`
- `0x14003c434`
- `0x14003c54c`
- `0x14003c69c`
- `0x14003c9cc`
- `0x14008863c`
- `0x14008b088`
- `0x14008d3d8`
- `0x14009257c`
- `0x140134cc6`
- `0x140134d20`

## import_xrefs

- `KERNEL32!ReadFile` at `0x140030297`
- `KERNEL32!ReadFile` at `0x140030297`
- `KERNEL32!GetFileSizeEx` at `0x1400301dc`
- `KERNEL32!GetFileSizeEx` at `0x1400301dc`
- `KERNEL32!CreateFileW` at `0x140030044`
- `KERNEL32!CreateFileW` at `0x140030044`
- `KERNEL32!CloseHandle` at `0x14003018e`
- `KERNEL32!CloseHandle` at `0x1400303ba`
- `KERNEL32!CloseHandle` at `0x14003018e`
- `KERNEL32!CloseHandle` at `0x1400303ba`
- `KERNEL32!GetLastError` at `0x140030058`
- `KERNEL32!GetLastError` at `0x1400301e6`
- `KERNEL32!GetLastError` at `0x1400302a1`
- `KERNEL32!GetLastError` at `0x140030058`
- `KERNEL32!GetLastError` at `0x1400301e6`
- `KERNEL32!GetLastError` at `0x1400302a1`
- `ole32!CoTaskMemFree` at `0x1400301a3`
- `ole32!CoTaskMemFree` at `0x1400301a3`

## pseudocode

```c

```
