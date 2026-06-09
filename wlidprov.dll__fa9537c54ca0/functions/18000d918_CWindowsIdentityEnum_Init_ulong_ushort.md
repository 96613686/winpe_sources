# CWindowsIdentityEnum::Init(ulong,ushort * *)

- ea: `0x18000d918`
- end: `0x18000d9e1`
- name: `?Init@CWindowsIdentityEnum@@QEAAJKPEAPEAG@Z`
- size: `201`
- prototype: `__int64 __fastcall(CWindowsIdentityEnum *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000c4f0`

## callees

- `0x1800090c0`
- `0x180009630`
- `0x18000d918`
- `0x18000da8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d992`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d992`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d973`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d973`

## string_xrefs

- `0x18000d93b`: `CWindowsIdentityEnum::Init`

## pseudocode

```c

```
