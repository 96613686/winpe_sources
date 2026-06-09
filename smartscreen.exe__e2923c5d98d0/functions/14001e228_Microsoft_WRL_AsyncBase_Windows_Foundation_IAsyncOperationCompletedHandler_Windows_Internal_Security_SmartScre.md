# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x14001e228`
- end: `0x14001e2c2`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001c5a0`

## callees

- `0x140012a84`
- `0x14001e228`
- `0x140068010`

## string_xrefs

- `0x14001e263`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Internal.Security.SmartScreen.UriReputationExperienceInfo>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 v3; // rax
  __int64 (__fastcall *v4)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, __int64, __int64); // rdi
  __int64 v5; // rbx
  GUID v6; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER v7; // [rsp+50h] [rbp-28h] BYREF
  __int64 v8; // [rsp+68h] [rbp-10h]

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(_QWORD *)Microsoft::WRL::gCausality;
    v8 = 0;
    v4 = *(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, __int64, __int64))(v3 + 48);
    v5 = *(unsigned int *)(a1 + 64);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v7,
      L"Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Internal.Security.SmartScreen.UriReputationExperienceInfo>",
      0x77u,
      0x76u);
    v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *)v4(
                                                                                      Microsoft::WRL::gCausality,
                                                                                      0,
                                                                                      2,
                                                                                      &v6,
                                                                                      a1,
                                                                                      v8,
                                                                                      v5);
  }
  return result;
}

```

## disassembly

```asm
0x14001e228  mov     r11, rsp
0x14001e22b  mov     [r11+8], rbx
0x14001e22f  mov     [r11+10h], rsi
0x14001e233  push    rdi
0x14001e234  sub     rsp, 70h
0x14001e238  mov     rsi, rcx
0x14001e23b  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x14001e242  test    rax, rax
0x14001e245  jz      short loc_14001E2B0
0x14001e247  mov     rax, [rax]
0x14001e24a  mov     qword ptr [r11-10h], 0
0x14001e252  mov     rdi, [rax+30h]
0x14001e256  mov     ebx, [rcx+40h]
0x14001e259  mov     r9d, 76h ; 'v'; unsigned int
0x14001e25f  lea     r8d, [r9+1]; unsigned int
0x14001e263  lea     rdx, aWindowsFoundat_3; "Windows.Foundation.AsyncOperationComple"...
0x14001e26a  lea     rcx, [r11-28h]; hstringHeader
0x14001e26e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14001e273  nop
0x14001e274  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x14001e27b  movdqu  [rsp+78h+var_38], xmm0
0x14001e281  mov     [rsp+78h+var_48], rbx
0x14001e286  mov     rcx, [rsp+78h+var_10]
0x14001e28b  mov     [rsp+78h+var_50], rcx
0x14001e290  mov     [rsp+78h+var_58], rsi
0x14001e295  lea     r9, [rsp+78h+var_38]
0x14001e29a  xor     edx, edx
0x14001e29c  lea     r8d, [rdx+2]
0x14001e2a0  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x14001e2a7  mov     rax, rdi
0x14001e2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e2af  nop
0x14001e2b0  lea     r11, [rsp+78h+var_8]
0x14001e2b5  mov     rbx, [r11+10h]
0x14001e2b9  mov     rsi, [r11+18h]
0x14001e2bd  mov     rsp, r11
0x14001e2c0  pop     rdi
0x14001e2c1  retn
```
