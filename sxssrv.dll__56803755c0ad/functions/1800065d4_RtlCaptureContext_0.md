# RtlCaptureContext_0

- ea: `0x1800065d4`
- end: `0x1800065da`
- name: `RtlCaptureContext_0`
- size: `6`
- prototype: `void __stdcall(PCONTEXT ContextRecord)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006330`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800065d4`

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
0x1800065d4  jmp     cs:__imp_RtlCaptureContext
```
