# SpReadPipeMsg(void *,ulong,SPIPCMSG * *,int)

- ea: `0x1800ec3bc`
- end: `0x1800ec55e`
- name: `?SpReadPipeMsg@@YAJPEAXKPEAPEAUSPIPCMSG@@H@Z`
- size: `418`
- prototype: `__int64 __fastcall(HANDLE hFile, DWORD dwMilliseconds, struct SPIPCMSG **, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18005a678`
- `0x1800e8c30`
- `0x1800e953c`
- `0x1800ea6b4`

## callees

- `0x180013ec0`
- `0x180045938`
- `0x1800ec1f0`
- `0x1800ec3bc`
- `0x1800ec564`
- `0x1800ec750`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec52f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec52f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ec445`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ec445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec4e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec4e9`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800ec4df`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800ec4df`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x1800ec4a1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x1800ec4a1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800ec487`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800ec487`

## string_xrefs

- `0x1800ec4c7`: `Failed to read a pipe message. Error = %X`

## pseudocode

```c

```
