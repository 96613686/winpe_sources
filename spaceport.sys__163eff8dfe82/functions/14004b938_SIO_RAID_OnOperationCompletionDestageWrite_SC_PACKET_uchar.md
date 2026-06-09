# SIO_RAID::OnOperationCompletionDestageWrite(SC_PACKET *,uchar)

- ea: `0x14004b938`
- end: `0x14004ba01`
- name: `?OnOperationCompletionDestageWrite@SIO_RAID@@AEAAJPEAVSC_PACKET@@E@Z`
- size: `201`
- prototype: `__int64 __fastcall(SIO_RAID *__hidden this, struct SC_PACKET *, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400158d0`

## callees

- `0x14002a360`
- `0x14004b938`
- `0x14004c604`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004b9e4`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004b9e4`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004b9a9`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004b9a9`

## pseudocode

```c

```
