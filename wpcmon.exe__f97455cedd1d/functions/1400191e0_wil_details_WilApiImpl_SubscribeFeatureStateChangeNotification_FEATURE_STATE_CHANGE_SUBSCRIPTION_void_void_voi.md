# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1400191e0`
- end: `0x1400192ed`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140018818`
- `0x140018914`
- `0x1400191e0`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140019281`
- `KERNEL32!GetProcAddress` at `0x140019281`
- `KERNEL32!GetModuleHandleW` at `0x14001926a`
- `KERNEL32!GetModuleHandleW` at `0x14001926a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140019230`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140019230`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400192d7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400192d7`

## string_xrefs

- `0x140019263`: `ntdll.dll`
- `0x140019277`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
