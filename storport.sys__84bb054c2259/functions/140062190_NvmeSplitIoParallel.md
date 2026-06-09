# NvmeSplitIoParallel

- ea: `0x140062190`
- end: `0x140062b20`
- name: `NvmeSplitIoParallel`
- size: `2448`
- prototype: `__int64 __usercall@<rax>(ULONG_PTR BugCheckParameter3@<rcx>, ULONG_PTR BugCheckParameter2@<rdx>, __int64, int, int, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x140051870`
- `0x1400604a0`
- `0x1400648b0`
- `0x14012f8c0`
- `0x140131650`
- `0x140133400`

## callees

- `0x140043ca0`
- `0x140060e90`
- `0x140062190`
- `0x14012e610`
- `0x14012f040`
- `0x14012f180`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006234b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006234b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140062a2e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140062a69`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140062aae`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140062a2e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140062a69`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140062aae`
- `ntoskrnl!KeLowerIrql` at `0x1400627e0`
- `ntoskrnl!KeLowerIrql` at `0x1400627e0`
- `ntoskrnl!KfRaiseIrql` at `0x1400626df`
- `ntoskrnl!KfRaiseIrql` at `0x1400626df`
- `ntoskrnl!KeBugCheckEx` at `0x1400622f9`
- `ntoskrnl!KeBugCheckEx` at `0x1400622f9`

## pseudocode

```c

```
