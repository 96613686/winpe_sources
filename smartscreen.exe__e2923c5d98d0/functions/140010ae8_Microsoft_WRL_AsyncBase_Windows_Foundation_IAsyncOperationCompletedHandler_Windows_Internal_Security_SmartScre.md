# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x140010ae8`
- end: `0x140010b95`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010a30`

## callees

- `0x140010ae8`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140010b3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140010b3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140010b29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140010b29`

## string_xrefs

- `0x140010b22`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Internal.Security.SmartScreen.UriReputationResult>`

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
0x140010ae8  mov     r11, rsp
0x140010aeb  mov     [r11+8], rbx
0x140010aef  mov     [r11+10h], rsi
0x140010af3  push    rdi
0x140010af4  sub     rsp, 70h
0x140010af8  mov     rbx, rcx
0x140010afb  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140010b02  test    rax, rax
0x140010b05  jz      short loc_140010B83
0x140010b07  mov     rdi, [rax]
0x140010b0a  mov     qword ptr [r11-10h], 0
0x140010b12  mov     esi, [rcx+40h]
0x140010b15  lea     r9, [r11-10h]; string
0x140010b19  lea     r8, [r11-28h]; hstringHeader
0x140010b1d  mov     edx, 6Eh ; 'n'; length
0x140010b22  lea     rcx, sourceString; "Windows.Foundation.AsyncOperationComple"...
0x140010b29  call    cs:__imp_WindowsCreateStringReference
0x140010b2f  test    eax, eax
0x140010b31  jns     short loc_140010B46
0x140010b33  xor     r9d, r9d; lpArguments
0x140010b36  xor     r8d, r8d; nNumberOfArguments
0x140010b39  lea     edx, [r9+1]; dwExceptionFlags
0x140010b3d  mov     ecx, eax; dwExceptionCode
0x140010b3f  call    cs:__imp_RaiseException
0x140010b45  nop
0x140010b46  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x140010b4d  movdqu  [rsp+78h+var_38], xmm0
0x140010b53  mov     [rsp+78h+var_48], rsi
0x140010b58  mov     rcx, [rsp+78h+var_10]
0x140010b5d  mov     [rsp+78h+var_50], rcx
0x140010b62  mov     [rsp+78h+var_58], rbx
0x140010b67  lea     r9, [rsp+78h+var_38]
0x140010b6c  xor     edx, edx
0x140010b6e  lea     r8d, [rdx+2]
0x140010b72  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140010b79  mov     rax, [rdi+30h]
0x140010b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b82  nop
0x140010b83  lea     r11, [rsp+78h+var_8]
0x140010b88  mov     rbx, [r11+10h]
0x140010b8c  mov     rsi, [r11+18h]
0x140010b90  mov     rsp, r11
0x140010b93  pop     rdi
0x140010b94  retn
```
