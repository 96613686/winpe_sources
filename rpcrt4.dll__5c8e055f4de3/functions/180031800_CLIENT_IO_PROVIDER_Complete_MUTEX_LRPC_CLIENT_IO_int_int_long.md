# CLIENT_IO_PROVIDER::Complete(MUTEX *,LRPC_CLIENT_IO *,int,int,long)

- ea: `0x180031800`
- end: `0x180031a6f`
- name: `?Complete@CLIENT_IO_PROVIDER@@QEAAJPEAVMUTEX@@PEAVLRPC_CLIENT_IO@@HHJ@Z`
- size: `623`
- prototype: `__int64 __usercall@<rax>(CLIENT_IO_PROVIDER *__hidden this@<rcx>, PRTL_CRITICAL_SECTION CriticalSection@<rdx>, struct LRPC_CLIENT_IO *@<r8>, int@<r9d>, int, int)`
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031b60`
- `0x180033000`
- `0x180035938`
- `0x1800636e8`
- `0x1800637f0`

## callees

- `0x180022870`
- `0x180028a00`
- `0x180030af8`
- `0x180031800`
- `0x180031a78`
- `0x180031a9c`
- `0x180031ae4`
- `0x180033060`
- `0x180033084`
- `0x180034244`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800318c9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800318c9`
- `ntdll!RtlEnterCriticalSection` at `0x18003188b`
- `ntdll!RtlEnterCriticalSection` at `0x18003188b`

## pseudocode

```c

```
