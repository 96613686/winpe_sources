# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x14001f620`
- end: `0x14001f6a1`
- name: `?InitCausality@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `129`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001f620`
- `0x14001f878`
- `0x140026c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001f66e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001f66e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001f652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001f652`

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
0x14001f620  sub     rsp, 58h
0x14001f624  mov     rax, cs:__security_cookie
0x14001f62b  xor     rax, rsp
0x14001f62e  mov     [rsp+58h+var_18], rax
0x14001f633  lea     r9, [rsp+58h+string]; string
0x14001f638  mov     [rsp+58h+string], 0
0x14001f641  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x14001f646  mov     edx, 33h ; '3'; length
0x14001f64b  lea     rcx, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QBGB; "Windows.Foundation.Diagnostics.AsyncCau"...
0x14001f652  call    cs:__imp_WindowsCreateStringReference
0x14001f659  nop     dword ptr [rax+rax+00h]
0x14001f65e  test    eax, eax
0x14001f660  jns     short loc_14001F67B
0x14001f662  xor     r9d, r9d; lpArguments
0x14001f665  xor     r8d, r8d; nNumberOfArguments
0x14001f668  mov     ecx, eax; dwExceptionCode
0x14001f66a  lea     edx, [r9+1]; dwExceptionFlags
0x14001f66e  call    cs:__imp_RaiseException
0x14001f675  nop     dword ptr [rax+rax+00h]
0x14001f67a  int     3; Trap to Debugger
0x14001f67b  mov     rcx, [rsp+58h+string]
0x14001f680  call    ??$GetActivationFactory@UIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAsyncCausalityTracerStatics@Diagnostics@01@@Z; Windows::Foundation::GetActivationFactory<Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics>(HSTRING__ *,Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * *)
0x14001f685  xor     ecx, ecx
0x14001f687  test    eax, eax
0x14001f689  setns   cl
0x14001f68c  mov     eax, ecx
0x14001f68e  mov     rcx, [rsp+58h+var_18]
0x14001f693  xor     rcx, rsp; StackCookie
0x14001f696  call    __security_check_cookie
0x14001f69b  add     rsp, 58h
0x14001f69f  retn
```
