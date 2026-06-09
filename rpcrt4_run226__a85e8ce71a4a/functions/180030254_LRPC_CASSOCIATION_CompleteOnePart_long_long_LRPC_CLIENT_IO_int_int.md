# LRPC_CASSOCIATION::CompleteOnePart(long,long,LRPC_CLIENT_IO *,int,int)

- ea: `0x180030254`
- end: `0x180030572`
- name: `?CompleteOnePart@LRPC_CASSOCIATION@@QEAAXJJPEAVLRPC_CLIENT_IO@@HH@Z`
- size: `798`
- prototype: `void __usercall(LRPC_CASSOCIATION *__hidden this@<rcx>, int@<edx>, int@<r8d>, struct LRPC_CLIENT_IO *@<r9>, int, int)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029798`
- `0x180068fe4`
- `0x1800b8e54`

## callees

- `0x180021ce0`
- `0x180022870`
- `0x1800274e0`
- `0x18002899c`
- `0x18002b7c0`
- `0x18002f070`
- `0x180030254`
- `0x180030578`
- `0x180030af8`
- `0x180031a9c`
- `0x180031ae4`
- `0x180033060`
- `0x180033084`
- `0x180034244`
- `0x18004c884`
- `0x180087cbc`
- `0x1800a2494`
- `0x1800d2010`

## import_xrefs

- `ntdll!NtClose` at `0x18003054f`
- `ntdll!NtClose` at `0x18003054f`
- `ntdll!RtlLeaveCriticalSection` at `0x180030302`
- `ntdll!RtlLeaveCriticalSection` at `0x180030302`
- `ntdll!RtlEnterCriticalSection` at `0x1800302c3`
- `ntdll!RtlEnterCriticalSection` at `0x180030342`
- `ntdll!RtlEnterCriticalSection` at `0x180030462`
- `ntdll!RtlEnterCriticalSection` at `0x1800302c3`
- `ntdll!RtlEnterCriticalSection` at `0x180030342`
- `ntdll!RtlEnterCriticalSection` at `0x180030462`

## pseudocode

```c

```
