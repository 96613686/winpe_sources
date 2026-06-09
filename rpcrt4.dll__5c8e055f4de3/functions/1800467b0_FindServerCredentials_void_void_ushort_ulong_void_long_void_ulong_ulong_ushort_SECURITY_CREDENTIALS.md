# FindServerCredentials(void (*)(void *,ushort *,ulong,void * *,long *),void *,ulong,ulong,ushort *,SECURITY_CREDENTIALS * *)

- ea: `0x1800467b0`
- end: `0x1800469e1`
- name: `?FindServerCredentials@@YAJP6AXPEAXPEAGKPEAPEAXPEAJ@Z0KK1PEAPEAVSECURITY_CREDENTIALS@@@Z`
- size: `561`
- prototype: `int(void (*)(void *, unsigned __int16 *, unsigned int, void **, int *), void *, unsigned int, unsigned int, unsigned __int16 *, struct SECURITY_CREDENTIALS **)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800466f0`
- `0x1800a393c`

## callees

- `0x180021e70`
- `0x1800283bc`
- `0x180045d90`
- `0x1800467b0`
- `0x18004700c`
- `0x180099eb8`
- `0x18009b738`
- `0x18009b874`
- `0x18009e1a0`
- `0x1800a4bc4`
- `0x1800a5004`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180046916`
- `ntdll!RtlLeaveCriticalSection` at `0x1800469bd`
- `ntdll!RtlLeaveCriticalSection` at `0x180046916`
- `ntdll!RtlLeaveCriticalSection` at `0x1800469bd`
- `ntdll!RtlEnterCriticalSection` at `0x180046852`
- `ntdll!RtlEnterCriticalSection` at `0x180046852`

## pseudocode

```c

```
