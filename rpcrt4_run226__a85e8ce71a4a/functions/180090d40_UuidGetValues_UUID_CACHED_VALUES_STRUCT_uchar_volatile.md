# UuidGetValues(_UUID_CACHED_VALUES_STRUCT *,uchar volatile *)

- ea: `0x180090d40`
- end: `0x180090e89`
- name: `?UuidGetValues@@YAJPEAU_UUID_CACHED_VALUES_STRUCT@@PECE@Z`
- size: `329`
- prototype: `__int64 __fastcall(struct _UUID_CACHED_VALUES_STRUCT *, volatile unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180090c30`

## callees

- `0x180090d40`

## import_xrefs

- `KERNELBASE!Sleep` at `0x180090e75`
- `KERNELBASE!Sleep` at `0x180090e75`
- `ntdll!NtAllocateUuids` at `0x180090d9a`
- `ntdll!NtAllocateUuids` at `0x180090d9a`
- `ntdll!RtlLeaveCriticalSection` at `0x180090e13`
- `ntdll!RtlLeaveCriticalSection` at `0x180090e34`
- `ntdll!RtlLeaveCriticalSection` at `0x180090e5d`
- `ntdll!RtlLeaveCriticalSection` at `0x180090e6a`
- `ntdll!RtlLeaveCriticalSection` at `0x180090e13`
- `ntdll!RtlLeaveCriticalSection` at `0x180090e34`
- `ntdll!RtlLeaveCriticalSection` at `0x180090e5d`
- `ntdll!RtlLeaveCriticalSection` at `0x180090e6a`
- `ntdll!RtlEnterCriticalSection` at `0x180090d77`
- `ntdll!RtlEnterCriticalSection` at `0x180090e7e`
- `ntdll!RtlEnterCriticalSection` at `0x180090d77`
- `ntdll!RtlEnterCriticalSection` at `0x180090e7e`

## pseudocode

```c

```
