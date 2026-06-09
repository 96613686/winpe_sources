# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x180014a88`
- end: `0x180014b5e`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800149f0`

## callees

- `0x180014a88`
- `0x180066910`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014b57`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014b57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014aff`

## string_xrefs

- `0x180014af8`: `Windows.Foundation.AsyncOperationWithProgressCompletedHandler`2<UInt32, UInt32>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned int,unsigned int>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
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
           L"Windows.Foundation.AsyncOperationWithProgressCompletedHandler`2<UInt32, UInt32>",
           0x4Fu,
           &hstringHeader,
           &string);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      JUMPOUT(0x180014B5DLL);
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
0x180014a88  mov     [rsp+arg_8], rbx
0x180014a8d  mov     [rsp+arg_10], rsi
0x180014a92  push    rdi
0x180014a93  sub     rsp, 80h
0x180014a9a  mov     rax, cs:__security_cookie
0x180014aa1  xor     rax, rsp
0x180014aa4  mov     [rsp+88h+var_18], rax
0x180014aa9  mov     rbx, rcx
0x180014aac  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180014ab3  test    rax, rax
0x180014ab6  jnz     short loc_180014ADA
0x180014ab8  mov     rcx, [rsp+88h+var_18]
0x180014abd  xor     rcx, rsp; StackCookie
0x180014ac0  call    __security_check_cookie
0x180014ac5  lea     r11, [rsp+88h+var_8]
0x180014acd  mov     rbx, [r11+18h]
0x180014ad1  mov     rsi, [r11+20h]
0x180014ad5  mov     rsp, r11
0x180014ad8  pop     rdi
0x180014ad9  retn
0x180014ada  mov     rdi, [rax]
0x180014add  mov     [rsp+88h+string], 0
0x180014ae6  mov     esi, [rcx+40h]
0x180014ae9  lea     r9, [rsp+88h+string]; string
0x180014aee  lea     r8, [rsp+88h+hstringHeader]; hstringHeader
0x180014af3  mov     edx, 4Fh ; 'O'; length
0x180014af8  lea     rcx, sourceString; "Windows.Foundation.AsyncOperationWithPr"...
0x180014aff  call    cs:__imp_WindowsCreateStringReference
0x180014b05  test    eax, eax
0x180014b07  js      short loc_180014B4B
0x180014b09  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180014b10  movdqu  [rsp+88h+var_48], xmm0
0x180014b16  mov     [rsp+88h+var_58], rsi
0x180014b1b  mov     rcx, [rsp+88h+string]
0x180014b20  mov     [rsp+88h+var_60], rcx
0x180014b25  mov     [rsp+88h+var_68], rbx
0x180014b2a  lea     r9, [rsp+88h+var_48]
0x180014b2f  xor     edx, edx
0x180014b31  lea     r8d, [rdx+2]
0x180014b35  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180014b3c  mov     rax, [rdi+30h]
0x180014b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b45  nop
0x180014b46  jmp     loc_180014AB8
0x180014b4b  xor     r9d, r9d; lpArguments
0x180014b4e  xor     r8d, r8d; nNumberOfArguments
0x180014b51  lea     edx, [r9+1]; dwExceptionFlags
0x180014b55  mov     ecx, eax; dwExceptionCode
0x180014b57  call    cs:__imp_RaiseException
```
