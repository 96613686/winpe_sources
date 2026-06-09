# SpWritePipeMsg(void *,_OVERLAPPED *,SPIPCMSG const *,int)

- ea: `0x1800ec78c`
- end: `0x1800ec988`
- name: `?SpWritePipeMsg@@YAJPEAXPEAU_OVERLAPPED@@PEBUSPIPCMSG@@H@Z`
- size: `508`
- prototype: `__int64 __fastcall(HANDLE hFile, LPOVERLAPPED lpOverlapped, LPCVOID lpBuffer, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x1800ea6b4`
- `0x1800ea868`
- `0x1800eac08`
- `0x1800eb684`
- `0x1800ec990`

## callees

- `0x180013ec0`
- `0x180045938`
- `0x1800ec1f0`
- `0x1800ec750`
- `0x1800ec78c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec85c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec85c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ec84b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ec84b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ec8fb`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ec929`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ec8fb`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ec929`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1800ec8a9`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1800ec8a9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x1800ec8e5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x1800ec8e5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800ec8cb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800ec8cb`

## pseudocode

```c

```
