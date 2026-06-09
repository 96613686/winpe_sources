# BlbimgCheckIfDiffBackupPossible<BLBIMGI_BACKUP_CONTEXT>(BLBIMGI_BACKUP_CONTEXT *,ushort const *,void *,BLBIMGI_BACKUP_FILE *,_GUID,uchar *,void * *,ulong *)

- ea: `0x1400b04c4`
- end: `0x1400b124f`
- name: `??$BlbimgCheckIfDiffBackupPossible@UBLBIMGI_BACKUP_CONTEXT@@@@YA?AW4_BLBIMG_RESULT_CODE@@PEAUBLBIMGI_BACKUP_CONTEXT@@PEBGPEAXPEAVBLBIMGI_BACKUP_FILE@@U_GUID@@PEAEPEAPEAXPEAK@Z`
- size: `3467`
- prototype: `__int64 __fastcall(unsigned int *Source1, __int64, __int64, BLBIMGI_BACKUP_FILE *, UUID *, _BYTE *, __int64, DWORD *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400c1f5c`

## callees

- `0x1400063b4`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000bc6c`
- `0x140014200`
- `0x140014260`
- `0x14003c480`
- `0x1400b04c4`
- `0x1400b28c8`
- `0x1400b3ce8`
- `0x1400b7d90`
- `0x1400b80a0`
- `0x1400b8514`
- `0x1400b8980`
- `0x1400bc034`
- `0x1400bd330`
- `0x1400bd37c`
- `0x1400c3c80`
- `0x1400c3d08`
- `0x1400c44b4`
- `0x1400c64b0`
- `0x1400c6bfc`
- `0x1400cceb4`
- `0x140134cd2`
- `0x140134d20`

## import_xrefs

- `KERNEL32!RtlCompareMemory` at `0x1400b05ab`
- `KERNEL32!RtlCompareMemory` at `0x1400b05ab`
- `KERNEL32!LocalAlloc` at `0x1400b0ae8`
- `KERNEL32!LocalAlloc` at `0x1400b0bf1`
- `KERNEL32!LocalAlloc` at `0x1400b0ae8`
- `KERNEL32!LocalAlloc` at `0x1400b0bf1`
- `KERNEL32!LocalFree` at `0x1400b0bcc`
- `KERNEL32!LocalFree` at `0x1400b0be1`
- `KERNEL32!LocalFree` at `0x1400b0c45`
- `KERNEL32!LocalFree` at `0x1400b0c4e`
- `KERNEL32!LocalFree` at `0x1400b0ca2`
- `KERNEL32!LocalFree` at `0x1400b0ceb`
- `KERNEL32!LocalFree` at `0x1400b0d4b`
- `KERNEL32!LocalFree` at `0x1400b10e2`
- `KERNEL32!LocalFree` at `0x1400b0bcc`
- `KERNEL32!LocalFree` at `0x1400b0be1`
- `KERNEL32!LocalFree` at `0x1400b0c45`
- `KERNEL32!LocalFree` at `0x1400b0c4e`
- `KERNEL32!LocalFree` at `0x1400b0ca2`
- `KERNEL32!LocalFree` at `0x1400b0ceb`
- `KERNEL32!LocalFree` at `0x1400b0d4b`
- `KERNEL32!LocalFree` at `0x1400b10e2`
- `KERNEL32!CreateFileW` at `0x1400b0920`
- `KERNEL32!CreateFileW` at `0x1400b0920`
- `KERNEL32!CloseHandle` at `0x1400b0a12`
- `KERNEL32!CloseHandle` at `0x1400b0a20`
- `KERNEL32!CloseHandle` at `0x1400b0a12`
- `KERNEL32!CloseHandle` at `0x1400b0a20`
- `KERNEL32!RaiseException` at `0x1400b0d7f`
- `KERNEL32!RaiseException` at `0x1400b0d7f`
- `KERNEL32!GetLastError` at `0x1400b0959`
- `KERNEL32!GetLastError` at `0x1400b09e2`
- `KERNEL32!GetLastError` at `0x1400b0af6`
- `KERNEL32!GetLastError` at `0x1400b0c39`
- `KERNEL32!GetLastError` at `0x1400b0d5e`
- `KERNEL32!GetLastError` at `0x1400b105a`
- `KERNEL32!GetLastError` at `0x1400b0959`
- `KERNEL32!GetLastError` at `0x1400b09e2`
- `KERNEL32!GetLastError` at `0x1400b0af6`
- `KERNEL32!GetLastError` at `0x1400b0c39`
- `KERNEL32!GetLastError` at `0x1400b0d5e`
- `KERNEL32!GetLastError` at `0x1400b105a`
- `KERNEL32!DeviceIoControl` at `0x1400b09b9`
- `KERNEL32!DeviceIoControl` at `0x1400b1030`
- `KERNEL32!DeviceIoControl` at `0x1400b09b9`
- `KERNEL32!DeviceIoControl` at `0x1400b1030`
- `ntdll!RtlClearAllBits` at `0x1400b0b29`
- `ntdll!RtlClearAllBits` at `0x1400b0c1b`
- `ntdll!RtlClearAllBits` at `0x1400b0b29`
- `ntdll!RtlClearAllBits` at `0x1400b0c1b`
- `ntdll!RtlSetBits` at `0x1400b0cda`
- `ntdll!RtlSetBits` at `0x1400b0da0`
- `ntdll!RtlSetBits` at `0x1400b10d3`
- `ntdll!RtlSetBits` at `0x1400b0cda`
- `ntdll!RtlSetBits` at `0x1400b0da0`
- `ntdll!RtlSetBits` at `0x1400b10d3`
- `ntdll!RtlNumberOfSetBits` at `0x1400b0dd4`
- `ntdll!RtlNumberOfSetBits` at `0x1400b0e15`
- `ntdll!RtlNumberOfSetBits` at `0x1400b0e3e`
- `ntdll!RtlNumberOfSetBits` at `0x1400b0e4c`
- `ntdll!RtlNumberOfSetBits` at `0x1400b0dd4`
- `ntdll!RtlNumberOfSetBits` at `0x1400b0e15`
- `ntdll!RtlNumberOfSetBits` at `0x1400b0e3e`
- `ntdll!RtlNumberOfSetBits` at `0x1400b0e4c`
- `ntdll!RtlInitializeBitMap` at `0x1400b0b1f`
- `ntdll!RtlInitializeBitMap` at `0x1400b0c11`
- `ntdll!RtlInitializeBitMap` at `0x1400b0db2`
- `ntdll!RtlInitializeBitMap` at `0x1400b0b1f`
- `ntdll!RtlInitializeBitMap` at `0x1400b0c11`
- `ntdll!RtlInitializeBitMap` at `0x1400b0db2`
- `ntdll!RtlAreBitsClear` at `0x1400b0cc7`
- `ntdll!RtlAreBitsClear` at `0x1400b0cc7`
- `RPCRT4!UuidToStringW` at `0x1400b0852`
- `RPCRT4!UuidToStringW` at `0x1400b0852`
- `RPCRT4!RpcStringFreeW` at `0x1400b08f2`
- `RPCRT4!RpcStringFreeW` at `0x1400b08f2`

## string_xrefs

- `0x1400b08a2`: `\\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy{`

## pseudocode

```c

```
