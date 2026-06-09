# TdhpEnumerateProviderFlagsFromWBEM(IWbemServices *,_GUID const *,_EVENT_FIELD_TYPE,ulong,_PROVIDER_FIELD_INFOARRAY *,ulong *)

- ea: `0x180029a28`
- end: `0x180029ac2`
- name: `?TdhpEnumerateProviderFlagsFromWBEM@@YAKPEAUIWbemServices@@PEBU_GUID@@W4_EVENT_FIELD_TYPE@@KPEAU_PROVIDER_FIELD_INFOARRAY@@PEAK@Z`
- size: `154`
- prototype: `unsigned int __usercall@<eax>(struct IWbemServices *@<rcx>, const struct _GUID *@<rdx>, enum _EVENT_FIELD_TYPE@<r8d>, unsigned int@<r9d>, struct _PROVIDER_FIELD_INFOARRAY *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800247d0`
- `0x18002b2c0`

## callees

- `0x1800064d0`
- `0x1800076e0`
- `0x18000c740`
- `0x180029a28`
- `0x18002ac2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180029a54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180029a54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029aa0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029aa0`

## pseudocode

```c

```
