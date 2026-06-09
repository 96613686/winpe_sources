# WlanRegisterDeviceServiceNotification

- ea: `0x180013a50`
- end: `0x180013ca2`
- name: `WlanRegisterDeviceServiceNotification`
- size: `594`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, const PWLAN_DEVICE_SERVICE_GUID_LIST pDevSvcGuidList)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x180013a50`
- `0x180019a20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180013bb9`
- `RPCRT4!NdrClientCall3` at `0x180013bb9`
- `RPCRT4!RpcExceptionFilter` at `0x180060ac8`
- `RPCRT4!RpcExceptionFilter` at `0x180060ac8`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180013c4a`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180013c4a`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180013b45`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180013b45`

## pseudocode

```c

```
