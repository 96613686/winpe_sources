# BlbimgReadVolsnapControlItems<BLBIMGI_REPLICATION_CONTEXT>(BLBIMGI_REPLICATION_CONTEXT *,BLBIMGI_BACKUP_FILE *,ulong *,_LIST_ENTRY *,ulong *,uchar,uchar)

- ea: `0x1400b6a74`
- end: `0x1400b7647`
- name: `??$BlbimgReadVolsnapControlItems@UBLBIMGI_REPLICATION_CONTEXT@@@@YA?AW4_BLBIMG_RESULT_CODE@@PEAUBLBIMGI_REPLICATION_CONTEXT@@PEAVBLBIMGI_BACKUP_FILE@@PEAKPEAU_LIST_ENTRY@@2EE@Z`
- size: `3027`
- prototype: `__int64 __fastcall(_DWORD *Source1, __int64, DWORD *, __int64, _DWORD *, char, char)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400b2394`
- `0x1400b2fc0`
- `0x1400b93e0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14003c434`
- `0x14003c480`
- `0x1400b6a74`
- `0x1400b8f4c`
- `0x1400bb79c`
- `0x1400bb9b0`
- `0x140134cde`

## import_xrefs

- `KERNEL32!RtlCompareMemory` at `0x1400b6b57`
- `KERNEL32!RtlCompareMemory` at `0x1400b6f27`
- `KERNEL32!RtlCompareMemory` at `0x1400b6b57`
- `KERNEL32!RtlCompareMemory` at `0x1400b6f27`
- `KERNEL32!LocalAlloc` at `0x1400b6d7b`
- `KERNEL32!LocalAlloc` at `0x1400b7418`
- `KERNEL32!LocalAlloc` at `0x1400b6d7b`
- `KERNEL32!LocalAlloc` at `0x1400b7418`
- `KERNEL32!LocalFree` at `0x1400b6c19`
- `KERNEL32!LocalFree` at `0x1400b6dcb`
- `KERNEL32!LocalFree` at `0x1400b6e14`
- `KERNEL32!LocalFree` at `0x1400b6e1d`
- `KERNEL32!LocalFree` at `0x1400b75c5`
- `KERNEL32!LocalFree` at `0x1400b6c19`
- `KERNEL32!LocalFree` at `0x1400b6dcb`
- `KERNEL32!LocalFree` at `0x1400b6e14`
- `KERNEL32!LocalFree` at `0x1400b6e1d`
- `KERNEL32!LocalFree` at `0x1400b75c5`
- `KERNEL32!GetLastError` at `0x1400b6dbe`
- `KERNEL32!GetLastError` at `0x1400b74eb`
- `KERNEL32!GetLastError` at `0x1400b6dbe`
- `KERNEL32!GetLastError` at `0x1400b74eb`

## string_xrefs

- `0x1400b6bf7`: `readBuffer != NULL`
- `0x1400b6d30`: `readBuffer != NULL`

## pseudocode

```c

```
