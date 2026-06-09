# RegisteredTaskImpl::Subscribe(void)

- ea: `0x1800456ac`
- end: `0x1800457a3`
- name: `?Subscribe@RegisteredTaskImpl@@AEAAJXZ`
- size: `247`
- prototype: `__int64 __fastcall(RegisteredTaskImpl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180045000`

## callees

- `0x1800456ac`
- `0x18004e024`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180045790`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180045790`
- `ntdll!RtlNtStatusToDosError` at `0x180045755`
- `ntdll!RtlNtStatusToDosError` at `0x180045755`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180045749`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180045749`

## pseudocode

```c

```
