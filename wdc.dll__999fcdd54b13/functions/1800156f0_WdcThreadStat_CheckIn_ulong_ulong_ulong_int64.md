# WdcThreadStat::CheckIn(ulong,ulong,ulong,__int64)

- ea: `0x1800156f0`
- end: `0x1800158ac`
- name: `?CheckIn@WdcThreadStat@@QEAAJKKK_J@Z`
- size: `444`
- prototype: `__int64 __fastcall(WdcThreadStat *this, unsigned int, int, int, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001c718`
- `0x18001efac`

## callees

- `0x1800065f0`
- `0x180008ab0`
- `0x18000b854`
- `0x1800156f0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800157c4`
- `KERNEL32!LeaveCriticalSection` at `0x1800157c4`
- `KERNEL32!EnterCriticalSection` at `0x18001571b`
- `KERNEL32!EnterCriticalSection` at `0x18001571b`

## string_xrefs

- `0x18001589b`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x180015894`: `WdcThreadStat::CheckIn`

## pseudocode

```c

```
