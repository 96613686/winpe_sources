# WctGetCritSecInfo(_WCT_CLIENT_HANDLE *,void *,ulong,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18005f878`
- end: `0x18005fa04`
- name: `?WctGetCritSecInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAXKPEAU_WAITCHAIN_NODE_INFO@@PEAK3@Z`
- size: `396`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *, void *, unsigned int, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18005fa0c`

## callees

- `0x180004c64`
- `0x180020680`
- `0x18005f878`
- `0x1800611cc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18005f920`
- `ntdll!RtlNtStatusToDosError` at `0x18005f920`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18005f8e2`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18005f8e2`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18005f90e`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18005f90e`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18005f9be`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18005f9be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f994`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f9aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f994`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f9aa`

## pseudocode

```c

```
