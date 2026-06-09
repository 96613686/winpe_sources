# ScWaitForFirstResponse(_SC_SERVICE_CHANNEL_CONTEXT *,void *,CServiceRecord *,ulong *)

- ea: `0x14000b014`
- end: `0x14000b1ef`
- name: `?ScWaitForFirstResponse@@YAKPEAU_SC_SERVICE_CHANNEL_CONTEXT@@PEAXPEAVCServiceRecord@@PEAK@Z`
- size: `475`
- prototype: `unsigned int(struct _SC_SERVICE_CHANNEL_CONTEXT *, void *, struct CServiceRecord *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x14003ae4c`
- `0x14007a510`

## callees

- `0x140002890`
- `0x140003e54`
- `0x14000b014`
- `0x14000b1f8`
- `0x14000cf60`
- `0x140013b0c`
- `0x140013f60`
- `0x14006daec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000b13b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000b13b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14000b062`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14000b062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0ed`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14000b0b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14000b0b6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000b071`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000b071`

## pseudocode

```c

```
