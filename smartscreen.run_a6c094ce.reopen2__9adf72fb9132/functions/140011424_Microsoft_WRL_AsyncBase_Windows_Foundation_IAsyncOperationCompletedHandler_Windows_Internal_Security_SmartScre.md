# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x140011424`
- end: `0x1400114e2`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011360`

## callees

- `0x140011424`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140011485`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140011485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140011469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140011469`

## string_xrefs

- `0x140011462`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Internal.Security.SmartScreen.UriReputationResult>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  HRESULT v5; // eax
  GUID v6; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER v7; // [rsp+50h] [rbp-28h] BYREF
  HSTRING v8; // [rsp+68h] [rbp-10h] BYREF

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(_QWORD *)Microsoft::WRL::gCausality;
    v8 = 0;
    v4 = *(unsigned int *)(a1 + 64);
    v5 = WindowsCreateStringReference(
           L"Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Internal.Security.SmartScreen.UriReputationResult>",
           0x6Eu,
           &v7,
           &v8);
    if ( v5 < 0 )
      RaiseException(v5, 1u, 0, 0);
    v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *)(*(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, HSTRING, __int64))(v3 + 48))(
                                                                                      Microsoft::WRL::gCausality,
                                                                                      0,
                                                                                      2,
                                                                                      &v6,
                                                                                      a1,
                                                                                      v8,
                                                                                      v4);
  }
  return result;
}

```

## disassembly

```asm
0x140011424  mov     r11, rsp
0x140011427  mov     [r11+8], rbx
0x14001142b  mov     [r11+10h], rsi
0x14001142f  push    rdi
0x140011430  sub     rsp, 70h
0x140011434  mov     rbx, rcx
0x140011437  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x14001143e  test    rax, rax
0x140011441  jz      loc_1400114CF
0x140011447  mov     rdi, [rax]
0x14001144a  mov     qword ptr [r11-10h], 0
0x140011452  mov     esi, [rcx+40h]
0x140011455  lea     r9, [r11-10h]; string
0x140011459  lea     r8, [r11-28h]; hstringHeader
0x14001145d  mov     edx, 6Eh ; 'n'; length
0x140011462  lea     rcx, sourceString; "Windows.Foundation.AsyncOperationComple"...
0x140011469  call    cs:__imp_WindowsCreateStringReference
0x140011470  nop     dword ptr [rax+rax+00h]
0x140011475  test    eax, eax
0x140011477  jns     short loc_140011492
0x140011479  xor     r9d, r9d; lpArguments
0x14001147c  xor     r8d, r8d; nNumberOfArguments
0x14001147f  lea     edx, [r9+1]; dwExceptionFlags
0x140011483  mov     ecx, eax; dwExceptionCode
0x140011485  call    cs:__imp_RaiseException
0x14001148c  nop     dword ptr [rax+rax+00h]
0x140011491  nop
0x140011492  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x140011499  movdqu  [rsp+78h+var_38], xmm0
0x14001149f  mov     [rsp+78h+var_48], rsi
0x1400114a4  mov     rcx, [rsp+78h+var_10]
0x1400114a9  mov     [rsp+78h+var_50], rcx
0x1400114ae  mov     [rsp+78h+var_58], rbx
0x1400114b3  lea     r9, [rsp+78h+var_38]
0x1400114b8  xor     edx, edx
0x1400114ba  lea     r8d, [rdx+2]
0x1400114be  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1400114c5  mov     rax, [rdi+30h]
0x1400114c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400114ce  nop
0x1400114cf  lea     r11, [rsp+78h+var_8]
0x1400114d4  mov     rbx, [r11+10h]
0x1400114d8  mov     rsi, [r11+18h]
0x1400114dc  mov     rsp, r11
0x1400114df  pop     rdi
0x1400114e0  retn
```
