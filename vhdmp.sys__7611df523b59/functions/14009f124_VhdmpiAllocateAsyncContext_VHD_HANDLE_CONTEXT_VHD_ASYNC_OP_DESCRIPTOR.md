# VhdmpiAllocateAsyncContext(_VHD_HANDLE_CONTEXT *,_VHD_ASYNC_OP_DESCRIPTOR *)

- ea: `0x14009f124`
- end: `0x14009f2de`
- name: `?VhdmpiAllocateAsyncContext@@YAPEAU_VHD_ASYNC_OP_CONTEXT@@PEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_ASYNC_OP_DESCRIPTOR@@@Z`
- size: `442`
- prototype: `struct _KEVENT *__fastcall(struct _LIST_ENTRY *, struct _VHD_ASYNC_OP_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14009f6cc`
- `0x1400c8208`

## callees

- `0x140001008`
- `0x140023560`
- `0x14005da00`
- `0x14009f124`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14009f242`
- `ntoskrnl!EtwActivityIdControl` at `0x14009f242`
- `ntoskrnl!ExAllocatePool2` at `0x14009f144`
- `ntoskrnl!ExAllocatePool2` at `0x14009f20d`
- `ntoskrnl!ExAllocatePool2` at `0x14009f144`
- `ntoskrnl!ExAllocatePool2` at `0x14009f20d`
- `ntoskrnl!KeInitializeEvent` at `0x14009f18b`
- `ntoskrnl!KeInitializeEvent` at `0x14009f1a0`
- `ntoskrnl!KeInitializeEvent` at `0x14009f1b5`
- `ntoskrnl!KeInitializeEvent` at `0x14009f18b`
- `ntoskrnl!KeInitializeEvent` at `0x14009f1a0`
- `ntoskrnl!KeInitializeEvent` at `0x14009f1b5`

## pseudocode

```c

```
