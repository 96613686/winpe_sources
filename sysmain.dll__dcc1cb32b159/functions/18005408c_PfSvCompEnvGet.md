# PfSvCompEnvGet

- ea: `0x18005408c`
- end: `0x180054293`
- name: `PfSvCompEnvGet`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180069cf0`

## callees

- `0x18005408c`
- `0x18005429c`

## import_xrefs

- `ntdll!RtlGetSuiteMask` at `0x180054119`
- `ntdll!RtlGetSuiteMask` at `0x180054119`
- `ntdll!RtlNtStatusToDosError` at `0x1800541cf`
- `ntdll!RtlNtStatusToDosError` at `0x1800541cf`
- `ntdll!RtlQueryResourcePolicy` at `0x1800541c3`
- `ntdll!RtlQueryResourcePolicy` at `0x1800541c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800540e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054189`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800540e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054189`
- `ext-ms-win-sysmain-plmapi-l1-1-0!MemUtilIsLowMemPolicyActive` at `0x180054277`
- `ext-ms-win-sysmain-plmapi-l1-1-0!MemUtilIsLowMemPolicyActive` at `0x180054277`

## pseudocode

```c

```
