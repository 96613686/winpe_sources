# SP_POOL::LaunchTasks(void)

- ea: `0x140028bb0`
- end: `0x140028cc9`
- name: `?LaunchTasks@SP_POOL@@QEAAXXZ`
- size: `281`
- prototype: `void __fastcall(SP_POOL *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140028b08`
- `0x14002de54`
- `0x14003258c`

## callees

- `0x140028bb0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140028c21`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140028c21`
- `ntoskrnl!ExQueueWorkItem` at `0x140028c9c`
- `ntoskrnl!ExQueueWorkItem` at `0x140028c9c`
- `ntoskrnl!KeClearEvent` at `0x140028c7f`
- `ntoskrnl!KeClearEvent` at `0x140028c7f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140028c40`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140028c40`

## pseudocode

```c

```
