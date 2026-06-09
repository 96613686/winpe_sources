# IsProcessShutdownInProgress(void)

- ea: `0x180004de4`
- end: `0x180004e45`
- name: `?IsProcessShutdownInProgress@@YA_NXZ`
- size: `97`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004d18`
- `0x1800201c8`

## callees

- `0x180004de4`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e2d`

## string_xrefs

- `0x180004e0f`: `ntdll.dll`
- `0x180004e23`: `RtlDllShutdownInProgress`

## pseudocode

```c

```
