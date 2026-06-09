# VMX_IO_OBJECT::PauseTasks(void)

- ea: `0x14000f5d0`
- end: `0x14000f69f`
- name: `?PauseTasks@VMX_IO_OBJECT@@UEAAXXZ`
- size: `207`
- prototype: `void __fastcall(VMX_IO_OBJECT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000f5a0`

## callees

- `0x14000f5d0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f5e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f5e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f61a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f61a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f646`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f646`
- `ntoskrnl!KeClearEvent` at `0x14000f5fc`
- `ntoskrnl!KeClearEvent` at `0x14000f5fc`

## pseudocode

```c

```
