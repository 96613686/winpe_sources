# __raise_securityfailure

- ea: `0x180001b28`
- end: `0x180001b5c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001b70`
- `0x180001d18`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001b3c`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b3c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b33`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b33`
- `KERNEL32!GetCurrentProcess` at `0x180001b42`
- `KERNEL32!GetCurrentProcess` at `0x180001b42`
- `KERNEL32!TerminateProcess` at `0x180001b55`

## pseudocode

```c

```
