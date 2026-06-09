# BlbQueryPersistentVolumeState(ushort const *,_FILE_FS_PERSISTENT_VOLUME_INFORMATION *)

- ea: `0x140122e0c`
- end: `0x140123097`
- name: `?BlbQueryPersistentVolumeState@@YAJPEBGPEAU_FILE_FS_PERSISTENT_VOLUME_INFORMATION@@@Z`
- size: `651`
- prototype: `int(const unsigned __int16 *, struct _FILE_FS_PERSISTENT_VOLUME_INFORMATION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14012391c`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb4c`
- `0x14001358c`
- `0x140014260`
- `0x140122e0c`
- `0x140134d20`

## import_xrefs

- `KERNEL32!QueryDosDeviceW` at `0x140122ef4`
- `KERNEL32!QueryDosDeviceW` at `0x140122ef4`
- `KERNEL32!CreateFileW` at `0x140122f69`
- `KERNEL32!CreateFileW` at `0x140122f69`
- `KERNEL32!CloseHandle` at `0x14012306d`
- `KERNEL32!CloseHandle` at `0x14012306d`
- `KERNEL32!GetLastError` at `0x140122f02`
- `KERNEL32!GetLastError` at `0x140122f78`
- `KERNEL32!GetLastError` at `0x14012301c`
- `KERNEL32!GetLastError` at `0x140122f02`
- `KERNEL32!GetLastError` at `0x140122f78`
- `KERNEL32!GetLastError` at `0x14012301c`
- `KERNEL32!DeviceIoControl` at `0x140123012`
- `KERNEL32!DeviceIoControl` at `0x140123012`

## pseudocode

```c

```
