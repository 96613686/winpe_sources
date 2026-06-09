# com::application_reputation_static::Release(void)

- ea: `0x18000b500`
- end: `0x18000b505`
- name: `?Release@application_reputation_static@com@@UEAAKXZ`
- size: `5`
- prototype: `unsigned int __fastcall(com::application_reputation_static *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b510`
- `0x18000b520`

## callees

- `0x18000b470`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall com::application_reputation_static::Release(com::application_reputation_static *this)
{
  return Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release();
}

```

## disassembly

```asm
0x18000b500  jmp     ?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
```
