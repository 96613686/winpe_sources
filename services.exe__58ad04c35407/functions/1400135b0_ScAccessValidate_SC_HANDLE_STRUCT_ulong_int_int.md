# ScAccessValidate(_SC_HANDLE_STRUCT *,ulong,int,int)

- ea: `0x1400135b0`
- end: `0x1400137be`
- name: `?ScAccessValidate@@YAKPEAU_SC_HANDLE_STRUCT@@KHH@Z`
- size: `526`
- prototype: `unsigned int __fastcall(struct _SC_HANDLE_STRUCT *, unsigned int, int, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140012e90`
- `0x140013050`
- `0x140013390`
- `0x140019370`

## callees

- `0x140004c58`
- `0x1400089c8`
- `0x1400135b0`
- `0x1400137d0`
- `0x140029228`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140013663`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140013663`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400136b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400136b7`
- `ntdll!RtlMapGenericMask` at `0x140013608`
- `ntdll!RtlMapGenericMask` at `0x140013678`
- `ntdll!RtlMapGenericMask` at `0x1400136f9`
- `ntdll!RtlMapGenericMask` at `0x140013608`
- `ntdll!RtlMapGenericMask` at `0x140013678`
- `ntdll!RtlMapGenericMask` at `0x1400136f9`

## string_xrefs

- `0x140013612`: `SERVICE OBJECT`
- `0x140013703`: `SERVICE OBJECT`

## pseudocode

```c

```
