# BLBIMGI_BACKUP_FILE::MoveCurrentBitToNextReadableBlock(uchar *,_OVERLAPPED *)

- ea: `0x1400c9adc`
- end: `0x1400ca342`
- name: `?MoveCurrentBitToNextReadableBlock@BLBIMGI_BACKUP_FILE@@AEAAHPEAEPEAU_OVERLAPPED@@@Z`
- size: `2150`
- prototype: `__int64 __fastcall(BLBIMGI_BACKUP_FILE *__hidden this, unsigned __int8 *, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1400cac1c`

## callees

- `0x140005070`
- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14003c434`
- `0x14003c69c`
- `0x1400c3d08`
- `0x1400c62e0`
- `0x1400c9adc`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x1400c9bce`
- `KERNEL32!GetOverlappedResult` at `0x1400ca170`
- `KERNEL32!GetOverlappedResult` at `0x1400c9bce`
- `KERNEL32!GetOverlappedResult` at `0x1400ca170`
- `KERNEL32!SetEvent` at `0x1400c9c38`
- `KERNEL32!SetEvent` at `0x1400c9c38`
- `KERNEL32!GetLastError` at `0x1400c9bf0`
- `KERNEL32!GetLastError` at `0x1400ca17e`
- `KERNEL32!GetLastError` at `0x1400c9bf0`
- `KERNEL32!GetLastError` at `0x1400ca17e`
- `ntdll!RtlInitializeBitMap` at `0x1400c9b1b`
- `ntdll!RtlInitializeBitMap` at `0x1400c9b1b`
- `ntdll!RtlAreBitsClear` at `0x1400c9e6f`
- `ntdll!RtlAreBitsClear` at `0x1400c9e93`
- `ntdll!RtlAreBitsClear` at `0x1400ca09b`
- `ntdll!RtlAreBitsClear` at `0x1400c9e6f`
- `ntdll!RtlAreBitsClear` at `0x1400c9e93`
- `ntdll!RtlAreBitsClear` at `0x1400ca09b`
- `ntdll!RtlSetAllBits` at `0x1400ca1c4`
- `ntdll!RtlSetAllBits` at `0x1400ca1c4`

## pseudocode

```c

```
