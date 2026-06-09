# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>::FillArrayWithIid(ulong *,_GUID *)

- ea: `0x18000af60`
- end: `0x18000af7a`
- name: `?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000af54`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>::FillArrayWithIid(
        __int64 a1,
        unsigned int *a2,
        __int64 a3)
{
  int v3; // ecx
  __int64 result; // rax

  v3 = *a2;
  *(GUID *)(a3 + 16LL * *a2) = GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34;
  result = (unsigned int)(v3 + 1);
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x18000af60  mov     ecx, [rdx]
0x18000af62  movups  xmm0, xmmword ptr cs:_GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34.Data1
0x18000af69  mov     eax, ecx
0x18000af6b  add     rax, rax
0x18000af6e  movdqu  xmmword ptr [r8+rax*8], xmm0
0x18000af74  lea     eax, [rcx+1]
0x18000af77  mov     [rdx], eax
0x18000af79  retn
```
