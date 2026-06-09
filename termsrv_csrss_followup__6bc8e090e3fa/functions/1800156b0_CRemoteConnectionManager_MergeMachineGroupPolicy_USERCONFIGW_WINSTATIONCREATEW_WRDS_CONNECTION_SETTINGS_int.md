# CRemoteConnectionManager::MergeMachineGroupPolicy(_USERCONFIGW *,_WINSTATIONCREATEW *,_WRDS_CONNECTION_SETTINGS *,int)

- ea: `0x1800156b0`
- end: `0x180015843`
- name: `?MergeMachineGroupPolicy@CRemoteConnectionManager@@UEAAJPEAU_USERCONFIGW@@PEAU_WINSTATIONCREATEW@@PEAU_WRDS_CONNECTION_SETTINGS@@H@Z`
- size: `403`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *__hidden this, struct _USERCONFIGW *, struct _WINSTATIONCREATEW *, struct _WRDS_CONNECTION_SETTINGS *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800156b0`
- `0x180034e64`
- `0x18004fecc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180015825`
- `ntdll!RtlReleaseResource` at `0x180015825`
- `ntdll!RtlAcquireResourceShared` at `0x1800156e8`
- `ntdll!RtlAcquireResourceShared` at `0x1800156e8`
- `REGAPI!RegMergeOnlyMachinePolicy` at `0x18001572a`
- `REGAPI!RegMergeOnlyMachinePolicy` at `0x18001572a`
- `REGAPI!RegMergeMachineAndProtocolPolicy` at `0x18001571c`
- `REGAPI!RegMergeMachineAndProtocolPolicy` at `0x18001571c`

## pseudocode

```c

```
