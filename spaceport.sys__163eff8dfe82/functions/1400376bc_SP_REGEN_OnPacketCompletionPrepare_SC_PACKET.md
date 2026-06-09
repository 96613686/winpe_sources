# SP_REGEN::OnPacketCompletionPrepare(SC_PACKET *)

- ea: `0x1400376bc`
- end: `0x1400378fa`
- name: `?OnPacketCompletionPrepare@SP_REGEN@@QEAAJPEAVSC_PACKET@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(SP_REGEN *__hidden this, struct SC_PACKET *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001fdb0`

## callees

- `0x14000200c`
- `0x14000315c`
- `0x140008a00`
- `0x14000aca0`
- `0x14000b290`
- `0x140030ce4`
- `0x1400376bc`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003779e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14003779e`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140037733`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140037733`
- `ntoskrnl!KeSetEvent` at `0x1400378dd`
- `ntoskrnl!KeSetEvent` at `0x1400378dd`

## pseudocode

```c

```
