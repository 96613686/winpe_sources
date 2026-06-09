# IsProcessShutdownInProgress(void)

- ea: `0x18004f490`
- end: `0x18004f4fa`
- name: `?IsProcessShutdownInProgress@@YA_NXZ`
- size: `106`
- prototype: `bool(void)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001fe0c`
- `0x18001fe90`
- `0x1800214d8`
- `0x180039534`
- `0x18003a5f8`
- `0x18003a6c0`
- `0x18003a7a8`
- `0x18003fed4`
- `0x1800434a0`

## callees

- `0x18004f490`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f4c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f4c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004f4ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004f4ab`

## string_xrefs

- `0x18004f4a2`: `ntdll.dll`
- `0x18004f4bc`: `RtlDllShutdownInProgress`

## pseudocode

```c

```
