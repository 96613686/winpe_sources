# RtlVirtualUnwind_0

- ea: `0x140001264`
- end: `0x14000126a`
- name: `RtlVirtualUnwind_0`
- size: `6`
- prototype: `PEXCEPTION_ROUTINE __stdcall(DWORD HandlerType, DWORD64 ImageBase, DWORD64 ControlPc, PRUNTIME_FUNCTION FunctionEntry, struct _CONTEXT *ContextRecord, PVOID *HandlerData, PDWORD64 EstablisherFrame, PKNONVOLATILE_CONTEXT_POINTERS ContextPointers)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001010`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x140001264`

## pseudocode

```c
// attributes: thunk
PEXCEPTION_ROUTINE __stdcall RtlVirtualUnwind_0(DWORD HandlerType, DWORD64 ImageBase, DWORD64 ControlPc, PRUNTIME_FUNCTION FunctionEntry, struct _CONTEXT *ContextRecord, PVOID *HandlerData, PDWORD64 EstablisherFrame, PKNONVOLATILE_CONTEXT_POINTERS ContextPointers)
{
  return RtlVirtualUnwind(
           HandlerType,
           ImageBase,
           ControlPc,
           FunctionEntry,
           ContextRecord,
           HandlerData,
           EstablisherFrame,
           ContextPointers);
}

```

## disassembly

```asm
0x140001264  jmp     cs:__imp_RtlVirtualUnwind
```
