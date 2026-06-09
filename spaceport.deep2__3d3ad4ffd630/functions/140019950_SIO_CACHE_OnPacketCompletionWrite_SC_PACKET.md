# SIO_CACHE::OnPacketCompletionWrite(SC_PACKET *)

- ea: `0x140019950`
- end: `0x140019a70`
- name: `?OnPacketCompletionWrite@SIO_CACHE@@IEAAJPEAVSC_PACKET@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, struct SC_PACKET *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140047430`

## callees

- `0x140019950`
- `0x140019a80`
- `0x14001a250`
- `0x140026a80`
- `0x14003f804`
- `0x140045810`
- `0x140047fbc`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140019a13`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140019a13`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400199a2`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400199a2`

## pseudocode

```c

```
