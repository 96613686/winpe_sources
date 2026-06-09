# McGenEventTracingRegister

- ea: `0x1800b9760`
- end: `0x1800b9948`
- name: `McGenEventTracingRegister`
- size: `488`
- prototype: `__int64 __fastcall(LPCGUID ControlGuid, WMIDPREQUEST RequestAddress, PTRACEHANDLE RegistrationHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002cd80`
- `0x18002d720`
- `0x1800b9760`
- `0x1800bc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b9805`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b981e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b9805`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b981e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b9836`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b9852`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b986e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b9836`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b9852`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b986e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800b97ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800b97ce`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800b9922`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800b9922`

## string_xrefs

- `0x1800b97fe`: `advapi32.dll`
- `0x1800b9817`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1800b982c`: `EventWrite`

## pseudocode

```c

```
