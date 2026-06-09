# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::ActivateInstance(IInspectable * *)

- ea: `0x18000acd0`
- end: `0x18000acf2`
- name: `?ActivateInstance@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ace2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ace2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::ActivateInstance(
        __int64 a1,
        _QWORD *a2)
{
  *a2 = 0;
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000acd0  sub     rsp, 28h
0x18000acd4  mov     qword ptr [rdx], 0
0x18000acdb  mov     ecx, 80004001h
0x18000ace0  xor     edx, edx
0x18000ace2  call    cs:__imp_RoOriginateError
0x18000ace8  mov     eax, 80004001h
0x18000aced  add     rsp, 28h
0x18000acf1  retn
```
