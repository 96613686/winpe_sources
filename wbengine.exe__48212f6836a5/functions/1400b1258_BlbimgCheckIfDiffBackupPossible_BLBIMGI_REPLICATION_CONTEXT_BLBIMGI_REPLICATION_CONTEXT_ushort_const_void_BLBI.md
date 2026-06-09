# BlbimgCheckIfDiffBackupPossible<BLBIMGI_REPLICATION_CONTEXT>(BLBIMGI_REPLICATION_CONTEXT *,ushort const *,void *,BLBIMGI_BACKUP_FILE *,_GUID,uchar *,void * *,ulong *)

- ea: `0x1400b1258`
- end: `0x1400b1e57`
- name: `??$BlbimgCheckIfDiffBackupPossible@UBLBIMGI_REPLICATION_CONTEXT@@@@YA?AW4_BLBIMG_RESULT_CODE@@PEAUBLBIMGI_REPLICATION_CONTEXT@@PEBGPEAXPEAVBLBIMGI_BACKUP_FILE@@U_GUID@@PEAEPEAPEAXPEAK@Z`
- size: `3071`
- prototype: `__int64 __fastcall(unsigned int *Source1, __int64, __int64, __int64, UUID *, _BYTE *, int, DWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400020d0`

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
- `0x1400b1258`
- `0x1400b2fc0`
- `0x1400b3ce8`
- `0x1400b7d90`
- `0x1400b80a0`
- `0x1400b8514`
- `0x1400b8980`
- `0x1400bc034`
- `0x1400c3c80`
- `0x1400c3d08`
- `0x140134cd2`
- `0x140134d20`

## import_xrefs

- `KERNEL32!RtlCompareMemory` at `0x1400b1318`
- `KERNEL32!RtlCompareMemory` at `0x1400b1318`
- `KERNEL32!LocalAlloc` at `0x1400b16f6`
- `KERNEL32!LocalAlloc` at `0x1400b17f2`
- `KERNEL32!LocalAlloc` at `0x1400b16f6`
- `KERNEL32!LocalAlloc` at `0x1400b17f2`
- `KERNEL32!LocalFree` at `0x1400b17da`
- `KERNEL32!LocalFree` at `0x1400b1844`
- `KERNEL32!LocalFree` at `0x1400b184d`
- `KERNEL32!LocalFree` at `0x1400b189f`
- `KERNEL32!LocalFree` at `0x1400b18ea`
- `KERNEL32!LocalFree` at `0x1400b194b`
- `KERNEL32!LocalFree` at `0x1400b1cf1`
- `KERNEL32!LocalFree` at `0x1400b17da`
- `KERNEL32!LocalFree` at `0x1400b1844`
- `KERNEL32!LocalFree` at `0x1400b184d`
- `KERNEL32!LocalFree` at `0x1400b189f`
- `KERNEL32!LocalFree` at `0x1400b18ea`
- `KERNEL32!LocalFree` at `0x1400b194b`
- `KERNEL32!LocalFree` at `0x1400b1cf1`
- `KERNEL32!CreateFileW` at `0x1400b1526`
- `KERNEL32!CreateFileW` at `0x1400b1526`
- `KERNEL32!CloseHandle` at `0x1400b161f`
- `KERNEL32!CloseHandle` at `0x1400b162d`
- `KERNEL32!CloseHandle` at `0x1400b161f`
- `KERNEL32!CloseHandle` at `0x1400b162d`
- `KERNEL32!RaiseException` at `0x1400b197f`
- `KERNEL32!RaiseException` at `0x1400b197f`
- `KERNEL32!GetLastError` at `0x1400b155f`
- `KERNEL32!GetLastError` at `0x1400b15ef`
- `KERNEL32!GetLastError` at `0x1400b1704`
- `KERNEL32!GetLastError` at `0x1400b1838`
- `KERNEL32!GetLastError` at `0x1400b195e`
- `KERNEL32!GetLastError` at `0x1400b1b69`
- `KERNEL32!GetLastError` at `0x1400b155f`
- `KERNEL32!GetLastError` at `0x1400b15ef`
- `KERNEL32!GetLastError` at `0x1400b1704`
- `KERNEL32!GetLastError` at `0x1400b1838`
- `KERNEL32!GetLastError` at `0x1400b195e`
- `KERNEL32!GetLastError` at `0x1400b1b69`
- `KERNEL32!DeviceIoControl` at `0x1400b15c6`
- `KERNEL32!DeviceIoControl` at `0x1400b1b38`
- `KERNEL32!DeviceIoControl` at `0x1400b15c6`
- `KERNEL32!DeviceIoControl` at `0x1400b1b38`
- `ntdll!RtlClearAllBits` at `0x1400b1737`
- `ntdll!RtlClearAllBits` at `0x1400b1819`
- `ntdll!RtlClearAllBits` at `0x1400b1737`
- `ntdll!RtlClearAllBits` at `0x1400b1819`
- `ntdll!RtlSetBits` at `0x1400b18d8`
- `ntdll!RtlSetBits` at `0x1400b1be9`
- `ntdll!RtlSetBits` at `0x1400b1bfb`
- `ntdll!RtlSetBits` at `0x1400b18d8`
- `ntdll!RtlSetBits` at `0x1400b1be9`
- `ntdll!RtlSetBits` at `0x1400b1bfb`
- `ntdll!RtlNumberOfSetBits` at `0x1400b1c36`
- `ntdll!RtlNumberOfSetBits` at `0x1400b1c77`
- `ntdll!RtlNumberOfSetBits` at `0x1400b1ca0`
- `ntdll!RtlNumberOfSetBits` at `0x1400b1cae`
- `ntdll!RtlNumberOfSetBits` at `0x1400b1c36`
- `ntdll!RtlNumberOfSetBits` at `0x1400b1c77`
- `ntdll!RtlNumberOfSetBits` at `0x1400b1ca0`
- `ntdll!RtlNumberOfSetBits` at `0x1400b1cae`
- `ntdll!RtlInitializeBitMap` at `0x1400b172d`
- `ntdll!RtlInitializeBitMap` at `0x1400b180f`
- `ntdll!RtlInitializeBitMap` at `0x1400b1c0d`
- `ntdll!RtlInitializeBitMap` at `0x1400b172d`
- `ntdll!RtlInitializeBitMap` at `0x1400b180f`
- `ntdll!RtlInitializeBitMap` at `0x1400b1c0d`
- `ntdll!RtlAreBitsClear` at `0x1400b18c5`
- `ntdll!RtlAreBitsClear` at `0x1400b18c5`
- `RPCRT4!UuidToStringW` at `0x1400b144c`
- `RPCRT4!UuidToStringW` at `0x1400b144c`
- `RPCRT4!RpcStringFreeW` at `0x1400b14f8`
- `RPCRT4!RpcStringFreeW` at `0x1400b14f8`

## string_xrefs

- `0x1400b14a0`: `\\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy{`

## pseudocode

```c

```
