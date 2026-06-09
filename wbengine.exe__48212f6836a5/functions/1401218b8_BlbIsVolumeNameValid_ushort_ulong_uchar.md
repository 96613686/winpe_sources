# BlbIsVolumeNameValid(ushort *,ulong,uchar *)

- ea: `0x1401218b8`
- end: `0x140121ad1`
- name: `?BlbIsVolumeNameValid@@YAJPEAGKPEAE@Z`
- size: `537`
- prototype: `__int64 __fastcall(wchar_t *String2, unsigned int, unsigned __int8 *)`
- caller_count: `11`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400290e4`
- `0x140029cf4`
- `0x14004647c`
- `0x140048e00`
- `0x14004d420`
- `0x14005baf8`
- `0x14005cedc`
- `0x140079410`
- `0x140104e8c`
- `0x14010e004`
- `0x14010fc5c`

## callees

- `0x14000bb4c`
- `0x140014260`
- `0x140028500`
- `0x14008f8ec`
- `0x1401218b8`
- `0x140134d20`

## import_xrefs

- `KERNEL32!FindVolumeClose` at `0x140121a69`
- `KERNEL32!FindVolumeClose` at `0x140121a69`
- `KERNEL32!FindNextVolumeW` at `0x1401219e8`
- `KERNEL32!FindNextVolumeW` at `0x1401219e8`
- `KERNEL32!FindFirstVolumeW` at `0x140121967`
- `KERNEL32!FindFirstVolumeW` at `0x140121967`
- `KERNEL32!GetLastError` at `0x140121976`
- `KERNEL32!GetLastError` at `0x1401219f2`
- `KERNEL32!GetLastError` at `0x140121976`
- `KERNEL32!GetLastError` at `0x1401219f2`
- `msvcrt!_wcsicmp` at `0x14012194b`
- `msvcrt!_wcsicmp` at `0x1401219d3`
- `msvcrt!_wcsicmp` at `0x14012194b`
- `msvcrt!_wcsicmp` at `0x1401219d3`
- `ole32!CoTaskMemFree` at `0x140121a5a`
- `ole32!CoTaskMemFree` at `0x140121a5a`

## pseudocode

```c

```
