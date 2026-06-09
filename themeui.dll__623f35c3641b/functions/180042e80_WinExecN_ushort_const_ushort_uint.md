# WinExecN(ushort const *,ushort *,uint)

- ea: `0x180042e80`
- end: `0x180042f7b`
- name: `?WinExecN@@YAIPEBGPEAGI@Z`
- size: `251`
- prototype: `unsigned int(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c608`

## callees

- `0x18003633c`
- `0x180042e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f44`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180042f0d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180042f0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f37`
- `USER32!WaitForInputIdle` at `0x180042f21`
- `USER32!WaitForInputIdle` at `0x180042f21`

## pseudocode

```c

```
