# WlanDeviceServiceCommand

- ea: `0x18000b110`
- end: `0x18000b499`
- name: `WlanDeviceServiceCommand`
- size: `905`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, const GUID *pInterfaceGuid, LPGUID pDeviceServiceGuid, DWORD dwOpCode, DWORD dwInBufferSize, PVOID pInBuffer, DWORD dwOutBufferSize, PVOID pOutBuffer, PDWORD pdwBytesReturned)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x18000b110`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b274`
- `RPCRT4!NdrClientCall3` at `0x18000b274`
- `RPCRT4!RpcExceptionFilter` at `0x180060574`
- `RPCRT4!RpcExceptionFilter` at `0x180060574`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18000b308`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18000b308`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000b1fa`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000b1fa`

## pseudocode

```c

```
