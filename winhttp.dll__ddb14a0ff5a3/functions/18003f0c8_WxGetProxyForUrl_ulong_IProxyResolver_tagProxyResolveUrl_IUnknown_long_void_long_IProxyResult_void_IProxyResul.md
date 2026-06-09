# WxGetProxyForUrl(ulong,IProxyResolver *,tagProxyResolveUrl *,IUnknown *,long (*)(void *,long,IProxyResult *),void *,IProxyResult * *)

- ea: `0x18003f0c8`
- end: `0x18003f588`
- name: `?WxGetProxyForUrl@@YAJKPEAUIProxyResolver@@PEAUtagProxyResolveUrl@@PEAUIUnknown@@P6AJPEAXJPEAUIProxyResult@@@Z3PEAPEAU4@@Z`
- size: `1216`
- prototype: `__int64 __fastcall(unsigned int, struct IProxyResolver *, struct tagProxyResolveUrl *, struct IUnknown *, int (*)(void *, int, struct IProxyResult *), void *, struct IProxyResult **)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180030ab0`
- `0x18003ebb0`
- `0x180081cd4`
- `0x1800b2b70`

## callees

- `0x18003f0c8`
- `0x18003faa4`
- `0x1800a1d10`
- `0x1800db6b0`
- `0x1800dc9fc`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18003f170`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18003f170`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f452`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f452`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f192`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f1ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f3f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f192`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f1ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f3f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f362`

## pseudocode

```c

```
