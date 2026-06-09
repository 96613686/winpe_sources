# SIO_CACHE::SetLine(SIO_CACHE_LINE *,unsigned __int64,uchar)

- ea: `0x140025800`
- end: `0x140025886`
- name: `?SetLine@SIO_CACHE@@IEAAJPEAVSIO_CACHE_LINE@@_KE@Z`
- size: `134`
- prototype: `int(SIO_CACHE *__hidden this, struct SIO_CACHE_LINE *, unsigned __int64, unsigned __int8)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140019bb0`
- `0x140029d2c`
- `0x140044138`

## callees

- `0x14000ea30`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002586a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002586a`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140025821`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140025821`

## pseudocode

```c

```
