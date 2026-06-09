# Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IOpacityEffect>::UsePropertyFactory<`Microsoft::Internal::UI::Composition::Effects::OpacityEffect::GetProperty(uint,Windows::Foundation::IPropertyValue * *)'::`2'::_lambda_1_>(`Microsoft::Internal::UI::Composition::Effects::OpacityEffect::GetProperty(uint,Windows::Foundation::IPropertyValue * *)'::`2'::_lambda_1_ const &)

- ea: `0x18001e2cc`
- end: `0x18001e3af`
- name: `??$UsePropertyFactory@V_lambda_1_@?1??GetProperty@OpacityEffect@Effects@Composition@UI@Internal@Microsoft@@UEAAJIPEAPEAUIPropertyValue@Foundation@Windows@@@Z@@?$EffectBase@UIOpacityEffect@Effects@Composition@UI@Internal@Microsoft@@@Effects@Composition@UI@Internal@Microsoft@@KAJAEBV_lambda_1_@?1??GetProperty@OpacityEffect@12345@UEAAJIPEAPEAUIPropertyValue@Foundation@Windows@@@Z@@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b710`

## callees

- `0x180017290`
- `0x18001e2cc`
- `0x180021060`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e324`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e324`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e30e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e30e`

## pseudocode

```c
__int64 __fastcall ___UsePropertyFactory_V_lambda_1___1__GetProperty_OpacityEffect_Effects_Composition_UI_Internal_Microsoft__UEAAJIPEAPEAUIPropertyValue_Foundation_Windows___Z____EffectBase_UIOpacityEffect_Effects_Composition_UI_Internal_Microsoft___Effects_Composition_UI_Internal_Microsoft__KAJAEBV_lambda_1___1__GetProperty_OpacityEffect_12345_UEAAJIPEAPEAUIPropertyValue_Foundation_Windows___Z__Z(
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
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 112LL))(
             v6,
             *(_QWORD *)(a1 + 8),
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
0x18001e2cc  mov     r11, rsp
0x18001e2cf  mov     [r11+10h], rbx
0x18001e2d3  push    rdi
0x18001e2d4  sub     rsp, 50h
0x18001e2d8  mov     rax, cs:__security_cookie
0x18001e2df  xor     rax, rsp
0x18001e2e2  mov     [rsp+58h+var_10], rax
0x18001e2e7  mov     rdi, rcx
0x18001e2ea  mov     qword ptr [r11-38h], 0
0x18001e2f2  mov     qword ptr [r11-18h], 0
0x18001e2fa  lea     r9, [r11-18h]; string
0x18001e2fe  lea     r8, [r11-30h]; hstringHeader
0x18001e302  mov     edx, 20h ; ' '; length
0x18001e307  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18001e30e  call    cs:__imp_WindowsCreateStringReference
0x18001e314  test    eax, eax
0x18001e316  jns     short loc_18001E32B
0x18001e318  xor     r9d, r9d; lpArguments
0x18001e31b  xor     r8d, r8d; nNumberOfArguments
0x18001e31e  lea     edx, [r9+1]; dwExceptionFlags
0x18001e322  mov     ecx, eax; dwExceptionCode
0x18001e324  call    cs:__imp_RaiseException
0x18001e32a  nop
0x18001e32b  lea     rdx, [rsp+58h+var_38]
0x18001e330  mov     rcx, [rsp+58h+var_18]
0x18001e335  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x18001e33a  mov     ebx, eax
0x18001e33c  test    eax, eax
0x18001e33e  js      short loc_18001E36C
0x18001e340  cmp     dword ptr [rdi], 0
0x18001e343  jz      short loc_18001E34C
0x18001e345  mov     ebx, 80070057h
0x18001e34a  jmp     short loc_18001E36C
0x18001e34c  mov     rcx, [rsp+58h+var_38]
0x18001e351  mov     rax, [rcx]
0x18001e354  mov     rdx, [rdi+8]
0x18001e358  mov     r8, [rdi+10h]
0x18001e35c  movss   xmm1, dword ptr [rdx+48h]
0x18001e361  mov     rax, [rax+70h]
0x18001e365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e36a  mov     ebx, eax
0x18001e36c  mov     [rsp+58h+var_18], 0
0x18001e375  mov     rcx, [rsp+58h+var_38]
0x18001e37a  test    rcx, rcx
0x18001e37d  jz      short loc_18001E395
0x18001e37f  mov     [rsp+58h+var_38], 0
0x18001e388  mov     rdx, [rcx]
0x18001e38b  mov     rax, [rdx+10h]
0x18001e38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e394  nop
0x18001e395  mov     eax, ebx
0x18001e397  mov     rcx, [rsp+58h+var_10]
0x18001e39c  xor     rcx, rsp; StackCookie
0x18001e39f  call    __security_check_cookie
0x18001e3a4  mov     rbx, [rsp+58h+arg_8]
0x18001e3a9  add     rsp, 50h
0x18001e3ad  pop     rdi
0x18001e3ae  retn
```
