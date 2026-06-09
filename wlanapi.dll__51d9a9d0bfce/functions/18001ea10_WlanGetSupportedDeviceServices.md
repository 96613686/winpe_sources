# WlanGetSupportedDeviceServices

- ea: `0x18001ea10`
- end: `0x18001ec77`
- name: `WlanGetSupportedDeviceServices`
- size: `615`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, const GUID *pInterfaceGuid, PWLAN_DEVICE_SERVICE_GUID_LIST *ppDevSvcGuidList)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x18001ea10`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001eb48`
- `RPCRT4!NdrClientCall3` at `0x18001eb48`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001ec30`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001ec30`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001eac0`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001eac0`

## pseudocode

```c

```
