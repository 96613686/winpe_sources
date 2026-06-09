# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x140035018`
- end: `0x1400350a7`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140034f20`

## callees

- `0x1400111a8`
- `0x140035018`
- `0x140068010`

## string_xrefs

- `0x140035041`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Internal.Security.SmartScreen.AppReputationResult>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
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
    v8 = L"Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Internal.Security.SmartScreen.AppReputationResult>";
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
0x140035018  mov     r11, rsp
0x14003501b  mov     [r11+8], rbx
0x14003501f  mov     [r11+18h], rsi
0x140035023  push    rdi
0x140035024  sub     rsp, 70h
0x140035028  mov     rsi, rcx
0x14003502b  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140035032  test    rax, rax
0x140035035  jz      short loc_140035095
0x140035037  mov     rax, [rax]
0x14003503a  mov     rdi, [rax+30h]
0x14003503e  mov     ebx, [rcx+40h]
0x140035041  lea     rax, aWindowsFoundat_8; "Windows.Foundation.AsyncOperationComple"...
0x140035048  mov     [r11+10h], rax
0x14003504c  lea     rdx, [r11+10h]
0x140035050  lea     rcx, [r11-28h]
0x140035054  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140035059  nop
0x14003505a  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x140035061  movdqu  [rsp+78h+var_38], xmm0
0x140035067  mov     [rsp+78h+var_48], rbx
0x14003506c  mov     rcx, [rax+18h]
0x140035070  mov     [rsp+78h+var_50], rcx
0x140035075  mov     [rsp+78h+var_58], rsi
0x14003507a  lea     r9, [rsp+78h+var_38]
0x14003507f  xor     edx, edx
0x140035081  lea     r8d, [rdx+2]
0x140035085  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x14003508c  mov     rax, rdi
0x14003508f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035094  nop
0x140035095  lea     r11, [rsp+78h+var_8]
0x14003509a  mov     rbx, [r11+10h]
0x14003509e  mov     rsi, [r11+20h]
0x1400350a2  mov     rsp, r11
0x1400350a5  pop     rdi
0x1400350a6  retn
```
