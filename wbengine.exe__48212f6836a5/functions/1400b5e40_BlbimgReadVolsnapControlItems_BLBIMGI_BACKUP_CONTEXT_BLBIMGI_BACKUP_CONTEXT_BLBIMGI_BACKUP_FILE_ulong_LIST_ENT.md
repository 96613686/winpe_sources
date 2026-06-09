# BlbimgReadVolsnapControlItems<BLBIMGI_BACKUP_CONTEXT>(BLBIMGI_BACKUP_CONTEXT *,BLBIMGI_BACKUP_FILE *,ulong *,_LIST_ENTRY *,ulong *,uchar,uchar)

- ea: `0x1400b5e40`
- end: `0x1400b6a6d`
- name: `??$BlbimgReadVolsnapControlItems@UBLBIMGI_BACKUP_CONTEXT@@@@YA?AW4_BLBIMG_RESULT_CODE@@PEAUBLBIMGI_BACKUP_CONTEXT@@PEAVBLBIMGI_BACKUP_FILE@@PEAKPEAU_LIST_ENTRY@@2EE@Z`
- size: `3117`
- prototype: `__int64 __fastcall(_DWORD *Source1, __int64, DWORD *, __int64, _DWORD *, char, char)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400b1e60`
- `0x1400b28c8`
- `0x1400b93e0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14003c434`
- `0x14003c480`
- `0x1400b5e40`
- `0x1400b8f4c`
- `0x1400bb79c`
- `0x1400bb9b0`
- `0x1400cc558`
- `0x140134cde`

## import_xrefs

- `KERNEL32!RtlCompareMemory` at `0x1400b5f38`
- `KERNEL32!RtlCompareMemory` at `0x1400b634e`
- `KERNEL32!RtlCompareMemory` at `0x1400b5f38`
- `KERNEL32!RtlCompareMemory` at `0x1400b634e`
- `KERNEL32!LocalAlloc` at `0x1400b61a0`
- `KERNEL32!LocalAlloc` at `0x1400b683e`
- `KERNEL32!LocalAlloc` at `0x1400b61a0`
- `KERNEL32!LocalAlloc` at `0x1400b683e`
- `KERNEL32!LocalFree` at `0x1400b6016`
- `KERNEL32!LocalFree` at `0x1400b61f3`
- `KERNEL32!LocalFree` at `0x1400b623c`
- `KERNEL32!LocalFree` at `0x1400b6245`
- `KERNEL32!LocalFree` at `0x1400b69e4`
- `KERNEL32!LocalFree` at `0x1400b6016`
- `KERNEL32!LocalFree` at `0x1400b61f3`
- `KERNEL32!LocalFree` at `0x1400b623c`
- `KERNEL32!LocalFree` at `0x1400b6245`
- `KERNEL32!LocalFree` at `0x1400b69e4`
- `KERNEL32!GetLastError` at `0x1400b61e6`
- `KERNEL32!GetLastError` at `0x1400b6911`
- `KERNEL32!GetLastError` at `0x1400b61e6`
- `KERNEL32!GetLastError` at `0x1400b6911`

## string_xrefs

- `0x1400b5ff4`: `readBuffer != NULL`
- `0x1400b6155`: `readBuffer != NULL`

## pseudocode

```c

```
