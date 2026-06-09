# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x14001e550`
- end: `0x14001e5c4`
- name: `?InitCausality@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `116`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001e550`
- `0x14001e7f0`
- `0x140025aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001e598`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001e598`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001e582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001e582`

## pseudocode

```c
_BOOL8 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  HRESULT v3; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF

  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Diagnostics.AsyncCausalityTracer",
         0x33u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  return (int)Windows::Foundation::GetActivationFactory<Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics>(string) >= 0;
}

```

## disassembly

```asm
0x14001e550  sub     rsp, 58h
0x14001e554  mov     rax, cs:__security_cookie
0x14001e55b  xor     rax, rsp
0x14001e55e  mov     [rsp+58h+var_18], rax
0x14001e563  lea     r9, [rsp+58h+string]; string
0x14001e568  mov     [rsp+58h+string], 0
0x14001e571  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x14001e576  mov     edx, 33h ; '3'; length
0x14001e57b  lea     rcx, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QBGB; "Windows.Foundation.Diagnostics.AsyncCau"...
0x14001e582  call    cs:__imp_WindowsCreateStringReference
0x14001e588  test    eax, eax
0x14001e58a  jns     short loc_14001E59F
0x14001e58c  xor     r9d, r9d; lpArguments
0x14001e58f  xor     r8d, r8d; nNumberOfArguments
0x14001e592  mov     ecx, eax; dwExceptionCode
0x14001e594  lea     edx, [r9+1]; dwExceptionFlags
0x14001e598  call    cs:__imp_RaiseException
0x14001e59e  int     3; Trap to Debugger
0x14001e59f  mov     rcx, [rsp+58h+string]
0x14001e5a4  call    ??$GetActivationFactory@UIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAsyncCausalityTracerStatics@Diagnostics@01@@Z; Windows::Foundation::GetActivationFactory<Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics>(HSTRING__ *,Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * *)
0x14001e5a9  xor     ecx, ecx
0x14001e5ab  test    eax, eax
0x14001e5ad  setns   cl
0x14001e5b0  mov     eax, ecx
0x14001e5b2  mov     rcx, [rsp+58h+var_18]
0x14001e5b7  xor     rcx, rsp; StackCookie
0x14001e5ba  call    __security_check_cookie
0x14001e5bf  add     rsp, 58h
0x14001e5c3  retn
```
