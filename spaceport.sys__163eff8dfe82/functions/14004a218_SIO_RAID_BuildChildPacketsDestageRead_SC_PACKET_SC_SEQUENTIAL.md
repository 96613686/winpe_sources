# SIO_RAID::BuildChildPacketsDestageRead(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x14004a218`
- end: `0x14004a2ea`
- name: `?BuildChildPacketsDestageRead@SIO_RAID@@AEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(SIO_RAID *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140006980`
- `0x140006b40`
- `0x140009770`

## callees

- `0x140027d70`
- `0x14002a360`
- `0x14004a218`
- `0x14004a2f0`
- `0x14004c604`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004a2ce`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004a2ce`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004a232`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004a232`

## pseudocode

```c

```
