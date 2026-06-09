# VMX_IO_OBJECT::ResumeTasks(void)

- ea: `0x140011e80`
- end: `0x140011fc9`
- name: `?ResumeTasks@VMX_IO_OBJECT@@UEAAXXZ`
- size: `329`
- prototype: `void __fastcall(VMX_IO_OBJECT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140011e50`

## callees

- `0x140011e80`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011eab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011eab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011f37`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011f37`

## pseudocode

```c

```
