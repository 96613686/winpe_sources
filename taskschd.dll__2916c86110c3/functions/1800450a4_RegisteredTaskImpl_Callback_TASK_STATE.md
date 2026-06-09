# RegisteredTaskImpl::Callback(_TASK_STATE)

- ea: `0x1800450a4`
- end: `0x18004512b`
- name: `?Callback@RegisteredTaskImpl@@QEAAXW4_TASK_STATE@@@Z`
- size: `135`
- prototype: `void __fastcall(RegisteredTaskImpl *__hidden this, enum _TASK_STATE)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180045590`

## callees

- `0x1800326b8`
- `0x1800351ec`
- `0x1800450a4`
- `0x180054010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800450de`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800450de`
- `ntdll!RtlNtStatusToDosError` at `0x1800450f5`
- `ntdll!RtlNtStatusToDosError` at `0x1800450f5`

## pseudocode

```c

```
