# SIO_RAID::BuildChildPacketsDestageRead(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x14004a158`
- end: `0x14004a22a`
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
- `0x14004a158`
- `0x14004a230`
- `0x14004c544`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004a20e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004a20e`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004a172`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004a172`

## pseudocode

```c

```
