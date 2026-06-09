# IsIntranetAvailableNLA(int *)

- ea: `0x1800ff8f8`
- end: `0x1800ffc52`
- name: `?IsIntranetAvailableNLA@@YAKPEAH@Z`
- size: `858`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180103100`

## callees

- `0x1800ff8f8`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffc05`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffc05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff9be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff9d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff9e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff9f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffa0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffa24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff9be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff9d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff9e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff9f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffa0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffa24`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ffb26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ffb26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ffba3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ffba3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800ff99d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800ff99d`

## string_xrefs

- `0x1800ff957`: `ws2_32.dll`
- `0x1800ff9c4`: `WSALookupServiceEnd`
- `0x1800ff9d9`: `WSACleanup`
- `0x1800ffa12`: `WSALookupServiceNextW`
- `0x1800ff9ff`: `WSALookupServiceBeginW`

## pseudocode

```c

```
