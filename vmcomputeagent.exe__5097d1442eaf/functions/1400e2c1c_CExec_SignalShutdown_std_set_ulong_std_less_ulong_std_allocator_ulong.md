# CExec::SignalShutdown(std::set<ulong,std::less<ulong>,std::allocator<ulong>> &)

- ea: `0x1400e2c1c`
- end: `0x1400e2dd2`
- name: `?SignalShutdown@CExec@@YA_NAEAV?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@@Z`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14008cc20`

## callees

- `0x140005360`
- `0x140006098`
- `0x1400e217c`
- `0x1400e2c1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400e2da6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400e2da6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400e2c4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400e2c4b`
- `ntdll!CsrClientCallServer` at `0x1400e2d0e`
- `ntdll!CsrClientCallServer` at `0x1400e2d0e`

## string_xrefs

- `0x1400e2d1b`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c

```
