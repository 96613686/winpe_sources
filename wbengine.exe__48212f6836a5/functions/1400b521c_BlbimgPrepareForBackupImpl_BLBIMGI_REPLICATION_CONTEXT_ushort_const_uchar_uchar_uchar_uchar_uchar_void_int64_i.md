# BlbimgPrepareForBackupImpl<BLBIMGI_REPLICATION_CONTEXT>(ushort const *,uchar,uchar,uchar,uchar,uchar (*)(void *,__int64,__int64),void *,uchar,__int64 *,BLBIMGI_REPLICATION_CONTEXT * *,__int64 *,__int64 *,ulong *)

- ea: `0x1400b521c`
- end: `0x1400b5e39`
- name: `??$BlbimgPrepareForBackupImpl@UBLBIMGI_REPLICATION_CONTEXT@@@@YA?AW4_BLBIMG_RESULT_CODE@@PEBGEEEEP6AEPEAX_J2@Z1EPEA_JPEAPEAUBLBIMGI_REPLICATION_CONTEXT@@44PEAK@Z`
- size: `3101`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, char, char, char, int, int, char, unsigned __int64 *, __int64 *, _QWORD *, _QWORD *, DWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, loader_planting`

## callers

- `0x1400bf788`

## callees

- `0x1400063b4`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x14003c434`
- `0x14003c69c`
- `0x14003cb70`
- `0x1400b38ec`
- `0x1400b521c`
- `0x1400b7be8`
- `0x1400b8440`
- `0x1400b8514`
- `0x1400b8c14`
- `0x1400b9ed8`
- `0x1400ba2a8`
- `0x1400baf74`
- `0x1400bb1f0`
- `0x1400be8b0`
- `0x1400c3fec`
- `0x1400c45c0`
- `0x140134d20`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1400b58a6`
- `KERNEL32!LocalAlloc` at `0x1400b5a84`
- `KERNEL32!LocalAlloc` at `0x1400b5c15`
- `KERNEL32!LocalAlloc` at `0x1400b58a6`
- `KERNEL32!LocalAlloc` at `0x1400b5a84`
- `KERNEL32!LocalAlloc` at `0x1400b5c15`
- `KERNEL32!LocalFree` at `0x1400b5830`
- `KERNEL32!LocalFree` at `0x1400b58df`
- `KERNEL32!LocalFree` at `0x1400b598c`
- `KERNEL32!LocalFree` at `0x1400b5a9e`
- `KERNEL32!LocalFree` at `0x1400b5bae`
- `KERNEL32!LocalFree` at `0x1400b5c33`
- `KERNEL32!LocalFree` at `0x1400b5cc6`
- `KERNEL32!LocalFree` at `0x1400b5cd0`
- `KERNEL32!LocalFree` at `0x1400b5cd9`
- `KERNEL32!LocalFree` at `0x1400b5830`
- `KERNEL32!LocalFree` at `0x1400b58df`
- `KERNEL32!LocalFree` at `0x1400b598c`
- `KERNEL32!LocalFree` at `0x1400b5a9e`
- `KERNEL32!LocalFree` at `0x1400b5bae`
- `KERNEL32!LocalFree` at `0x1400b5c33`
- `KERNEL32!LocalFree` at `0x1400b5cc6`
- `KERNEL32!LocalFree` at `0x1400b5cd0`
- `KERNEL32!LocalFree` at `0x1400b5cd9`
- `KERNEL32!CreateFileW` at `0x1400b548a`
- `KERNEL32!CreateFileW` at `0x1400b548a`
- `KERNEL32!CloseHandle` at `0x1400b557d`
- `KERNEL32!CloseHandle` at `0x1400b5586`
- `KERNEL32!CloseHandle` at `0x1400b57a5`
- `KERNEL32!CloseHandle` at `0x1400b57ae`
- `KERNEL32!CloseHandle` at `0x1400b5983`
- `KERNEL32!CloseHandle` at `0x1400b557d`
- `KERNEL32!CloseHandle` at `0x1400b5586`
- `KERNEL32!CloseHandle` at `0x1400b57a5`
- `KERNEL32!CloseHandle` at `0x1400b57ae`
- `KERNEL32!CloseHandle` at `0x1400b5983`
- `KERNEL32!GetLastError` at `0x1400b5499`
- `KERNEL32!GetLastError` at `0x1400b5825`
- `KERNEL32!GetLastError` at `0x1400b585f`
- `KERNEL32!GetLastError` at `0x1400b58d4`
- `KERNEL32!GetLastError` at `0x1400b5977`
- `KERNEL32!GetLastError` at `0x1400b5a93`
- `KERNEL32!GetLastError` at `0x1400b5c27`
- `KERNEL32!GetLastError` at `0x1400b5499`
- `KERNEL32!GetLastError` at `0x1400b5825`
- `KERNEL32!GetLastError` at `0x1400b585f`
- `KERNEL32!GetLastError` at `0x1400b58d4`
- `KERNEL32!GetLastError` at `0x1400b5977`
- `KERNEL32!GetLastError` at `0x1400b5a93`
- `KERNEL32!GetLastError` at `0x1400b5c27`
- `KERNEL32!DeviceIoControl` at `0x1400b580f`
- `KERNEL32!DeviceIoControl` at `0x1400b596d`
- `KERNEL32!DeviceIoControl` at `0x1400b580f`
- `KERNEL32!DeviceIoControl` at `0x1400b596d`
- `ntdll!RtlNumberOfSetBits` at `0x1400b5d01`
- `ntdll!RtlNumberOfSetBits` at `0x1400b5d91`
- `ntdll!RtlNumberOfSetBits` at `0x1400b5d01`
- `ntdll!RtlNumberOfSetBits` at `0x1400b5d91`
- `ntdll!RtlInitializeBitMap` at `0x1400b5aba`
- `ntdll!RtlInitializeBitMap` at `0x1400b5c5e`
- `ntdll!RtlInitializeBitMap` at `0x1400b5aba`
- `ntdll!RtlInitializeBitMap` at `0x1400b5c5e`
- `ntdll!RtlSetAllBits` at `0x1400b5ac5`
- `ntdll!RtlSetAllBits` at `0x1400b5ac5`

## pseudocode

```c

```
