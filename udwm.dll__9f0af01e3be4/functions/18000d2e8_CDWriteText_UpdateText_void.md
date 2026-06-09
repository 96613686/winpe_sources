# CDWriteText::UpdateText(void)

- ea: `0x18000d2e8`
- end: `0x18000def2`
- name: `?UpdateText@CDWriteText@@AEAAJXZ`
- size: `3082`
- prototype: `__int64 __fastcall(CDWriteText *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006cc90`

## callees

- `0x1800029dc`
- `0x1800029e8`
- `0x180008d68`
- `0x18000c458`
- `0x18000d2e8`
- `0x18000f470`
- `0x180052df0`
- `0x180081a68`
- `0x180095130`
- `0x180095abc`
- `0x180095ae0`
- `0x1800b8d08`
- `0x1800ea010`

## string_xrefs

- `0x18000d864`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x18000da1a`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x18000daeb`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x18000dbb5`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x18000dbea`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x18000dc92`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x18000dd57`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x18000dd95`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x18000dddb`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x18000de1c`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x18000debb`: `clientcore\windows\dwm\udwm\dwritetext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CDWriteText::UpdateText(CDWriteText *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  int TextLayout; // eax
  int v5; // eax
  float v6; // xmm9_4
  float v7; // xmm10_4
  __m128 v8; // xmm0
  __m128 v9; // xmm6
  __m128 v10; // xmm0
  __m128 v11; // xmm8
  CGraphicsDeviceManager *v12; // rsi
  int v13; // eax
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 (__fastcall **v19)(__int64, GUID *, __int64); // rdx
  __int64 v20; // r9
  _QWORD *v21; // rbx
  __int64 (__fastcall *v22)(_QWORD *, _QWORD, GUID *, __int64 *); // rsi
  __int64 v23; // rcx
  CGraphicsDeviceManager *v24; // rbx
  int v25; // eax
  int v26; // esi
  __m128 v27; // xmm1
  __m128 v28; // xmm0
  CGraphicsDeviceManager *v29; // rbx
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 (__fastcall **v32)(__int64, GUID *, __int64); // rdx
  __int64 v33; // r9
  int v34; // eax
  _QWORD *v35; // rcx
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  int v39; // eax
  __int64 (*v40)(void); // rax
  __int64 v41; // r8
  __int64 v42; // rax
  __int64 (__fastcall **v43)(__int64, GUID *, __int64); // rdx
  __int64 v44; // r9
  int v45; // eax
  __int64 v46; // rbx
  __m128 v47; // xmm0
  int v48; // eax
  _QWORD *v50; // rcx
  int v51; // eax
  unsigned __int64 v52; // r9
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rdx
  CGraphicsDeviceManager *v56; // rbx
  __int64 v57; // rdx
  int v58; // [rsp+28h] [rbp-E0h]
  int *v59; // [rsp+28h] [rbp-E0h]
  _QWORD *v60; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v61; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD *v62; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD *v63; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v64; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v65; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v66; // [rsp+68h] [rbp-A0h] BYREF
  CGraphicsDeviceManager *v67; // [rsp+70h] [rbp-98h] BYREF
  int v68[2]; // [rsp+78h] [rbp-90h] BYREF
  CGraphicsDeviceManager **v69; // [rsp+80h] [rbp-88h]
  _QWORD **v70; // [rsp+88h] [rbp-80h]
  char v71; // [rsp+90h] [rbp-78h]
  __int128 v72; // [rsp+98h] [rbp-70h] BYREF
  __int128 v73; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v74; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v75; // [rsp+C8h] [rbp-40h]
  int v76; // [rsp+D8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v62 = 0;
  v2 = CSpriteVisual::GetBrush<Windows::UI::Composition::ICompositionSurfaceBrush>(this, &v62);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)v2,
      v58);
    if ( v62 )
      (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
    return v3;
  }
  if ( !*((_DWORD *)this + 16) )
  {
    v50 = v62;
    if ( !v62 )
      goto LABEL_55;
    TextLayout = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v62 + 104LL))(v62, 0);
    v3 = TextLayout;
    if ( TextLayout >= 0 )
    {
      v50 = v62;
      goto LABEL_55;
    }
    v54 = 102;
    goto LABEL_126;
  }
  TextLayout = CDWriteText::CreateTextLayout(this);
  v3 = TextLayout;
  if ( TextLayout < 0 )
  {
    v54 = 110;
LABEL_126:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v54,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)TextLayout,
      v58);
    goto LABEL_123;
  }
  v60 = 0;
  v61 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v72 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 28) + 480LL))(*((_QWORD *)this + 28), &v74);
  v3 = v5;
  if ( v5 < 0 )
  {
    v53 = 119;
LABEL_129:
    v52 = (unsigned int)v5;
    goto LABEL_121;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 28) + 488LL))(*((_QWORD *)this + 28), &v72);
  v3 = v5;
  if ( v5 < 0 )
  {
    v53 = 120;
    goto LABEL_129;
  }
  v6 = floorf(COERCE_FLOAT(v72 ^ _xmm)) - 1.0;
  v7 = floorf(COERCE_FLOAT(DWORD1(v72) ^ _xmm)) - 1.0;
  v8 = (__m128)DWORD2(v72);
  v8.m128_f32[0] = o_ceilf_0(*((float *)&v72 + 2) + *((float *)&v75 + 1));
  v9 = v8;
  v9.m128_f32[0] = (float)(v8.m128_f32[0] + 1.0) - v6;
  v10 = (__m128)HIDWORD(v72);
  v10.m128_f32[0] = o_ceilf_0(*((float *)&v72 + 3) + *((float *)&v75 + 2));
  v11 = v10;
  v12 = (CGraphicsDeviceManager *)*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 7);
  v13 = CGraphicsDeviceManager::EnsureGraphicsDeviceCreated(v12);
  v3 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\GraphicsDeviceManager.h",
      (const char *)(unsigned int)v13,
      v58);
    v52 = v3;
    v53 = 136;
LABEL_121:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v53,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)v52,
      v58);
LABEL_122:
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v61);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v60);
LABEL_123:
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v62);
    return v3;
  }
  if ( g_simulateDeviceLost )
    CGraphicsDeviceManager::SimulateDeviceLost(v12);
  v67 = v12;
  v14 = (__int64 *)*((_QWORD *)v12 + 7);
  v63 = 0;
  v15 = *v14;
  v63 = 0;
  v59 = (int *)&v63;
  v11.m128_f32[0] = (float)(v10.m128_f32[0] + 1.0) - v7;
  v16 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int64, __int64))(v15 + 48))(
          v14,
          _mm_unpacklo_ps(v9, v11).m128_u64[0],
          87);
  v3 = v16;
  if ( v16 < 0 )
  {
    v55 = 144;
LABEL_132:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v55,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)v16,
      (int)v59);
LABEL_141:
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v63);
    goto LABEL_122;
  }
  v60 = 0;
  v18 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
          &v60,
          *v63,
          v17,
          v63);
  v16 = (*v19)(v20, &GUID_fd04e6e3_fe0c_4c3c_ab19_a07601a576ee, v18);
  v3 = v16;
  if ( v16 < 0 )
  {
    v55 = 147;
    goto LABEL_132;
  }
  *(_QWORD *)v68 = 0;
  v21 = v60;
  v22 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, GUID *, __int64 *))(*v60 + 24LL);
  v23 = v61;
  v61 = 0;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v59 = v68;
  v16 = v22(v21, 0, &GUID_e8f7fe7a_191c_466d_ad95_975678bda998, &v61);
  v3 = v16;
  if ( v16 < 0 )
  {
    v55 = 155;
    goto LABEL_132;
  }
  v64 = 0;
  v24 = v67;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v67 + 3) + 32LL))(*((_QWORD *)v67 + 3));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v24 + 9) + 24LL))(*((_QWORD *)v24 + 9));
  v69 = &v67;
  v70 = &v60;
  v71 = 1;
  v73 = 0;
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v61 + 376LL))(v61, &v73);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v61 + 272LL))(v61, 2);
  *(float *)&v73 = (float)*((unsigned __int8 *)this + 448) / 255.0;
  *((float *)&v73 + 1) = (float)*((unsigned __int8 *)this + 449) / 255.0;
  *((float *)&v73 + 2) = (float)*((unsigned __int8 *)this + 450) / 255.0;
  HIDWORD(v73) = 1065353216;
  v25 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, __int64 *))(*(_QWORD *)v61 + 64LL))(v61, &v73, 0, &v64);
  v26 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)v25,
      (int)v68);
    v56 = v67;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v67 + 9) + 32LL))(*((_QWORD *)v67 + 9));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v56 + 3) + 40LL))(*((_QWORD *)v56 + 3));
    (*(void (__fastcall **)(_QWORD *))(*v60 + 32LL))(v60);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v64);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v63);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v61);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v60);
    v3 = v26;
    goto LABEL_123;
  }
  v27 = (__m128)COERCE_UNSIGNED_INT((float)v68[0]);
  v27.m128_f32[0] = v27.m128_f32[0] - v6;
  v28 = (__m128)COERCE_UNSIGNED_INT((float)v68[1]);
  v28.m128_f32[0] = v28.m128_f32[0] - v7;
  (*(void (__fastcall **)(__int64, unsigned __int64, _QWORD, __int64))(*(_QWORD *)v61 + 224LL))(
    v61,
    _mm_unpacklo_ps(v27, v28).m128_u64[0],
    *((_QWORD *)this + 28),
    v64);
  v29 = v67;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v67 + 9) + 32LL))(*((_QWORD *)v67 + 9));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v29 + 3) + 40LL))(*((_QWORD *)v29 + 3));
  (*(void (__fastcall **)(_QWORD *))(*v60 + 32LL))(v60);
  v65 = 0;
  v31 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
          &v65,
          *v60,
          v30,
          v60);
  v34 = (*v32)(v33, &GUID_1527540d_42c7_47a6_a408_668f79a90dfb, v31);
  v3 = v34;
  if ( v34 < 0 )
  {
    v57 = 191;
LABEL_140:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v57,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)v34,
      0);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v65);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v64);
    goto LABEL_141;
  }
  v35 = v62;
  if ( v62 )
    goto LABEL_22;
  v36 = *(__int64 **)(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 6) + 40LL);
  v37 = *v36;
  v62 = 0;
  v38 = (*(__int64 (__fastcall **)(__int64 *, _QWORD **))(v37 + 184))(v36, &v62);
  v3 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)v38,
      0);
    if ( v65 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    if ( v64 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    if ( v63 )
      (*(void (__fastcall **)(_QWORD *))(*v63 + 16LL))(v63);
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    if ( v60 )
      (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
    if ( v62 )
      (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
    return v3;
  }
  v34 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v62 + 88LL))(v62, 0);
  v3 = v34;
  if ( v34 < 0 )
  {
    v57 = 198;
    goto LABEL_140;
  }
  v34 = (*(__int64 (__fastcall **)(_QWORD *))(*v62 + 120LL))(v62);
  v3 = v34;
  if ( v34 < 0 )
  {
    v57 = 199;
    goto LABEL_140;
  }
  v34 = CSpriteVisual::SetBrush<Windows::UI::Composition::ICompositionColorBrush *>(this, v62);
  v3 = v34;
  if ( v34 < 0 )
  {
    v57 = 200;
    goto LABEL_140;
  }
  v35 = v62;
LABEL_22:
  v39 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v35 + 104LL))(v35, v65);
  v3 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)v39,
      0);
    if ( v65 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    if ( v64 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    if ( v63 )
      (*(void (__fastcall **)(_QWORD *))(*v63 + 16LL))(v63);
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    if ( v60 )
      (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
    if ( v62 )
      (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
    return v3;
  }
  v40 = *(__int64 (**)(void))(*v62 + 72LL);
  if ( (*((_BYTE *)this + 36) & 1) != 0 )
  {
    v51 = v40();
    v3 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD0,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
        (const char *)(unsigned int)v51,
        0);
      if ( v65 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      if ( v64 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      if ( v63 )
        (*(void (__fastcall **)(_QWORD *))(*v63 + 16LL))(v63);
      if ( v61 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      if ( v60 )
        (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
      if ( v62 )
        (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
      return v3;
    }
    goto LABEL_25;
  }
  v34 = v40();
  v3 = v34;
  if ( v34 < 0 )
  {
    v57 = 212;
    goto LABEL_140;
  }
LABEL_25:
  v66 = 0;
  v42 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
          &v66,
          *v62,
          v41,
          v62);
  v45 = (*v43)(v44, &GUID_d27174d5_64f5_4692_9dc7_71b61d7e5880, v42);
  v3 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)v45,
      0);
    if ( v66 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    if ( v65 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    if ( v64 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    if ( v63 )
      (*(void (__fastcall **)(_QWORD *))(*v63 + 16LL))(v63);
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    if ( v60 )
      (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
    if ( v62 )
      (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
    return v3;
  }
  v46 = v66;
  v47 = _mm_xor_ps((__m128)DWORD1(v72), (__m128)(unsigned int)_xmm);
  v47.m128_f32[0] = floorf(v47.m128_f32[0]);
  v47.m128_f32[0] = floorf(
                      (float)(v47.m128_f32[0] - 1.0)
                    + (float)((float)((float)*((int *)this + 17) - *(float *)&v75) * 0.5));
  v48 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v46 + 88LL))(
          v46,
          _mm_unpacklo_ps((__m128)0LL, v47).m128_u64[0]);
  v3 = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)v48,
      0);
    if ( v66 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    if ( v65 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    if ( v64 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    if ( v63 )
      (*(void (__fastcall **)(_QWORD *))(*v63 + 16LL))(v63);
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    if ( v60 )
      (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
    if ( v62 )
      (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
    return v3;
  }
  if ( v66 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  if ( v65 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  if ( v64 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  if ( v63 )
    (*(void (__fastcall **)(_QWORD *))(*v63 + 16LL))(v63);
  if ( v61 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  if ( v60 )
    (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
  v50 = v62;
LABEL_55:
  if ( v50 )
    (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
  return 0;
}

```

