# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x180021bf8`
- end: `0x180021cce`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021b60`

## callees

- `0x180021bf8`
- `0x180066910`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021cc7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021c6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021c6f`

## string_xrefs

- `0x180021c68`: `Windows.Foundation.AsyncOperationWithProgressCompletedHandler`2<Windows.Storage.Streams.IBuffer, UInt32>`

## pseudocode

```c
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  HRESULT v5; // eax
  GUID v6; // [rsp+40h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-38h] BYREF
  HSTRING string; // [rsp+68h] [rbp-20h] BYREF

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(_QWORD *)Microsoft::WRL::gCausality;
    string = 0;
    v4 = *(unsigned int *)(a1 + 64);
    v5 = WindowsCreateStringReference(
           L"Windows.Foundation.AsyncOperationWithProgressCompletedHandler`2<Windows.Storage.Streams.IBuffer, UInt32>",
           0x68u,
           &hstringHeader,
           &string);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      JUMPOUT(0x180021CCDLL);
    }
    v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *)(*(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, HSTRING, __int64))(v3 + 48))(
                                                                                      Microsoft::WRL::gCausality,
                                                                                      0,
                                                                                      2,
                                                                                      &v6,
                                                                                      a1,
                                                                                      string,
                                                                                      v4);
  }
  return result;
}

```

## disassembly

```asm
0x180021bf8  mov     [rsp+arg_8], rbx
0x180021bfd  mov     [rsp+arg_10], rsi
0x180021c02  push    rdi
0x180021c03  sub     rsp, 80h
0x180021c0a  mov     rax, cs:__security_cookie
0x180021c11  xor     rax, rsp
0x180021c14  mov     [rsp+88h+var_18], rax
0x180021c19  mov     rbx, rcx
0x180021c1c  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180021c23  test    rax, rax
0x180021c26  jnz     short loc_180021C4A
0x180021c28  mov     rcx, [rsp+88h+var_18]
0x180021c2d  xor     rcx, rsp; StackCookie
0x180021c30  call    __security_check_cookie
0x180021c35  lea     r11, [rsp+88h+var_8]
0x180021c3d  mov     rbx, [r11+18h]
0x180021c41  mov     rsi, [r11+20h]
0x180021c45  mov     rsp, r11
0x180021c48  pop     rdi
0x180021c49  retn
0x180021c4a  mov     rdi, [rax]
0x180021c4d  mov     [rsp+88h+string], 0
0x180021c56  mov     esi, [rcx+40h]
0x180021c59  lea     r9, [rsp+88h+string]; string
0x180021c5e  lea     r8, [rsp+88h+hstringHeader]; hstringHeader
0x180021c63  mov     edx, 68h ; 'h'; length
0x180021c68  lea     rcx, aWindowsFoundat_9; "Windows.Foundation.AsyncOperationWithPr"...
0x180021c6f  call    cs:__imp_WindowsCreateStringReference
0x180021c75  test    eax, eax
0x180021c77  js      short loc_180021CBB
0x180021c79  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180021c80  movdqu  [rsp+88h+var_48], xmm0
0x180021c86  mov     [rsp+88h+var_58], rsi
0x180021c8b  mov     rcx, [rsp+88h+string]
0x180021c90  mov     [rsp+88h+var_60], rcx
0x180021c95  mov     [rsp+88h+var_68], rbx
0x180021c9a  lea     r9, [rsp+88h+var_48]
0x180021c9f  xor     edx, edx
0x180021ca1  lea     r8d, [rdx+2]
0x180021ca5  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180021cac  mov     rax, [rdi+30h]
0x180021cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cb5  nop
0x180021cb6  jmp     loc_180021C28
0x180021cbb  xor     r9d, r9d; lpArguments
0x180021cbe  xor     r8d, r8d; nNumberOfArguments
0x180021cc1  lea     edx, [r9+1]; dwExceptionFlags
0x180021cc5  mov     ecx, eax; dwExceptionCode
0x180021cc7  call    cs:__imp_RaiseException
```
