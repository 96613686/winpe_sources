# SIO_RAID::BuildChildPacketsWrite(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x140006c30`
- end: `0x140006ffc`
- name: `?BuildChildPacketsWrite@SIO_RAID@@AEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `972`
- prototype: `__int64 __fastcall(SIO_RAID *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140006b40`
- `0x140009770`

## callees

- `0x140006940`
- `0x140006c30`
- `0x140007010`
- `0x14004a8d0`
- `0x140057b6c`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x140006e79`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140006e79`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140006e20`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140006e20`

## pseudocode

```c

```
