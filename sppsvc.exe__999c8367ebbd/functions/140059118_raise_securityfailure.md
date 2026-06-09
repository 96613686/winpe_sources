# __raise_securityfailure

- ea: `0x140059118`
- end: `0x14005914c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140059160`
- `0x140059308`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x140059145`
- `KERNEL32!GetCurrentProcess` at `0x140059132`
- `KERNEL32!GetCurrentProcess` at `0x140059132`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14005912c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14005912c`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140059123`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140059123`

## pseudocode

```c

```
