# RetrieveUrlCacheEntryStreamHelper(ushort const *,CAppCacheHandle *,ulong,int,ushort const *,void * *,_APP_CACHE_RETRIEVE_STATE *,CCacheClientEntry * *,ulong *,unsigned __int64 *)

- ea: `0x18009aac8`
- end: `0x18009b0d4`
- name: `?RetrieveUrlCacheEntryStreamHelper@@YAJPEBGPEAVCAppCacheHandle@@KH0PEAPEAXPEAU_APP_CACHE_RETRIEVE_STATE@@PEAPEAVCCacheClientEntry@@PEAKPEA_K@Z`
- size: `1548`
- prototype: `int(const unsigned __int16 *, struct CAppCacheHandle *, unsigned int, int, const unsigned __int16 *, void **, struct _APP_CACHE_RETRIEVE_STATE *, struct CCacheClientEntry **, unsigned int *, unsigned __int64 *)`
- caller_count: `7`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180099100`
- `0x1800a3b80`
- `0x180142170`
- `0x1801423d0`
- `0x180198550`
- `0x180198790`
- `0x180198a00`

## callees

- `0x180007858`
- `0x180046a1c`
- `0x1800701d0`
- `0x1800999f0`
- `0x18009a424`
- `0x18009aac8`
- `0x18009b0dc`
- `0x1800d1834`
- `0x1800d1bec`
- `0x18010edfc`
- `0x180116f04`
- `0x18012c568`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x180194b5c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009aead`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009aead`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ae40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ae40`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009adae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009adae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009ac8a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009ac8a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18009ad81`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18009ad81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009af24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009af24`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009ad5b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009af7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009ad5b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009af7b`

## pseudocode

```c

```
