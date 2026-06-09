# ScGetTriggerInfo(_SERVICE_CONFIG_ROOT *,ushort const *,HKEY__ *,ulong,int,int,_SERVICE_TRIGGER_INFO * *)

- ea: `0x1400282a4`
- end: `0x140028fac`
- name: `?ScGetTriggerInfo@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEBGPEAUHKEY__@@KHHPEAPEAU_SERVICE_TRIGGER_INFO@@@Z`
- size: `3336`
- prototype: `unsigned int __fastcall(struct _SERVICE_CONFIG_ROOT *, const unsigned __int16 *, HKEY, unsigned int, int, int, struct _SERVICE_TRIGGER_INFO **)`
- caller_count: `5`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140028140`
- `0x140029908`
- `0x14003ab5c`
- `0x1400686dc`
- `0x14006b060`

## callees

- `0x140003e54`
- `0x140008b90`
- `0x14000bcc4`
- `0x14001df34`
- `0x140021d08`
- `0x1400282a4`
- `0x140028fb4`
- `0x140029274`
- `0x140032be0`
- `0x14004b524`
- `0x1400575b0`
- `0x140064a90`
- `0x140064b54`
- `0x140064c4c`
- `0x14007df34`
- `0x14007e060`
- `0x14007e18c`
- `0x14007e268`
- `0x140092060`
- `0x140092420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002883e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002883e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028ddc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400287d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140028ea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140028eb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400287d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140028ea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140028eb3`
- `ntdll!RtlFreeHeap` at `0x140028a34`
- `ntdll!RtlFreeHeap` at `0x140028ef8`
- `ntdll!RtlFreeHeap` at `0x140028f1e`
- `ntdll!RtlFreeHeap` at `0x140028f40`
- `ntdll!RtlFreeHeap` at `0x140028f78`
- `ntdll!RtlFreeHeap` at `0x140028a34`
- `ntdll!RtlFreeHeap` at `0x140028ef8`
- `ntdll!RtlFreeHeap` at `0x140028f1e`
- `ntdll!RtlFreeHeap` at `0x140028f40`
- `ntdll!RtlFreeHeap` at `0x140028f78`
- `ntdll!RtlAllocateHeap` at `0x140028578`
- `ntdll!RtlAllocateHeap` at `0x1400286eb`
- `ntdll!RtlAllocateHeap` at `0x140028779`
- `ntdll!RtlAllocateHeap` at `0x140028d21`
- `ntdll!RtlAllocateHeap` at `0x140028dca`
- `ntdll!RtlAllocateHeap` at `0x140028578`
- `ntdll!RtlAllocateHeap` at `0x1400286eb`
- `ntdll!RtlAllocateHeap` at `0x140028779`
- `ntdll!RtlAllocateHeap` at `0x140028d21`
- `ntdll!RtlAllocateHeap` at `0x140028dca`

## pseudocode

```c

```
