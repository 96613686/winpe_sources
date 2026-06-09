# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000b180`
- end: `0x18000b1a2`
- name: `?GetRuntimeClassName@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b1b0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b192`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b192`

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
0x18000b180  sub     rsp, 28h
0x18000b184  mov     qword ptr [rdx], 0
0x18000b18b  mov     ecx, 8000000Eh
0x18000b190  xor     edx, edx
0x18000b192  call    cs:__imp_RoOriginateError
0x18000b198  mov     eax, 8000000Eh
0x18000b19d  add     rsp, 28h
0x18000b1a1  retn
```
