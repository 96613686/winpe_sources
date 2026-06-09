# LocalGetSidForString

- ea: `0x180006540`
- end: `0x18000666f`
- name: `LocalGetSidForString`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800092d0`
- `0x1800224e8`

## callees

- `0x180004f20`
- `0x180006540`
- `0x180008220`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180006645`
- `ntdll!RtlNtStatusToDosError` at `0x180006645`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006632`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000664d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006632`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000664d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006653`

## pseudocode

```c

```
