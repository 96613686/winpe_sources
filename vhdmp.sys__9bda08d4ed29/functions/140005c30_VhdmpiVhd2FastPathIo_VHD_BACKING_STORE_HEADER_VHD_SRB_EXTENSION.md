# VhdmpiVhd2FastPathIo(_VHD_BACKING_STORE_HEADER *,_VHD_SRB_EXTENSION *)

- ea: `0x140005c30`
- end: `0x140006004`
- name: `?VhdmpiVhd2FastPathIo@@YAEPEAU_VHD_BACKING_STORE_HEADER@@PEAU_VHD_SRB_EXTENSION@@@Z`
- size: `980`
- prototype: `unsigned __int8 __fastcall(struct _VHD_BACKING_STORE_HEADER *, struct _VHD_SRB_EXTENSION *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140005c30`
- `0x140006010`
- `0x1400072f0`
- `0x14002b4ec`
- `0x14005dbb0`
- `0x14005dc30`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!ExTryQueueWorkItem` at `0x140005e94`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140005e94`
- `ntoskrnl!KeInsertQueue` at `0x140005feb`
- `ntoskrnl!KeInsertQueue` at `0x140005feb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140005dbb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140005dbb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005e3a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005e3a`

## pseudocode

```c

```
