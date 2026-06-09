# WdcDiskMonitor::EventFileDelete(_EVENT_RECORD *)

- ea: `0x1800056ec`
- end: `0x18000595c`
- name: `?EventFileDelete@WdcDiskMonitor@@AEAAJPEAU_EVENT_RECORD@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(WdcDiskMonitor *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000a4d0`

## callees

- `0x1800056ec`
- `0x1800065f0`
- `0x18000b854`
- `0x180017d10`
- `0x180086010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000585f`
- `KERNEL32!LeaveCriticalSection` at `0x18000585f`
- `KERNEL32!EnterCriticalSection` at `0x18000571d`
- `KERNEL32!EnterCriticalSection` at `0x18000571d`

## string_xrefs

- `0x1800058f4`: `WdcDiskMonitor::DeleteFileObject`
- `0x180005927`: `WdcDiskMonitor::EventFileDelete`

## pseudocode

```c

```
