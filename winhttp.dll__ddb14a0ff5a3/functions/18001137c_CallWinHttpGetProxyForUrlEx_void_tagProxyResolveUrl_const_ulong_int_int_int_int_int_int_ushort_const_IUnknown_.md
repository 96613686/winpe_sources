# CallWinHttpGetProxyForUrlEx(void *,tagProxyResolveUrl const *,ulong,int,int,int,int,int,int,ushort const *,IUnknown *,ulong (*)(long,_PROXY_CONFIG_INFO const *,RefCountContext *),RefCountContext *)

- ea: `0x18001137c`
- end: `0x180011961`
- name: `?CallWinHttpGetProxyForUrlEx@@YAJPEAXPEBUtagProxyResolveUrl@@KHHHHHHPEBGPEAUIUnknown@@P6AKJPEBU_PROXY_CONFIG_INFO@@PEAVRefCountContext@@@Z5@Z`
- size: `1509`
- prototype: `__int64 __fastcall(HANDLE_OBJECT *this, const struct tagProxyResolveUrl *, __int16, int, int, int, int, int, int, const unsigned __int16 *, struct IUnknown *, unsigned int (*)(int, const struct _PROXY_CONFIG_INFO *, struct RefCountContext *), struct RefCountContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011000`

## callees

- `0x18000c000`
- `0x18000fc50`
- `0x18001137c`
- `0x180011970`
- `0x180012f10`
- `0x18003b230`
- `0x180041eb0`
- `0x1800a1d10`
- `0x1800db6b0`
- `0x1800dc348`
- `0x1800dd1e0`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800114d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800114d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011873`
- `ntdll!EtwEventActivityIdControl` at `0x180011636`
- `ntdll!EtwEventActivityIdControl` at `0x180011636`

## pseudocode

```c

```
