# CreateBackdropEffectGraph(winrt::Windows::UI::Color const &,float,float)

- ea: `0x180010ecc`
- end: `0x180011559`
- name: `?CreateBackdropEffectGraph@@YA?AUIGraphicsEffect@Effects@Graphics@Windows@winrt@@AEBUColor@UI@45@MM@Z`
- size: `1677`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180010aac`
- `0x180010c58`

## callees

- `0x180010864`
- `0x180010ecc`
- `0x180012040`
- `0x18001254c`
- `0x1800125d0`
- `0x18001295c`
- `0x18001e988`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x180010f3f`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\microsoft.internal.ui.composition.effects.h`
- `0x1800110d8`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\microsoft.internal.ui.composition.effects.h`
- `0x180011175`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\microsoft.internal.ui.composition.effects.h`
- `0x180011216`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\microsoft.internal.ui.composition.effects.h`
- `0x18001129d`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\microsoft.internal.ui.composition.effects.h`
- `0x1800112e8`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\microsoft.internal.ui.composition.effects.h`
- `0x180011344`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\microsoft.internal.ui.composition.effects.h`
- `0x1800113c1`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\microsoft.internal.ui.composition.effects.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_QWORD *__fastcall CreateBackdropEffectGraph(_QWORD *a1, unsigned int *a2)
{
  _DWORD **v4; // rsi
  void (__fastcall ***v5)(_QWORD, __int64 *, _DWORD ***); // rbx
  int v6; // eax
  __int64 v7; // r15
  int v8; // eax
  _DWORD **v9; // rbx
  int v10; // eax
  void (__fastcall ***v11)(_QWORD, __int64 *, _DWORD ***); // r12
  int v12; // eax
  __int64 v13; // r14
  int v14; // eax
  _DWORD **v15; // rbx
  int v16; // eax
  _DWORD **v17; // rdi
  int v18; // eax
  void (__fastcall ***v19)(_QWORD, __int64 *, _DWORD ***); // rbx
  _DWORD **v20; // rdx
  int v21; // eax
  void (__fastcall ***v22)(_QWORD, __int64 *, _DWORD ***); // rdx
  void (__fastcall ***v23)(_QWORD, __int64 *, _DWORD ***); // rbx
  int v24; // eax
  _DWORD **v25; // rbx
  int v26; // eax
  void (__fastcall ***v27)(_QWORD, __int64 *, _DWORD ***); // rsi
  int v28; // eax
  void (__fastcall ***v29)(_QWORD, __int64 *, _DWORD ***); // rdx
  void (__fastcall ***v30)(_QWORD, __int64 *, _DWORD ***); // rsi
  int v31; // eax
  void (__fastcall ***v33)(_QWORD, __int64 *, _DWORD ***); // [rsp+28h] [rbp-89h] BYREF
  __int64 *v34; // [rsp+30h] [rbp-81h] BYREF
  __int64 v35; // [rsp+38h] [rbp-79h] BYREF
  __int64 v36; // [rsp+40h] [rbp-71h]
  const wchar_t *v37; // [rsp+48h] [rbp-69h]
  _DWORD **v38; // [rsp+50h] [rbp-61h] BYREF
  _DWORD **v39; // [rsp+58h] [rbp-59h] BYREF
  _DWORD **v40; // [rsp+60h] [rbp-51h] BYREF
  void (__fastcall ***v41)(_QWORD, __int64 *, _DWORD ***); // [rsp+68h] [rbp-49h] BYREF
  __int64 v42; // [rsp+70h] [rbp-41h] BYREF
  _QWORD v43[2]; // [rsp+78h] [rbp-39h] BYREF
  _DWORD *v44; // [rsp+88h] [rbp-29h] BYREF
  _DWORD v45[4]; // [rsp+90h] [rbp-21h] BYREF
  const wchar_t *v46; // [rsp+A0h] [rbp-11h]

  v4 = 0;
  CreateEffect<Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,winrt::Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect>(&v41);
  v35 = 0x900000001LL;
  v37 = L"TintColor";
  v34 = &v35;
  winrt::impl::consume_Windows_Graphics_Effects_IGraphicsEffect<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::Name(
    &v41,
    &v34);
  LODWORD(v34) = 693;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v5 = v41;
  v6 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64 *, _DWORD ***), _QWORD))(*v41)[7])(v41, *a2);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v34);
  CreateEffect<Microsoft::Internal::UI::Composition::Effects::OpacityEffect,winrt::Microsoft::Internal::UI::Composition::Effects::OpacityEffect>(v43);
  v35 = 0xB00000001LL;
  v37 = L"TintOpacity";
  v34 = &v35;
  winrt::impl::consume_Windows_Graphics_Effects_IGraphicsEffect<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::Name(
    v43,
    &v34);
  v7 = v43[0];
  LODWORD(v34) = 3295;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v43[0] + 56LL))(v43[0]);
  if ( v8 < 0 )
    winrt::throw_hresult((unsigned int)v8, &v34);
  v39 = 0;
  (**v5)(v5, winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>, &v39);
  v9 = v39;
  v40 = v39;
  LODWORD(v34) = 3329;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _DWORD **))(*(_QWORD *)v7 + 72LL))(v7, v39);
  if ( v10 < 0 )
    winrt::throw_hresult((unsigned int)v10, &v34);
  if ( v9 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v40);
  CreateEffect<Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,winrt::Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect>(&v39);
  v35 = 0xF00000001LL;
  v37 = L"LuminosityColor";
  v34 = &v35;
  winrt::impl::consume_Windows_Graphics_Effects_IGraphicsEffect<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::Name(
    &v39,
    &v34);
  v11 = (void (__fastcall ***)(_QWORD, __int64 *, _DWORD ***))v39;
  LODWORD(v34) = 693;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v12 = (*((__int64 (__fastcall **)(_DWORD **, _QWORD))*v39 + 7))(v39, *a2);
  if ( v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, &v34);
  CreateEffect<Microsoft::Internal::UI::Composition::Effects::OpacityEffect,winrt::Microsoft::Internal::UI::Composition::Effects::OpacityEffect>(&v42);
  v35 = 0x1100000001LL;
  v37 = L"LuminosityOpacity";
  v34 = &v35;
  winrt::impl::consume_Windows_Graphics_Effects_IGraphicsEffect<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::Name(
    &v42,
    &v34);
  v13 = v42;
  LODWORD(v34) = 3295;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 56LL))(v42);
  if ( v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v34);
  v38 = 0;
  (**v11)(v11, winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>, &v38);
  v15 = v38;
  v40 = v38;
  LODWORD(v34) = 3329;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, _DWORD **))(*(_QWORD *)v13 + 72LL))(v13, v38);
  if ( v16 < 0 )
    winrt::throw_hresult((unsigned int)v16, &v34);
  if ( v15 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v40);
  CreateEffect<Microsoft::Internal::UI::Composition::Effects::BlendEffect,winrt::Microsoft::Internal::UI::Composition::Effects::BlendEffect>(&v40);
  v17 = v40;
  LODWORD(v34) = 353;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v18 = (*((__int64 (__fastcall **)(_DWORD **, __int64))*v40 + 7))(v40, 22);
  if ( v18 < 0 )
    winrt::throw_hresult((unsigned int)v18, &v34);
  v45[0] = 1;
  v45[1] = 8;
  v46 = L"Backdrop";
  v44 = v45;
  v38 = &v44;
  ___call_factory_UCompositionEffectSourceParameter_Composition_UI_Windows_winrt__UICompositionEffectSourceParameterFactory_2345_V_lambda_20____0___012345_QEAA_AEBUhstring_param_5__Z__impl_winrt__YA_A_P__QEAV_lambda_20____0___0CompositionEffectSourceParameter_Composition_UI_Windows_1_QEAA_AEBUhstring_param_1__Z__Z(
    &v33,
    &v38);
  v19 = v33;
  if ( v33 )
  {
    v38 = 0;
    (**v33)(v33, winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>, &v38);
    v20 = v38;
    v4 = v38;
  }
  else
  {
    v20 = 0;
  }
  v38 = v20;
  LODWORD(v34) = 387;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v21 = (*((__int64 (__fastcall **)(_DWORD **))*v17 + 9))(v17);
  if ( v21 < 0 )
    winrt::throw_hresult((unsigned int)v21, &v34);
  if ( v4 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
  if ( v19 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v33);
  if ( v13 )
  {
    v33 = 0;
    (**(void (__fastcall ***)(__int64, __int64 *, _QWORD))v13)(
      v13,
      winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>,
      &v33);
    v22 = v33;
    v23 = v33;
  }
  else
  {
    v22 = 0;
    v23 = 0;
  }
  v33 = v22;
  LODWORD(v34) = 421;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v24 = (*((__int64 (__fastcall **)(_DWORD **))*v17 + 11))(v17);
  if ( v24 < 0 )
    winrt::throw_hresult((unsigned int)v24, &v34);
  if ( v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v33);
  CreateEffect<Microsoft::Internal::UI::Composition::Effects::BlendEffect,winrt::Microsoft::Internal::UI::Composition::Effects::BlendEffect>(&v38);
  v25 = v38;
  LODWORD(v34) = 353;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v26 = (*((__int64 (__fastcall **)(_DWORD **, __int64))*v38 + 7))(v38, 23);
  if ( v26 < 0 )
    winrt::throw_hresult((unsigned int)v26, &v34);
  v33 = 0;
  (*(void (__fastcall **)(_DWORD **, __int64 *, _QWORD))*v17)(
    v17,
    winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>,
    &v33);
  v27 = v33;
  LODWORD(v34) = 387;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v28 = (*((__int64 (__fastcall **)(_DWORD **, void (__fastcall ***)(_QWORD, __int64 *, _DWORD ***)))*v25 + 9))(
          v25,
          v33);
  if ( v28 < 0 )
    winrt::throw_hresult((unsigned int)v28, &v34);
  if ( v27 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v33);
  if ( v7 )
  {
    v33 = 0;
    (**(void (__fastcall ***)(__int64, __int64 *, _QWORD))v7)(
      v7,
      winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>,
      &v33);
    v29 = v33;
    v30 = v33;
  }
  else
  {
    v29 = 0;
    v30 = 0;
  }
  v33 = v29;
  LODWORD(v34) = 421;
  v35 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
  v36 = 0;
  v31 = (*((__int64 (__fastcall **)(_DWORD **))*v25 + 11))(v25);
  if ( v31 < 0 )
    winrt::throw_hresult((unsigned int)v31, &v34);
  if ( v30 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v33);
  v33 = 0;
  (*(void (__fastcall **)(_DWORD **, __int64 *, _QWORD))*v25)(
    v25,
    winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffect>,
    &v33);
  *a1 = v33;
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
  if ( v17 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v40);
  if ( v13 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
  if ( v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
  if ( v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v43);
  if ( v41 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
  return a1;
}

```

