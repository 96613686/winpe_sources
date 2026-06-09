# FindSecurityPackage(ulong,ulong,uint *,uint *)

- ea: `0x180057b70`
- end: `0x180057fec`
- name: `?FindSecurityPackage@@YAJKKPEAI0@Z`
- size: `1148`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005775c`
- `0x180057948`
- `0x1800585e0`
- `0x1800a83f4`

## callees

- `0x180023020`
- `0x180023a40`
- `0x180057b70`
- `0x180057ff4`
- `0x18005822c`
- `0x1800a87e0`
- `0x1800bf600`
- `0x1800cea7c`
- `0x1800d7010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x180057f9d`
- `ntdll!_wcsicmp` at `0x180057f9d`
- `ntdll!RtlLeaveCriticalSection` at `0x180057c58`
- `ntdll!RtlLeaveCriticalSection` at `0x180057c58`
- `ntdll!RtlEnterCriticalSection` at `0x180057bde`
- `ntdll!RtlEnterCriticalSection` at `0x180057bde`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057d40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057d40`

## string_xrefs

- `0x180057d39`: `InitSecurityInterfaceW`

## pseudocode

```c

```
