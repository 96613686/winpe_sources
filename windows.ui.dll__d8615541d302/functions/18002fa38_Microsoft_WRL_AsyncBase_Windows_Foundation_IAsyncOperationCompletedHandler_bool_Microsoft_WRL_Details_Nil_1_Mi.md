# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::UI::Core::CoreAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x18002fa38`
- end: `0x18002fb09`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CoreAsyncOperationName@Core@UI@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002f9a0`

## callees

- `0x18002fa38`
- `0x18002fdc8`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fb02`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fb02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fa96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fa96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::UI::Core::CoreAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  unsigned int v5; // eax
  UINT32 v6; // edx
  HRESULT v7; // eax
  GUID v8; // [rsp+40h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-58h] BYREF
  HSTRING string; // [rsp+68h] [rbp-40h] BYREF

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(_QWORD *)Microsoft::WRL::gCausality;
    string = 0;
    v4 = *(unsigned int *)(a1 + 64);
    v5 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x3Eu);
    v6 = v5 - 1;
    if ( v5 > 0x3E )
      v6 = 62;
    v7 = WindowsCreateStringReference(
           L"Windows.Foundation.IAsyncAction Windows.UI.Core.CoreDispatcher",
           v6,
           &hstringHeader,
           &string);
    if ( v7 < 0 )
    {
      RaiseException(v7, 1u, 0, 0);
      JUMPOUT(0x18002FB08LL);
    }
    v8 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *)(*(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, HSTRING, __int64))(v3 + 48))(
                                                                                      Microsoft::WRL::gCausality,
                                                                                      0,
                                                                                      2,
                                                                                      &v8,
                                                                                      a1,
                                                                                      string,
                                                                                      v4);
  }
  return result;
}

```

## disassembly

```asm
0x18002fa38  push    rbx
0x18002fa3a  push    rbp
0x18002fa3b  push    rsi
0x18002fa3c  push    rdi
0x18002fa3d  sub     rsp, 88h
0x18002fa44  mov     rax, cs:__security_cookie
0x18002fa4b  xor     rax, rsp
0x18002fa4e  mov     [rsp+0A8h+var_38], rax
0x18002fa53  mov     rbx, rcx
0x18002fa56  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18002fa5d  test    rax, rax
0x18002fa60  jz      short loc_18002FADD
0x18002fa62  mov     rdi, [rax]
0x18002fa65  mov     [rsp+0A8h+string], 0
0x18002fa6e  mov     esi, [rcx+40h]
0x18002fa71  mov     ebp, 3Eh ; '>'
0x18002fa76  mov     ecx, ebp; unsigned int
0x18002fa78  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002fa7d  lea     edx, [rax-1]
0x18002fa80  cmp     eax, ebp
0x18002fa82  cmova   edx, ebp; length
0x18002fa85  lea     r9, [rsp+0A8h+string]; string
0x18002fa8a  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x18002fa8f  lea     rcx, ?CoreAsyncOperationName@Core@UI@Windows@@3QBGB; "Windows.Foundation.IAsyncAction Windows"...
0x18002fa96  call    cs:__imp_WindowsCreateStringReference
0x18002fa9c  test    eax, eax
0x18002fa9e  js      short loc_18002FAF6
0x18002faa0  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18002faa7  movdqu  [rsp+0A8h+var_68], xmm0
0x18002faad  mov     [rsp+0A8h+var_78], rsi
0x18002fab2  mov     rcx, [rsp+0A8h+string]
0x18002fab7  mov     [rsp+0A8h+var_80], rcx
0x18002fabc  mov     [rsp+0A8h+var_88], rbx
0x18002fac1  lea     r9, [rsp+0A8h+var_68]
0x18002fac6  xor     edx, edx
0x18002fac8  lea     r8d, [rbp-3Ch]
0x18002facc  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18002fad3  mov     rax, [rdi+30h]
0x18002fad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fadc  nop
0x18002fadd  mov     rcx, [rsp+0A8h+var_38]
0x18002fae2  xor     rcx, rsp; StackCookie
0x18002fae5  call    __security_check_cookie
0x18002faea  add     rsp, 88h
0x18002faf1  pop     rdi
0x18002faf2  pop     rsi
0x18002faf3  pop     rbp
0x18002faf4  pop     rbx
0x18002faf5  retn
0x18002faf6  xor     r9d, r9d; lpArguments
0x18002faf9  xor     r8d, r8d; nNumberOfArguments
0x18002fafc  lea     edx, [r9+1]; dwExceptionFlags
0x18002fb00  mov     ecx, eax; dwExceptionCode
0x18002fb02  call    cs:__imp_RaiseException
```
