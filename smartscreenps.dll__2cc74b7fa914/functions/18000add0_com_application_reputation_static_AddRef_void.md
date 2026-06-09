# com::application_reputation_static::AddRef(void)

- ea: `0x18000add0`
- end: `0x18000add5`
- name: `?AddRef@application_reputation_static@com@@UEAAKXZ`
- size: `5`
- prototype: `unsigned int __fastcall(com::application_reputation_static *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ade0`
- `0x18000adf0`

## callees

- `0x18000ad50`

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
0x18000add0  jmp     ?AddRef@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)
```
