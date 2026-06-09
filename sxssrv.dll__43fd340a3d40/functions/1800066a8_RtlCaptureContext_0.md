# RtlCaptureContext_0

- ea: `0x1800066a8`
- end: `0x1800066ae`
- name: `RtlCaptureContext_0`
- size: `6`
- prototype: `void __stdcall(PCONTEXT ContextRecord)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006400`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800066a8`

## pseudocode

```c
// attributes: thunk
void __stdcall RtlCaptureContext_0(PCONTEXT ContextRecord)
{
  RtlCaptureContext(ContextRecord);
}

```

## disassembly

```asm
0x1800066a8  jmp     cs:__imp_RtlCaptureContext
```
