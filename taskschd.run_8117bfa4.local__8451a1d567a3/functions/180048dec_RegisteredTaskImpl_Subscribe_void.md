# RegisteredTaskImpl::Subscribe(void)

- ea: `0x180048dec`
- end: `0x180048ef6`
- name: `?Subscribe@RegisteredTaskImpl@@AEAAJXZ`
- size: `266`
- prototype: `__int64 __fastcall(RegisteredTaskImpl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180048740`

## callees

- `0x180048dec`
- `0x180051c90`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180048edc`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180048edc`
- `ntdll!RtlNtStatusToDosError` at `0x180048e9b`
- `ntdll!RtlNtStatusToDosError` at `0x180048e9b`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180048e89`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180048e89`

## pseudocode

```c

```
