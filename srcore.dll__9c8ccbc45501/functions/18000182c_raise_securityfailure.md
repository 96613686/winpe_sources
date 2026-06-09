# __raise_securityfailure

- ea: `0x18000182c`
- end: `0x180001860`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001870`
- `0x180001a18`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001840`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001840`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001837`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001837`
- `KERNEL32!GetCurrentProcess` at `0x180001846`
- `KERNEL32!GetCurrentProcess` at `0x180001846`
- `KERNEL32!TerminateProcess` at `0x180001859`

## pseudocode

```c

```
