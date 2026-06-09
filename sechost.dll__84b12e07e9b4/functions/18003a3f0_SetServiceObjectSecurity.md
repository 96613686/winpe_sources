# SetServiceObjectSecurity

- ea: `0x18003a3f0`
- end: `0x18003a4fc`
- name: `SetServiceObjectSecurity`
- size: `268`
- prototype: `BOOL __stdcall(SC_HANDLE hService, SECURITY_INFORMATION dwSecurityInformation, PSECURITY_DESCRIPTOR lpSecurityDescriptor)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18003a3f0`
- `0x18004abac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003a47c`
- `ntdll!RtlNtStatusToDosError` at `0x18003a47c`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18003a414`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18003a465`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18003a414`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18003a465`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a426`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a426`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a43f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a43f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a474`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a4dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a474`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a4dc`
- `RPCRT4!NdrClientCall2` at `0x18003a4b3`
- `RPCRT4!NdrClientCall2` at `0x18003a4b3`

## pseudocode

```c

```
