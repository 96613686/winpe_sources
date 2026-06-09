# BlbimgExcludeExistingDiffAreas<BLBIMGI_BACKUP_CONTEXT>(BLBIMGI_BACKUP_CONTEXT *,BLBIMGI_BACKUP_FILE *,_RTL_BITMAP *,ulong *)

- ea: `0x1400b28c8`
- end: `0x1400b2fb8`
- name: `??$BlbimgExcludeExistingDiffAreas@UBLBIMGI_BACKUP_CONTEXT@@@@YA?AW4_BLBIMG_RESULT_CODE@@PEAUBLBIMGI_BACKUP_CONTEXT@@PEAVBLBIMGI_BACKUP_FILE@@PEAU_RTL_BITMAP@@PEAK@Z`
- size: `1776`
- prototype: `__int64 __fastcall(unsigned int *Source1, __int64, struct _RTL_BITMAP *, DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1400b04c4`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000bcbc`
- `0x14003c69c`
- `0x1400b28c8`
- `0x1400b5e40`
- `0x1400b7d58`
- `0x1400b80a0`
- `0x1400b8980`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1400b295c`
- `KERNEL32!LocalAlloc` at `0x1400b2b70`
- `KERNEL32!LocalAlloc` at `0x1400b295c`
- `KERNEL32!LocalAlloc` at `0x1400b2b70`
- `KERNEL32!LocalFree` at `0x1400b2bdb`
- `KERNEL32!LocalFree` at `0x1400b2d3e`
- `KERNEL32!LocalFree` at `0x1400b2f1a`
- `KERNEL32!LocalFree` at `0x1400b2f4e`
- `KERNEL32!LocalFree` at `0x1400b2f65`
- `KERNEL32!LocalFree` at `0x1400b2bdb`
- `KERNEL32!LocalFree` at `0x1400b2d3e`
- `KERNEL32!LocalFree` at `0x1400b2f1a`
- `KERNEL32!LocalFree` at `0x1400b2f4e`
- `KERNEL32!LocalFree` at `0x1400b2f65`
- `KERNEL32!GetLastError` at `0x1400b296b`
- `KERNEL32!GetLastError` at `0x1400b2bc2`
- `KERNEL32!GetLastError` at `0x1400b296b`
- `KERNEL32!GetLastError` at `0x1400b2bc2`
- `ntdll!RtlNumberOfSetBits` at `0x1400b2ceb`
- `ntdll!RtlNumberOfSetBits` at `0x1400b2e57`
- `ntdll!RtlNumberOfSetBits` at `0x1400b2ceb`
- `ntdll!RtlNumberOfSetBits` at `0x1400b2e57`
- `ntdll!RtlInitializeBitMap` at `0x1400b298a`
- `ntdll!RtlInitializeBitMap` at `0x1400b298a`
- `ntdll!RtlSetAllBits` at `0x1400b2994`
- `ntdll!RtlSetAllBits` at `0x1400b2994`

## string_xrefs

- `0x1400b2a81`: `!IsListEmpty(&diffsInSource)`

## pseudocode

```c

```
