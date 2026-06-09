# CoInternetQueryInfo

- ea: `0x18006d2d0`
- end: `0x18006d71d`
- name: `CoInternetQueryInfo`
- size: `1101`
- prototype: `HRESULT __stdcall(LPCWSTR pwzUrl, QUERYOPTION QueryOptions, DWORD dwQueryFlags, LPVOID pvBuffer, DWORD cbBuffer, DWORD *pcbBuffer, DWORD dwReserved)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18011bdd4`

## callees

- `0x18001d540`
- `0x18001db50`
- `0x18001db94`
- `0x180028410`
- `0x18002fee0`
- `0x1800325fc`
- `0x18006d2d0`
- `0x18006d724`
- `0x18011d924`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d406`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d406`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d3d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d3d5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18006d31f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18006d31f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18006d5f0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18006d5f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d64a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d64a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d680`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d680`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006d668`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006d668`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x18006d516`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x18006d516`
- `WININET!GetUrlCacheEntryInfoExW` at `0x18006d625`
- `WININET!GetUrlCacheEntryInfoExW` at `0x18006d625`

## pseudocode

```c

```
