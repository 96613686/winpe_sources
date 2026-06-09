# OutProcGetProxyForUrl(INTERNET_SESSION_HANDLE_OBJECT *,ushort const *,_WINHTTP_AUTOPROXY_OPTIONS const *,_WINHTTP_PROXY_INFO *)

- ea: `0x18000ec00`
- end: `0x18000ee88`
- name: `?OutProcGetProxyForUrl@@YAJPEAVINTERNET_SESSION_HANDLE_OBJECT@@PEBGPEBU_WINHTTP_AUTOPROXY_OPTIONS@@PEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(struct INTERNET_SESSION_HANDLE_OBJECT *, const unsigned __int16 *, const struct _WINHTTP_AUTOPROXY_OPTIONS *, struct _WINHTTP_PROXY_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000d5c0`

## callees

- `0x1800065a0`
- `0x18000ec00`
- `0x18000ee90`
- `0x18000f50c`
- `0x18000f744`
- `0x180011b98`
- `0x1800241a0`
- `0x18005ae20`
- `0x18007fec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ed15`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ed15`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ec72`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ec72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edc7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ec44`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ec44`

## pseudocode

```c

```
