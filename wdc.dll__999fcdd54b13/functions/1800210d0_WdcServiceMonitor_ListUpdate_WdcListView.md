# WdcServiceMonitor::ListUpdate(WdcListView *)

- ea: `0x1800210d0`
- end: `0x1800211e4`
- name: `?ListUpdate@WdcServiceMonitor@@UEAAJPEAVWdcListView@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(WdcServiceMonitor *__hidden this, struct WdcListView *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x1800096f0`
- `0x18000b854`
- `0x1800210d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800211cc`
- `KERNEL32!LeaveCriticalSection` at `0x1800211cc`
- `KERNEL32!TryEnterCriticalSection` at `0x1800210f3`
- `KERNEL32!TryEnterCriticalSection` at `0x1800210f3`

## string_xrefs

- `0x18002112c`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x180021125`: `WdcServiceMonitor::ListUpdate`

## pseudocode

```c

```