## disassembly

```asm
0x18000d2e8  mov     rax, rsp
0x18000d2eb  mov     [rax+10h], rbx
0x18000d2ef  mov     [rax+18h], rsi
0x18000d2f3  push    rbp
0x18000d2f4  push    rdi
0x18000d2f5  push    r14
0x18000d2f7  lea     rbp, [rax-58h]
0x18000d2fb  sub     rsp, 140h
0x18000d302  movaps  xmmword ptr [rax-28h], xmm6
0x18000d306  movaps  xmmword ptr [rax-38h], xmm7
0x18000d30a  movaps  xmmword ptr [rax-48h], xmm8
0x18000d30f  movaps  xmmword ptr [rax-58h], xmm9
0x18000d314  movaps  xmmword ptr [rax-68h], xmm10
0x18000d319  movaps  xmmword ptr [rax-78h], xmm11
0x18000d31e  mov     rax, cs:__security_cookie
0x18000d325  xor     rax, rsp
0x18000d328  mov     [rbp+50h+var_78], rax
0x18000d32c  mov     rdi, rcx
0x18000d32f  xor     r14d, r14d
0x18000d332  mov     [rsp+150h+var_110], r14
0x18000d337  lea     rdx, [rsp+150h+var_110]
0x18000d33c  call    ??$GetBrush@UICompositionSurfaceBrush@Composition@UI@Windows@@@CSpriteVisual@@QEBAJPEAPEAUICompositionSurfaceBrush@Composition@UI@Windows@@@Z; CSpriteVisual::GetBrush<Windows::UI::Composition::ICompositionSurfaceBrush>(Windows::UI::Composition::ICompositionSurfaceBrush * *)
0x18000d341  mov     ebx, eax
0x18000d343  test    eax, eax
0x18000d345  js      loc_18000DBAE
0x18000d34b  cmp     [rdi+40h], r14d
0x18000d34f  jz      loc_18000DA03
0x18000d355  mov     rcx, rdi; this
0x18000d358  call    ?CreateTextLayout@CDWriteText@@AEAAJXZ; CDWriteText::CreateTextLayout(void)
0x18000d35d  mov     ebx, eax
0x18000d35f  test    eax, eax
0x18000d361  js      loc_18000DD90
0x18000d367  mov     [rsp+150h+var_120], r14
0x18000d36c  mov     [rsp+150h+var_118], r14
0x18000d371  xorps   xmm0, xmm0
0x18000d374  xor     eax, eax
0x18000d376  movups  [rbp+50h+var_A0], xmm0
0x18000d37a  movups  [rbp+50h+var_90], xmm0
0x18000d37e  mov     [rbp+50h+var_80], eax
0x18000d381  movups  [rbp+50h+var_C0], xmm0
0x18000d385  mov     rcx, [rdi+0E0h]
0x18000d38c  mov     rax, [rcx]
0x18000d38f  lea     rdx, [rbp+50h+var_A0]
0x18000d393  mov     rax, [rax+1E0h]
0x18000d39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d39f  mov     ebx, eax
0x18000d3a1  test    eax, eax
0x18000d3a3  js      loc_18000DDAA
0x18000d3a9  mov     rcx, [rdi+0E0h]
0x18000d3b0  mov     rax, [rcx]
0x18000d3b3  lea     rdx, [rbp+50h+var_C0]
0x18000d3b7  mov     rax, [rax+1E8h]
0x18000d3be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c3  mov     ebx, eax
0x18000d3c5  test    eax, eax
0x18000d3c7  js      loc_18000DDB1
0x18000d3cd  movss   xmm0, dword ptr [rbp+50h+var_C0]
0x18000d3d2  movss   xmm11, dword ptr cs:__xmm@80000000800000008000000080000000
0x18000d3db  xorps   xmm0, xmm11; X
0x18000d3df  call    floorf
0x18000d3e4  movaps  xmm9, xmm0
0x18000d3e8  movss   xmm7, cs:__real@3f800000
0x18000d3f0  subss   xmm9, xmm7
0x18000d3f5  movss   xmm0, dword ptr [rbp+50h+var_C0+4]
0x18000d3fa  xorps   xmm0, xmm11; X
0x18000d3fe  call    floorf
0x18000d403  movaps  xmm10, xmm0
0x18000d407  subss   xmm10, xmm7
0x18000d40c  movss   xmm0, dword ptr [rbp+50h+var_C0+8]
0x18000d411  addss   xmm0, dword ptr [rbp+50h+var_90+4]; X
0x18000d416  call    _o_ceilf_0
0x18000d41b  movaps  xmm6, xmm0
0x18000d41e  addss   xmm6, xmm7
0x18000d422  subss   xmm6, xmm9
0x18000d427  movss   xmm0, dword ptr [rbp+50h+var_C0+0Ch]
0x18000d42c  addss   xmm0, dword ptr [rbp+50h+var_90+8]; X
0x18000d431  call    _o_ceilf_0
0x18000d436  movaps  xmm8, xmm0
0x18000d43a  addss   xmm8, xmm7
0x18000d43f  subss   xmm8, xmm10
0x18000d444  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18000d44b  mov     rsi, [rax+38h]
0x18000d44f  mov     rcx, rsi; this
0x18000d452  call    ?EnsureGraphicsDeviceCreated@CGraphicsDeviceManager@@IEAAJXZ; CGraphicsDeviceManager::EnsureGraphicsDeviceCreated(void)
0x18000d457  mov     ebx, eax
0x18000d459  test    eax, eax
0x18000d45b  js      loc_18000DD33
0x18000d461  cmp     cs:?g_simulateDeviceLost@@3_NA, r14b; bool g_simulateDeviceLost
0x18000d468  jnz     loc_18000DDBB
0x18000d46e  mov     [rsp+150h+var_E8], rsi
0x18000d473  mov     rcx, [rsi+38h]
0x18000d477  mov     [rsp+150h+var_108], r14
0x18000d47c  mov     rax, [rcx]
0x18000d47f  mov     [rsp+150h+var_108], r14
0x18000d484  lea     rdx, [rsp+150h+var_108]
0x18000d489  mov     qword ptr [rsp+150h+var_130], rdx
0x18000d48e  mov     r9d, 1
0x18000d494  lea     r8d, [r9+56h]
0x18000d498  unpcklps xmm6, xmm8
0x18000d49c  movq    rdx, xmm6
0x18000d4a1  mov     rax, [rax+30h]
0x18000d4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4aa  mov     ebx, eax
0x18000d4ac  test    eax, eax
0x18000d4ae  js      loc_18000DDC8
0x18000d4b4  mov     rcx, [rsp+150h+var_120]
0x18000d4b9  mov     [rsp+150h+var_120], r14
0x18000d4be  test    rcx, rcx
0x18000d4c1  jnz     loc_18000DDEC
0x18000d4c7  mov     r9, [rsp+150h+var_108]
0x18000d4cc  mov     rdx, [r9]
0x18000d4cf  lea     rcx, [rsp+150h+var_120]
0x18000d4d4  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18000d4d9  mov     r8, rax
0x18000d4dc  mov     rax, [rdx]
0x18000d4df  lea     rdx, _GUID_fd04e6e3_fe0c_4c3c_ab19_a07601a576ee
0x18000d4e6  mov     rcx, r9
0x18000d4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4ee  mov     ebx, eax
0x18000d4f0  test    eax, eax
0x18000d4f2  js      loc_18000DDFD
0x18000d4f8  mov     qword ptr [rsp+150h+var_E0], r14
0x18000d4fd  mov     rbx, [rsp+150h+var_120]
0x18000d502  mov     rax, [rbx]
0x18000d505  mov     rsi, [rax+18h]
0x18000d509  mov     rcx, [rsp+150h+var_118]
0x18000d50e  mov     [rsp+150h+var_118], r14
0x18000d513  test    rcx, rcx
0x18000d516  jnz     loc_18000DE04
0x18000d51c  lea     rax, [rsp+150h+var_E0]
0x18000d521  mov     qword ptr [rsp+150h+var_130], rax; int
0x18000d526  lea     r9, [rsp+150h+var_118]
0x18000d52b  lea     r8, _GUID_e8f7fe7a_191c_466d_ad95_975678bda998
0x18000d532  xor     edx, edx
0x18000d534  mov     rcx, rbx
0x18000d537  mov     rax, rsi
0x18000d53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53f  mov     ebx, eax
0x18000d541  test    eax, eax
0x18000d543  js      loc_18000DDCF
0x18000d549  mov     [rsp+150h+var_100], r14
0x18000d54e  mov     rbx, [rsp+150h+var_E8]
0x18000d553  mov     rcx, [rbx+18h]
0x18000d557  mov     rax, [rcx]
0x18000d55a  mov     rax, [rax+20h]
0x18000d55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d563  mov     rcx, [rbx+48h]
0x18000d567  mov     rax, [rcx]
0x18000d56a  mov     rax, [rax+18h]
0x18000d56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d573  lea     rax, [rsp+150h+var_E8]
0x18000d578  mov     [rsp+150h+var_D8], rax
0x18000d57d  lea     rax, [rsp+150h+var_120]
0x18000d582  mov     [rbp+50h+var_D0], rax
0x18000d586  mov     [rbp+50h+var_C8], 1
0x18000d58a  mov     rcx, [rsp+150h+var_118]
0x18000d58f  xorps   xmm0, xmm0
0x18000d592  movups  [rbp+50h+var_B0], xmm0
0x18000d596  mov     rax, [rcx]
0x18000d599  lea     rdx, [rbp+50h+var_B0]
0x18000d59d  mov     rax, [rax+178h]
0x18000d5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5a9  mov     rcx, [rsp+150h+var_118]
0x18000d5ae  mov     rax, [rcx]
0x18000d5b1  mov     edx, 2
0x18000d5b6  mov     rax, [rax+110h]
0x18000d5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5c2  mov     rcx, [rsp+150h+var_118]
0x18000d5c7  movzx   eax, byte ptr [rdi+1C0h]
0x18000d5ce  movd    xmm0, eax
0x18000d5d2  cvtdq2ps xmm0, xmm0
0x18000d5d5  movss   xmm2, cs:__real@437f0000
0x18000d5dd  divss   xmm0, xmm2
0x18000d5e1  movss   dword ptr [rbp+50h+var_B0], xmm0
0x18000d5e6  movzx   eax, byte ptr [rdi+1C1h]
0x18000d5ed  movd    xmm0, eax
0x18000d5f1  cvtdq2ps xmm0, xmm0
0x18000d5f4  divss   xmm0, xmm2
0x18000d5f8  movss   dword ptr [rbp+50h+var_B0+4], xmm0
0x18000d5fd  movzx   eax, byte ptr [rdi+1C2h]
0x18000d604  movd    xmm1, eax
0x18000d608  cvtdq2ps xmm1, xmm1
0x18000d60b  divss   xmm1, xmm2
0x18000d60f  movss   dword ptr [rbp+50h+var_B0+8], xmm1
0x18000d614  mov     dword ptr [rbp+50h+var_B0+0Ch], 3F800000h
0x18000d61b  mov     rax, [rcx]
0x18000d61e  lea     r9, [rsp+150h+var_100]
0x18000d623  xor     r8d, r8d
0x18000d626  lea     rdx, [rbp+50h+var_B0]
0x18000d62a  mov     rax, [rax+40h]
0x18000d62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d633  mov     esi, eax
0x18000d635  test    eax, eax
0x18000d637  js      loc_18000DE15
0x18000d63d  mov     rcx, [rsp+150h+var_118]
0x18000d642  movd    xmm1, [rsp+150h+var_E0]
0x18000d648  cvtdq2ps xmm1, xmm1
0x18000d64b  subss   xmm1, xmm9
0x18000d650  movd    xmm0, [rsp+150h+var_E0+4]
0x18000d656  cvtdq2ps xmm0, xmm0
0x18000d659  subss   xmm0, xmm10
0x18000d65e  mov     rax, [rcx]
0x18000d661  mov     [rsp+150h+var_130], r14d; int
0x18000d666  mov     r9, [rsp+150h+var_100]
0x18000d66b  mov     r8, [rdi+0E0h]
0x18000d672  unpcklps xmm1, xmm0
0x18000d675  movq    rdx, xmm1
0x18000d67a  mov     rax, [rax+0E0h]
0x18000d681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d686  nop
0x18000d687  mov     rbx, [rsp+150h+var_E8]
0x18000d68c  mov     rcx, [rbx+48h]
0x18000d690  mov     rax, [rcx]
0x18000d693  mov     rax, [rax+20h]
0x18000d697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d69c  mov     rcx, [rbx+18h]
0x18000d6a0  mov     rax, [rcx]
0x18000d6a3  mov     rax, [rax+28h]
0x18000d6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6ac  mov     rcx, [rsp+150h+var_120]
0x18000d6b1  mov     rax, [rcx]
0x18000d6b4  mov     rax, [rax+20h]
0x18000d6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6bd  nop
0x18000d6be  mov     [rsp+150h+var_F8], r14
0x18000d6c3  mov     r9, [rsp+150h+var_120]
0x18000d6c8  mov     rdx, [r9]
0x18000d6cb  lea     rcx, [rsp+150h+var_F8]
0x18000d6d0  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18000d6d5  mov     r8, rax
0x18000d6d8  mov     rax, [rdx]
0x18000d6db  lea     rdx, _GUID_1527540d_42c7_47a6_a408_668f79a90dfb
0x18000d6e2  mov     rcx, r9
0x18000d6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6ea  mov     ebx, eax
0x18000d6ec  test    eax, eax
0x18000d6ee  js      loc_18000DE97
0x18000d6f4  xorps   xmm6, xmm6
0x18000d6f7  mov     rcx, [rsp+150h+var_110]
0x18000d6fc  test    rcx, rcx
0x18000d6ff  jnz     loc_18000D78E
0x18000d705  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18000d70c  mov     rcx, [rax+30h]
0x18000d710  mov     rcx, [rcx+28h]
0x18000d714  mov     rax, [rcx]
0x18000d717  mov     [rsp+150h+var_110], r14
0x18000d71c  lea     rdx, [rsp+150h+var_110]
0x18000d721  mov     rax, [rax+0B8h]
0x18000d728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d72d  mov     ebx, eax
0x18000d72f  test    eax, eax
0x18000d731  js      loc_18000DC8B
0x18000d737  mov     rcx, [rsp+150h+var_110]
0x18000d73c  mov     rax, [rcx]
0x18000d73f  xor     edx, edx
0x18000d741  mov     rax, [rax+58h]
0x18000d745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d74a  mov     ebx, eax
0x18000d74c  test    eax, eax
0x18000d74e  js      loc_18000DE9E
0x18000d754  mov     rcx, [rsp+150h+var_110]
0x18000d759  mov     rax, [rcx]
0x18000d75c  xorps   xmm1, xmm1
0x18000d75f  mov     rax, [rax+78h]
0x18000d763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d768  mov     ebx, eax
0x18000d76a  test    eax, eax
0x18000d76c  js      loc_18000DEA5
0x18000d772  mov     rdx, [rsp+150h+var_110]
0x18000d777  mov     rcx, rdi
0x18000d77a  call    ??$SetBrush@PEAUICompositionColorBrush@Composition@UI@Windows@@@CSpriteVisual@@QEAAJPEAUICompositionColorBrush@Composition@UI@Windows@@@Z; CSpriteVisual::SetBrush<Windows::UI::Composition::ICompositionColorBrush *>(Windows::UI::Composition::ICompositionColorBrush *)
0x18000d77f  mov     ebx, eax
0x18000d781  test    eax, eax
0x18000d783  js      loc_18000DEAC
0x18000d789  mov     rcx, [rsp+150h+var_110]
0x18000d78e  mov     rax, [rcx]
0x18000d791  mov     rdx, [rsp+150h+var_F8]
0x18000d796  mov     rax, [rax+68h]
0x18000d79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d79f  mov     ebx, eax
0x18000d7a1  test    eax, eax
0x18000d7a3  js      loc_18000DBE3
0x18000d7a9  mov     rcx, [rsp+150h+var_110]
0x18000d7ae  mov     rax, [rcx]
0x18000d7b1  mov     rax, [rax+48h]
0x18000d7b5  test    byte ptr [rdi+24h], 1
0x18000d7b9  jnz     loc_18000DAD2
0x18000d7bf  xorps   xmm1, xmm1
0x18000d7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7c7  mov     ebx, eax
0x18000d7c9  test    eax, eax
0x18000d7cb  js      loc_18000DEB3
0x18000d7d1  mov     [rsp+150h+var_F0], r14
0x18000d7d6  mov     r9, [rsp+150h+var_110]
0x18000d7db  mov     rdx, [r9]
0x18000d7de  lea     rcx, [rsp+150h+var_F0]
0x18000d7e3  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18000d7e8  mov     r8, rax
0x18000d7eb  mov     rax, [rdx]
0x18000d7ee  lea     rdx, _GUID_d27174d5_64f5_4692_9dc7_71b61d7e5880
  ... truncated ...
```
