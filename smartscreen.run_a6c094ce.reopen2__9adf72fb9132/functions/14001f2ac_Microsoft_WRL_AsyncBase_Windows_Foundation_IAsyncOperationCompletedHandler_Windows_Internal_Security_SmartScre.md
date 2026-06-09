# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x14001f2ac`
- end: `0x14001f33c`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d500`

## callees

- `0x140011aa0`
- `0x14001f2ac`
- `0x14006a010`

## string_xrefs

- `0x14001f2d5`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Internal.Security.SmartScreen.UriReputationExperienceInfo>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 (__fastcall *v3)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, PVOID, __int64); // rdi
  __int64 v4; // rbx
  HSTRING_HEADER *v5; // rax
  GUID v6; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER v7; // [rsp+50h] [rbp-28h] BYREF
  const WCHAR *v8; // [rsp+88h] [rbp+10h] BYREF

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, PVOID, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 48LL);
    v4 = *(unsigned int *)(a1 + 64);
    v8 = L"Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Internal.Security.SmartScreen.UriReputationExperienceInfo>";
    v5 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, &v8);
    v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *)v3(
                                                                                      Microsoft::WRL::gCausality,
                                                                                      0,
                                                                                      2,
                                                                                      &v6,
                                                                                      a1,
                                                                                      v5[1].Reserved.Reserved1,
                                                                                      v4);
  }
  return result;
}

```

## disassembly

```asm
0x14001f2ac  mov     r11, rsp
0x14001f2af  mov     [r11+8], rbx
0x14001f2b3  mov     [r11+18h], rsi
0x14001f2b7  push    rdi
0x14001f2b8  sub     rsp, 70h
0x14001f2bc  mov     rsi, rcx
0x14001f2bf  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x14001f2c6  test    rax, rax
0x14001f2c9  jz      short loc_14001F329
0x14001f2cb  mov     rax, [rax]
0x14001f2ce  mov     rdi, [rax+30h]
0x14001f2d2  mov     ebx, [rcx+40h]
0x14001f2d5  lea     rax, aWindowsFoundat_3; "Windows.Foundation.AsyncOperationComple"...
0x14001f2dc  mov     [r11+10h], rax
0x14001f2e0  lea     rdx, [r11+10h]
0x14001f2e4  lea     rcx, [r11-28h]
0x14001f2e8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14001f2ed  nop
0x14001f2ee  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x14001f2f5  movdqu  [rsp+78h+var_38], xmm0
0x14001f2fb  mov     [rsp+78h+var_48], rbx
0x14001f300  mov     rcx, [rax+18h]
0x14001f304  mov     [rsp+78h+var_50], rcx
0x14001f309  mov     [rsp+78h+var_58], rsi
0x14001f30e  lea     r9, [rsp+78h+var_38]
0x14001f313  xor     edx, edx
0x14001f315  lea     r8d, [rdx+2]
0x14001f319  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x14001f320  mov     rax, rdi
0x14001f323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f328  nop
0x14001f329  lea     r11, [rsp+78h+var_8]
0x14001f32e  mov     rbx, [r11+10h]
0x14001f332  mov     rsi, [r11+20h]
0x14001f336  mov     rsp, r11
0x14001f339  pop     rdi
0x14001f33a  retn
```
