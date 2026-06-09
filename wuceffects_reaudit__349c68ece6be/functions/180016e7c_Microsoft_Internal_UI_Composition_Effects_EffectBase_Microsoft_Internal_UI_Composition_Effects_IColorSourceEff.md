# Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IColorSourceEffect>::UsePropertyFactory<`Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect::GetProperty(uint,Windows::Foundation::IPropertyValue * *)'::`2'::_lambda_1_>(`Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect::GetProperty(uint,Windows::Foundation::IPropertyValue * *)'::`2'::_lambda_1_ const &)

- ea: `0x180016e7c`
- end: `0x180016f56`
- name: `??$UsePropertyFactory@V_lambda_1_@?1??GetProperty@ColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@@UEAAJIPEAPEAUIPropertyValue@Foundation@Windows@@@Z@@?$EffectBase@UIColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@@@Effects@Composition@UI@Internal@Microsoft@@KAJAEBV_lambda_1_@?1??GetProperty@ColorSourceEffect@12345@UEAAJIPEAPEAUIPropertyValue@Foundation@Windows@@@Z@@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016e50`

## callees

- `0x180016e7c`
- `0x180016f5c`
- `0x180017290`
- `0x180021060`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016ed4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016ebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016ebe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ___UsePropertyFactory_V_lambda_1___1__GetProperty_ColorSourceEffect_Effects_Composition_UI_Internal_Microsoft__UEAAJIPEAPEAUIPropertyValue_Foundation_Windows___Z____EffectBase_UIColorSourceEffect_Effects_Composition_UI_Internal_Microsoft___Effects_Composition_UI_Internal_Microsoft__KAJAEBV_lambda_1___1__GetProperty_ColorSourceEffect_12345_UEAAJIPEAPEAUIPropertyValue_Foundation_Windows___Z__Z(
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
    RaiseException(v2, 1u, 0, 0);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
         v8,
         &v6);
  if ( v3 >= 0 )
  {
    if ( *(_DWORD *)a1 )
      v3 = -2147024809;
    else
      v3 = Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IColorSourceEffect>::CreateColor<4>(
             v6,
             *(unsigned int *)(*(_QWORD *)(a1 + 8) + 64LL),
             *(_QWORD *)(a1 + 16));
  }
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
0x180016e7c  mov     r11, rsp
0x180016e7f  mov     [r11+10h], rbx
0x180016e83  push    rdi
0x180016e84  sub     rsp, 50h
0x180016e88  mov     rax, cs:__security_cookie
0x180016e8f  xor     rax, rsp
0x180016e92  mov     [rsp+58h+var_10], rax
0x180016e97  mov     rdi, rcx
0x180016e9a  mov     qword ptr [r11-38h], 0
0x180016ea2  mov     qword ptr [r11-18h], 0
0x180016eaa  lea     r9, [r11-18h]; string
0x180016eae  lea     r8, [r11-30h]; hstringHeader
0x180016eb2  mov     edx, 20h ; ' '; length
0x180016eb7  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180016ebe  call    cs:__imp_WindowsCreateStringReference
0x180016ec4  test    eax, eax
0x180016ec6  jns     short loc_180016EDB
0x180016ec8  xor     r9d, r9d; lpArguments
0x180016ecb  xor     r8d, r8d; nNumberOfArguments
0x180016ece  lea     edx, [r9+1]; dwExceptionFlags
0x180016ed2  mov     ecx, eax; dwExceptionCode
0x180016ed4  call    cs:__imp_RaiseException
0x180016eda  nop
0x180016edb  lea     rdx, [rsp+58h+var_38]
0x180016ee0  mov     rcx, [rsp+58h+var_18]
0x180016ee5  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x180016eea  mov     ebx, eax
0x180016eec  test    eax, eax
0x180016eee  js      short loc_180016F13
0x180016ef0  cmp     dword ptr [rdi], 0
0x180016ef3  jz      short loc_180016EFC
0x180016ef5  mov     ebx, 80070057h
0x180016efa  jmp     short loc_180016F13
0x180016efc  mov     rdx, [rdi+8]
0x180016f00  mov     r8, [rdi+10h]
0x180016f04  mov     edx, [rdx+40h]
0x180016f07  mov     rcx, [rsp+58h+var_38]
0x180016f0c  call    ??$CreateColor@$03@?$EffectBase@UIColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@@@Effects@Composition@UI@Internal@Microsoft@@KAJPEAUIPropertyValueStatics@Foundation@Windows@@UColor@38@PEAPEAUIPropertyValue@78@@Z; Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IColorSourceEffect>::CreateColor<4>(Windows::Foundation::IPropertyValueStatics *,Windows::UI::Color,Windows::Foundation::IPropertyValue * *)
0x180016f11  mov     ebx, eax
0x180016f13  mov     [rsp+58h+var_18], 0
0x180016f1c  mov     rcx, [rsp+58h+var_38]
0x180016f21  test    rcx, rcx
0x180016f24  jz      short loc_180016F3C
0x180016f26  mov     [rsp+58h+var_38], 0
0x180016f2f  mov     rdx, [rcx]
0x180016f32  mov     rax, [rdx+10h]
0x180016f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f3b  nop
0x180016f3c  mov     eax, ebx
0x180016f3e  mov     rcx, [rsp+58h+var_10]
0x180016f43  xor     rcx, rsp; StackCookie
0x180016f46  call    __security_check_cookie
0x180016f4b  mov     rbx, [rsp+58h+arg_8]
0x180016f50  add     rsp, 50h
0x180016f54  pop     rdi
0x180016f55  retn
```
