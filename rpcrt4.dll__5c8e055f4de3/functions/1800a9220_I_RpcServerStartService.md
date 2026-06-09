# I_RpcServerStartService

- ea: `0x1800a9220`
- end: `0x1800a92dd`
- name: `I_RpcServerStartService`
- size: `189`
- prototype: `RPC_STATUS __stdcall(RPC_WSTR Protseq, RPC_WSTR Endpoint, RPC_IF_HANDLE IfSpec)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x18006d0e0`
- `0x18006e1e0`
- `0x180070400`
- `0x180095dc4`
- `0x1800a9220`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800a9282`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a928d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a9282`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a928d`
- `ntdll!RtlEnterCriticalSection` at `0x1800a923f`
- `ntdll!RtlEnterCriticalSection` at `0x1800a923f`

## pseudocode

```c

```
