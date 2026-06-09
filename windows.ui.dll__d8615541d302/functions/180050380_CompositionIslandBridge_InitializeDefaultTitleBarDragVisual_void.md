# CompositionIslandBridge::InitializeDefaultTitleBarDragVisual(void)

- ea: `0x180050380`
- end: `0x1800508db`
- name: `?InitializeDefaultTitleBarDragVisual@CompositionIslandBridge@@QEAAJXZ`
- size: `1371`
- prototype: `__int64 __fastcall(CompositionIslandBridge *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180079680`

## callees

- `0x1800038e0`
- `0x18002582c`
- `0x18002eaa0`
- `0x18004c4b8`
- `0x18004f474`
- `0x180050360`
- `0x180050380`
- `0x180051568`
- `0x180051750`
- `0x180051aa0`
- `0x180051b2c`
- `0x180051b7c`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800503e9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800506ef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800503e9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800506ef`

## string_xrefs

- `0x1800503fa`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x18005042f`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050480`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800504b0`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800504ea`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050538`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050566`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050597`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800505d4`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x18005061b`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050663`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800506a0`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050700`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050748`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x18005077a`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800507ad`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800507e0`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x18005080e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x18005083e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800506c4`: `Windows.UI.Internal.Input.ActivationConfigurationInputObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CompositionIslandBridge::InitializeDefaultTitleBarDragVisual(
        CompositionIslandBridge *this,
        __int64 a2)
{
  const unsigned __int16 (*v3)[40]; // rdx
  __int64 v4; // rbx
  int ActivationFactory; // eax
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  _QWORD *v10; // r14
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  _QWORD *v18; // rax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64, __int64 *); // rbx
  int v25; // eax
  int v26; // eax
  __int64 v27; // rbx
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, __int64 *); // rbx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int CoreApplicationViewOfCurrentThread; // eax
  int v35; // eax
  int v36; // eax
  int v38; // [rsp+20h] [rbp-69h] BYREF
  unsigned int v39; // [rsp+24h] [rbp-65h]
  __int64 v40; // [rsp+28h] [rbp-61h] BYREF
  __int64 v41; // [rsp+30h] [rbp-59h] BYREF
  __int64 v42; // [rsp+38h] [rbp-51h] BYREF
  struct Windows::ApplicationModel::Core::ICoreApplicationView *v43; // [rsp+40h] [rbp-49h] BYREF
  __int64 v44; // [rsp+48h] [rbp-41h] BYREF
  __int64 v45; // [rsp+50h] [rbp-39h] BYREF
  __int64 v46; // [rsp+58h] [rbp-31h] BYREF
  __int64 v47; // [rsp+60h] [rbp-29h] BYREF
  __int64 v48; // [rsp+68h] [rbp-21h] BYREF
  __int64 v49; // [rsp+70h] [rbp-19h] BYREF
  __int64 v50; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  __int64 v52; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( *((_DWORD *)this + 6) )
  {
    LOBYTE(a2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SmoothWindowDrag>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_SmoothWindowDrag>::GetImpl'::`2'::impl,
      a2);
    v42 = 0;
    v4 = *(_QWORD *)Windows::Internal::StringReference::StringReference((HSTRING *)&hstringHeader, v3);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v42);
    ActivationFactory = RoGetActivationFactory(v4, &GUID_5c1a374d_09bf_5edf_8c80_7b81826d2c42, &v42);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x28F,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v38);
    LOBYTE(v38) = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 48LL))(v42, &v38);
    if ( v6 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x292,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v6,
        v38);
    if ( (_BYTE)v38 )
    {
      v41 = 0;
      v7 = *((_QWORD *)this + 7);
      v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 176LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v41);
      v9 = v8(v7, &v41);
      if ( v9 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x299,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v9,
          v38);
      v10 = (_QWORD *)((char *)this + 152);
      v11 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ISpriteVisual>::As<Windows::UI::Composition::IVisual>(
              &v41,
              (char *)this + 152);
      if ( v11 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x29B,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v11,
          v38);
      v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v10 + 288LL))(
              *v10,
              _mm_unpacklo_ps((__m128)0LL, (__m128)0LL).m128_u64[0]);
      if ( v12 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x29F,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v12,
          v38);
      v39 = -256;
      v47 = 0;
      v13 = *((_QWORD *)this + 7);
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v13 + 64LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v47);
      v15 = v14(v13, v39, &v47);
      if ( v15 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2A4,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v15,
          v38);
      v50 = 0;
      v16 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionColorBrush>::As<Windows::UI::Composition::ICompositionBrush>(
              &v47,
              &v50);
      if ( v16 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2A7,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v16,
          v38);
      v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 56LL))(v41, v50);
      if ( v17 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2A9,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v17,
          v38);
      v49 = 0;
      v18 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                        (HSTRING *)&hstringHeader,
                        L"Windows.UI.Internal.Input.InputSite");
      v19 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Internal::Input::IInputSiteStatics>>(
              *v18,
              &v49);
      if ( v19 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2B1,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v19,
          v38);
      v40 = 0;
      v20 = v49;
      v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v49 + 48LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v40);
      v22 = v21(v20, *v10, &v40);
      if ( v22 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2B3,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v22,
          v38);
      v46 = 0;
      v23 = v42;
      v24 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v42 + 56LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v46);
      v25 = v24(v23, v40, &v46);
      if ( v25 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2B7,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v25,
          v38);
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = xmmword_18010AF30;
      v26 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v46 + 56LL))(v46, &hstringHeader);
      if ( v26 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2B8,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v26,
          v38);
      v45 = 0;
      v52 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.UI.Internal.Input.ActivationConfigurationInputObject",
        0x3Du,
        0x3Cu);
      v27 = v52;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v45);
      v28 = RoGetActivationFactory(v27, &GUID_4c8421ca_3863_5236_b09a_757cf68c5fa5, &v45);
      if ( v28 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2BD,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v28,
          v38);
      v44 = 0;
      v29 = v45;
      v30 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v45 + 48LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v44);
      v31 = v30(v29, v40, &v44);
      if ( v31 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2C2,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v31,
          v38);
      v32 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 56LL))(v44, 2);
      if ( v32 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2C4,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v32,
          v38);
      v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 18) + 72LL))(*((_QWORD *)this + 18), *v10);
      if ( v33 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2CA,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v33,
          v38);
      v43 = 0;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v43);
      CoreApplicationViewOfCurrentThread = GetCoreApplicationViewOfCurrentThread(&v43);
      if ( CoreApplicationViewOfCurrentThread < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2D0,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)CoreApplicationViewOfCurrentThread,
          v38);
      v48 = 0;
      v35 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationView>::As<Windows::Foundation::Private::ICoreApplicationView4>(
              &v43,
              &v48);
      if ( v35 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2D3,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v35,
          v38);
      v36 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v48 + 80LL))(v48, *v10);
      if ( v36 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x2D5,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v36,
          v38);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v48);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v50);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v41);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v42);
  }
  return 0;
}

