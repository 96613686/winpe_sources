# SIO_CACHE::GetPendingUnmapRanges(SDB_RANGES * *)

- ea: `0x1400469b8`
- end: `0x140046a8c`
- name: `?GetPendingUnmapRanges@SIO_CACHE@@QEAAJPEAPEAVSDB_RANGES@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, struct SDB_RANGES **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002b608`

## callees

- `0x1400268c0`
- `0x140026db0`
- `0x1400469b8`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x140046a04`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140046a04`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400469ed`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400469ed`

## pseudocode

```c

```
