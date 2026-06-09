# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x1800457c0`
- end: `0x18004588f`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800455e0`

## callees

- `0x1800457c0`
- `0x180066910`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180045888`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180045888`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180045813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180045813`

## string_xrefs

- `0x18004580c`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Boolean>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  HRESULT v5; // eax
  GUID v6; // [rsp+40h] [rbp-48h] BYREF
  HSTRING_HEADER v7; // [rsp+50h] [rbp-38h] BYREF
  HSTRING v8; // [rsp+68h] [rbp-20h] BYREF

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(_QWORD *)Microsoft::WRL::gCausality;
    v8 = 0;
    v4 = *(unsigned int *)(a1 + 64);
    v5 = WindowsCreateStringReference(L"Windows.Foundation.AsyncOperationCompletedHandler`1<Boolean>", 0x3Cu, &v7, &v8);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      JUMPOUT(0x18004588ELL);
    }
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
0x1800457c0  mov     r11, rsp
0x1800457c3  mov     [r11+10h], rbx
0x1800457c7  mov     [r11+18h], rsi
0x1800457cb  push    rdi
0x1800457cc  sub     rsp, 80h
0x1800457d3  mov     rax, cs:__security_cookie
0x1800457da  xor     rax, rsp
0x1800457dd  mov     [rsp+88h+var_18], rax
0x1800457e2  mov     rbx, rcx
0x1800457e5  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800457ec  test    rax, rax
0x1800457ef  jz      short loc_18004585A
0x1800457f1  mov     rdi, [rax]
0x1800457f4  mov     qword ptr [r11-20h], 0
0x1800457fc  mov     esi, [rcx+40h]
0x1800457ff  lea     r9, [r11-20h]; string
0x180045803  lea     r8, [r11-38h]; hstringHeader
0x180045807  mov     edx, 3Ch ; '<'; length
0x18004580c  lea     rcx, aWindowsFoundat_3; "Windows.Foundation.AsyncOperationComple"...
0x180045813  call    cs:__imp_WindowsCreateStringReference
0x180045819  test    eax, eax
0x18004581b  js      short loc_18004587C
0x18004581d  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180045824  movdqu  [rsp+88h+var_48], xmm0
0x18004582a  mov     [rsp+88h+var_58], rsi
0x18004582f  mov     rcx, [rsp+88h+var_20]
0x180045834  mov     [rsp+88h+var_60], rcx
0x180045839  mov     [rsp+88h+var_68], rbx
0x18004583e  lea     r9, [rsp+88h+var_48]
0x180045843  xor     edx, edx
0x180045845  lea     r8d, [rdx+2]
0x180045849  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180045850  mov     rax, [rdi+30h]
0x180045854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045859  nop
0x18004585a  mov     rcx, [rsp+88h+var_18]
0x18004585f  xor     rcx, rsp; StackCookie
0x180045862  call    __security_check_cookie
0x180045867  lea     r11, [rsp+88h+var_8]
0x18004586f  mov     rbx, [r11+18h]
0x180045873  mov     rsi, [r11+20h]
0x180045877  mov     rsp, r11
0x18004587a  pop     rdi
0x18004587b  retn
0x18004587c  xor     r9d, r9d; lpArguments
0x18004587f  xor     r8d, r8d; nNumberOfArguments
0x180045882  lea     edx, [r9+1]; dwExceptionFlags
0x180045886  mov     ecx, eax; dwExceptionCode
0x180045888  call    cs:__imp_RaiseException
```
