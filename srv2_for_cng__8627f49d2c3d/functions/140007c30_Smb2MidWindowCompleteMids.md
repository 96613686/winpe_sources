# Smb2MidWindowCompleteMids

- ea: `0x140007c30`
- end: `0x140007dfd`
- name: `Smb2MidWindowCompleteMids`
- size: `461`
- prototype: `__int64 __fastcall(PEX_SPIN_LOCK SpinLock)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007400`
- `0x140007900`

## callees

- `0x140007c30`
- `0x140017ef0`

## import_xrefs

- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140007c64`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140007c64`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140007d1c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140007dc7`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140007d1c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140007dc7`

## pseudocode

```c

```
