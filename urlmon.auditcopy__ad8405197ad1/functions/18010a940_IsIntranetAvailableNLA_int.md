# IsIntranetAvailableNLA(int *)

- ea: `0x18010a940`
- end: `0x18010acda`
- name: `?IsIntranetAvailableNLA@@YAKPEAH@Z`
- size: `922`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18010e3a0`

## callees

- `0x18010a940`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010ac83`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010ac83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010aa90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18010ab98`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18010ab98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010ac1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010ac1b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18010a9e5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18010a9e5`

## string_xrefs

- `0x18010a99f`: `ws2_32.dll`
- `0x18010aa33`: `WSACleanup`
- `0x18010aa18`: `WSALookupServiceEnd`
- `0x18010aa65`: `WSALookupServiceBeginW`
- `0x18010aa7e`: `WSALookupServiceNextW`

## pseudocode

```c

```
