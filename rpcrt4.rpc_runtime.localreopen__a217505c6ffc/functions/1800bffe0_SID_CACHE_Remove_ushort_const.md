# SID_CACHE::Remove(ushort const *)

- ea: `0x1800bffe0`
- end: `0x1800c0080`
- name: `?Remove@SID_CACHE@@QEAAJPEBG@Z`
- size: `160`
- prototype: `int(SID_CACHE *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1800993d4`

## callees

- `0x180023a40`
- `0x1800bffe0`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800c0021`
- `ntdll!_wcsicmp` at `0x1800c0021`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c0066`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c0066`
- `ntdll!RtlEnterCriticalSection` at `0x1800bfffe`
- `ntdll!RtlEnterCriticalSection` at `0x1800bfffe`

## pseudocode

```c

```