## disassembly

```asm
0x180010ecc  mov     rax, rsp
0x180010ecf  push    rbp
0x180010ed0  push    rbx
0x180010ed1  push    rsi
0x180010ed2  push    rdi
0x180010ed3  push    r12
0x180010ed5  push    r13
0x180010ed7  push    r14
0x180010ed9  push    r15
0x180010edb  lea     rbp, [rax-5Fh]
0x180010edf  sub     rsp, 0C8h
0x180010ee6  movaps  xmmword ptr [rax-58h], xmm6
0x180010eea  movaps  xmmword ptr [rax-68h], xmm7
0x180010eee  movaps  xmm7, xmm3
0x180010ef1  movaps  xmm6, xmm2
0x180010ef4  mov     rdi, rdx
0x180010ef7  mov     r13, rcx
0x180010efa  xor     esi, esi
0x180010efc  lea     rcx, [rbp+57h+var_A0]
0x180010f00  call    ??$CreateEffect@VColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ; CreateEffect<Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,winrt::Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect>(void)
0x180010f05  nop
0x180010f06  lea     r12d, [rsi+1]
0x180010f0a  mov     dword ptr [rbp+57h+var_D0], r12d
0x180010f0e  mov     dword ptr [rbp+57h+var_D0+4], 9
0x180010f15  lea     rax, aTintcolor; "TintColor"
0x180010f1c  mov     [rbp+57h+var_C0], rax
0x180010f20  lea     rax, [rbp+57h+var_D0]
0x180010f24  mov     [rsp+100h+var_D8], rax
0x180010f29  lea     rdx, [rsp+100h+var_D8]
0x180010f2e  lea     rcx, [rbp+57h+var_A0]
0x180010f32  call    ?Name@?$consume_Windows_Graphics_Effects_IGraphicsEffect@UCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Graphics_Effects_IGraphicsEffect<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::Name(winrt::param::hstring const &)
0x180010f37  mov     dword ptr [rsp+100h+var_D8], 2B5h
0x180010f3f  lea     r14, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180010f46  mov     [rbp+57h+var_D0], r14
0x180010f4a  mov     [rbp+57h+var_C8], rsi
0x180010f4e  mov     rbx, [rbp+57h+var_A0]
0x180010f52  mov     rax, [rbx]
0x180010f55  mov     edx, [rdi]
0x180010f57  mov     rcx, rbx
0x180010f5a  mov     rax, [rax+38h]
0x180010f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f63  test    eax, eax
0x180010f65  js      loc_1800114A1
0x180010f6b  lea     rcx, [rbp+57h+var_90]
0x180010f6f  call    ??$CreateEffect@VOpacityEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUOpacityEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ; CreateEffect<Microsoft::Internal::UI::Composition::Effects::OpacityEffect,winrt::Microsoft::Internal::UI::Composition::Effects::OpacityEffect>(void)
0x180010f74  nop
0x180010f75  mov     dword ptr [rbp+57h+var_D0], r12d
0x180010f79  mov     dword ptr [rbp+57h+var_D0+4], 0Bh
0x180010f80  lea     rax, aTintopacity; "TintOpacity"
0x180010f87  mov     [rbp+57h+var_C0], rax
0x180010f8b  lea     rax, [rbp+57h+var_D0]
0x180010f8f  mov     [rsp+100h+var_D8], rax
0x180010f94  lea     rdx, [rsp+100h+var_D8]
0x180010f99  lea     rcx, [rbp+57h+var_90]
0x180010f9d  call    ?Name@?$consume_Windows_Graphics_Effects_IGraphicsEffect@UCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Graphics_Effects_IGraphicsEffect<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::Name(winrt::param::hstring const &)
0x180010fa2  mov     r15, [rbp+57h+var_90]
0x180010fa6  mov     dword ptr [rsp+100h+var_D8], 0CDFh
0x180010fae  mov     [rbp+57h+var_D0], r14
0x180010fb2  mov     [rbp+57h+var_C8], rsi
0x180010fb6  mov     rax, [r15]
0x180010fb9  movaps  xmm1, xmm6
0x180010fbc  mov     rcx, r15
0x180010fbf  mov     rax, [rax+38h]
0x180010fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fc8  test    eax, eax
0x180010fca  js      loc_1800114AE
0x180010fd0  mov     [rbp+57h+var_B0], rsi
0x180010fd4  mov     rax, [rbx]
0x180010fd7  lea     r8, [rbp+57h+var_B0]
0x180010fdb  lea     rdx, ??$guid_v@UIGraphicsEffectSource@Effects@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>
0x180010fe2  mov     rcx, rbx
0x180010fe5  mov     rax, [rax]
0x180010fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fed  mov     rbx, [rbp+57h+var_B0]
0x180010ff1  mov     [rbp+57h+var_A8], rbx
0x180010ff5  mov     dword ptr [rsp+100h+var_D8], 0D01h
0x180010ffd  mov     [rbp+57h+var_D0], r14
0x180011001  mov     [rbp+57h+var_C8], rsi
0x180011005  mov     rax, [r15]
0x180011008  mov     rdx, rbx
0x18001100b  mov     rcx, r15
0x18001100e  mov     rax, [rax+48h]
0x180011012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011017  test    eax, eax
0x180011019  js      loc_1800114BB
0x18001101f  test    rbx, rbx
0x180011022  jz      short loc_18001102D
0x180011024  lea     rcx, [rbp+57h+var_A8]
0x180011028  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001102d  lea     rcx, [rbp+57h+var_B0]
0x180011031  call    ??$CreateEffect@VColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ; CreateEffect<Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,winrt::Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect>(void)
0x180011036  nop
0x180011037  mov     dword ptr [rbp+57h+var_D0], r12d
0x18001103b  mov     dword ptr [rbp+57h+var_D0+4], 0Fh
0x180011042  lea     rax, aLuminositycolo; "LuminosityColor"
0x180011049  mov     [rbp+57h+var_C0], rax
0x18001104d  lea     rax, [rbp+57h+var_D0]
0x180011051  mov     [rsp+100h+var_D8], rax
0x180011056  lea     rdx, [rsp+100h+var_D8]
0x18001105b  lea     rcx, [rbp+57h+var_B0]
0x18001105f  call    ?Name@?$consume_Windows_Graphics_Effects_IGraphicsEffect@UCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Graphics_Effects_IGraphicsEffect<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::Name(winrt::param::hstring const &)
0x180011064  mov     r12, [rbp+57h+var_B0]
0x180011068  mov     dword ptr [rsp+100h+var_D8], 2B5h
0x180011070  mov     [rbp+57h+var_D0], r14
0x180011074  mov     [rbp+57h+var_C8], rsi
0x180011078  mov     rax, [r12]
0x18001107c  mov     edx, [rdi]
0x18001107e  mov     rcx, r12
0x180011081  mov     rax, [rax+38h]
0x180011085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001108a  test    eax, eax
0x18001108c  js      loc_1800114C8
0x180011092  lea     rcx, [rbp+57h+var_98]
0x180011096  call    ??$CreateEffect@VOpacityEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUOpacityEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ; CreateEffect<Microsoft::Internal::UI::Composition::Effects::OpacityEffect,winrt::Microsoft::Internal::UI::Composition::Effects::OpacityEffect>(void)
0x18001109b  nop
0x18001109c  mov     dword ptr [rbp+57h+var_D0], 1
0x1800110a3  mov     dword ptr [rbp+57h+var_D0+4], 11h
0x1800110aa  lea     rax, aLuminosityopac; "LuminosityOpacity"
0x1800110b1  mov     [rbp+57h+var_C0], rax
0x1800110b5  lea     rax, [rbp+57h+var_D0]
0x1800110b9  mov     [rsp+100h+var_D8], rax
0x1800110be  lea     rdx, [rsp+100h+var_D8]
0x1800110c3  lea     rcx, [rbp+57h+var_98]
0x1800110c7  call    ?Name@?$consume_Windows_Graphics_Effects_IGraphicsEffect@UCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Graphics_Effects_IGraphicsEffect<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::Name(winrt::param::hstring const &)
0x1800110cc  mov     r14, [rbp+57h+var_98]
0x1800110d0  mov     dword ptr [rsp+100h+var_D8], 0CDFh
0x1800110d8  lea     rdi, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800110df  mov     [rbp+57h+var_D0], rdi
0x1800110e3  mov     [rbp+57h+var_C8], rsi
0x1800110e7  mov     rax, [r14]
0x1800110ea  movaps  xmm1, xmm7
0x1800110ed  mov     rcx, r14
0x1800110f0  mov     rax, [rax+38h]
0x1800110f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110f9  test    eax, eax
0x1800110fb  js      loc_1800114D5
0x180011101  mov     [rbp+57h+var_B8], rsi
0x180011105  mov     rax, [r12]
0x180011109  lea     r8, [rbp+57h+var_B8]
0x18001110d  lea     rdx, ??$guid_v@UIGraphicsEffectSource@Effects@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>
0x180011114  mov     rcx, r12
0x180011117  mov     rax, [rax]
0x18001111a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001111f  mov     rbx, [rbp+57h+var_B8]
0x180011123  mov     [rbp+57h+var_A8], rbx
0x180011127  mov     dword ptr [rsp+100h+var_D8], 0D01h
0x18001112f  mov     [rbp+57h+var_D0], rdi
0x180011133  mov     [rbp+57h+var_C8], rsi
0x180011137  mov     rax, [r14]
0x18001113a  mov     rdx, rbx
0x18001113d  mov     rcx, r14
0x180011140  mov     rax, [rax+48h]
0x180011144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011149  test    eax, eax
0x18001114b  js      loc_1800114E2
0x180011151  test    rbx, rbx
0x180011154  jz      short loc_18001115F
0x180011156  lea     rcx, [rbp+57h+var_A8]
0x18001115a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001115f  lea     rcx, [rbp+57h+var_A8]
0x180011163  call    ??$CreateEffect@VBlendEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUBlendEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ; CreateEffect<Microsoft::Internal::UI::Composition::Effects::BlendEffect,winrt::Microsoft::Internal::UI::Composition::Effects::BlendEffect>(void)
0x180011168  nop
0x180011169  mov     rdi, [rbp+57h+var_A8]
0x18001116d  mov     dword ptr [rsp+100h+var_D8], 161h
0x180011175  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001117c  mov     [rbp+57h+var_D0], rax
0x180011180  mov     [rbp+57h+var_C8], rsi
0x180011184  mov     rax, [rdi]
0x180011187  mov     edx, 16h
0x18001118c  mov     rcx, rdi
0x18001118f  mov     rax, [rax+38h]
0x180011193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011198  test    eax, eax
0x18001119a  js      loc_1800114EF
0x1800111a0  mov     [rbp+57h+var_78], 1
0x1800111a7  mov     [rbp+57h+var_74], 8
0x1800111ae  lea     rax, aBackdrop; "Backdrop"
0x1800111b5  mov     [rbp+57h+var_68], rax
0x1800111b9  lea     rax, [rbp+57h+var_78]
0x1800111bd  mov     [rbp+57h+var_80], rax
0x1800111c1  lea     rax, [rbp+57h+var_80]
0x1800111c5  mov     [rbp+57h+var_B8], rax
0x1800111c9  lea     rdx, [rbp+57h+var_B8]
0x1800111cd  lea     rcx, [rsp+100h+var_E0]
0x1800111d2  call    ??$call_factory@UCompositionEffectSourceParameter@Composition@UI@Windows@winrt@@UICompositionEffectSourceParameterFactory@2345@V_lambda_20__@?0???012345@QEAA@AEBUhstring@param@5@@Z@@impl@winrt@@YA?A_P$$QEAV_lambda_20__@?0???0CompositionEffectSourceParameter@Composition@UI@Windows@1@QEAA@AEBUhstring@param@1@@Z@@Z
0x1800111d7  nop
0x1800111d8  mov     rbx, [rsp+100h+var_E0]
0x1800111dd  test    rbx, rbx
0x1800111e0  jz      loc_1800114FC
0x1800111e6  mov     [rbp+57h+var_B8], rsi
0x1800111ea  mov     rax, [rbx]
0x1800111ed  lea     r8, [rbp+57h+var_B8]
0x1800111f1  lea     rdx, ??$guid_v@UIGraphicsEffectSource@Effects@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>
0x1800111f8  mov     rcx, rbx
0x1800111fb  mov     rax, [rax]
0x1800111fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011203  mov     rdx, [rbp+57h+var_B8]
0x180011207  mov     rsi, rdx
0x18001120a  mov     [rbp+57h+var_B8], rdx
0x18001120e  mov     dword ptr [rsp+100h+var_D8], 183h
0x180011216  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001121d  mov     [rbp+57h+var_D0], rax
0x180011221  mov     [rbp+57h+var_C8], 0
0x180011229  mov     rax, [rdi]
0x18001122c  mov     rcx, rdi
0x18001122f  mov     rax, [rax+48h]
0x180011233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011238  test    eax, eax
0x18001123a  js      loc_180011504
0x180011240  test    rsi, rsi
0x180011243  jz      short loc_18001124F
0x180011245  lea     rcx, [rbp+57h+var_B8]
0x180011249  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001124e  nop
0x18001124f  xor     esi, esi
0x180011251  test    rbx, rbx
0x180011254  jz      short loc_180011260
0x180011256  lea     rcx, [rsp+100h+var_E0]
0x18001125b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011260  test    r14, r14
0x180011263  jz      loc_180011511
0x180011269  mov     [rsp+100h+var_E0], rsi
0x18001126e  mov     rax, [r14]
0x180011271  lea     r8, [rsp+100h+var_E0]
0x180011276  lea     rdx, ??$guid_v@UIGraphicsEffectSource@Effects@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>
0x18001127d  mov     rcx, r14
0x180011280  mov     rax, [rax]
0x180011283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011288  mov     rdx, [rsp+100h+var_E0]
0x18001128d  mov     rbx, rdx
0x180011290  mov     [rsp+100h+var_E0], rdx
0x180011295  mov     dword ptr [rsp+100h+var_D8], 1A5h
0x18001129d  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800112a4  mov     [rbp+57h+var_D0], rax
0x1800112a8  mov     [rbp+57h+var_C8], rsi
0x1800112ac  mov     rax, [rdi]
0x1800112af  mov     rcx, rdi
0x1800112b2  mov     rax, [rax+58h]
0x1800112b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112bb  test    eax, eax
0x1800112bd  js      loc_18001151C
0x1800112c3  test    rbx, rbx
0x1800112c6  jz      short loc_1800112D2
0x1800112c8  lea     rcx, [rsp+100h+var_E0]
0x1800112cd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800112d2  lea     rcx, [rbp+57h+var_B8]
0x1800112d6  call    ??$CreateEffect@VBlendEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUBlendEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ; CreateEffect<Microsoft::Internal::UI::Composition::Effects::BlendEffect,winrt::Microsoft::Internal::UI::Composition::Effects::BlendEffect>(void)
0x1800112db  nop
0x1800112dc  mov     rbx, [rbp+57h+var_B8]
0x1800112e0  mov     dword ptr [rsp+100h+var_D8], 161h
0x1800112e8  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800112ef  mov     [rbp+57h+var_D0], rax
0x1800112f3  mov     [rbp+57h+var_C8], rsi
0x1800112f7  mov     rax, [rbx]
0x1800112fa  mov     edx, 17h
0x1800112ff  mov     rcx, rbx
0x180011302  mov     rax, [rax+38h]
0x180011306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001130b  test    eax, eax
0x18001130d  js      loc_180011529
0x180011313  mov     [rsp+100h+var_E0], rsi
0x180011318  mov     rax, [rdi]
0x18001131b  lea     r8, [rsp+100h+var_E0]
0x180011320  lea     rdx, ??$guid_v@UIGraphicsEffectSource@Effects@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>
0x180011327  mov     rcx, rdi
0x18001132a  mov     rax, [rax]
0x18001132d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011332  mov     rsi, [rsp+100h+var_E0]
0x180011337  mov     [rsp+100h+var_E0], rsi
0x18001133c  mov     dword ptr [rsp+100h+var_D8], 183h
0x180011344  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001134b  mov     [rbp+57h+var_D0], rax
0x18001134f  mov     [rbp+57h+var_C8], 0
0x180011357  mov     rax, [rbx]
0x18001135a  mov     rdx, rsi
0x18001135d  mov     rcx, rbx
0x180011360  mov     rax, [rax+48h]
0x180011364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011369  test    eax, eax
0x18001136b  js      loc_180011536
0x180011371  test    rsi, rsi
0x180011374  jz      short loc_180011380
0x180011376  lea     rcx, [rsp+100h+var_E0]
0x18001137b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011380  test    r15, r15
0x180011383  jz      loc_180011543
0x180011389  mov     [rsp+100h+var_E0], 0
0x180011392  mov     rax, [r15]
0x180011395  lea     r8, [rsp+100h+var_E0]
0x18001139a  lea     rdx, ??$guid_v@UIGraphicsEffectSource@Effects@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>
0x1800113a1  mov     rcx, r15
0x1800113a4  mov     rax, [rax]
0x1800113a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ac  mov     rdx, [rsp+100h+var_E0]
0x1800113b1  mov     rsi, rdx
0x1800113b4  mov     [rsp+100h+var_E0], rdx
0x1800113b9  mov     dword ptr [rsp+100h+var_D8], 1A5h
0x1800113c1  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800113c8  mov     [rbp+57h+var_D0], rax
0x1800113cc  mov     [rbp+57h+var_C8], 0
  ... truncated ...
```
