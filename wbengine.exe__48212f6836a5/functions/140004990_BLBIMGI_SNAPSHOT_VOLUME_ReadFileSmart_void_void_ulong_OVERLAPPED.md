# BLBIMGI_SNAPSHOT_VOLUME::ReadFileSmart(void *,void *,ulong,_OVERLAPPED *)

- ea: `0x140004990`
- end: `0x140004f18`
- name: `?ReadFileSmart@BLBIMGI_SNAPSHOT_VOLUME@@AEAAXPEAX0KPEAU_OVERLAPPED@@@Z`
- size: `1416`
- prototype: `void(BLBIMGI_SNAPSHOT_VOLUME *__hidden this, void *, void *, unsigned int, struct _OVERLAPPED *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1400042e0`
- `0x1400d0994`

## callees

- `0x140004990`
- `0x140005070`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x1400c3d08`
- `0x1400c472c`
- `0x1400d0c50`
- `0x1400d0d70`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x140004b5a`
- `KERNEL32!GetOverlappedResult` at `0x140004e35`
- `KERNEL32!GetOverlappedResult` at `0x140004b5a`
- `KERNEL32!GetOverlappedResult` at `0x140004e35`
- `KERNEL32!ReadFile` at `0x140004d28`
- `KERNEL32!ReadFile` at `0x140004d28`
- `KERNEL32!SetEvent` at `0x140004def`
- `KERNEL32!SetEvent` at `0x140004ef7`
- `KERNEL32!SetEvent` at `0x140004def`
- `KERNEL32!SetEvent` at `0x140004ef7`
- `KERNEL32!GetLastError` at `0x140004c3c`
- `KERNEL32!GetLastError` at `0x140004d36`
- `KERNEL32!GetLastError` at `0x140004e57`
- `KERNEL32!GetLastError` at `0x140004c3c`
- `KERNEL32!GetLastError` at `0x140004d36`
- `KERNEL32!GetLastError` at `0x140004e57`

## string_xrefs

- `0x140004e07`: `splitRead`

## pseudocode

```c

```
