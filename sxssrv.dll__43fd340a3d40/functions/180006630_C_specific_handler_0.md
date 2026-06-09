# __C_specific_handler_0

- ea: `0x180006630`
- end: `0x180006636`
- name: `__C_specific_handler_0`
- size: `6`
- prototype: `EXCEPTION_DISPOSITION __cdecl(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x180006c48`

## import_xrefs

- `ntdll!__C_specific_handler` at `0x180006630`

## pseudocode

```c
// attributes: thunk
EXCEPTION_DISPOSITION __cdecl _C_specific_handler_0(
        struct _EXCEPTION_RECORD *ExceptionRecord,
        void *EstablisherFrame,
        struct _CONTEXT *ContextRecord,
        struct _DISPATCHER_CONTEXT *DispatcherContext)
{
  return __C_specific_handler(ExceptionRecord, EstablisherFrame, ContextRecord, DispatcherContext);
}

```

## disassembly

```asm
0x180006630  jmp     cs:__imp___C_specific_handler
```
