# WinHttpClientResolver::GetProxyForUrlImpl(ulong,tagProxyResolveUrl const *,IUnknown *,IGetProxyForUrlCompletion *,WinHttpClientCompletion *,IProxyResult * *)

- ea: `0x18004f4e0`
- end: `0x18004fc8c`
- name: `?GetProxyForUrlImpl@WinHttpClientResolver@@AEAAJKPEBUtagProxyResolveUrl@@PEAUIUnknown@@PEAUIGetProxyForUrlCompletion@@PEAVWinHttpClientCompletion@@PEAPEAUIProxyResult@@@Z`
- size: `1964`
- prototype: `__int64 __usercall@<rax>(WinHttpClientResolver *__hidden this@<rcx>, unsigned int@<edx>, const struct tagProxyResolveUrl *@<r8>, struct IUnknown *@<r9>, struct IGetProxyForUrlCompletion *, struct WinHttpClientCompletion *, struct IProxyResult **)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004f360`
- `0x18004f4b0`

## callees

- `0x18000f064`
- `0x180014398`
- `0x18003fad0`
- `0x18004e298`
- `0x18004f4e0`
- `0x18004fc94`
- `0x18004fd60`
- `0x1800519e0`
- `0x180062570`
- `0x18006cc48`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800d52c0`
- `0x1800d72d0`
- `0x1800db6b0`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f5e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f5e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f97f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f97f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004f5b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004f5d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004f5b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004f5d4`
- `ntdll!EtwEventActivityIdControl` at `0x18004f698`
- `ntdll!EtwEventActivityIdControl` at `0x18004f698`

## pseudocode

```c

```
