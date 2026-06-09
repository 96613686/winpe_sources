# ScPrepareServicePreshutdownList(_SERVICE_PRESHUTDOWN_DATA *,ulong,_SERVICE_PRESHUTDOWN_DATA * *,ulong *)

- ea: `0x14006cc44`
- end: `0x14006d029`
- name: `?ScPrepareServicePreshutdownList@@YAKPEAU_SERVICE_PRESHUTDOWN_DATA@@KPEAPEAU1@PEAK@Z`
- size: `997`
- prototype: `unsigned int __fastcall(struct _SERVICE_PRESHUTDOWN_DATA *, unsigned int, struct _SERVICE_PRESHUTDOWN_DATA **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callers

- `0x1400386c4`

## callees

- `0x140002890`
- `0x140003310`
- `0x140004c58`
- `0x140007130`
- `0x140007960`
- `0x140013f60`
- `0x1400188fc`
- `0x140020cbc`
- `0x140029228`
- `0x14006cc44`
- `0x140092420`
- `0x140094020`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x14006cdb4`
- `ntdll!RtlAcquireResourceExclusive` at `0x14006cf9c`
- `ntdll!RtlAcquireResourceExclusive` at `0x14006cdb4`
- `ntdll!RtlAcquireResourceExclusive` at `0x14006cf9c`
- `ntdll!RtlReleaseResource` at `0x14006cf8d`
- `ntdll!RtlReleaseResource` at `0x14006cfdb`
- `ntdll!RtlReleaseResource` at `0x14006cff4`
- `ntdll!RtlReleaseResource` at `0x14006cf8d`
- `ntdll!RtlReleaseResource` at `0x14006cfdb`
- `ntdll!RtlReleaseResource` at `0x14006cff4`
- `ntdll!RtlFreeHeap` at `0x14006cee0`
- `ntdll!RtlFreeHeap` at `0x14006cfce`
- `ntdll!RtlFreeHeap` at `0x14006cee0`
- `ntdll!RtlFreeHeap` at `0x14006cfce`
- `ntdll!RtlAllocateHeap` at `0x14006ccf1`
- `ntdll!RtlAllocateHeap` at `0x14006ceab`
- `ntdll!RtlAllocateHeap` at `0x14006ccf1`
- `ntdll!RtlAllocateHeap` at `0x14006ceab`

## pseudocode

```c

```
