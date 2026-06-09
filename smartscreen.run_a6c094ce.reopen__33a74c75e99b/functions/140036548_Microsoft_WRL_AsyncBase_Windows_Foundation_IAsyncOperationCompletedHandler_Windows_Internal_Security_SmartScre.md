# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x140036548`
- end: `0x1400365d8`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140036430`

## callees

- `0x140011aa0`
- `0x140036548`
- `0x14006a010`

## string_xrefs

- `0x140036571`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Internal.Security.SmartScreen.AppReputationResult>`

## pseudocode

```c
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
0x140036548  mov     r11, rsp
0x14003654b  mov     [r11+8], rbx
0x14003654f  mov     [r11+18h], rsi
0x140036553  push    rdi
0x140036554  sub     rsp, 70h
0x140036558  mov     rsi, rcx
0x14003655b  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140036562  test    rax, rax
0x140036565  jz      short loc_1400365C5
0x140036567  mov     rax, [rax]
0x14003656a  mov     rdi, [rax+30h]
0x14003656e  mov     ebx, [rcx+40h]
0x140036571  lea     rax, aWindowsFoundat_8; "Windows.Foundation.AsyncOperationComple"...
0x140036578  mov     [r11+10h], rax
0x14003657c  lea     rdx, [r11+10h]
0x140036580  lea     rcx, [r11-28h]
0x140036584  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140036589  nop
0x14003658a  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x140036591  movdqu  [rsp+78h+var_38], xmm0
0x140036597  mov     [rsp+78h+var_48], rbx
0x14003659c  mov     rcx, [rax+18h]
0x1400365a0  mov     [rsp+78h+var_50], rcx
0x1400365a5  mov     [rsp+78h+var_58], rsi
0x1400365aa  lea     r9, [rsp+78h+var_38]
0x1400365af  xor     edx, edx
0x1400365b1  lea     r8d, [rdx+2]
0x1400365b5  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1400365bc  mov     rax, rdi
0x1400365bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400365c4  nop
0x1400365c5  lea     r11, [rsp+78h+var_8]
0x1400365ca  mov     rbx, [r11+10h]
0x1400365ce  mov     rsi, [r11+20h]
0x1400365d2  mov     rsp, r11
0x1400365d5  pop     rdi
0x1400365d6  retn
```
