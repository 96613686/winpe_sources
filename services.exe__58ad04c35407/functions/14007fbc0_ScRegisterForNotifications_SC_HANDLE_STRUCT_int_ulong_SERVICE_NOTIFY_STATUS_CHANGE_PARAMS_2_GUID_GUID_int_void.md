# ScRegisterForNotifications(_SC_HANDLE_STRUCT *,int,ulong,_SERVICE_NOTIFY_STATUS_CHANGE_PARAMS_2 *,_GUID *,_GUID *,int *,void * *)

- ea: `0x14007fbc0`
- end: `0x14007ff9a`
- name: `?ScRegisterForNotifications@@YAKPEAU_SC_HANDLE_STRUCT@@HKPEAU_SERVICE_NOTIFY_STATUS_CHANGE_PARAMS_2@@PEAU_GUID@@2PEAHPEAPEAX@Z`
- size: `986`
- prototype: `unsigned int __usercall@<eax>(struct _SC_HANDLE_STRUCT *@<rcx>, int@<edx>, unsigned int@<r8d>, struct _SERVICE_NOTIFY_STATUS_CHANGE_PARAMS_2 *@<r9>, struct _GUID *, struct _GUID *, int *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x140035280`

## callees

- `0x140003e54`
- `0x1400044a4`
- `0x14001c87c`
- `0x14001f7c0`
- `0x14001f99c`
- `0x140020d84`
- `0x140025d08`
- `0x1400432dc`
- `0x140043af4`
- `0x14007f3b0`
- `0x14007fbc0`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x14007fdad`
- `ntdll!RtlAcquireResourceExclusive` at `0x14007fdad`
- `ntdll!RtlReleaseResource` at `0x14007fe7a`
- `ntdll!RtlReleaseResource` at `0x14007ff50`
- `ntdll!RtlReleaseResource` at `0x14007fe7a`
- `ntdll!RtlReleaseResource` at `0x14007ff50`
- `ntdll!RtlFreeHeap` at `0x14007fe92`
- `ntdll!RtlFreeHeap` at `0x14007feb8`
- `ntdll!RtlFreeHeap` at `0x14007fe92`
- `ntdll!RtlFreeHeap` at `0x14007feb8`
- `ntdll!RtlAllocateHeap` at `0x14007fc7a`
- `ntdll!RtlAllocateHeap` at `0x14007fd3e`
- `ntdll!RtlAllocateHeap` at `0x14007fc7a`
- `ntdll!RtlAllocateHeap` at `0x14007fd3e`

## pseudocode

```c

```
