# VhdmpiVhd2ProcessSingleSrbRange(_VHD2_BACKING_STORE *,_VHD2_SRB_RANGE *,VHD_PARSE_THREAD_CONTEXT *)

- ea: `0x1400068d0`
- end: `0x140007219`
- name: `?VhdmpiVhd2ProcessSingleSrbRange@@YAXPEAU_VHD2_BACKING_STORE@@PEAU_VHD2_SRB_RANGE@@PEAUVHD_PARSE_THREAD_CONTEXT@@@Z`
- size: `2377`
- prototype: `void __fastcall(struct _VHD2_BACKING_STORE *, struct _VHD2_SRB_RANGE *, struct VHD_PARSE_THREAD_CONTEXT *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x140006860`

## callees

- `0x1400047b8`
- `0x140005000`
- `0x140006010`
- `0x140006068`
- `0x1400068d0`
- `0x1400072f0`
- `0x140007860`
- `0x1400078f0`
- `0x14001660c`
- `0x14002b4ec`
- `0x14003f964`
- `0x14005dc30`
- `0x1400de0d4`
- `0x1400e606c`

## import_xrefs

- `ntoskrnl!ExTryQueueWorkItem` at `0x140006c97`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140006f66`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140006c97`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140006f66`
- `ntoskrnl!KeInsertQueue` at `0x1400071ba`
- `ntoskrnl!KeInsertQueue` at `0x140007208`
- `ntoskrnl!KeInsertQueue` at `0x1400071ba`
- `ntoskrnl!KeInsertQueue` at `0x140007208`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006b2c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006bce`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006da5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006e94`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006b2c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006bce`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006da5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006e94`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006b87`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006c45`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006f18`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006b87`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006c45`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006f18`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140006e18`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140006e18`

## pseudocode

```c

```
