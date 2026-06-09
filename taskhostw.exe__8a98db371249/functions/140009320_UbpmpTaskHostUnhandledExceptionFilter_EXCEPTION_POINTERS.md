# UbpmpTaskHostUnhandledExceptionFilter(_EXCEPTION_POINTERS *)

- ea: `0x140009320`
- end: `0x140009327`
- name: `?UbpmpTaskHostUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `7`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## import_xrefs

- `ntdll!RtlUnhandledExceptionFilter` at `0x140009320`

## pseudocode

```c
// attributes: thunk
LONG __stdcall UbpmpTaskHostUnhandledExceptionFilter(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  return RtlUnhandledExceptionFilter(ExceptionInfo);
}

```

## disassembly

```asm
0x140009320  jmp     cs:__imp_RtlUnhandledExceptionFilter
```
