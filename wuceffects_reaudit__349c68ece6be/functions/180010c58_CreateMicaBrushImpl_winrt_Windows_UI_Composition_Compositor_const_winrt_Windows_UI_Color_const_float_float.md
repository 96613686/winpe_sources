# CreateMicaBrushImpl(winrt::Windows::UI::Composition::Compositor const &,winrt::Windows::UI::Color const &,float,float)

- ea: `0x180010c58`
- end: `0x180010ec4`
- name: `?CreateMicaBrushImpl@@YA?AUCompositionBrush@Composition@UI@Windows@winrt@@AEBUCompositor@2345@AEBUColor@345@MM@Z`
- size: `620`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180010930`

## callees

- `0x1800101b4`
- `0x180010c58`
- `0x180010ecc`
- `0x180012040`
- `0x1800120cc`
- `0x1800123fc`
- `0x18001246c`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x180010d1a`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`
- `0x180010e48`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall CreateMicaBrushImpl(_QWORD *a1, __int64 a2, unsigned int *a3)
{
  void (__fastcall ***v6)(_QWORD, __int64 *, _QWORD *); // rdi
  __int64 v7; // rsi
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 *); // rbx
  int v9; // eax
  __int64 *v10; // rcx
  void (__fastcall ***v12)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v13; // r8
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // [rsp+20h] [rbp-41h] BYREF
  __int64 v17; // [rsp+28h] [rbp-39h] BYREF
  void (__fastcall ***v18)(_QWORD, __int64 *, __int64 *); // [rsp+30h] [rbp-31h] BYREF
  __int64 v19; // [rsp+38h] [rbp-29h] BYREF
  __int64 v20; // [rsp+40h] [rbp-21h] BYREF
  void (__fastcall ***v21)(_QWORD, __int64 *, __int64 *); // [rsp+48h] [rbp-19h] BYREF
  int *v22; // [rsp+50h] [rbp-11h]
  int v23; // [rsp+58h] [rbp-9h] BYREF
  int v24; // [rsp+5Ch] [rbp-5h]
  const wchar_t *v25; // [rsp+68h] [rbp+7h]
  int v26; // [rsp+70h] [rbp+Fh] BYREF
  const char *v27; // [rsp+78h] [rbp+17h]
  __int64 v28; // [rsp+80h] [rbp+1Fh]

  CreateBackdropEffectGraph(&v20, a3);
  winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateEffectFactory(
    a2,
    &v19,
    &v20);
  winrt::impl::consume_Windows_UI_Composition_ICompositionEffectFactory<winrt::Windows::UI::Composition::ICompositionEffectFactory>::CreateBrush(
    &v19,
    &v18);
  winrt::impl::consume_Windows_UI_Composition_ICompositorWithBlurredWallpaperBackdropBrush<winrt::Windows::UI::Composition::Compositor>::TryCreateBlurredWallpaperBackdropBrush(
    a2,
    &v21);
  v6 = v21;
  if ( v21 )
  {
    v16 = 0;
    (**v21)(v21, winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>, &v16);
    v7 = v16;
    v23 = 1;
    v24 = 8;
    v25 = L"Backdrop";
    v22 = &v23;
    v8 = v18;
    v26 = 1972;
    v27 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
    v28 = 0;
    v9 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), int *))(*v18)[7])(v18, &v23);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v26);
    if ( v7 )
    {
      v10 = &v16;
LABEL_5:
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
    }
  }
  else
  {
    v12 = *(void (__fastcall ****)(_QWORD, __int64 *, __int64 *))winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateColorBrush(
                                                                   a2,
                                                                   &v17,
                                                                   a3);
    if ( v12 )
    {
      v16 = 0;
      (**v12)(v12, winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>, &v16);
      v13 = v16;
      v14 = v16;
    }
    else
    {
      v13 = 0;
      v14 = 0;
    }
    v16 = v13;
    v23 = 1;
    v24 = 8;
    v25 = L"Backdrop";
    v22 = &v23;
    v8 = v18;
    v26 = 1972;
    v27 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
    v28 = 0;
    v15 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), int *))(*v18)[7])(v18, &v23);
    if ( v15 < 0 )
      winrt::throw_hresult((unsigned int)v15, &v26);
    if ( v14 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
    if ( v17 )
    {
      v10 = &v17;
      goto LABEL_5;
    }
  }
  if ( v8 )
  {
    v17 = 0;
    (**v8)(v8, winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>, &v17);
    *a1 = v17;
  }
  else
  {
    *a1 = 0;
  }
  if ( v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
  if ( v8 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
  if ( v19 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
  if ( v20 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
  return a1;
}

```

