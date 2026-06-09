# WFDMgrDiscoverDeviceServiceInformationInternal(_WFD_MANAGER *,uchar const (*)[6],ulong,_WFD_REQUESTED_SERVICE_INFO *,_WFD_DEVICE_SERVICE_INFO_ARRAY * *,ulong *,ulong *)

- ea: `0x180180044`
- end: `0x18018030f`
- name: `?WFDMgrDiscoverDeviceServiceInformationInternal@@YAKPEAU_WFD_MANAGER@@PEAY05$$CBEKPEAU_WFD_REQUESTED_SERVICE_INFO@@PEAPEAU_WFD_DEVICE_SERVICE_INFO_ARRAY@@PEAK4@Z`
- size: `715`
- prototype: `unsigned int(struct _WFD_MANAGER *, const unsigned __int8 (*)[6], unsigned int, struct _WFD_REQUESTED_SERVICE_INFO *, struct _WFD_DEVICE_SERVICE_INFO_ARRAY **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18017ff30`

## callees

- `0x18000a704`
- `0x18000aa0c`
- `0x18000be00`
- `0x180011530`
- `0x18005c808`
- `0x1800e1698`
- `0x1800e16e4`
- `0x180180044`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801801df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801801fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801801df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801801fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180180101`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180180101`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18018018c`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18018018c`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1801802c6`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1801802c6`

## pseudocode

```c

```
