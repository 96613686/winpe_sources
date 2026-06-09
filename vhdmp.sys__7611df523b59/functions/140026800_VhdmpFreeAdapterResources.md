# VhdmpFreeAdapterResources

- ea: `0x140026800`
- end: `0x1400269c3`
- name: `VhdmpFreeAdapterResources`
- size: `451`
- prototype: `__int64 __fastcall(struct _VHD_ADAPTER_EXTENSION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400b8410`

## callees

- `0x140026800`
- `0x1400269cc`
- `0x14002ed20`
- `0x1400b7628`
- `0x1400b7658`
- `0x1400b83e4`
- `0x1400d2e58`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140026915`
- `ntoskrnl!KeCancelTimer` at `0x140026915`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002692f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002692f`
- `ntoskrnl!PcwUnregister` at `0x140026957`
- `ntoskrnl!PcwUnregister` at `0x140026957`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14002693b`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14002693b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026851`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026851`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400268bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400268bc`

## pseudocode

```c

```
