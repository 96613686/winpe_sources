# DeviceClassEnumeratorHandler::Initialize(long)

- ea: `0x18002df90`
- end: `0x18002e1a6`
- name: `?Initialize@DeviceClassEnumeratorHandler@@UEAAJJ@Z`
- size: `534`
- prototype: `__int64 __fastcall(DeviceClassEnumeratorHandler *__hidden this, int)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, service_task`

## callees

- `0x180006b88`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000f4fc`
- `0x180011a94`
- `0x1800174c4`
- `0x18002df90`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002e09d`
- `KERNEL32!GetLastError` at `0x18002e0d3`
- `KERNEL32!GetLastError` at `0x18002e09d`
- `KERNEL32!GetLastError` at `0x18002e0d3`
- `USER32!RegisterDeviceNotificationW` at `0x18002e07a`
- `USER32!RegisterDeviceNotificationW` at `0x18002e07a`

## string_xrefs

- `0x18002dfc3`: `ServiceStatus`
- `0x18002e0a6`: `Attempt to register for PnP notifications on our device class interface index %d failed. Error:0x%X`
- `0x18002e0dc`: `Attempt to register for PnP notifications on our device class interface index %d failed. Error:0x%X`
- `0x18002e123`: `The Image device class enumerator could not register with PnP for device notifications because we could not get the service's notification handle`
- `0x18002e14e`: `The Image device class enumerator could not register with PnP for device notifications because we could not get the service's notification handle`

## pseudocode

```c

```
