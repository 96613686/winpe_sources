# Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IBlendEffect>::UsePropertyFactory<`Microsoft::Internal::UI::Composition::Effects::BlendEffect::GetProperty(uint,Windows::Foundation::IPropertyValue * *)'::`2'::_lambda_1_>(`Microsoft::Internal::UI::Composition::Effects::BlendEffect::GetProperty(uint,Windows::Foundation::IPropertyValue * *)'::`2'::_lambda_1_ const &)

- ea: `0x18001704c`
- end: `0x180017133`
- name: `??$UsePropertyFactory@V_lambda_1_@?1??GetProperty@BlendEffect@Effects@Composition@UI@Internal@Microsoft@@UEAAJIPEAPEAUIPropertyValue@Foundation@Windows@@@Z@@?$EffectBase@UIBlendEffect@Effects@Composition@UI@Internal@Microsoft@@@Effects@Composition@UI@Internal@Microsoft@@KAJAEBV_lambda_1_@?1??GetProperty@BlendEffect@12345@UEAAJIPEAPEAUIPropertyValue@Foundation@Windows@@@Z@@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017020`

## callees

- `0x18001704c`
- `0x180017290`
- `0x180021060`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800170fc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800170fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001708e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001708e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ___UsePropertyFactory_V_lambda_1___1__GetProperty_BlendEffect_Effects_Composition_UI_Internal_Microsoft__UEAAJIPEAPEAUIPropertyValue_Foundation_Windows___Z____EffectBase_UIBlendEffect_Effects_Composition_UI_Internal_Microsoft___Effects_Composition_UI_Internal_Microsoft__KAJAEBV_lambda_1___1__GetProperty_BlendEffect_12345_UEAAJIPEAPEAUIPropertyValue_Foundation_Windows___Z__Z(
        __int64 a1)
{
  HRESULT v2; // eax
  int v3; // ebx
  __int64 v4; // rcx
  __int64 v6; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER v7; // [rsp+28h] [rbp-30h] BYREF
  HSTRING v8; // [rsp+40h] [rbp-18h] BYREF

  v6 = 0;
  v8 = 0;
  v2 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &v7, &v8);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
  }
  else
  {
    v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
           v8,
           &v6);
    if ( v3 < 0 )
      goto LABEL_3;
  }
  if ( *(_DWORD *)a1 )
    v3 = -2147024809;
  else
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 88LL))(
           v6,
           *(unsigned int *)(*(_QWORD *)(a1 + 8) + 80LL),
           *(_QWORD *)(a1 + 16));
LABEL_3:
  v8 = 0;
  v4 = v6;
  if ( v6 )
  {
    v6 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001704c  mov     r11, rsp
0x18001704f  mov     [r11+10h], rbx
0x180017053  push    rdi
0x180017054  sub     rsp, 50h
0x180017058  mov     rax, cs:__security_cookie
0x18001705f  xor     rax, rsp
0x180017062  mov     [rsp+58h+var_10], rax
0x180017067  mov     rdi, rcx
0x18001706a  mov     qword ptr [r11-38h], 0
0x180017072  mov     qword ptr [r11-18h], 0
0x18001707a  lea     r9, [r11-18h]; string
0x18001707e  lea     r8, [r11-30h]; hstringHeader
0x180017082  mov     edx, 20h ; ' '; length
0x180017087  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18001708e  call    cs:__imp_WindowsCreateStringReference
0x180017094  test    eax, eax
0x180017096  js      short loc_1800170F0
0x180017098  lea     rdx, [rsp+58h+var_38]
0x18001709d  mov     rcx, [rsp+58h+var_18]
0x1800170a2  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x1800170a7  mov     ebx, eax
0x1800170a9  test    eax, eax
0x1800170ab  jns     short loc_180017103
0x1800170ad  mov     [rsp+58h+var_18], 0
0x1800170b6  mov     rcx, [rsp+58h+var_38]
0x1800170bb  test    rcx, rcx
0x1800170be  jz      short loc_1800170D6
0x1800170c0  mov     [rsp+58h+var_38], 0
0x1800170c9  mov     rdx, [rcx]
0x1800170cc  mov     rax, [rdx+10h]
0x1800170d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170d5  nop
0x1800170d6  mov     eax, ebx
0x1800170d8  mov     rcx, [rsp+58h+var_10]
0x1800170dd  xor     rcx, rsp; StackCookie
0x1800170e0  call    __security_check_cookie
0x1800170e5  mov     rbx, [rsp+58h+arg_8]
0x1800170ea  add     rsp, 50h
0x1800170ee  pop     rdi
0x1800170ef  retn
0x1800170f0  xor     r9d, r9d; lpArguments
0x1800170f3  xor     r8d, r8d; nNumberOfArguments
0x1800170f6  lea     edx, [r9+1]; dwExceptionFlags
0x1800170fa  mov     ecx, eax; dwExceptionCode
0x1800170fc  call    cs:__imp_RaiseException
0x180017102  nop
0x180017103  cmp     dword ptr [rdi], 0
0x180017106  jz      short loc_18001710F
0x180017108  mov     ebx, 80070057h
0x18001710d  jmp     short loc_1800170AD
0x18001710f  mov     rcx, [rsp+58h+var_38]
0x180017114  mov     rax, [rcx]
0x180017117  mov     rdx, [rdi+8]
0x18001711b  mov     r8, [rdi+10h]
0x18001711f  mov     edx, [rdx+50h]
0x180017122  mov     rax, [rax+58h]
0x180017126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001712b  mov     ebx, eax
0x18001712d  jmp     loc_1800170AD
```
