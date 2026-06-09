# NvmeControllerCreatePendingIoQueueContext

- ea: `0x14010e360`
- end: `0x14010e64e`
- name: `NvmeControllerCreatePendingIoQueueContext`
- size: `750`
- prototype: `__int64 __fastcall(PVOID DeferredContext)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140104a30`
- `0x14011158c`

## callees

- `0x1400290b0`
- `0x1400b64dc`
- `0x14010e360`
- `0x14010e864`

## import_xrefs

- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x14010e554`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x14010e611`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x14010e554`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x14010e611`
- `ntoskrnl!KeInitializeTimer` at `0x14010e4b1`
- `ntoskrnl!KeInitializeTimer` at `0x14010e4b1`
- `ntoskrnl!InitializeSListHead` at `0x14010e572`
- `ntoskrnl!InitializeSListHead` at `0x14010e572`
- `ntoskrnl!KeInitializeDpc` at `0x14010e511`
- `ntoskrnl!KeInitializeDpc` at `0x14010e5ce`
- `ntoskrnl!KeInitializeDpc` at `0x14010e511`
- `ntoskrnl!KeInitializeDpc` at `0x14010e5ce`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14010e3ea`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14010e3ea`
- `ntoskrnl!KeSetImportanceDpc` at `0x14010e531`
- `ntoskrnl!KeSetImportanceDpc` at `0x14010e5ee`
- `ntoskrnl!KeSetImportanceDpc` at `0x14010e531`
- `ntoskrnl!KeSetImportanceDpc` at `0x14010e5ee`

## pseudocode

```c

```
