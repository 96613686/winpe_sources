# SIO_CACHE::OnPacketCompletionRead(SC_PACKET *)

- ea: `0x140047828`
- end: `0x1400478e8`
- name: `?OnPacketCompletionRead@SIO_CACHE@@IEAAJPEAVSC_PACKET@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, struct SC_PACKET *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140047430`

## callees

- `0x140026a80`
- `0x140045810`
- `0x140045d80`
- `0x140046710`
- `0x140047828`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x1400478b9`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x1400478b9`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140047877`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140047877`

## pseudocode

```c

```
