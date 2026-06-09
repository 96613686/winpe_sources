# BlbimgPrepareForBackupImpl<BLBIMGI_BACKUP_CONTEXT>(ushort const *,uchar,uchar,uchar,uchar,uchar (*)(void *,__int64,__int64),void *,uchar,__int64 *,BLBIMGI_BACKUP_CONTEXT * *,__int64 *,__int64 *,ulong *)

- ea: `0x1400b4540`
- end: `0x1400b5216`
- name: `??$BlbimgPrepareForBackupImpl@UBLBIMGI_BACKUP_CONTEXT@@@@YA?AW4_BLBIMG_RESULT_CODE@@PEBGEEEEP6AEPEAX_J2@Z1EPEA_JPEAPEAUBLBIMGI_BACKUP_CONTEXT@@44PEAK@Z`
- size: `3286`
- prototype: `__int64 __fastcall(unsigned __int16 *, char, char, char, int, int, int, int, unsigned __int64 *, __int64 *, _QWORD *, _QWORD *, DWORD *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, loader_planting`

## callers

- `0x1400bf574`

## callees

- `0x1400063b4`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x14003c434`
- `0x14003c69c`
- `0x14003cb70`
- `0x1400b36a8`
- `0x1400b4540`
- `0x1400b7be8`
- `0x1400b8440`
- `0x1400b8514`
- `0x1400b8c14`
- `0x1400b9ed8`
- `0x1400ba2a8`
- `0x1400ba704`
- `0x1400baf74`
- `0x1400bb1f0`
- `0x1400be8b0`
- `0x1400c3fec`
- `0x1400c45c0`
- `0x140134d20`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1400b4bb9`
- `KERNEL32!LocalAlloc` at `0x1400b4d8b`
- `KERNEL32!LocalAlloc` at `0x1400b4f02`
- `KERNEL32!LocalAlloc` at `0x1400b4fb7`
- `KERNEL32!LocalAlloc` at `0x1400b4bb9`
- `KERNEL32!LocalAlloc` at `0x1400b4d8b`
- `KERNEL32!LocalAlloc` at `0x1400b4f02`
- `KERNEL32!LocalAlloc` at `0x1400b4fb7`
- `KERNEL32!LocalFree` at `0x1400b4b3d`
- `KERNEL32!LocalFree` at `0x1400b4bf2`
- `KERNEL32!LocalFree` at `0x1400b4c93`
- `KERNEL32!LocalFree` at `0x1400b4da5`
- `KERNEL32!LocalFree` at `0x1400b4eb5`
- `KERNEL32!LocalFree` at `0x1400b4f20`
- `KERNEL32!LocalFree` at `0x1400b5055`
- `KERNEL32!LocalFree` at `0x1400b505f`
- `KERNEL32!LocalFree` at `0x1400b5068`
- `KERNEL32!LocalFree` at `0x1400b4b3d`
- `KERNEL32!LocalFree` at `0x1400b4bf2`
- `KERNEL32!LocalFree` at `0x1400b4c93`
- `KERNEL32!LocalFree` at `0x1400b4da5`
- `KERNEL32!LocalFree` at `0x1400b4eb5`
- `KERNEL32!LocalFree` at `0x1400b4f20`
- `KERNEL32!LocalFree` at `0x1400b5055`
- `KERNEL32!LocalFree` at `0x1400b505f`
- `KERNEL32!LocalFree` at `0x1400b5068`
- `KERNEL32!CreateFileW` at `0x1400b47ce`
- `KERNEL32!CreateFileW` at `0x1400b47ce`
- `KERNEL32!CloseHandle` at `0x1400b48c1`
- `KERNEL32!CloseHandle` at `0x1400b48ca`
- `KERNEL32!CloseHandle` at `0x1400b4c8a`
- `KERNEL32!CloseHandle` at `0x1400b48c1`
- `KERNEL32!CloseHandle` at `0x1400b48ca`
- `KERNEL32!CloseHandle` at `0x1400b4c8a`
- `KERNEL32!GetLastError` at `0x1400b47dd`
- `KERNEL32!GetLastError` at `0x1400b4b32`
- `KERNEL32!GetLastError` at `0x1400b4b6c`
- `KERNEL32!GetLastError` at `0x1400b4be7`
- `KERNEL32!GetLastError` at `0x1400b4c7e`
- `KERNEL32!GetLastError` at `0x1400b4d9a`
- `KERNEL32!GetLastError` at `0x1400b4f14`
- `KERNEL32!GetLastError` at `0x1400b47dd`
- `KERNEL32!GetLastError` at `0x1400b4b32`
- `KERNEL32!GetLastError` at `0x1400b4b6c`
- `KERNEL32!GetLastError` at `0x1400b4be7`
- `KERNEL32!GetLastError` at `0x1400b4c7e`
- `KERNEL32!GetLastError` at `0x1400b4d9a`
- `KERNEL32!GetLastError` at `0x1400b4f14`
- `KERNEL32!DeviceIoControl` at `0x1400b4b1a`
- `KERNEL32!DeviceIoControl` at `0x1400b4c74`
- `KERNEL32!DeviceIoControl` at `0x1400b4b1a`
- `KERNEL32!DeviceIoControl` at `0x1400b4c74`
- `ntdll!RtlNumberOfSetBits` at `0x1400b5090`
- `ntdll!RtlNumberOfSetBits` at `0x1400b512e`
- `ntdll!RtlNumberOfSetBits` at `0x1400b5090`
- `ntdll!RtlNumberOfSetBits` at `0x1400b512e`
- `ntdll!RtlInitializeBitMap` at `0x1400b4dc1`
- `ntdll!RtlInitializeBitMap` at `0x1400b4fed`
- `ntdll!RtlInitializeBitMap` at `0x1400b4dc1`
- `ntdll!RtlInitializeBitMap` at `0x1400b4fed`
- `ntdll!RtlSetAllBits` at `0x1400b4dcc`
- `ntdll!RtlSetAllBits` at `0x1400b4dcc`

## pseudocode

```c

```
