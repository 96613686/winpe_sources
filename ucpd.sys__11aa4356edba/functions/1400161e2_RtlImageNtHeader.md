# RtlImageNtHeader

- ea: `0x1400161e2`
- end: `0x1400161e9`
- name: `RtlImageNtHeader`
- size: `7`
- prototype: `PIMAGE_NT_HEADERS __stdcall(PVOID BaseAddress)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x140005dbc`
- `0x140005e20`

## import_xrefs

- `ntoskrnl!RtlImageNtHeader` at `0x1400161e2`

## pseudocode

```c
// attributes: thunk
PIMAGE_NT_HEADERS __stdcall RtlImageNtHeader(PVOID BaseAddress)
{
  return __imp_RtlImageNtHeader(BaseAddress);
}

```

## disassembly

```asm
0x1400161e2  jmp     cs:__imp_RtlImageNtHeader
```
