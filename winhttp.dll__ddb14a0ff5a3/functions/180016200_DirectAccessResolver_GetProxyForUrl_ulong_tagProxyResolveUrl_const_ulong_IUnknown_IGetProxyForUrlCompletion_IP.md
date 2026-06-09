# DirectAccessResolver::GetProxyForUrl(ulong,tagProxyResolveUrl const *,ulong *,IUnknown *,IGetProxyForUrlCompletion *,IProxyResult * *)

- ea: `0x180016200`
- end: `0x180016689`
- name: `?GetProxyForUrl@DirectAccessResolver@@UEAAJKPEBUtagProxyResolveUrl@@PEAKPEAUIUnknown@@PEAUIGetProxyForUrlCompletion@@PEAPEAUIProxyResult@@@Z`
- size: `1161`
- prototype: `__int64 __fastcall(DirectAccessResolver *__hidden this, unsigned int, const struct tagProxyResolveUrl *, unsigned int *, struct IUnknown *, struct IGetProxyForUrlCompletion *, struct IProxyResult **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18001476c`
- `0x180016200`
- `0x180016888`
- `0x180017678`
- `0x1800639c0`
- `0x1800663a0`
- `0x1800c1aa0`
- `0x1800cf008`
- `0x1800d0220`
- `0x1800db6b0`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800162fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800162fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016327`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016511`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016327`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016511`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001625e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001625e`
- `DNSAPI!DnsGetProxyInformationEx` at `0x180016358`
- `DNSAPI!DnsGetProxyInformationEx` at `0x180016358`

## pseudocode

```c

```
