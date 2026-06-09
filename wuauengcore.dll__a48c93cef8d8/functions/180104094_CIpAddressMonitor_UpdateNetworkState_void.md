# CIpAddressMonitor::UpdateNetworkState(void)

- ea: `0x180104094`
- end: `0x1801043fc`
- name: `?UpdateNetworkState@CIpAddressMonitor@@AEAAXXZ`
- size: `872`
- prototype: `void __fastcall(CIpAddressMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180103acc`
- `0x180103dc4`

## callees

- `0x180104094`
- `0x180113a10`
- `0x180113ae8`
- `0x18012b618`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801040de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801040de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180104243`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801043cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180104243`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801043cb`
- `WS2_32!WSAIoctl` at `0x180104152`
- `WS2_32!WSAIoctl` at `0x1801041cf`
- `WS2_32!WSAIoctl` at `0x180104152`
- `WS2_32!WSAIoctl` at `0x1801041cf`
- `WS2_32!__imp_WSAGetLastError` at `0x18010416f`
- `WS2_32!__imp_WSAGetLastError` at `0x1801041da`
- `WS2_32!__imp_WSAGetLastError` at `0x1801042fa`
- `WS2_32!__imp_WSAGetLastError` at `0x18010416f`
- `WS2_32!__imp_WSAGetLastError` at `0x1801041da`
- `WS2_32!__imp_WSAGetLastError` at `0x1801042fa`

## string_xrefs

- `0x180104335`: `UpdateNetworkState Ipv%ws, WSAIoctl call 1 with SIO_ADDRESS_LIST_QUERY`
- `0x18010410e`: `UpdateNetworkState Ipv%ws, returning since socket is invalid.`
- `0x180104366`: `UpdateNetworkState Ipv%ws`
- `0x180104215`: `UpdateNetworkState Ipv%ws, WSAIoctl call 2 with SIO_ADDRESS_LIST_QUERY`
- `0x180104398`: `UpdateNetworkState Ipv%ws, cNetworkInterfaces = %d.`

## pseudocode

```c

```
