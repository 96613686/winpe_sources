# WdcDiskMonitor::EventFileCreate(_EVENT_RECORD *)

- ea: `0x1800081e0`
- end: `0x1800085e2`
- name: `?EventFileCreate@WdcDiskMonitor@@AEAAJPEAU_EVENT_RECORD@@@Z`
- size: `1026`
- prototype: `__int64 __fastcall(WdcDiskMonitor *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a4d0`

## callees

- `0x180005964`
- `0x1800081e0`
- `0x1800085f0`
- `0x18000b854`
- `0x18003b0ac`
- `0x180069b40`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000837e`
- `KERNEL32!GetProcessHeap` at `0x18000837e`
- `KERNEL32!HeapAlloc` at `0x18000838f`
- `KERNEL32!HeapAlloc` at `0x18000838f`
- `KERNEL32!LeaveCriticalSection` at `0x1800084d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800084d6`
- `KERNEL32!EnterCriticalSection` at `0x180008308`
- `KERNEL32!EnterCriticalSection` at `0x180008308`

## string_xrefs

- `0x18000850f`: `WdcDiskMonitor::EventFileCreate`
- `0x180008537`: `WdcDiskMonitor::CreateEntry`

## pseudocode

```c

```
