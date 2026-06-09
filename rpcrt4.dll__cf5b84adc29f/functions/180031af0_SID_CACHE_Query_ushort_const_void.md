# SID_CACHE::Query(ushort const *,void * *)

- ea: `0x180031af0`
- end: `0x180031bff`
- name: `?Query@SID_CACHE@@QEAAJPEBGPEAPEAX@Z`
- size: `271`
- prototype: `int(SID_CACHE *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002f480`
- `0x180031a64`

## callees

- `0x180023a40`
- `0x1800307e0`
- `0x180031af0`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x180031b23`
- `ntdll!NtQuerySystemTime` at `0x180031b23`
- `ntdll!_wcsicmp` at `0x180031b65`
- `ntdll!_wcsicmp` at `0x180031b65`
- `ntdll!RtlLeaveCriticalSection` at `0x180031ba7`
- `ntdll!RtlLeaveCriticalSection` at `0x180031ba7`
- `ntdll!RtlEnterCriticalSection` at `0x180031b3e`
- `ntdll!RtlEnterCriticalSection` at `0x180031b3e`

## pseudocode

```c

```
