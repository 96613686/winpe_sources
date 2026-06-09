# SetProcessWin32Capabilities

- ea: `0x180079390`
- end: `0x18007940b`
- name: `SetProcessWin32Capabilities`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180079390`
- `0x1800a2010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800793f8`
- `ntdll!RtlSetLastWin32Error` at `0x1800793f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800793c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800793c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800793b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800793b2`

## string_xrefs

- `0x1800793ab`: `win32u.dll`

## pseudocode

```c

```
