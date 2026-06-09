# SIO_RAID::OnPacketCompletionWriteLog(SC_PACKET *)

- ea: `0x14004be48`
- end: `0x14004bfdc`
- name: `?OnPacketCompletionWriteLog@SIO_RAID@@AEAAJPEAVSC_PACKET@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(SIO_RAID *__hidden this, struct SC_PACKET *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140011e70`
- `0x140012280`

## callees

- `0x140025710`
- `0x140026410`
- `0x14004be48`
- `0x140057228`
- `0x140057dd8`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004bf01`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004bf01`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14004bf5d`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14004bf5d`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14004bf3e`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14004bf3e`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004beaa`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004beaa`

## pseudocode

```c

```
