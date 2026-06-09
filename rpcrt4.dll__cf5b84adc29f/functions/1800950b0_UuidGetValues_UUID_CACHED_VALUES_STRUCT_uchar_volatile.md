# UuidGetValues(_UUID_CACHED_VALUES_STRUCT *,uchar volatile *)

- ea: `0x1800950b0`
- end: `0x18009522e`
- name: `?UuidGetValues@@YAJPEAU_UUID_CACHED_VALUES_STRUCT@@PECE@Z`
- size: `382`
- prototype: `__int64 __fastcall(struct _UUID_CACHED_VALUES_STRUCT *, volatile unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180094fa0`

## callees

- `0x1800950b0`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18009520e`
- `KERNELBASE!Sleep` at `0x18009520e`
- `ntdll!NtAllocateUuids` at `0x180095110`
- `ntdll!NtAllocateUuids` at `0x180095110`
- `ntdll!RtlLeaveCriticalSection` at `0x180095193`
- `ntdll!RtlLeaveCriticalSection` at `0x1800951bb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800951ea`
- `ntdll!RtlLeaveCriticalSection` at `0x1800951fd`
- `ntdll!RtlLeaveCriticalSection` at `0x180095193`
- `ntdll!RtlLeaveCriticalSection` at `0x1800951bb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800951ea`
- `ntdll!RtlLeaveCriticalSection` at `0x1800951fd`
- `ntdll!RtlEnterCriticalSection` at `0x1800950e7`
- `ntdll!RtlEnterCriticalSection` at `0x18009521d`
- `ntdll!RtlEnterCriticalSection` at `0x1800950e7`
- `ntdll!RtlEnterCriticalSection` at `0x18009521d`

## pseudocode

```c

```
