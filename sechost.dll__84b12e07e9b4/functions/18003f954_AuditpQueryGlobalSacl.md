# AuditpQueryGlobalSacl

- ea: `0x18003f954`
- end: `0x18003fa21`
- name: `AuditpQueryGlobalSacl`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003f5b0`

## callees

- `0x18003f954`
- `0x18004f902`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f9f1`
- `ntdll!RtlNtStatusToDosError` at `0x18003f9f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fa0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fa0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f9b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f9b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f9e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f9e7`
- `RPCRT4!NdrClientCall3` at `0x18003f99d`
- `RPCRT4!NdrClientCall3` at `0x18003f99d`

## pseudocode

```c

```
