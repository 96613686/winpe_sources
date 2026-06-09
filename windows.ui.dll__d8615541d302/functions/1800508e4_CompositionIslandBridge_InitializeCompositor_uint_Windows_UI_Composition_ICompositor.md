# CompositionIslandBridge::InitializeCompositor(uint,Windows::UI::Composition::ICompositor *)

- ea: `0x1800508e4`
- end: `0x180051065`
- name: `?InitializeCompositor@CompositionIslandBridge@@QEAAJIPEAUICompositor@Composition@UI@Windows@@@Z`
- size: `1921`
- prototype: `__int64 __fastcall(CompositionIslandBridge *__hidden this, unsigned int, struct Windows::UI::Composition::ICompositor *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075ad0`

## callees

- `0x1800038e0`
- `0x18000cdc8`
- `0x180014754`
- `0x1800251d8`
- `0x180025228`
- `0x18002eaa0`
- `0x18003c6dc`
- `0x18003f584`
- `0x180045578`
- `0x18004fc30`
- `0x18004fc70`
- `0x18004fe94`
- `0x180050360`
- `0x1800508e4`
- `0x180051568`
- `0x180051608`
- `0x180051658`
- `0x1800516b0`
- `0x180051700`
- `0x180051750`
- `0x1800517a0`
- `0x18006c508`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180050ed7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180050ed7`
- `api-ms-win-rtcore-ntuser-private-l1-1-8!AddVisualIdentifier` at `0x180050f6a`
- `api-ms-win-rtcore-ntuser-private-l1-1-8!AddVisualIdentifier` at `0x180050f6a`

## string_xrefs

- `0x180050eb8`: `Windows.UI.Composition.CompositionIsland`
- `0x180050939`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050981`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800509b8`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050a04`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050a50`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050a88`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050aca`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050af3`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050b35`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050b68`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050ba6`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050c06`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050c33`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050c77`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050ca5`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050ceb`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050d21`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050d80`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050dae`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050de2`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050e1d`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050e5f`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050e8b`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050ee8`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050f1c`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050f50`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050f78`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050fbd`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180051008`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050925`: `CoreWindow is already configured for CompositionIslands`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CompositionIslandBridge::InitializeCompositor(
        CompositionIslandBridge *this,
        int a2,
        struct Windows::UI::Composition::ICompositor *a3)
{
  unsigned int v4; // ebx
  int v6; // eax
  int v7; // eax
  struct Windows::ApplicationModel::Core::ICoreApplicationView *v8; // rdi
  __int64 (__fastcall *v9)(struct Windows::ApplicationModel::Core::ICoreApplicationView *, _QWORD, _QWORD, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, char *); // rbx
  _QWORD *v15; // r12
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, char *); // rbx
  struct Windows::UI::Composition::IVisual **v20; // r14
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, __int64 *); // rbx
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, struct Windows::ApplicationModel::Core::ICoreApplicationView **); // rbx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, __int64, char *); // rbx
  int v34; // eax
  int v35; // eax
  int CoreApplicationViewOfCurrentThread; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, char *); // rbx
  int v42; // eax
  _QWORD *v43; // rbx
  int v44; // eax
  int ActivationFactory; // eax
  int v46; // eax
  int v47; // eax
  const char *v48; // r9
  int v49; // eax
  int v50; // eax
  __int64 v51; // rdx
  int v52; // [rsp+20h] [rbp-49h]
  const char *v53; // [rsp+28h] [rbp-41h]
  struct Windows::ApplicationModel::Core::ICoreApplicationView *v54; // [rsp+30h] [rbp-39h] BYREF
  __int64 v55; // [rsp+38h] [rbp-31h] BYREF
  __int64 v56; // [rsp+40h] [rbp-29h] BYREF
  __int64 v57; // [rsp+48h] [rbp-21h] BYREF
  __int64 v58; // [rsp+50h] [rbp-19h] BYREF
  __int64 v59; // [rsp+58h] [rbp-11h] BYREF
  __int64 v60; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  __int64 v62; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 6, 1, 0) == 1 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)0x80070057LL,
      (int)"CoreWindow is already configured for CompositionIslands",
      v53);
    return v4;
  }
  *((_DWORD *)this + 4) = a2;
  Microsoft::WRL::ComPtr<IUnknown>::operator=((char *)this + 56, a3);
  v57 = 0;
  v6 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::ICompositorWithCompositionIslands>(
         (char *)this + 56,
         &v57);
  if ( v6 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v6,
      v52);
  if ( !*((_BYTE *)this + 21) )
  {
    v54 = 0;
    v7 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::Desktop::ICompositorDesktopInterop>(
           (char *)this + 56,
           &v54);
    if ( v7 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v7,
        v52);
    v55 = 0;
    v8 = v54;
    v9 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Core::ICoreApplicationView *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v54 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
    v10 = v9(v8, *(_QWORD *)this, 0, &v55);
    v4 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v10,
        v52);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v54);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v57);
      return v4;
    }
    v11 = Microsoft::WRL::ComPtr<Windows::UI::Composition::Desktop::IDesktopWindowTarget>::As<Windows::UI::Composition::Private::ICompositionTargetPartner>(
            &v55,
            (char *)this + 64);
    if ( v11 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v11,
        v52);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v54);
  }
  v12 = CompositionIslandBridge::InitializeRootVisual(this);
  if ( v12 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v12,
      v52);
  v13 = v57;
  v14 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v57 + 48LL);
  v15 = (_QWORD *)((char *)this + 88);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 88);
  v16 = v14(v13, (char *)this + 88);
  if ( v16 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v16,
      v52);
  v17 = Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisualIslandSite>::As<Windows::UI::Composition::ICompositionIslandSite>(
          (char *)this + 88,
          (char *)this + 80);
  if ( v17 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v17,
      v52);
  v18 = *v15;
  v19 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)*v15 + 88LL);
  v20 = (struct Windows::UI::Composition::IVisual **)((char *)this + 72);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 72);
  v21 = v19(v18, (char *)this + 72);
  if ( v21 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v21,
      v52);
  v22 = (*(__int64 (__fastcall **)(_QWORD, struct Windows::UI::Composition::IVisual *))(**((_QWORD **)this + 18) + 64LL))(
          *((_QWORD *)this + 18),
          *v20);
  if ( v22 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v22,
      v52);
  if ( *((_BYTE *)this + 21) )
  {
    v24 = *((_QWORD *)this + 4);
    if ( v24 && *((_QWORD *)this + 5) )
    {
      v55 = 0;
      v25 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 224LL);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v55,
        0);
      v26 = v25(v24, *((_QWORD *)this + 5), &v55);
      if ( v26 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xE8,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v26,
          v52);
      v56 = 0;
      v27 = Microsoft::WRL::ComPtr<Windows::UI::Composition::Internal::ICompositionIslandPartner>::As<Windows::UI::Composition::ICompositionObject>(
              (char *)this + 72,
              &v56);
      if ( v27 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xEB,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v27,
          v52);
      v54 = 0;
      v28 = v56;
      v29 = *(__int64 (__fastcall **)(__int64, struct Windows::ApplicationModel::Core::ICoreApplicationView **))(*(_QWORD *)v56 + 48LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v54);
      v30 = v29(v28, &v54);
      if ( v30 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v30,
          v52);
      v59 = 0;
      v31 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::ICompositorPartner>(
              &v54,
              &v59);
      if ( v31 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xF1,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v31,
          v52);
      v32 = v59;
      v33 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v59 + 72LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 48);
      v34 = v33(v32, v55, (char *)this + 48);
      if ( v34 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v34,
          v52);
      v35 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 32LL))(
              *((_QWORD *)this + 6),
              *((_QWORD *)this + 17));
      if ( v35 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v35,
          v52);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v59);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v54);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v55);
    }
    else
    {
      v54 = 0;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v54);
      CoreApplicationViewOfCurrentThread = GetCoreApplicationViewOfCurrentThread(&v54);
      if ( CoreApplicationViewOfCurrentThread < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xD9,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)CoreApplicationViewOfCurrentThread,
          v52);
      v56 = 0;
      v37 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationView>::As<Windows::Foundation::Private::ICoreApplicationView4>(
              &v54,
              &v56);
      if ( v37 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v37,
          v52);
      v38 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 72LL))(v56, *((_QWORD *)this + 17));
      if ( v38 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v38,
          v52);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v54);
    }
  }
  else
  {
    v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 8) + 56LL))(
            *((_QWORD *)this + 8),
            *((_QWORD *)this + 17));
    if ( v23 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v23,
        v52);
  }
  v39 = CompositionIslandBridge::AttachInputSink(this, *v20);
  if ( v39 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v39,
      v52);
  v40 = v57;
  v41 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v57 + 56LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 104);
  v42 = v41(v40, (char *)this + 104);
  if ( v42 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v42,
      v52);
  v43 = (_QWORD *)((char *)this + 96);
  v44 = Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisualTreeIsland>::As<Windows::UI::Composition::ICompositionIsland>(
          (char *)this + 104,
          (char *)this + 96);
  if ( v44 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v44,
      v52);
  v58 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v58);
  v62 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.Composition.CompositionIsland",
    0x29u,
    0x28u);
  ActivationFactory = RoGetActivationFactory(v62, &GUID_77fcc60e_69bd_4d67_8fab_e9787219b184, &v58);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v52);
  v46 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v58 + 48LL))(v58, *((_QWORD *)this + 10), *v43);
  if ( v46 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v46,
      v52);
  v60 = 0;
  v47 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v43 + 88LL))(*v43, &v60);
  if ( v47 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v47,
      v52);
  if ( !(unsigned int)AddVisualIdentifier(*((_QWORD *)this + 1), &v60) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      v48);
  v49 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v15 + 56LL))(
          *v15,
          _mm_unpacklo_ps((__m128)*((unsigned int *)this + 32), (__m128)*((unsigned int *)this + 33)).m128_u64[0]);
  if ( v49 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v49,
      v52);
  v50 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)this + 17) + 288LL))(
          *((_QWORD *)this + 17),
          _mm_unpacklo_ps((__m128)*((unsigned int *)this + 32), (__m128)*((unsigned int *)this + 33)).m128_u64[0]);
  if ( v50 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x122,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)(unsigned int)v50,
      v52);
  LOBYTE(v51) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_NoPlatformScaling>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_NoPlatformScaling>::GetImpl'::`2'::impl,
    v51);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v57);
  return 0;
}

