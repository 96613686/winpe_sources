# LocalConvertStringSidToSid

- ea: `0x180007fcc`
- end: `0x180007fff`
- name: `LocalConvertStringSidToSid`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180005d00`

## callees

- `0x180007fcc`
- `0x180008220`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180007fed`
- `ntdll!RtlNtStatusToDosError` at `0x180007fed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007fdb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ff5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007fdb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ff5`

## pseudocode

```c

```
