# WdcTraceControl::TraceThread(void *)

- ea: `0x180075f70`
- end: `0x1800760ec`
- name: `?TraceThread@WdcTraceControl@@CAKPEAX@Z`
- size: `380`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000b854`
- `0x180075f70`
- `0x180086010`

## import_xrefs

- `ADVAPI32!ProcessTrace` at `0x180076085`
- `ADVAPI32!ProcessTrace` at `0x180076085`
- `KERNEL32!SetEvent` at `0x1800760d9`
- `KERNEL32!SetEvent` at `0x1800760d9`
- `KERNEL32!TlsSetValue` at `0x180075f86`
- `KERNEL32!TlsSetValue` at `0x180075f86`

## string_xrefs

- `0x1800760b2`: `WdcTraceControl::TraceThread`

## pseudocode

```c

```
