# GetKeyboardInputThreadId

- ea: `0x180078ff0`
- end: `0x180079057`
- name: `GetKeyboardInputThreadId`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180078ff0`
- `0x1800a2010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18007904a`
- `ntdll!RtlSetLastWin32Error` at `0x18007904a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007901c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007901c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180079007`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180079007`

## string_xrefs

- `0x180079012`: `NtUserGetKeyboardInputThreadId`
- `0x180079000`: `win32u.dll`

## pseudocode

```c

```
