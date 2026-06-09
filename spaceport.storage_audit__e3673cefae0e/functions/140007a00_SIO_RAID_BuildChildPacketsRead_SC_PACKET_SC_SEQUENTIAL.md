# SIO_RAID::BuildChildPacketsRead(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x140007a00`
- end: `0x140007bd8`
- name: `?BuildChildPacketsRead@SIO_RAID@@AEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `472`
- prototype: `__int64 __fastcall(SIO_RAID *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140006980`
- `0x140006b40`
- `0x140009770`

## callees

- `0x140006280`
- `0x140006940`
- `0x140007a00`
- `0x140007be0`
- `0x14000e530`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x140007ba6`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140007ba6`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140007b46`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140007b46`

## pseudocode

```c

```
