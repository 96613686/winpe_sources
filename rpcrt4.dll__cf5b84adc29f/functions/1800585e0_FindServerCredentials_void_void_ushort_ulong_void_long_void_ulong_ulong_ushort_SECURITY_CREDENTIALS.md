# FindServerCredentials(void (*)(void *,ushort *,ulong,void * *,long *),void *,ulong,ulong,ushort *,SECURITY_CREDENTIALS * *)

- ea: `0x1800585e0`
- end: `0x180058824`
- name: `?FindServerCredentials@@YAJP6AXPEAXPEAGKPEAPEAXPEAJ@Z0KK1PEAPEAVSECURITY_CREDENTIALS@@@Z`
- size: `580`
- prototype: `int(void (*)(void *, unsigned __int16 *, unsigned int, void **, int *), void *, unsigned int, unsigned int, unsigned __int16 *, struct SECURITY_CREDENTIALS **)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058520`
- `0x1800a6f90`

## callees

- `0x180023020`
- `0x1800295d8`
- `0x180057b70`
- `0x1800585e0`
- `0x180059b74`
- `0x18006b36c`
- `0x180093944`
- `0x18009d838`
- `0x1800a1b88`
- `0x1800a8240`
- `0x1800a87e0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18005874c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800587f9`
- `ntdll!RtlLeaveCriticalSection` at `0x18005874c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800587f9`
- `ntdll!RtlEnterCriticalSection` at `0x180058682`
- `ntdll!RtlEnterCriticalSection` at `0x180058682`

## pseudocode

```c

```
