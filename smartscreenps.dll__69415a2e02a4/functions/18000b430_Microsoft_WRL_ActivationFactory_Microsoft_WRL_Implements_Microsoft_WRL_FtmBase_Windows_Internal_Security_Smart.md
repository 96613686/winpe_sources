# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000b430`
- end: `0x18000b459`
- name: `?GetRuntimeClassName@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b460`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b442`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b442`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  *a2 = 0;
  RoOriginateError(2147483662LL, 0);
  return 2147483662LL;
}

```

## disassembly

```asm
0x18000b430  sub     rsp, 28h
0x18000b434  mov     qword ptr [rdx], 0
0x18000b43b  mov     ecx, 8000000Eh
0x18000b440  xor     edx, edx
0x18000b442  call    cs:__imp_RoOriginateError
0x18000b449  nop     dword ptr [rax+rax+00h]
0x18000b44e  mov     eax, 8000000Eh
0x18000b453  add     rsp, 28h
0x18000b457  retn
```
