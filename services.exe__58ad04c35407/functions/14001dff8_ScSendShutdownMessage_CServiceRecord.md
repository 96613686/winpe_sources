# ScSendShutdownMessage(CServiceRecord *)

- ea: `0x14001dff8`
- end: `0x14001e124`
- name: `?ScSendShutdownMessage@@YAXPEAVCServiceRecord@@@Z`
- size: `300`
- prototype: `void __fastcall(struct CServiceRecord *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1400386c4`
- `0x140038a8c`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14000cf60`
- `0x14001dff8`
- `0x14001e12c`
- `0x1400575b0`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14001e031`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14001e031`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001e018`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001e018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e0e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e0e6`
- `ntdll!RtlReleaseResource` at `0x14001e077`
- `ntdll!RtlReleaseResource` at `0x14001e077`
- `ntdll!RtlAcquireResourceShared` at `0x14001e048`
- `ntdll!RtlAcquireResourceShared` at `0x14001e048`

## pseudocode

```c

```
