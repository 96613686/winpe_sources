# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18004b520`
- end: `0x18004b5a3`
- name: `?InitCausality@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `131`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18004b520`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b568`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b552`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b582`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004b582`

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
  return (int)RoGetActivationFactory(string, &GUID_50850b26_267e_451b_a890_ab6a370245ee, &Microsoft::WRL::gCausality) >= 0;
}

```

## disassembly

```asm
0x18004b520  sub     rsp, 58h
0x18004b524  mov     rax, cs:__security_cookie
0x18004b52b  xor     rax, rsp
0x18004b52e  mov     [rsp+58h+var_18], rax
0x18004b533  lea     r9, [rsp+58h+string]; string
0x18004b538  mov     [rsp+58h+string], 0
0x18004b541  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18004b546  mov     edx, 33h ; '3'; length
0x18004b54b  lea     rcx, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QBGB; "Windows.Foundation.Diagnostics.AsyncCau"...
0x18004b552  call    cs:__imp_WindowsCreateStringReference
0x18004b558  test    eax, eax
0x18004b55a  jns     short loc_18004B56F
0x18004b55c  xor     r9d, r9d; lpArguments
0x18004b55f  xor     r8d, r8d; nNumberOfArguments
0x18004b562  mov     ecx, eax; dwExceptionCode
0x18004b564  lea     edx, [r9+1]; dwExceptionFlags
0x18004b568  call    cs:__imp_RaiseException
0x18004b56e  int     3; Trap to Debugger
0x18004b56f  mov     rcx, [rsp+58h+string]
0x18004b574  lea     r8, ?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18004b57b  lea     rdx, _GUID_50850b26_267e_451b_a890_ab6a370245ee
0x18004b582  call    cs:__imp_RoGetActivationFactory
0x18004b588  xor     ecx, ecx
0x18004b58a  test    eax, eax
0x18004b58c  setns   cl
0x18004b58f  mov     eax, ecx
0x18004b591  mov     rcx, [rsp+58h+var_18]
0x18004b596  xor     rcx, rsp; StackCookie
0x18004b599  call    __security_check_cookie
0x18004b59e  add     rsp, 58h
0x18004b5a2  retn
```
