# ScWaitForServiceStableState(CServiceRecord *,unsigned __int64,uchar,ulong)

- ea: `0x14006d170`
- end: `0x14006d3ec`
- name: `?ScWaitForServiceStableState@@YAKPEAVCServiceRecord@@_KEK@Z`
- size: `636`
- prototype: `unsigned int __fastcall(struct CServiceRecord *, unsigned __int64, unsigned __int8, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1400337a8`

## callees

- `0x140003e54`
- `0x1400188fc`
- `0x14001c738`
- `0x1400575b0`
- `0x14006d170`
- `0x14006dbbc`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14006d1b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14006d22b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14006d2be`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14006d1b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14006d22b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14006d2be`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14006d23b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14006d23b`
- `ntdll!RtlReleaseResource` at `0x14006d350`
- `ntdll!RtlReleaseResource` at `0x14006d350`
- `ntdll!RtlAcquireResourceShared` at `0x14006d2b8`
- `ntdll!RtlAcquireResourceShared` at `0x14006d2b8`
- `ntdll!DbgPrintEx` at `0x14006d336`
- `ntdll!DbgPrintEx` at `0x14006d336`

## string_xrefs

- `0x14006d311`: `Service timeout`
- `0x14006d31c`: `\n=======================================================================================================================\n\n[SCM] !!!! %ws -- Contact timed out service '%ws', PID 0x%08lx owner to debug why %ws took %I64d msecs !!!!\n\n\n=======================================================================================================================\n\n`

## pseudocode

```c

```
