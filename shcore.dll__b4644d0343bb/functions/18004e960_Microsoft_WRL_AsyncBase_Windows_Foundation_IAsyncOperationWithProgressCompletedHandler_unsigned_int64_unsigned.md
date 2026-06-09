# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x18004e960`
- end: `0x18004ea2f`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@_K_K@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180082370`

## callees

- `0x18004e960`
- `0x180066910`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004ea28`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004ea28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e9b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e9b3`

## string_xrefs

- `0x18004e9ac`: `Windows.Foundation.AsyncOperationWithProgressCompletedHandler`2<UInt64, UInt64>`

## pseudocode

```c
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
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
    v5 = WindowsCreateStringReference(
           L"Windows.Foundation.AsyncOperationWithProgressCompletedHandler`2<UInt64, UInt64>",
           0x4Fu,
           &v7,
           &v8);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      JUMPOUT(0x18004EA2ELL);
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
0x18004e960  mov     r11, rsp
0x18004e963  mov     [r11+10h], rbx
0x18004e967  mov     [r11+18h], rsi
0x18004e96b  push    rdi
0x18004e96c  sub     rsp, 80h
0x18004e973  mov     rax, cs:__security_cookie
0x18004e97a  xor     rax, rsp
0x18004e97d  mov     [rsp+88h+var_18], rax
0x18004e982  mov     rbx, rcx
0x18004e985  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18004e98c  test    rax, rax
0x18004e98f  jz      short loc_18004E9FA
0x18004e991  mov     rdi, [rax]
0x18004e994  mov     qword ptr [r11-20h], 0
0x18004e99c  mov     esi, [rcx+40h]
0x18004e99f  lea     r9, [r11-20h]; string
0x18004e9a3  lea     r8, [r11-38h]; hstringHeader
0x18004e9a7  mov     edx, 4Fh ; 'O'; length
0x18004e9ac  lea     rcx, aWindowsFoundat_2; "Windows.Foundation.AsyncOperationWithPr"...
0x18004e9b3  call    cs:__imp_WindowsCreateStringReference
0x18004e9b9  test    eax, eax
0x18004e9bb  js      short loc_18004EA1C
0x18004e9bd  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18004e9c4  movdqu  [rsp+88h+var_48], xmm0
0x18004e9ca  mov     [rsp+88h+var_58], rsi
0x18004e9cf  mov     rcx, [rsp+88h+var_20]
0x18004e9d4  mov     [rsp+88h+var_60], rcx
0x18004e9d9  mov     [rsp+88h+var_68], rbx
0x18004e9de  lea     r9, [rsp+88h+var_48]
0x18004e9e3  xor     edx, edx
0x18004e9e5  lea     r8d, [rdx+2]
0x18004e9e9  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18004e9f0  mov     rax, [rdi+30h]
0x18004e9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9f9  nop
0x18004e9fa  mov     rcx, [rsp+88h+var_18]
0x18004e9ff  xor     rcx, rsp; StackCookie
0x18004ea02  call    __security_check_cookie
0x18004ea07  lea     r11, [rsp+88h+var_8]
0x18004ea0f  mov     rbx, [r11+18h]
0x18004ea13  mov     rsi, [r11+20h]
0x18004ea17  mov     rsp, r11
0x18004ea1a  pop     rdi
0x18004ea1b  retn
0x18004ea1c  xor     r9d, r9d; lpArguments
0x18004ea1f  xor     r8d, r8d; nNumberOfArguments
0x18004ea22  lea     edx, [r9+1]; dwExceptionFlags
0x18004ea26  mov     ecx, eax; dwExceptionCode
0x18004ea28  call    cs:__imp_RaiseException
```