```

## disassembly

```asm
0x180050380  push    rbp
0x180050382  push    rbx
0x180050383  push    rsi
0x180050384  push    rdi
0x180050385  push    r14
0x180050387  push    r15
0x180050389  lea     rbp, [rsp-2Fh]
0x18005038e  sub     rsp, 0B8h
0x180050395  mov     rax, cs:__security_cookie
0x18005039c  xor     rax, rsp
0x18005039f  mov     [rbp+57h+var_40], rax
0x1800503a3  mov     rsi, rcx
0x1800503a6  mov     eax, [rcx+18h]
0x1800503a9  xor     r15d, r15d
0x1800503ac  test    eax, eax
0x1800503ae  jz      loc_1800508BD
0x1800503b4  mov     dl, 1
0x1800503b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SmoothWindowDrag@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SmoothWindowDrag@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SmoothWindowDrag> `wil::Feature<__WilFeatureTraits_Feature_SmoothWindowDrag>::GetImpl(void)'::`2'::impl
0x1800503bd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SmoothWindowDrag@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SmoothWindowDrag>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800503c2  mov     [rbp+57h+var_A8], r15
0x1800503c6  lea     rcx, [rbp+57h+hstringHeader]; string
0x1800503ca  call    ??$?0$0CI@@StringReference@Internal@Windows@@QEAA@AEAY0CI@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[40])
0x1800503cf  mov     rbx, [rax]
0x1800503d2  lea     rcx, [rbp+57h+var_A8]
0x1800503d6  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800503db  lea     r8, [rbp+57h+var_A8]
0x1800503df  lea     rdx, _GUID_5c1a374d_09bf_5edf_8c80_7b81826d2c42
0x1800503e6  mov     rcx, rbx
0x1800503e9  call    cs:__imp_RoGetActivationFactory
0x1800503ef  mov     rcx, [rbp+5Fh]; this
0x1800503f3  test    eax, eax
0x1800503f5  jns     short loc_18005040C
0x1800503f7  mov     r9d, eax; char *
0x1800503fa  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050401  mov     edx, 28Fh; void *
0x180050406  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18005040c  mov     byte ptr [rbp+57h+var_C0], r15b
0x180050410  mov     rcx, [rbp+57h+var_A8]
0x180050414  mov     rax, [rcx]
0x180050417  lea     rdx, [rbp+57h+var_C0]
0x18005041b  mov     rax, [rax+30h]
0x18005041f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050424  mov     rcx, [rbp+5Fh]; this
0x180050428  test    eax, eax
0x18005042a  jns     short loc_180050441
0x18005042c  mov     r9d, eax; char *
0x18005042f  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050436  mov     edx, 292h; void *
0x18005043b  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050441  cmp     byte ptr [rbp+57h+var_C0], r15b
0x180050445  jz      loc_1800508B4
0x18005044b  mov     [rbp+57h+var_B0], r15
0x18005044f  mov     rdi, [rsi+38h]
0x180050453  mov     rax, [rdi]
0x180050456  mov     rbx, [rax+0B0h]
0x18005045d  lea     rcx, [rbp+57h+var_B0]
0x180050461  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050466  lea     rdx, [rbp+57h+var_B0]
0x18005046a  mov     rcx, rdi
0x18005046d  mov     rax, rbx
0x180050470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050475  mov     rcx, [rbp+5Fh]; this
0x180050479  test    eax, eax
0x18005047b  jns     short loc_180050492
0x18005047d  mov     r9d, eax; char *
0x180050480  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050487  mov     edx, 299h; void *
0x18005048c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050492  lea     r14, [rsi+98h]
0x180050499  mov     rdx, r14
0x18005049c  lea     rcx, [rbp+57h+var_B0]
0x1800504a0  call    ??$As@UIVisual@Composition@UI@Windows@@@?$ComPtr@UISpriteVisual@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVisual@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ISpriteVisual>::As<Windows::UI::Composition::IVisual>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisual>>)
0x1800504a5  mov     rcx, [rbp+5Fh]; this
0x1800504a9  test    eax, eax
0x1800504ab  jns     short loc_1800504C2
0x1800504ad  mov     r9d, eax; char *
0x1800504b0  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800504b7  mov     edx, 29Bh; void *
0x1800504bc  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800504c2  mov     rcx, [r14]
0x1800504c5  xorps   xmm0, xmm0
0x1800504c8  mov     rax, [rcx]
0x1800504cb  unpcklps xmm0, xmm0
0x1800504ce  movq    rdx, xmm0
0x1800504d3  mov     rax, [rax+120h]
0x1800504da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504df  mov     rcx, [rbp+5Fh]; this
0x1800504e3  test    eax, eax
0x1800504e5  jns     short loc_1800504FC
0x1800504e7  mov     r9d, eax; char *
0x1800504ea  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800504f1  mov     edx, 29Fh; void *
0x1800504f6  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800504fc  mov     [rbp+57h+var_BC], 0FFFFFF00h
0x180050503  mov     [rbp+57h+var_80], r15
0x180050507  mov     rdi, [rsi+38h]
0x18005050b  mov     rax, [rdi]
0x18005050e  mov     rbx, [rax+40h]
0x180050512  lea     rcx, [rbp+57h+var_80]
0x180050516  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005051b  lea     r8, [rbp+57h+var_80]
0x18005051f  mov     edx, [rbp+57h+var_BC]
0x180050522  mov     rcx, rdi
0x180050525  mov     rax, rbx
0x180050528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005052d  mov     rcx, [rbp+5Fh]; this
0x180050531  test    eax, eax
0x180050533  jns     short loc_18005054A
0x180050535  mov     r9d, eax; char *
0x180050538  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005053f  mov     edx, 2A4h; void *
0x180050544  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18005054a  mov     [rbp+57h+var_68], r15
0x18005054e  lea     rdx, [rbp+57h+var_68]
0x180050552  lea     rcx, [rbp+57h+var_80]
0x180050556  call    ??$As@UICompositionBrush@Composition@UI@Windows@@@?$ComPtr@UICompositionColorBrush@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionBrush@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionColorBrush>::As<Windows::UI::Composition::ICompositionBrush>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionBrush>>)
0x18005055b  mov     rcx, [rbp+5Fh]; this
0x18005055f  test    eax, eax
0x180050561  jns     short loc_180050578
0x180050563  mov     r9d, eax; char *
0x180050566  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005056d  mov     edx, 2A7h; void *
0x180050572  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050578  mov     rcx, [rbp+57h+var_B0]
0x18005057c  mov     rax, [rcx]
0x18005057f  mov     rdx, [rbp+57h+var_68]
0x180050583  mov     rax, [rax+38h]
0x180050587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005058c  mov     rcx, [rbp+5Fh]; this
0x180050590  test    eax, eax
0x180050592  jns     short loc_1800505A9
0x180050594  mov     r9d, eax; char *
0x180050597  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005059e  mov     edx, 2A9h; void *
0x1800505a3  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800505a9  mov     [rbp+57h+var_70], r15
0x1800505ad  lea     rdx, ?RuntimeClass_Windows_UI_Internal_Input_InputSite@@3QBGB; "Windows.UI.Internal.Input.InputSite"
0x1800505b4  lea     rcx, [rbp+57h+hstringHeader]; string
0x1800505b8  call    ??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[36])
0x1800505bd  lea     rdx, [rbp+57h+var_70]
0x1800505c1  mov     rcx, [rax]
0x1800505c4  call    ??$GetActivationFactory@V?$ComPtr@UIInputSiteStatics@Input@Internal@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIInputSiteStatics@Input@Internal@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Internal::Input::IInputSiteStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Internal::Input::IInputSiteStatics>>)
0x1800505c9  mov     rcx, [rbp+5Fh]; this
0x1800505cd  test    eax, eax
0x1800505cf  jns     short loc_1800505E6
0x1800505d1  mov     r9d, eax; char *
0x1800505d4  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800505db  mov     edx, 2B1h; void *
0x1800505e0  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800505e6  mov     [rbp+57h+var_B8], r15
0x1800505ea  mov     rdi, [rbp+57h+var_70]
0x1800505ee  mov     rax, [rdi]
0x1800505f1  mov     rbx, [rax+30h]
0x1800505f5  lea     rcx, [rbp+57h+var_B8]
0x1800505f9  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800505fe  lea     r8, [rbp+57h+var_B8]
0x180050602  mov     rdx, [r14]
0x180050605  mov     rcx, rdi
0x180050608  mov     rax, rbx
0x18005060b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050610  mov     rcx, [rbp+5Fh]; this
0x180050614  test    eax, eax
0x180050616  jns     short loc_18005062D
0x180050618  mov     r9d, eax; char *
0x18005061b  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050622  mov     edx, 2B3h; void *
0x180050627  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18005062d  mov     [rbp+57h+var_88], r15
0x180050631  mov     rdi, [rbp+57h+var_A8]
0x180050635  mov     rax, [rdi]
0x180050638  mov     rbx, [rax+38h]
0x18005063c  lea     rcx, [rbp+57h+var_88]
0x180050640  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050645  lea     r8, [rbp+57h+var_88]
0x180050649  mov     rdx, [rbp+57h+var_B8]
0x18005064d  mov     rcx, rdi
0x180050650  mov     rax, rbx
0x180050653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050658  mov     rcx, [rbp+5Fh]; this
0x18005065c  test    eax, eax
0x18005065e  jns     short loc_180050675
0x180050660  mov     r9d, eax; char *
0x180050663  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005066a  mov     edx, 2B7h; void *
0x18005066f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050675  mov     rcx, [rbp+57h+var_88]
0x180050679  movups  xmm0, cs:xmmword_18010AF30
0x180050680  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180050685  mov     rax, [rcx]
0x180050688  lea     rdx, [rbp+57h+hstringHeader]
0x18005068c  mov     rax, [rax+38h]
0x180050690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050695  mov     rcx, [rbp+5Fh]; this
0x180050699  test    eax, eax
0x18005069b  jns     short loc_1800506B2
0x18005069d  mov     r9d, eax; char *
0x1800506a0  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800506a7  mov     edx, 2B8h; void *
0x1800506ac  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800506b2  mov     [rbp+57h+var_90], r15
0x1800506b6  mov     [rbp+57h+var_48], r15
0x1800506ba  mov     r9d, 3Ch ; '<'; unsigned int
0x1800506c0  lea     r8d, [r9+1]; unsigned int
0x1800506c4  lea     rdx, ?RuntimeClass_Windows_UI_Internal_Input_ActivationConfigurationInputObject@@3QBGB; "Windows.UI.Internal.Input.ActivationCon"...
0x1800506cb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800506cf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800506d4  mov     rbx, [rbp+57h+var_48]
0x1800506d8  lea     rcx, [rbp+57h+var_90]
0x1800506dc  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800506e1  lea     r8, [rbp+57h+var_90]
0x1800506e5  lea     rdx, _GUID_4c8421ca_3863_5236_b09a_757cf68c5fa5
0x1800506ec  mov     rcx, rbx
0x1800506ef  call    cs:__imp_RoGetActivationFactory
0x1800506f5  mov     rcx, [rbp+5Fh]; this
0x1800506f9  test    eax, eax
0x1800506fb  jns     short loc_180050712
0x1800506fd  mov     r9d, eax; char *
0x180050700  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050707  mov     edx, 2BDh; void *
0x18005070c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050712  mov     [rbp+57h+var_98], r15
0x180050716  mov     rdi, [rbp+57h+var_90]
0x18005071a  mov     rax, [rdi]
0x18005071d  mov     rbx, [rax+30h]
0x180050721  lea     rcx, [rbp+57h+var_98]
0x180050725  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005072a  lea     r8, [rbp+57h+var_98]
0x18005072e  mov     rdx, [rbp+57h+var_B8]
0x180050732  mov     rcx, rdi
0x180050735  mov     rax, rbx
0x180050738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005073d  mov     rcx, [rbp+5Fh]; this
0x180050741  test    eax, eax
0x180050743  jns     short loc_18005075A
0x180050745  mov     r9d, eax; char *
0x180050748  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005074f  mov     edx, 2C2h; void *
0x180050754  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18005075a  mov     rcx, [rbp+57h+var_98]
0x18005075e  mov     rax, [rcx]
0x180050761  mov     edx, 2
0x180050766  mov     rax, [rax+38h]
0x18005076a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005076f  mov     rcx, [rbp+5Fh]; this
0x180050773  test    eax, eax
0x180050775  jns     short loc_18005078C
0x180050777  mov     r9d, eax; char *
0x18005077a  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050781  mov     edx, 2C4h; void *
0x180050786  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18005078c  mov     rcx, [rsi+90h]
0x180050793  mov     rax, [rcx]
0x180050796  mov     rdx, [r14]
0x180050799  mov     rax, [rax+48h]
0x18005079d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507a2  mov     rcx, [rbp+5Fh]; this
0x1800507a6  test    eax, eax
0x1800507a8  jns     short loc_1800507BF
0x1800507aa  mov     r9d, eax; char *
0x1800507ad  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800507b4  mov     edx, 2CAh; void *
0x1800507b9  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800507bf  mov     [rbp+57h+var_A0], r15
0x1800507c3  lea     rcx, [rbp+57h+var_A0]
0x1800507c7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800507cc  lea     rcx, [rbp+57h+var_A0]; struct Windows::ApplicationModel::Core::ICoreApplicationView **
0x1800507d0  call    ?GetCoreApplicationViewOfCurrentThread@@YAJPEAPEAUICoreApplicationView@Core@ApplicationModel@Windows@@@Z; GetCoreApplicationViewOfCurrentThread(Windows::ApplicationModel::Core::ICoreApplicationView * *)
0x1800507d5  mov     rcx, [rbp+5Fh]; this
0x1800507d9  test    eax, eax
0x1800507db  jns     short loc_1800507F2
0x1800507dd  mov     r9d, eax; char *
0x1800507e0  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800507e7  mov     edx, 2D0h; void *
0x1800507ec  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800507f2  mov     [rbp+57h+var_78], r15
0x1800507f6  lea     rdx, [rbp+57h+var_78]
0x1800507fa  lea     rcx, [rbp+57h+var_A0]
0x1800507fe  call    ??$As@UICoreApplicationView4@Private@Foundation@Windows@@@?$ComPtr@UICoreApplicationView@Core@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreApplicationView4@Private@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationView>::As<Windows::Foundation::Private::ICoreApplicationView4>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICoreApplicationView4>>)
0x180050803  mov     rcx, [rbp+5Fh]; this
0x180050807  test    eax, eax
0x180050809  jns     short loc_180050820
0x18005080b  mov     r9d, eax; char *
0x18005080e  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050815  mov     edx, 2D3h; void *
0x18005081a  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050820  mov     rcx, [rbp+57h+var_78]
0x180050824  mov     rax, [rcx]
0x180050827  mov     rdx, [r14]
0x18005082a  mov     rax, [rax+50h]
0x18005082e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050833  mov     rcx, [rbp+5Fh]; this
0x180050837  test    eax, eax
0x180050839  jns     short loc_180050850
0x18005083b  mov     r9d, eax; char *
0x18005083e  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050845  mov     edx, 2D5h; void *
0x18005084a  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050850  lea     rcx, [rbp+57h+var_78]
0x180050854  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050859  nop
  ... truncated ...
```
