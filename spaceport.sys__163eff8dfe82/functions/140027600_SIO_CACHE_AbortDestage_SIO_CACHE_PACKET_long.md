# SIO_CACHE::AbortDestage(SIO_CACHE_PACKET *,long)

- ea: `0x140027600`
- end: `0x1400276c8`
- name: `?AbortDestage@SIO_CACHE@@QEAAXPEAVSIO_CACHE_PACKET@@J@Z`
- size: `200`
- prototype: `void __fastcall(SIO_CACHE *__hidden this, struct SIO_CACHE_PACKET *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14002b360`
- `0x1400443c8`

## callees

- `0x140027600`
- `0x1400276d0`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400276aa`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400276aa`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140027624`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140027624`

## pseudocode

```c

```
