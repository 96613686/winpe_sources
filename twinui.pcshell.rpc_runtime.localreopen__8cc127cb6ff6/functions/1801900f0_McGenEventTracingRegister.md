# McGenEventTracingRegister

- ea: `0x1801900f0`
- end: `0x1801902a0`
- name: `McGenEventTracingRegister`
- size: `432`
- prototype: `__int64 __fastcall(LPCGUID ControlGuid, WMIDPREQUEST RequestAddress, PTRACEHANDLE RegistrationHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1801900f0`
- `0x180356360`
- `0x180356edc`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801901e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180190261`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801901e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180190261`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801901f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180190214`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18019027e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801901f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180190214`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18019027e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180190176`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180190176`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1806f769d`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1806f769d`

## string_xrefs

- `0x1801901ee`: `EventWrite`
- `0x1801901d9`: `advapi32.dll`
- `0x18019025a`: `api-ms-win-eventing-provider-l1-1-0.dll`

## pseudocode

```c

```