## disassembly

```asm
0x180010c58  push    rbp
0x180010c5a  push    rbx
0x180010c5b  push    rsi
0x180010c5c  push    rdi
0x180010c5d  push    r14
0x180010c5f  lea     rbp, [rsp-2Fh]
0x180010c64  sub     rsp, 90h
0x180010c6b  movaps  xmm2, xmm3
0x180010c6e  mov     rsi, r8
0x180010c71  mov     rbx, rdx
0x180010c74  mov     r14, rcx
0x180010c77  movss   xmm3, [rbp+4Fh+arg_20]
0x180010c7c  mov     rdx, r8
0x180010c7f  lea     rcx, [rbp+4Fh+var_70]
0x180010c83  call    ?CreateBackdropEffectGraph@@YA?AUIGraphicsEffect@Effects@Graphics@Windows@winrt@@AEBUColor@UI@45@MM@Z; CreateBackdropEffectGraph(winrt::Windows::UI::Color const &,float,float)
0x180010c88  nop
0x180010c89  lea     r8, [rbp+4Fh+var_70]
0x180010c8d  lea     rdx, [rbp+4Fh+var_78]
0x180010c91  mov     rcx, rbx
0x180010c94  call    ?CreateEffectFactory@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUIGraphicsEffect@Effects@Graphics@Windows@3@@Z; winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateEffectFactory(winrt::Windows::Graphics::Effects::IGraphicsEffect const &)
0x180010c99  nop
0x180010c9a  lea     rdx, [rbp+4Fh+var_80]
0x180010c9e  lea     rcx, [rbp+4Fh+var_78]
0x180010ca2  call    ?CreateBrush@?$consume_Windows_UI_Composition_ICompositionEffectFactory@UICompositionEffectFactory@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ICompositionEffectFactory<winrt::Windows::UI::Composition::ICompositionEffectFactory>::CreateBrush(void)
0x180010ca7  nop
0x180010ca8  lea     rdx, [rbp+4Fh+var_68]
0x180010cac  mov     rcx, rbx
0x180010caf  call    ?TryCreateBlurredWallpaperBackdropBrush@?$consume_Windows_UI_Composition_ICompositorWithBlurredWallpaperBackdropBrush@UCompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ICompositorWithBlurredWallpaperBackdropBrush<winrt::Windows::UI::Composition::Compositor>::TryCreateBlurredWallpaperBackdropBrush(void)
0x180010cb4  nop
0x180010cb5  mov     rdi, [rbp+4Fh+var_68]
0x180010cb9  test    rdi, rdi
0x180010cbc  jz      loc_180010DD7
0x180010cc2  mov     [rbp+4Fh+var_90], 0
0x180010cca  mov     rax, [rdi]
0x180010ccd  lea     r8, [rbp+4Fh+var_90]
0x180010cd1  lea     rdx, ??$guid_v@UICompositionBrush@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>
0x180010cd8  mov     rcx, rdi
0x180010cdb  mov     rax, [rax]
0x180010cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ce3  mov     r8, [rbp+4Fh+var_90]
0x180010ce7  mov     [rbp+4Fh+var_90], r8
0x180010ceb  mov     rsi, r8
0x180010cee  mov     [rbp+4Fh+var_58], 1
0x180010cf5  mov     [rbp+4Fh+var_54], 8
0x180010cfc  lea     rax, aBackdrop; "Backdrop"
0x180010d03  mov     [rbp+4Fh+var_48], rax
0x180010d07  lea     rax, [rbp+4Fh+var_58]
0x180010d0b  mov     [rbp+4Fh+var_60], rax
0x180010d0f  mov     rbx, [rbp+4Fh+var_80]
0x180010d13  mov     [rbp+4Fh+var_40], 7B4h
0x180010d1a  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180010d21  mov     [rbp+4Fh+var_38], rax
0x180010d25  mov     [rbp+4Fh+var_30], 0
0x180010d2d  mov     rax, [rbx]
0x180010d30  lea     rdx, [rbp+4Fh+var_58]
0x180010d34  mov     rcx, rbx
0x180010d37  mov     rax, [rax+38h]
0x180010d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d40  test    eax, eax
0x180010d42  js      loc_180010E95
0x180010d48  test    rsi, rsi
0x180010d4b  jz      short loc_180010D56
0x180010d4d  lea     rcx, [rbp+4Fh+var_90]
0x180010d51  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010d56  test    rbx, rbx
0x180010d59  jz      loc_180010EB7
0x180010d5f  mov     [rbp+4Fh+var_88], 0
0x180010d67  mov     rax, [rbx]
0x180010d6a  lea     r8, [rbp+4Fh+var_88]
0x180010d6e  lea     rdx, ??$guid_v@UICompositionBrush@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>
0x180010d75  mov     rcx, rbx
0x180010d78  mov     rax, [rax]
0x180010d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d80  mov     rax, [rbp+4Fh+var_88]
0x180010d84  mov     [r14], rax
0x180010d87  test    rdi, rdi
0x180010d8a  jz      short loc_180010D96
0x180010d8c  lea     rcx, [rbp+4Fh+var_68]
0x180010d90  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010d95  nop
0x180010d96  test    rbx, rbx
0x180010d99  jz      short loc_180010DA5
0x180010d9b  lea     rcx, [rbp+4Fh+var_80]
0x180010d9f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010da4  nop
0x180010da5  cmp     [rbp+4Fh+var_78], 0
0x180010daa  jz      short loc_180010DB6
0x180010dac  lea     rcx, [rbp+4Fh+var_78]
0x180010db0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010db5  nop
0x180010db6  cmp     [rbp+4Fh+var_70], 0
0x180010dbb  jz      short loc_180010DC6
0x180010dbd  lea     rcx, [rbp+4Fh+var_70]
0x180010dc1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010dc6  mov     rax, r14
0x180010dc9  add     rsp, 90h
0x180010dd0  pop     r14
0x180010dd2  pop     rdi
0x180010dd3  pop     rsi
0x180010dd4  pop     rbx
0x180010dd5  pop     rbp
0x180010dd6  retn
0x180010dd7  mov     r8, rsi
0x180010dda  lea     rdx, [rbp+4Fh+var_88]
0x180010dde  mov     rcx, rbx
0x180010de1  call    ?CreateColorBrush@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUColor@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateColorBrush(winrt::Windows::UI::Color const &)
0x180010de6  nop
0x180010de7  mov     rcx, [rax]
0x180010dea  test    rcx, rcx
0x180010ded  jz      loc_180010EA1
0x180010df3  mov     [rbp+4Fh+var_90], 0
0x180010dfb  mov     rax, [rcx]
0x180010dfe  lea     r8, [rbp+4Fh+var_90]
0x180010e02  lea     rdx, ??$guid_v@UICompositionBrush@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>
0x180010e09  mov     rax, [rax]
0x180010e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e11  mov     r8, [rbp+4Fh+var_90]
0x180010e15  mov     rsi, r8
0x180010e18  mov     [rbp+4Fh+var_90], r8
0x180010e1c  mov     [rbp+4Fh+var_58], 1
0x180010e23  mov     [rbp+4Fh+var_54], 8
0x180010e2a  lea     rax, aBackdrop; "Backdrop"
0x180010e31  mov     [rbp+4Fh+var_48], rax
0x180010e35  lea     rax, [rbp+4Fh+var_58]
0x180010e39  mov     [rbp+4Fh+var_60], rax
0x180010e3d  mov     rbx, [rbp+4Fh+var_80]
0x180010e41  mov     [rbp+4Fh+var_40], 7B4h
0x180010e48  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180010e4f  mov     [rbp+4Fh+var_38], rax
0x180010e53  mov     [rbp+4Fh+var_30], 0
0x180010e5b  mov     rax, [rbx]
0x180010e5e  lea     rdx, [rbp+4Fh+var_58]
0x180010e62  mov     rcx, rbx
0x180010e65  mov     rax, [rax+38h]
0x180010e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e6e  test    eax, eax
0x180010e70  js      short loc_180010EAB
0x180010e72  test    rsi, rsi
0x180010e75  jz      short loc_180010E81
0x180010e77  lea     rcx, [rbp+4Fh+var_90]
0x180010e7b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010e80  nop
0x180010e81  cmp     [rbp+4Fh+var_88], 0
0x180010e86  jz      loc_180010D56
0x180010e8c  lea     rcx, [rbp+4Fh+var_88]
0x180010e90  jmp     loc_180010D51
0x180010e95  lea     rdx, [rbp+4Fh+var_40]
0x180010e99  mov     ecx, eax
0x180010e9b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180010ea1  xor     r8d, r8d
0x180010ea4  xor     esi, esi
0x180010ea6  jmp     loc_180010E18
0x180010eab  lea     rdx, [rbp+4Fh+var_40]
0x180010eaf  mov     ecx, eax
0x180010eb1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180010eb7  mov     qword ptr [r14], 0
0x180010ebe  jmp     loc_180010D87
```
