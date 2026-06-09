# CHttpRequest::MapURLToPath(char *,ulong *,_HSE_URL_MAPEX_INFO *)

- ea: `0x1800067b8`
- end: `0x180006bc1`
- name: `?MapURLToPath@CHttpRequest@@AEAAHPEADPEAKPEAU_HSE_URL_MAPEX_INFO@@@Z`
- size: `1033`
- prototype: `int(CHttpRequest *__hidden this, char *, unsigned int *, struct _HSE_URL_MAPEX_INFO *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800033c0`
- `0x180020c80`

## callees

- `0x180006168`
- `0x1800062a8`
- `0x1800067b8`
- `0x180006bc8`
- `0x18004eb70`
- `0x18004ec9c`
- `0x18005430c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x18000685b`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x18000685b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006802`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006802`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006947`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006947`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006a0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006a0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b1e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000693e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000693e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000698d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180006b4e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000698d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180006b4e`

## pseudocode

```c

```
