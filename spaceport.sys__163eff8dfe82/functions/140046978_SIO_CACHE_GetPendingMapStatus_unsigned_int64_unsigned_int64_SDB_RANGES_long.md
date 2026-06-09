# SIO_CACHE::GetPendingMapStatus(unsigned __int64,unsigned __int64,SDB_RANGES *,long)

- ea: `0x140046978`
- end: `0x140046a71`
- name: `?GetPendingMapStatus@SIO_CACHE@@QEAAJ_K0PEAVSDB_RANGES@@J@Z`
- size: `249`
- prototype: `int(SIO_CACHE *__hidden this, unsigned __int64, unsigned __int64, struct SDB_RANGES *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003be40`

## callees

- `0x14000e530`
- `0x140046978`
- `0x140061e04`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x140046a1f`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140046a1f`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400469e2`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400469e2`

## pseudocode

```c

```
