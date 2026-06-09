# CServiceRecord::PostCompletedNotification(CServiceRecord *,ulong,_SC_NOTIFY_BLOCK *,void * *)

- ea: `0x1400044a4`
- end: `0x140004986`
- name: `?PostCompletedNotification@CServiceRecord@@QEAAXPEAV1@KPEAU_SC_NOTIFY_BLOCK@@PEAPEAX@Z`
- size: `1250`
- prototype: `void(CServiceRecord *__hidden this, struct CServiceRecord *, unsigned int, struct _SC_NOTIFY_BLOCK *, void **)`
- caller_count: `6`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140004428`
- `0x1400269f4`
- `0x14002a54c`
- `0x14003d5f0`
- `0x14006a9e0`
- `0x14007fbc0`

## callees

- `0x140003e54`
- `0x1400044a4`
- `0x14001700c`
- `0x140019cac`
- `0x14002b4e0`
- `0x140033204`
- `0x140071c88`
- `0x140080ba4`
- `0x140080c50`
- `0x1400811b0`
- `0x140081470`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400047c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400047c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000485a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000485a`
- `ntdll!RtlPublishWnfStateData` at `0x140004517`
- `ntdll!RtlPublishWnfStateData` at `0x14000454b`
- `ntdll!RtlPublishWnfStateData` at `0x140004517`
- `ntdll!RtlPublishWnfStateData` at `0x14000454b`

## pseudocode

```c

```
