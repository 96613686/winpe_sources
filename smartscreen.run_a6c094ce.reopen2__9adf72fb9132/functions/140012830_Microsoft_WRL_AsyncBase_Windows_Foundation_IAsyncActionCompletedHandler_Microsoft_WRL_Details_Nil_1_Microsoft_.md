# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x140012830`
- end: `0x1400128ee`
- name: `?TraceOperationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ec90`

## callees

- `0x140012830`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012891`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012875`

## string_xrefs

- `0x14001286e`: `SmartScreen.ComApi.MakeAsyncAction.LogEvent`

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
0x140012830  mov     r11, rsp
0x140012833  mov     [r11+8], rbx
0x140012837  mov     [r11+10h], rsi
0x14001283b  push    rdi
0x14001283c  sub     rsp, 70h
0x140012840  mov     rbx, rcx
0x140012843  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x14001284a  test    rax, rax
0x14001284d  jz      loc_1400128DB
0x140012853  mov     rdi, [rax]
0x140012856  mov     qword ptr [r11-10h], 0
0x14001285e  mov     esi, [rcx+40h]
0x140012861  lea     r9, [r11-10h]; string
0x140012865  lea     r8, [r11-28h]; hstringHeader
0x140012869  mov     edx, 2Bh ; '+'; length
0x14001286e  lea     rcx, ?k_OperationLogEventStr@@3QBGB; "SmartScreen.ComApi.MakeAsyncAction.LogE"...
0x140012875  call    cs:__imp_WindowsCreateStringReference
0x14001287c  nop     dword ptr [rax+rax+00h]
0x140012881  test    eax, eax
0x140012883  jns     short loc_14001289E
0x140012885  xor     r9d, r9d; lpArguments
0x140012888  xor     r8d, r8d; nNumberOfArguments
0x14001288b  lea     edx, [r9+1]; dwExceptionFlags
0x14001288f  mov     ecx, eax; dwExceptionCode
0x140012891  call    cs:__imp_RaiseException
0x140012898  nop     dword ptr [rax+rax+00h]
0x14001289d  nop
0x14001289e  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1400128a5  movdqu  [rsp+78h+var_38], xmm0
0x1400128ab  mov     [rsp+78h+var_48], rsi
0x1400128b0  mov     rcx, [rsp+78h+var_10]
0x1400128b5  mov     [rsp+78h+var_50], rcx
0x1400128ba  mov     [rsp+78h+var_58], rbx
0x1400128bf  lea     r9, [rsp+78h+var_38]
0x1400128c4  xor     edx, edx
0x1400128c6  lea     r8d, [rdx+2]
0x1400128ca  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1400128d1  mov     rax, [rdi+30h]
0x1400128d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400128da  nop
0x1400128db  lea     r11, [rsp+78h+var_8]
0x1400128e0  mov     rbx, [r11+10h]
0x1400128e4  mov     rsi, [r11+18h]
0x1400128e8  mov     rsp, r11
0x1400128eb  pop     rdi
0x1400128ec  retn
```
