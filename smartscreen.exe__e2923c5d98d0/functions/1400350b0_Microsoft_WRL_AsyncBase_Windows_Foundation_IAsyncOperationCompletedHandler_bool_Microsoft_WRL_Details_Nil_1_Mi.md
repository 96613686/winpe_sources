# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x1400350b0`
- end: `0x14003513f`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140034fa0`

## callees

- `0x1400111a8`
- `0x1400350b0`
- `0x140068010`

## string_xrefs

- `0x1400350d9`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Boolean>`

## pseudocode

```c
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 (__fastcall *v3)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, PVOID, __int64); // rdi
  __int64 v4; // rbx
  HSTRING_HEADER *v5; // rax
  GUID v6; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER v7; // [rsp+50h] [rbp-28h] BYREF
  const WCHAR *v8; // [rsp+88h] [rbp+10h] BYREF

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, PVOID, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 48LL);
    v4 = *(unsigned int *)(a1 + 64);
    v8 = L"Windows.Foundation.AsyncOperationCompletedHandler`1<Boolean>";
    v5 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, &v8);
    v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *)v3(
                                                                                      Microsoft::WRL::gCausality,
                                                                                      0,
                                                                                      2,
                                                                                      &v6,
                                                                                      a1,
                                                                                      v5[1].Reserved.Reserved1,
                                                                                      v4);
  }
  return result;
}

```

## disassembly

```asm
0x1400350b0  mov     r11, rsp
0x1400350b3  mov     [r11+8], rbx
0x1400350b7  mov     [r11+18h], rsi
0x1400350bb  push    rdi
0x1400350bc  sub     rsp, 70h
0x1400350c0  mov     rsi, rcx
0x1400350c3  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1400350ca  test    rax, rax
0x1400350cd  jz      short loc_14003512D
0x1400350cf  mov     rax, [rax]
0x1400350d2  mov     rdi, [rax+30h]
0x1400350d6  mov     ebx, [rcx+40h]
0x1400350d9  lea     rax, aWindowsFoundat_2; "Windows.Foundation.AsyncOperationComple"...
0x1400350e0  mov     [r11+10h], rax
0x1400350e4  lea     rdx, [r11+10h]
0x1400350e8  lea     rcx, [r11-28h]
0x1400350ec  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1400350f1  nop
0x1400350f2  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1400350f9  movdqu  [rsp+78h+var_38], xmm0
0x1400350ff  mov     [rsp+78h+var_48], rbx
0x140035104  mov     rcx, [rax+18h]
0x140035108  mov     [rsp+78h+var_50], rcx
0x14003510d  mov     [rsp+78h+var_58], rsi
0x140035112  lea     r9, [rsp+78h+var_38]
0x140035117  xor     edx, edx
0x140035119  lea     r8d, [rdx+2]
0x14003511d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140035124  mov     rax, rdi
0x140035127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003512c  nop
0x14003512d  lea     r11, [rsp+78h+var_8]
0x140035132  mov     rbx, [r11+10h]
0x140035136  mov     rsi, [r11+20h]
0x14003513a  mov     rsp, r11
0x14003513d  pop     rdi
0x14003513e  retn
```
