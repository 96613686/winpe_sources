# SIO_RAID::OnPacketCompletionWriteLog(SC_PACKET *)

- ea: `0x14004bd88`
- end: `0x14004bf1c`
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
- `0x14004bd88`
- `0x140057128`
- `0x140057cd8`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004be41`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004be41`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14004be9d`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14004be9d`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14004be7e`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14004be7e`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004bdea`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004bdea`

## pseudocode

```c

```
