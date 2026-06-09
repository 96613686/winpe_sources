# FindSecurityPackage(ulong,ulong,uint *,uint *)

- ea: `0x180045d90`
- end: `0x1800461f3`
- name: `?FindSecurityPackage@@YAJKKPEAI0@Z`
- size: `1123`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800459a8`
- `0x180045b94`
- `0x1800467b0`
- `0x1800a4c9c`

## callees

- `0x180021e70`
- `0x180022870`
- `0x180045d90`
- `0x1800461fc`
- `0x18004640c`
- `0x1800a5004`
- `0x1800bb000`
- `0x1800c9e34`
- `0x1800d2010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800461aa`
- `ntdll!_wcsicmp` at `0x1800461aa`
- `ntdll!RtlLeaveCriticalSection` at `0x180045e72`
- `ntdll!RtlLeaveCriticalSection` at `0x180045e72`
- `ntdll!RtlEnterCriticalSection` at `0x180045dfe`
- `ntdll!RtlEnterCriticalSection` at `0x180045dfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045f53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045f53`

## string_xrefs

- `0x180045f4c`: `InitSecurityInterfaceW`

## pseudocode

```c

```
