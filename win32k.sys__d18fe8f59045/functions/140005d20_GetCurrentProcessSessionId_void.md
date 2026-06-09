# GetCurrentProcessSessionId(void)

- ea: `0x140005d20`
- end: `0x140005d83`
- name: `?GetCurrentProcessSessionId@@YAKXZ`
- size: `99`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005790`
- `0x1400057b8`
- `0x14001c980`

## callees

- `0x140005d20`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140005d26`
- `ntoskrnl!PsGetCurrentProcess` at `0x140005d51`
- `ntoskrnl!PsGetCurrentProcess` at `0x140005d26`
- `ntoskrnl!PsGetCurrentProcess` at `0x140005d51`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140005d35`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140005d35`
- `ntoskrnl!KeBugCheckEx` at `0x140005d76`
- `ntoskrnl!KeBugCheckEx` at `0x140005d76`

## pseudocode

```c

```
