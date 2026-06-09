# SP_DRIVE::UpdateLost(void)

- ea: `0x14003cd08`
- end: `0x14003cfd8`
- name: `?UpdateLost@SP_DRIVE@@AEAAJXZ`
- size: `720`
- prototype: `__int64 __fastcall(SP_DRIVE *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140022500`
- `0x14008cf60`

## callees

- `0x1400268c0`
- `0x14003cd08`
- `0x140068600`
- `0x1400b68c0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003cf09`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003cf09`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ceec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cf43`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cfa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cfba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ceec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cf43`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cfa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cfba`
- `ntoskrnl!RtlInitializeBitMap` at `0x14003cf2e`
- `ntoskrnl!RtlInitializeBitMap` at `0x14003cf74`
- `ntoskrnl!RtlInitializeBitMap` at `0x14003cf2e`
- `ntoskrnl!RtlInitializeBitMap` at `0x14003cf74`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003cf85`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003cf85`

## pseudocode

```c

```
