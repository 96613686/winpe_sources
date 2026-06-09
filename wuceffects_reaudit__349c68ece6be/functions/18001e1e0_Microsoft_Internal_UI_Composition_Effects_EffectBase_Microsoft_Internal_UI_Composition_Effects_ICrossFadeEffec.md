# Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::ICrossFadeEffect>::UsePropertyFactory<`Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect::GetProperty(uint,Windows::Foundation::IPropertyValue * *)'::`2'::_lambda_1_>(`Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect::GetProperty(uint,Windows::Foundation::IPropertyValue * *)'::`2'::_lambda_1_ const &)

- ea: `0x18001e1e0`
- end: `0x18001e2c3`
- name: `??$UsePropertyFactory@V_lambda_1_@?1??GetProperty@CrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@@UEAAJIPEAPEAUIPropertyValue@Foundation@Windows@@@Z@@?$EffectBase@UICrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@@@Effects@Composition@UI@Internal@Microsoft@@KAJAEBV_lambda_1_@?1??GetProperty@CrossFadeEffect@12345@UEAAJIPEAPEAUIPropertyValue@Foundation@Windows@@@Z@@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001c2c0`

## callees

- `0x180017290`
- `0x18001e1e0`
- `0x180021060`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e238`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e222`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e222`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ___UsePropertyFactory_V_lambda_1___1__GetProperty_CrossFadeEffect_Effects_Composition_UI_Internal_Microsoft__UEAAJIPEAPEAUIPropertyValue_Foundation_Windows___Z____EffectBase_UICrossFadeEffect_Effects_Composition_UI_Internal_Microsoft___Effects_Composition_UI_Internal_Microsoft__KAJAEBV_lambda_1___1__GetProperty_CrossFadeEffect_12345_UEAAJIPEAPEAUIPropertyValue_Foundation_Windows___Z__Z(
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
0x18001e1e0  mov     r11, rsp
0x18001e1e3  mov     [r11+10h], rbx
0x18001e1e7  push    rdi
0x18001e1e8  sub     rsp, 50h
0x18001e1ec  mov     rax, cs:__security_cookie
0x18001e1f3  xor     rax, rsp
0x18001e1f6  mov     [rsp+58h+var_10], rax
0x18001e1fb  mov     rdi, rcx
0x18001e1fe  mov     qword ptr [r11-38h], 0
0x18001e206  mov     qword ptr [r11-18h], 0
0x18001e20e  lea     r9, [r11-18h]; string
0x18001e212  lea     r8, [r11-30h]; hstringHeader
0x18001e216  mov     edx, 20h ; ' '; length
0x18001e21b  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18001e222  call    cs:__imp_WindowsCreateStringReference
0x18001e228  test    eax, eax
0x18001e22a  jns     short loc_18001E23F
0x18001e22c  xor     r9d, r9d; lpArguments
0x18001e22f  xor     r8d, r8d; nNumberOfArguments
0x18001e232  lea     edx, [r9+1]; dwExceptionFlags
0x18001e236  mov     ecx, eax; dwExceptionCode
0x18001e238  call    cs:__imp_RaiseException
0x18001e23e  nop
0x18001e23f  lea     rdx, [rsp+58h+var_38]
0x18001e244  mov     rcx, [rsp+58h+var_18]
0x18001e249  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x18001e24e  mov     ebx, eax
0x18001e250  test    eax, eax
0x18001e252  js      short loc_18001E280
0x18001e254  cmp     dword ptr [rdi], 0
0x18001e257  jz      short loc_18001E260
0x18001e259  mov     ebx, 80070057h
0x18001e25e  jmp     short loc_18001E280
0x18001e260  mov     rcx, [rsp+58h+var_38]
0x18001e265  mov     rax, [rcx]
0x18001e268  mov     rdx, [rdi+8]
0x18001e26c  mov     r8, [rdi+10h]
0x18001e270  movss   xmm1, dword ptr [rdx+50h]
0x18001e275  mov     rax, [rax+70h]
0x18001e279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e27e  mov     ebx, eax
0x18001e280  mov     [rsp+58h+var_18], 0
0x18001e289  mov     rcx, [rsp+58h+var_38]
0x18001e28e  test    rcx, rcx
0x18001e291  jz      short loc_18001E2A9
0x18001e293  mov     [rsp+58h+var_38], 0
0x18001e29c  mov     rdx, [rcx]
0x18001e29f  mov     rax, [rdx+10h]
0x18001e2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2a8  nop
0x18001e2a9  mov     eax, ebx
0x18001e2ab  mov     rcx, [rsp+58h+var_10]
0x18001e2b0  xor     rcx, rsp; StackCookie
0x18001e2b3  call    __security_check_cookie
0x18001e2b8  mov     rbx, [rsp+58h+arg_8]
0x18001e2bd  add     rsp, 50h
0x18001e2c1  pop     rdi
0x18001e2c2  retn
```
