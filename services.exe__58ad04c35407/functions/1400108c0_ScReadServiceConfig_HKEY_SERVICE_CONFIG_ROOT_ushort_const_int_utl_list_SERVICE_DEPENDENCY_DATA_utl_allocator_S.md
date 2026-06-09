# ScReadServiceConfig(HKEY__ *,_SERVICE_CONFIG_ROOT *,ushort const *,int *,utl::list<_SERVICE_DEPENDENCY_DATA,utl::allocator<_SERVICE_DEPENDENCY_DATA>> &,utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>> *)

- ea: `0x1400108c0`
- end: `0x1400112ab`
- name: `?ScReadServiceConfig@@YAKPEAUHKEY__@@PEAU_SERVICE_CONFIG_ROOT@@PEBGPEAHAEAV?$list@U_SERVICE_DEPENDENCY_DATA@@V?$allocator@U_SERVICE_DEPENDENCY_DATA@@@utl@@@utl@@PEAV?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@4@@Z`
- size: `2539`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, struct _SERVICE_CONFIG_ROOT *@<rdx>, unsigned __int16 *@<r8>, __int64, __int64)`
- caller_count: `2`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001064c`
- `0x1400709e0`

## callees

- `0x1400037c8`
- `0x140003e54`
- `0x140004c98`
- `0x140006df4`
- `0x140007130`
- `0x14000b674`
- `0x14000b7e4`
- `0x14000b958`
- `0x14000c310`
- `0x14000c8f0`
- `0x14000c988`
- `0x14000ca18`
- `0x14000d1dc`
- `0x1400108c0`
- `0x140011ba0`
- `0x140014074`
- `0x140017230`
- `0x1400188fc`
- `0x140019014`
- `0x14001a350`
- `0x140020f3c`
- `0x140021b78`
- `0x140021c54`
- `0x140021d08`
- `0x1400233ac`
- `0x14002a44c`
- `0x140030590`
- `0x1400420d0`
- `0x140043584`
- `0x14007b06c`
- `0x14007b0e8`
- `0x14007b418`
- `0x14007db5c`
- `0x14007e344`
- `0x140086624`
- `0x140094020`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14001117f`
- `ntdll!RtlFreeHeap` at `0x14001123c`
- `ntdll!RtlFreeHeap` at `0x14001125d`
- `ntdll!RtlFreeHeap` at `0x14001127e`
- `ntdll!RtlFreeHeap` at `0x14001117f`
- `ntdll!RtlFreeHeap` at `0x14001123c`
- `ntdll!RtlFreeHeap` at `0x14001125d`
- `ntdll!RtlFreeHeap` at `0x14001127e`
- `ntdll!RtlAllocateHeap` at `0x14001111c`
- `ntdll!RtlAllocateHeap` at `0x14001111c`

## string_xrefs

- `0x140010fa6`: `RequiredPrivileges`
- `0x140010ac5`: `OriginalServiceName`

## pseudocode

```c

```
