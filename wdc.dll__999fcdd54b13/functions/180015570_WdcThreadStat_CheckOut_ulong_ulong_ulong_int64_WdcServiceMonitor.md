# WdcThreadStat::CheckOut(ulong,ulong,ulong,__int64,WdcServiceMonitor *)

- ea: `0x180015570`
- end: `0x1800156e8`
- name: `?CheckOut@WdcThreadStat@@QEAAJKKK_JPEAVWdcServiceMonitor@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(WdcThreadStat *this, unsigned int, __int64, int, __int64, struct WdcServiceMonitor *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001efac`

## callees

- `0x18000b854`
- `0x1800137d0`
- `0x180015570`
- `0x180086010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001564a`
- `KERNEL32!LeaveCriticalSection` at `0x18001564a`
- `KERNEL32!EnterCriticalSection` at `0x18001558f`
- `KERNEL32!EnterCriticalSection` at `0x18001558f`

## string_xrefs

- `0x1800156d0`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x1800156c9`: `WdcThreadStat::CheckOut`

## pseudocode

```c

```