```

## disassembly

```asm
0x1800508e4  mov     [rsp-8+arg_8], rbx
0x1800508e9  push    rbp
0x1800508ea  push    rsi
0x1800508eb  push    rdi
0x1800508ec  push    r12
0x1800508ee  push    r13
0x1800508f0  push    r14
0x1800508f2  push    r15
0x1800508f4  lea     rbp, [rsp-27h]
0x1800508f9  sub     rsp, 90h
0x180050900  mov     rax, cs:__security_cookie
0x180050907  xor     rax, rsp
0x18005090a  mov     [rbp+57h+var_38], rax
0x18005090e  mov     rsi, rcx
0x180050911  mov     ecx, 1
0x180050916  xor     eax, eax
0x180050918  lock cmpxchg [rsi+18h], ecx
0x18005091d  cmp     eax, ecx
0x18005091f  jnz     short loc_180050951
0x180050921  mov     rcx, [rbp+5Fh]; this
0x180050925  lea     rax, aCorewindowIsAl; "CoreWindow is already configured for Co"...
0x18005092c  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180050931  mov     ebx, 80070057h
0x180050936  mov     r9d, ebx; char *
0x180050939  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050940  mov     edx, 9Bh; void *
0x180050945  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005094a  mov     eax, ebx
0x18005094c  jmp     loc_18005103E
0x180050951  mov     [rsi+10h], edx
0x180050954  lea     rbx, [rsi+38h]
0x180050958  mov     rdx, r8
0x18005095b  mov     rcx, rbx
0x18005095e  call    ??4?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUnknown@@@Z; Microsoft::WRL::ComPtr<IUnknown>::operator=(IUnknown *)
0x180050963  xor     r15d, r15d
0x180050966  mov     [rbp+57h+var_78], r15
0x18005096a  lea     rdx, [rbp+57h+var_78]
0x18005096e  mov     rcx, rbx
0x180050971  call    ??$As@UICompositorWithCompositionIslands@Composition@UI@Windows@@@?$ComPtr@UICompositor@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositorWithCompositionIslands@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::ICompositorWithCompositionIslands>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositorWithCompositionIslands>>)
0x180050976  mov     rcx, [rbp+5Fh]; this
0x18005097a  test    eax, eax
0x18005097c  jns     short loc_180050993
0x18005097e  mov     r9d, eax; char *
0x180050981  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050988  mov     edx, 0A9h; void *
0x18005098d  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050993  cmp     [rsi+15h], r15b
0x180050997  jnz     loc_180050A75
0x18005099d  mov     [rbp+57h+var_90], r15
0x1800509a1  lea     rdx, [rbp+57h+var_90]
0x1800509a5  mov     rcx, rbx
0x1800509a8  call    ??$As@UICompositorDesktopInterop@Desktop@Composition@UI@Windows@@@?$ComPtr@UICompositor@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositorDesktopInterop@Desktop@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::Desktop::ICompositorDesktopInterop>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::Desktop::ICompositorDesktopInterop>>)
0x1800509ad  mov     rcx, [rbp+5Fh]; this
0x1800509b1  test    eax, eax
0x1800509b3  jns     short loc_1800509CA
0x1800509b5  mov     r9d, eax; char *
0x1800509b8  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800509bf  mov     edx, 0B1h; void *
0x1800509c4  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800509ca  mov     [rbp+57h+var_88], r15
0x1800509ce  mov     rdi, [rbp+57h+var_90]
0x1800509d2  mov     rax, [rdi]
0x1800509d5  mov     rbx, [rax+18h]
0x1800509d9  lea     rcx, [rbp+57h+var_88]
0x1800509dd  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800509e2  lea     r9, [rbp+57h+var_88]
0x1800509e6  xor     r8d, r8d
0x1800509e9  mov     rdx, [rsi]
0x1800509ec  mov     rcx, rdi
0x1800509ef  mov     rax, rbx
0x1800509f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509f7  mov     ebx, eax
0x1800509f9  test    eax, eax
0x1800509fb  jns     short loc_180050A38
0x1800509fd  mov     rcx, [rbp+5Fh]; this
0x180050a01  mov     r9d, eax; char *
0x180050a04  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050a0b  mov     edx, 0B8h; void *
0x180050a10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050a15  nop
0x180050a16  lea     rcx, [rbp+57h+var_88]
0x180050a1a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050a1f  nop
0x180050a20  lea     rcx, [rbp+57h+var_90]
0x180050a24  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050a29  nop
0x180050a2a  lea     rcx, [rbp+57h+var_78]
0x180050a2e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050a33  jmp     loc_18005094A
0x180050a38  lea     rdx, [rsi+40h]
0x180050a3c  lea     rcx, [rbp+57h+var_88]
0x180050a40  call    ??$As@UICompositionTargetPartner@Private@Composition@UI@Windows@@@?$ComPtr@UIDesktopWindowTarget@Desktop@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionTargetPartner@Private@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::Desktop::IDesktopWindowTarget>::As<Windows::UI::Composition::Private::ICompositionTargetPartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::Private::ICompositionTargetPartner>>)
0x180050a45  mov     rcx, [rbp+5Fh]; this
0x180050a49  test    eax, eax
0x180050a4b  jns     short loc_180050A62
0x180050a4d  mov     r9d, eax; char *
0x180050a50  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050a57  mov     edx, 0BAh; void *
0x180050a5c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050a62  lea     rcx, [rbp+57h+var_88]
0x180050a66  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050a6b  nop
0x180050a6c  lea     rcx, [rbp+57h+var_90]
0x180050a70  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050a75  mov     rcx, rsi; this
0x180050a78  call    ?InitializeRootVisual@CompositionIslandBridge@@AEAAJXZ; CompositionIslandBridge::InitializeRootVisual(void)
0x180050a7d  mov     rcx, [rbp+5Fh]; this
0x180050a81  test    eax, eax
0x180050a83  jns     short loc_180050A9A
0x180050a85  mov     r9d, eax; char *
0x180050a88  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050a8f  mov     edx, 0BDh; void *
0x180050a94  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050a9a  mov     rdi, [rbp+57h+var_78]
0x180050a9e  mov     rax, [rdi]
0x180050aa1  mov     rbx, [rax+30h]
0x180050aa5  lea     r12, [rsi+58h]
0x180050aa9  mov     rcx, r12
0x180050aac  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050ab1  mov     rdx, r12
0x180050ab4  mov     rcx, rdi
0x180050ab7  mov     rax, rbx
0x180050aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050abf  mov     rcx, [rbp+5Fh]; this
0x180050ac3  test    eax, eax
0x180050ac5  jns     short loc_180050ADC
0x180050ac7  mov     r9d, eax; char *
0x180050aca  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050ad1  mov     edx, 0C1h; void *
0x180050ad6  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050adc  lea     rdx, [rsi+50h]
0x180050ae0  mov     rcx, r12
0x180050ae3  call    ??$As@UICompositionIslandSite@Composition@UI@Windows@@@?$ComPtr@UIVisualIslandSite@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionIslandSite@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisualIslandSite>::As<Windows::UI::Composition::ICompositionIslandSite>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandSite>>)
0x180050ae8  mov     rcx, [rbp+5Fh]; this
0x180050aec  test    eax, eax
0x180050aee  jns     short loc_180050B05
0x180050af0  mov     r9d, eax; char *
0x180050af3  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050afa  mov     edx, 0C2h; void *
0x180050aff  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050b05  mov     rdi, [r12]
0x180050b09  mov     rax, [rdi]
0x180050b0c  mov     rbx, [rax+58h]
0x180050b10  lea     r14, [rsi+48h]
0x180050b14  mov     rcx, r14
0x180050b17  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050b1c  mov     rdx, r14
0x180050b1f  mov     rcx, rdi
0x180050b22  mov     rax, rbx
0x180050b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b2a  mov     rcx, [rbp+5Fh]; this
0x180050b2e  test    eax, eax
0x180050b30  jns     short loc_180050B47
0x180050b32  mov     r9d, eax; char *
0x180050b35  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050b3c  mov     edx, 0C4h; void *
0x180050b41  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050b47  mov     rcx, [rsi+90h]
0x180050b4e  mov     rax, [rcx]
0x180050b51  mov     rdx, [r14]
0x180050b54  mov     rax, [rax+40h]
0x180050b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b5d  mov     rcx, [rbp+5Fh]; this
0x180050b61  test    eax, eax
0x180050b63  jns     short loc_180050B7A
0x180050b65  mov     r9d, eax; char *
0x180050b68  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050b6f  mov     edx, 0C6h; void *
0x180050b74  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050b7a  cmp     [rsi+15h], r15b
0x180050b7e  jnz     short loc_180050BB8
0x180050b80  mov     rcx, [rsi+40h]
0x180050b84  mov     rax, [rcx]
0x180050b87  mov     rdx, [rsi+88h]
0x180050b8e  mov     rax, [rax+38h]
0x180050b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b97  mov     rcx, [rbp+5Fh]; this
0x180050b9b  test    eax, eax
0x180050b9d  jns     loc_180050E07
0x180050ba3  mov     r9d, eax; char *
0x180050ba6  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050bad  mov     edx, 0D0h; void *
0x180050bb2  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050bb8  mov     rdi, [rsi+20h]
0x180050bbc  test    rdi, rdi
0x180050bbf  jz      loc_180050D5F
0x180050bc5  cmp     [rsi+28h], r15
0x180050bc9  jz      loc_180050D5F
0x180050bcf  mov     [rbp+57h+var_88], r15
0x180050bd3  mov     rax, [rdi]
0x180050bd6  mov     rbx, [rax+0E0h]
0x180050bdd  xor     edx, edx
0x180050bdf  lea     rcx, [rbp+57h+var_88]
0x180050be3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180050be8  lea     r8, [rbp+57h+var_88]
0x180050bec  mov     rdx, [rsi+28h]
0x180050bf0  mov     rcx, rdi
0x180050bf3  mov     rax, rbx
0x180050bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bfb  mov     rcx, [rbp+5Fh]; this
0x180050bff  test    eax, eax
0x180050c01  jns     short loc_180050C18
0x180050c03  mov     r9d, eax; char *
0x180050c06  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050c0d  mov     edx, 0E8h; void *
0x180050c12  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050c18  mov     [rbp+57h+var_80], r15
0x180050c1c  lea     rdx, [rbp+57h+var_80]
0x180050c20  mov     rcx, r14
0x180050c23  call    ??$As@UICompositionObject@Composition@UI@Windows@@@?$ComPtr@UICompositionIslandPartner@Internal@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::Internal::ICompositionIslandPartner>::As<Windows::UI::Composition::ICompositionObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject>>)
0x180050c28  mov     rcx, [rbp+5Fh]; this
0x180050c2c  test    eax, eax
0x180050c2e  jns     short loc_180050C45
0x180050c30  mov     r9d, eax; char *
0x180050c33  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050c3a  mov     edx, 0EBh; void *
0x180050c3f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050c45  mov     [rbp+57h+var_90], r15
0x180050c49  mov     rdi, [rbp+57h+var_80]
0x180050c4d  mov     rax, [rdi]
0x180050c50  mov     rbx, [rax+30h]
0x180050c54  lea     rcx, [rbp+57h+var_90]
0x180050c58  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050c5d  lea     rdx, [rbp+57h+var_90]
0x180050c61  mov     rcx, rdi
0x180050c64  mov     rax, rbx
0x180050c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c6c  mov     rcx, [rbp+5Fh]; this
0x180050c70  test    eax, eax
0x180050c72  jns     short loc_180050C89
0x180050c74  mov     r9d, eax; char *
0x180050c77  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050c7e  mov     edx, 0EEh; void *
0x180050c83  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050c89  mov     [rbp+57h+var_68], r15
0x180050c8d  lea     rdx, [rbp+57h+var_68]
0x180050c91  lea     rcx, [rbp+57h+var_90]
0x180050c95  call    ??$As@UICompositorPartner@Composition@UI@Windows@@@?$ComPtr@UICompositor@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositorPartner@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::ICompositorPartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositorPartner>>)
0x180050c9a  mov     rcx, [rbp+5Fh]; this
0x180050c9e  test    eax, eax
0x180050ca0  jns     short loc_180050CB7
0x180050ca2  mov     r9d, eax; char *
0x180050ca5  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050cac  mov     edx, 0F1h; void *
0x180050cb1  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050cb7  mov     rdi, [rbp+57h+var_68]
0x180050cbb  mov     rax, [rdi]
0x180050cbe  mov     rbx, [rax+48h]
0x180050cc2  lea     r15, [rsi+30h]
0x180050cc6  mov     rcx, r15
0x180050cc9  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050cce  mov     r8, r15
0x180050cd1  mov     rdx, [rbp+57h+var_88]
0x180050cd5  mov     rcx, rdi
0x180050cd8  mov     rax, rbx
0x180050cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ce0  mov     rcx, [rbp+5Fh]; this
0x180050ce4  test    eax, eax
0x180050ce6  jns     short loc_180050CFD
0x180050ce8  mov     r9d, eax; char *
0x180050ceb  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050cf2  mov     edx, 0F5h; void *
0x180050cf7  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050cfd  mov     rcx, [r15]
0x180050d00  mov     rax, [rcx]
0x180050d03  mov     rdx, [rsi+88h]
0x180050d0a  mov     rax, [rax+20h]
0x180050d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d13  mov     rcx, [rbp+5Fh]; this
0x180050d17  xor     r15d, r15d
0x180050d1a  test    eax, eax
0x180050d1c  jns     short loc_180050D33
0x180050d1e  mov     r9d, eax; char *
0x180050d21  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050d28  mov     edx, 0F7h; void *
0x180050d2d  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050d33  lea     rcx, [rbp+57h+var_68]
0x180050d37  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050d3c  nop
0x180050d3d  lea     rcx, [rbp+57h+var_90]
0x180050d41  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050d46  nop
0x180050d47  lea     rcx, [rbp+57h+var_80]
0x180050d4b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050d50  nop
0x180050d51  lea     rcx, [rbp+57h+var_88]
0x180050d55  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180050d5a  jmp     loc_180050E07
0x180050d5f  mov     [rbp+57h+var_90], r15
0x180050d63  lea     rcx, [rbp+57h+var_90]
0x180050d67  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050d6c  lea     rcx, [rbp+57h+var_90]; struct Windows::ApplicationModel::Core::ICoreApplicationView **
0x180050d70  call    ?GetCoreApplicationViewOfCurrentThread@@YAJPEAPEAUICoreApplicationView@Core@ApplicationModel@Windows@@@Z; GetCoreApplicationViewOfCurrentThread(Windows::ApplicationModel::Core::ICoreApplicationView * *)
0x180050d75  mov     rcx, [rbp+5Fh]; this
0x180050d79  test    eax, eax
0x180050d7b  jns     short loc_180050D92
0x180050d7d  mov     r9d, eax; char *
0x180050d80  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050d87  mov     edx, 0D9h; void *
0x180050d8c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
  ... truncated ...
```
