# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x140011dfc`
- end: `0x140011ea9`
- name: `?TraceOperationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e510`

## callees

- `0x140011dfc`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140011e53`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140011e53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140011e3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140011e3d`

## string_xrefs

- `0x140011e36`: `SmartScreen.ComApi.MakeAsyncAction.LogEvent`

## pseudocode

```c
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
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
    v5 = WindowsCreateStringReference(L"SmartScreen.ComApi.MakeAsyncAction.LogEvent", 0x2Bu, &v7, &v8);
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
0x140011dfc  mov     r11, rsp
0x140011dff  mov     [r11+8], rbx
0x140011e03  mov     [r11+10h], rsi
0x140011e07  push    rdi
0x140011e08  sub     rsp, 70h
0x140011e0c  mov     rbx, rcx
0x140011e0f  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140011e16  test    rax, rax
0x140011e19  jz      short loc_140011E97
0x140011e1b  mov     rdi, [rax]
0x140011e1e  mov     qword ptr [r11-10h], 0
0x140011e26  mov     esi, [rcx+40h]
0x140011e29  lea     r9, [r11-10h]; string
0x140011e2d  lea     r8, [r11-28h]; hstringHeader
0x140011e31  mov     edx, 2Bh ; '+'; length
0x140011e36  lea     rcx, ?k_OperationLogEventStr@@3QBGB; "SmartScreen.ComApi.MakeAsyncAction.LogE"...
0x140011e3d  call    cs:__imp_WindowsCreateStringReference
0x140011e43  test    eax, eax
0x140011e45  jns     short loc_140011E5A
0x140011e47  xor     r9d, r9d; lpArguments
0x140011e4a  xor     r8d, r8d; nNumberOfArguments
0x140011e4d  lea     edx, [r9+1]; dwExceptionFlags
0x140011e51  mov     ecx, eax; dwExceptionCode
0x140011e53  call    cs:__imp_RaiseException
0x140011e59  nop
0x140011e5a  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x140011e61  movdqu  [rsp+78h+var_38], xmm0
0x140011e67  mov     [rsp+78h+var_48], rsi
0x140011e6c  mov     rcx, [rsp+78h+var_10]
0x140011e71  mov     [rsp+78h+var_50], rcx
0x140011e76  mov     [rsp+78h+var_58], rbx
0x140011e7b  lea     r9, [rsp+78h+var_38]
0x140011e80  xor     edx, edx
0x140011e82  lea     r8d, [rdx+2]
0x140011e86  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140011e8d  mov     rax, [rdi+30h]
0x140011e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e96  nop
0x140011e97  lea     r11, [rsp+78h+var_8]
0x140011e9c  mov     rbx, [r11+10h]
0x140011ea0  mov     rsi, [r11+18h]
0x140011ea4  mov     rsp, r11
0x140011ea7  pop     rdi
0x140011ea8  retn
```
