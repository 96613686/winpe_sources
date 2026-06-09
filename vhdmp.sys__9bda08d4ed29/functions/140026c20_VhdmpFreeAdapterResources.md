# VhdmpFreeAdapterResources

- ea: `0x140026c20`
- end: `0x140026de3`
- name: `VhdmpFreeAdapterResources`
- size: `451`
- prototype: `__int64 __fastcall(struct _VHD_ADAPTER_EXTENSION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400b8400`

## callees

- `0x140026c20`
- `0x140026dec`
- `0x14002f1e0`
- `0x1400b7610`
- `0x1400b7640`
- `0x1400b83cc`
- `0x1400d2de8`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140026d35`
- `ntoskrnl!KeCancelTimer` at `0x140026d35`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140026d4f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140026d4f`
- `ntoskrnl!PcwUnregister` at `0x140026d77`
- `ntoskrnl!PcwUnregister` at `0x140026d77`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140026d5b`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140026d5b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026c71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026c71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026cdc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026cdc`

## pseudocode

```c

```
