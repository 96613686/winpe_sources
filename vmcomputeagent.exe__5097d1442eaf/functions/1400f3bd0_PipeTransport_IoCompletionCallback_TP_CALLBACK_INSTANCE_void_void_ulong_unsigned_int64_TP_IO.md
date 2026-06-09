# PipeTransport::IoCompletionCallback(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x1400f3bd0`
- end: `0x1400f3e92`
- name: `?IoCompletionCallback@PipeTransport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `706`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x140009f8c`
- `0x14002e120`
- `0x14005f06c`
- `0x14005f364`
- `0x140060364`
- `0x14006265c`
- `0x1400f2978`
- `0x1400f3bd0`
- `0x1400f3f88`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f3d28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f3dc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f3d28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f3dc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f3cb8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f3d52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f3cb8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f3d52`

## string_xrefs

- `0x1400f3c2d`: `PipeTransport_IoComplete`
- `0x1400f3e7f`: `onecore\vm\compute\common\transport\pipetransport.cpp`

## pseudocode

```c

```
