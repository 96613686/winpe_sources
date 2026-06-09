# WorkThreadManager::s_QueuePoolTask(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,Windows::Internal::IComPoolTask *)

- ea: `0x18002a4c4`
- end: `0x18002a7d8`
- name: `?s_QueuePoolTask@WorkThreadManager@@CAJW4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAUIComPoolTask@34@@Z`
- size: `788`
- prototype: `static int __high(enum Windows::Internal::TaskApartment, enum Windows::Internal::TaskOptions, unsigned int, struct Windows::Internal::IComPoolTask *)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029330`
- `0x180074c64`

## callees

- `0x180028e70`
- `0x18002a4c4`
- `0x18002ab04`
- `0x18002ae44`
- `0x18002b6bc`
- `0x18002bee4`
- `0x18002bfbc`
- `0x18002daf8`
- `0x18002dc10`
- `0x1800362d4`
- `0x180059aac`
- `0x180073ee4`
- `0x180074e7c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a50d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a761`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a50d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a761`
- `ole32!CoWaitForMultipleHandles` at `0x18002a6fe`
- `ole32!CoWaitForMultipleHandles` at `0x18002a6fe`

## string_xrefs

- `0x18002a54e`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18002a5e0`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18002a68c`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18002a711`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c

```
