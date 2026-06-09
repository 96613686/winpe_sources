# Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>::FillArrayWithIid(ulong *,_GUID *)

- ea: `0x18000af54`
- end: `0x18000af59`
- name: `?FillArrayWithIid@?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000af80`

## callees

- `0x18000af60`

## pseudocode

```c
// attributes: thunk
__int64 Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>::FillArrayWithIid()
{
  return Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>::FillArrayWithIid();
}

```

## disassembly

```asm
0x18000af54  jmp     ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>::FillArrayWithIid(ulong *,_GUID *)
```
