# SIO_CACHE::GetPendingMapStatus(unsigned __int64,unsigned __int64,SDB_RANGES *,long)

- ea: `0x1400468b8`
- end: `0x1400469b1`
- name: `?GetPendingMapStatus@SIO_CACHE@@QEAAJ_K0PEAVSDB_RANGES@@J@Z`
- size: `249`
- prototype: `int(SIO_CACHE *__hidden this, unsigned __int64, unsigned __int64, struct SDB_RANGES *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003bd80`

## callees

- `0x14000e530`
- `0x1400468b8`
- `0x140061cb4`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x14004695f`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14004695f`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140046922`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140046922`

## pseudocode

```c

```
