# VhdmpiCreateErrorLogEntry(_VHD_SRB_EXTENSION *)

- ea: `0x140041338`
- end: `0x1400414dc`
- name: `?VhdmpiCreateErrorLogEntry@@YAXPEAU_VHD_SRB_EXTENSION@@@Z`
- size: `420`
- prototype: `void __fastcall(struct _VHD_SRB_EXTENSION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140010fa0`

## callees

- `0x140041338`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140041383`
- `ntoskrnl!ExAllocatePool2` at `0x140041383`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140041354`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140041354`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400414b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400414b8`

## pseudocode

```c

```
