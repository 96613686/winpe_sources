# ScExtpExecuteTriggerAction(_SERVICE_TRIGGER_SUBSCRIPTION *,ushort *)

- ea: `0x140018d90`
- end: `0x14001900d`
- name: `?ScExtpExecuteTriggerAction@@YAKPEAU_SERVICE_TRIGGER_SUBSCRIPTION@@PEAG@Z`
- size: `637`
- prototype: `unsigned int(struct _SERVICE_TRIGGER_SUBSCRIPTION *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x140017980`
- `0x140018b50`

## callees

- `0x140003e54`
- `0x140018d90`
- `0x14004b1c0`
- `0x140091f60`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x140018f74`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140018fbb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140018fee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140018f74`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140018fbb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140018fee`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140018dfb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140018dfb`
- `ntdll!RtlNtStatusToDosError` at `0x140018f65`
- `ntdll!RtlNtStatusToDosError` at `0x140018f65`
- `ntdll!RtlFreeHeap` at `0x140018f8c`
- `ntdll!RtlFreeHeap` at `0x140018fa9`
- `ntdll!RtlFreeHeap` at `0x140018f8c`
- `ntdll!RtlFreeHeap` at `0x140018fa9`
- `ntdll!TpSimpleTryPost` at `0x140018f1e`
- `ntdll!TpSimpleTryPost` at `0x140018f1e`
- `ntdll!RtlAllocateHeap` at `0x140018e79`
- `ntdll!RtlAllocateHeap` at `0x140018eae`
- `ntdll!RtlAllocateHeap` at `0x140018e79`
- `ntdll!RtlAllocateHeap` at `0x140018eae`

## pseudocode

```c

```
