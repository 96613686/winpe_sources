# VMX_MIRROR_SYNCHRONIZATION_TASK::Resume(void)

- ea: `0x1400118e0`
- end: `0x140011a04`
- name: `?Resume@VMX_MIRROR_SYNCHRONIZATION_TASK@@UEAAXXZ`
- size: `292`
- prototype: `void __fastcall(VMX_MIRROR_SYNCHRONIZATION_TASK *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1400118e0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011907`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011907`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011948`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011948`

## pseudocode

```c

```
