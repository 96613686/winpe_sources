# com::application_reputation_static::AddRef(void)

- ea: `0x18000b060`
- end: `0x18000b065`
- name: `?AddRef@application_reputation_static@com@@UEAAKXZ`
- size: `5`
- prototype: `unsigned int __fastcall(com::application_reputation_static *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b070`
- `0x18000b080`

## callees

- `0x18000afe0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall com::application_reputation_static::AddRef(__int64 this)
{
  return Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(this);
}

```

## disassembly

```asm
0x18000b060  jmp     ?AddRef@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)
```
