# CLIENT_IO_PROVIDER::Complete(MUTEX *,LRPC_CLIENT_IO *,int,int,long)

- ea: `0x180031c08`
- end: `0x180031e84`
- name: `?Complete@CLIENT_IO_PROVIDER@@QEAAJPEAVMUTEX@@PEAVLRPC_CLIENT_IO@@HHJ@Z`
- size: `636`
- prototype: `__int64 __usercall@<rax>(CLIENT_IO_PROVIDER *__hidden this@<rcx>, PRTL_CRITICAL_SECTION CriticalSection@<rdx>, struct LRPC_CLIENT_IO *@<r8>, int@<r9d>, int, int)`
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032fa0`
- `0x180034dc4`
- `0x1800361a0`
- `0x18007b77c`
- `0x180092de0`

## callees

- `0x180023a40`
- `0x180029c38`
- `0x180031c08`
- `0x180031e8c`
- `0x180031eb0`
- `0x18003227c`
- `0x180032f20`
- `0x18005b774`
- `0x180094ea0`
- `0x180095bdc`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180031cd7`
- `ntdll!RtlLeaveCriticalSection` at `0x180031cd7`
- `ntdll!RtlEnterCriticalSection` at `0x180031c93`
- `ntdll!RtlEnterCriticalSection` at `0x180031c93`

## pseudocode

```c

```
