# BlbimgExcludeExistingDiffAreas<BLBIMGI_REPLICATION_CONTEXT>(BLBIMGI_REPLICATION_CONTEXT *,BLBIMGI_BACKUP_FILE *,_RTL_BITMAP *,ulong *)

- ea: `0x1400b2fc0`
- end: `0x1400b36a0`
- name: `??$BlbimgExcludeExistingDiffAreas@UBLBIMGI_REPLICATION_CONTEXT@@@@YA?AW4_BLBIMG_RESULT_CODE@@PEAUBLBIMGI_REPLICATION_CONTEXT@@PEAVBLBIMGI_BACKUP_FILE@@PEAU_RTL_BITMAP@@PEAK@Z`
- size: `1760`
- prototype: `__int64 __fastcall(unsigned int *Source1, __int64, struct _RTL_BITMAP *, DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1400b1258`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000bcbc`
- `0x14003c69c`
- `0x1400b2fc0`
- `0x1400b6a74`
- `0x1400b7d58`
- `0x1400b80a0`
- `0x1400b8980`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1400b304f`
- `KERNEL32!LocalAlloc` at `0x1400b3262`
- `KERNEL32!LocalAlloc` at `0x1400b304f`
- `KERNEL32!LocalAlloc` at `0x1400b3262`
- `KERNEL32!LocalFree` at `0x1400b32cd`
- `KERNEL32!LocalFree` at `0x1400b3430`
- `KERNEL32!LocalFree` at `0x1400b360c`
- `KERNEL32!LocalFree` at `0x1400b3640`
- `KERNEL32!LocalFree` at `0x1400b3657`
- `KERNEL32!LocalFree` at `0x1400b32cd`
- `KERNEL32!LocalFree` at `0x1400b3430`
- `KERNEL32!LocalFree` at `0x1400b360c`
- `KERNEL32!LocalFree` at `0x1400b3640`
- `KERNEL32!LocalFree` at `0x1400b3657`
- `KERNEL32!GetLastError` at `0x1400b305e`
- `KERNEL32!GetLastError` at `0x1400b32b4`
- `KERNEL32!GetLastError` at `0x1400b305e`
- `KERNEL32!GetLastError` at `0x1400b32b4`
- `ntdll!RtlNumberOfSetBits` at `0x1400b33dd`
- `ntdll!RtlNumberOfSetBits` at `0x1400b3549`
- `ntdll!RtlNumberOfSetBits` at `0x1400b33dd`
- `ntdll!RtlNumberOfSetBits` at `0x1400b3549`
- `ntdll!RtlInitializeBitMap` at `0x1400b307d`
- `ntdll!RtlInitializeBitMap` at `0x1400b307d`
- `ntdll!RtlSetAllBits` at `0x1400b3087`
- `ntdll!RtlSetAllBits` at `0x1400b3087`

## string_xrefs

- `0x1400b3173`: `!IsListEmpty(&diffsInSource)`

## pseudocode

```c

```
