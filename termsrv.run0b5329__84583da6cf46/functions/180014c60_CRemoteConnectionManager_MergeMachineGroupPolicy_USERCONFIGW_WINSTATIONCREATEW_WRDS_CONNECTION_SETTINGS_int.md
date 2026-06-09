# CRemoteConnectionManager::MergeMachineGroupPolicy(_USERCONFIGW *,_WINSTATIONCREATEW *,_WRDS_CONNECTION_SETTINGS *,int)

- ea: `0x180014c60`
- end: `0x180014dda`
- name: `?MergeMachineGroupPolicy@CRemoteConnectionManager@@UEAAJPEAU_USERCONFIGW@@PEAU_WINSTATIONCREATEW@@PEAU_WRDS_CONNECTION_SETTINGS@@H@Z`
- size: `378`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *__hidden this, struct _USERCONFIGW *, struct _WINSTATIONCREATEW *, struct _WRDS_CONNECTION_SETTINGS *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180014c60`
- `0x1800330c4`
- `0x18004d884`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180014dc3`
- `ntdll!RtlReleaseResource` at `0x180014dc3`
- `ntdll!RtlAcquireResourceShared` at `0x180014c98`
- `ntdll!RtlAcquireResourceShared` at `0x180014c98`
- `REGAPI!RegMergeOnlyMachinePolicy` at `0x180014cce`
- `REGAPI!RegMergeOnlyMachinePolicy` at `0x180014cce`
- `REGAPI!RegMergeMachineAndProtocolPolicy` at `0x180014cc6`
- `REGAPI!RegMergeMachineAndProtocolPolicy` at `0x180014cc6`

## pseudocode

```c

```
