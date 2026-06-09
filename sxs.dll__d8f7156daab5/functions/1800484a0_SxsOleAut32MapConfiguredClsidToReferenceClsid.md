# SxsOleAut32MapConfiguredClsidToReferenceClsid

- ea: `0x1800484a0`
- end: `0x180048670`
- name: `SxsOleAut32MapConfiguredClsidToReferenceClsid`
- size: `464`
- prototype: `__int64 __fastcall(GUID *lpGuidToFind)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001c2c8`
- `0x18002e98c`
- `0x1800484a0`
- `0x18005d2b0`
- `0x180067170`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18004859e`
- `ntdll!RtlPopFrame` at `0x18004859e`
- `ntdll!RtlPushFrame` at `0x1800484fe`
- `ntdll!RtlPushFrame` at `0x1800484fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004856c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004856c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048637`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004865f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004865f`
- `KERNEL32!FindActCtxSectionGuid` at `0x18004855c`
- `KERNEL32!FindActCtxSectionGuid` at `0x18004855c`

## pseudocode

```c

```
