# __raise_securityfailure

- ea: `0x180001b54`
- end: `0x180001b88`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001b90`
- `0x180001d38`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001b68`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b68`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b5f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b5f`
- `KERNEL32!GetCurrentProcess` at `0x180001b6e`
- `KERNEL32!GetCurrentProcess` at `0x180001b6e`
- `KERNEL32!TerminateProcess` at `0x180001b81`

## pseudocode

```c

```
