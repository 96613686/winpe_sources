# CVirtualDesktopManager::SwitchDesktopInternalPrivate(IVirtualDesktop *,VirtualDesktopSwitchType)

- ea: `0x180580384`
- end: `0x180580b33`
- name: `?SwitchDesktopInternalPrivate@CVirtualDesktopManager@@AEAAJPEAUIVirtualDesktop@@W4VirtualDesktopSwitchType@@@Z`
- size: `1967`
- prototype: ``
- caller_count: `6`
- callee_count: `37`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18057da10`
- `0x18057fef0`
- `0x18057ff90`
- `0x180580120`
- `0x180580370`
- `0x180580ed0`

## callees

- `0x1800237c8`
- `0x180031c70`
- `0x1800358f0`
- `0x1800896e0`
- `0x1800912d0`
- `0x1800aed30`
- `0x1800aef08`
- `0x1800c1b9c`
- `0x1800c1c00`
- `0x1800e39c4`
- `0x180118604`
- `0x180118660`
- `0x180163850`
- `0x1801b2690`
- `0x1801c0a78`
- `0x1801c0b64`
- `0x1801d4908`
- `0x1801dbccc`
- `0x1802435f0`
- `0x180243998`
- `0x18026bb3c`
- `0x1802864d8`
- `0x180286a6c`
- `0x1802882f8`
- `0x18028913c`
- `0x1802c3dec`
- `0x1802db0fc`
- `0x1802de09c`
- `0x18032c3bc`
- `0x180356360`
- `0x18057ad5c`
- `0x18057b75c`
- `0x18057b794`
- `0x18057c5a0`
- `0x180580384`
- `0x1805811ac`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805807aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18058080b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180580820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18058084e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805808cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180580959`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18058096a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805807aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18058080b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180580820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18058084e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805808cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180580959`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18058096a`
- `ext-ms-win-ntuser-window-l1-1-3!LockSetForegroundWindow` at `0x180580980`
- `ext-ms-win-ntuser-window-l1-1-3!LockSetForegroundWindow` at `0x180580980`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CVirtualDesktopManager::SwitchDesktopInternalPrivate(
        __int64 a1,
        struct IUnknown *a2,
        unsigned int a3)
{
  unsigned int v3; // r13d
  int CurrentDesktopInternal; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rdx
  struct IVirtualDesktop *v10; // rdi
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // r12d
  __int64 v18; // rax
  int updated; // eax
  __int64 v20; // r14
  __int64 v21; // r13
  _QWORD *v22; // rbx
  __int64 (__fastcall **v23)(struct IVirtualDesktop *, GUID *, __int64 **); // rax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  char v28; // bl
  CVirtualDesktopManager *v29; // rcx
  int CurrentRenderedWallpaperPath; // eax
  HSTRING v31; // rbx
  int v32; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  int v34; // eax
  __int64 v35; // r14
  int (__fastcall *v36)(__int64, HSTRING *); // r12
  HSTRING v37; // rbx
  int v38; // eax
  wil::details::in1diag3 *v39; // rcx
  __int64 v40; // rdx
  __int64 *v41; // r14
  __int64 (__fastcall *v42)(__int64 *, HSTRING *); // r12
  HSTRING v43; // rbx
  int v44; // eax
  int v45; // r14d
  HSTRING v46; // rbx
  int v47; // eax
  int v48; // eax
  int v49; // eax
  unsigned int SwitcherType; // eax
  int v52; // [rsp+20h] [rbp-E0h]
  HSTRING v53; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v54; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  struct IVirtualDesktop *v56; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v57; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v58; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v60; // [rsp+68h] [rbp-98h] BYREF
  __int64 v61; // [rsp+70h] [rbp-90h] BYREF
  struct IUnknown *v62; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h] BYREF
  __int64 v64; // [rsp+88h] [rbp-78h]
  __int128 v65; // [rsp+98h] [rbp-68h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-58h]
  _BYTE v67[56]; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v68; // [rsp+E8h] [rbp-18h]
  _QWORD v69[42]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v3 = a3;
  LODWORD(v53) = a3;
  v62 = 0;
  CurrentDesktopInternal = CVirtualDesktopManager::GetCurrentDesktopInternal(
                             (CVirtualDesktopManager *)(a1 + 8),
                             (struct IVirtualDesktop **)&v62);
  v7 = CurrentDesktopInternal;
  if ( CurrentDesktopInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x240,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)(unsigned int)CurrentDesktopInternal,
      v52);
    goto LABEL_84;
  }
  if ( (unsigned int)SHIsSameObject(a2, v62) )
  {
    v8 = CVirtualDesktopManager::FireVirtualDesktopSwitchedEvent(a1, a2, v3);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x244,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
        (const char *)(unsigned int)v8,
        v52);
    v7 = 0;
    goto LABEL_84;
  }
  wil::ActivityBase<WindowManagementLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WindowManagementLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v69);
  v69[0] = &VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity::`vftable';
  VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity::StartActivity((VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity *)v69);
  if ( *(_DWORD *)(a1 + 204) )
  {
    v7 = -2147019873;
    v9 = 585;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)v7,
      v52);
LABEL_10:
    VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity::~VirtualDesktopSwitchedActivity((VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity *)v69);
    goto LABEL_84;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, struct IUnknown *))(**(_QWORD **)(a1 + 104) + 32LL))(
          *(_QWORD *)(a1 + 104),
          a2) )
  {
    v7 = -2147024809;
    v9 = 586;
    goto LABEL_9;
  }
  if ( !*(_QWORD *)(a1 + 112) )
  {
    v7 = -2147417848;
    v9 = 587;
    goto LABEL_9;
  }
  wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>(
    &v56,
    &v62);
  v10 = v56;
  CVirtualDesktopManager::UpdateCurrentDesktop((CVirtualDesktopManager *)a1, v56, (struct IVirtualDesktop *)a2);
  v54 = 0;
  v11 = *(__int64 **)(a1 + 112);
  v12 = *v11;
  v54 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v12 + 24))(v11, &v54);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 593;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)(unsigned int)v13,
      v52);
LABEL_18:
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v54);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v56);
    goto LABEL_10;
  }
  v57 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v54 + 24))(v54, &v57);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 596;
    goto LABEL_17;
  }
  CVirtualDesktopManager::GetCurrentDesktopCollection(a1, &v63);
  v17 = 0;
  if ( v57 )
  {
    while ( 1 )
    {
      v59 = 0;
      v18 = *v54;
      v59 = 0;
      updated = (*(__int64 (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v18 + 32))(
                  v54,
                  v17,
                  &GUID_372e1d3b_38d3_42e4_a15b_8ab2b178f513,
                  &v59);
      v7 = updated;
      if ( updated < 0 )
        break;
      v65 = 0;
      v66 = 0;
      if ( (v64 - v63) >> 3 )
      {
        std::vector<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>::_Buy_nonzero(&v65);
        v20 = v63;
        v21 = v64;
        v22 = (_QWORD *)v65;
        while ( v20 != v21 )
        {
          wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>(
            v22++,
            v20);
          v20 += 8;
        }
        std::_Destroy_range<std::allocator<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>>(v22, v22);
        *((_QWORD *)&v65 + 1) = v22;
        string = 0;
        std::_Tidy_guard<std::vector<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>>::~_Tidy_guard<std::vector<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>>(&string);
      }
      updated = CVirtualDesktopManager::UpdateViewVisibility(a1, v59, &v65);
      v7 = updated;
      if ( updated < 0 )
      {
        v25 = 602;
        goto LABEL_36;
      }
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v59);
      if ( ++v17 >= v57 )
      {
        v3 = (unsigned int)v53;
        goto LABEL_31;
      }
    }
    v25 = 601;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)(unsigned int)updated,
      v52);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v59);
    goto LABEL_37;
  }
LABEL_31:
  LOBYTE(v16) = 3;
  LOBYTE(v15) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_VwUpdates>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_VwUpdates>::GetImpl'::`2'::impl,
    v15,
    v16);
  v58 = 0;
  v23 = *(__int64 (__fastcall ***)(struct IVirtualDesktop *, GUID *, __int64 **))v10;
  v58 = 0;
  v24 = (*v23)(v10, &GUID_c9be252c_e386_425e_b33c_ca422112f51f, &v58);
  v7 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26A,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)(unsigned int)v24,
      v52);
LABEL_33:
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v58);
LABEL_37:
    std::vector<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>::_Tidy(&v63);
    goto LABEL_18;
  }
  v53 = 0;
  v26 = *v58;
  v53 = 0;
  if ( (*(int (__fastcall **)(__int64 *, HSTRING *))(v26 + 48))(v58, &v53) < 0 || (v28 = 1, v53) )
    v28 = 0;
  LOBYTE(v27) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_VwSotUpdates>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_VwSotUpdates>::GetImpl'::`2'::impl,
    v27);
  if ( v28 && !CVirtualDesktopManager::IsSlideShowEnabled() )
  {
    string = 0;
    CurrentRenderedWallpaperPath = CVirtualDesktopManager::GetCurrentRenderedWallpaperPath(v29, &string);
    v31 = string;
    if ( CurrentRenderedWallpaperPath >= 0 )
    {
      if ( string )
      {
        v32 = CVirtualDesktopManager::AssignWallpaperToDesktop((CVirtualDesktopManager *)a1, v10, string);
        if ( v32 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x273,
            (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
            (const char *)(unsigned int)v32,
            v52);
      }
    }
    if ( v31 )
      WindowsDeleteString(v31);
  }
  v60 = 0;
  lpVtbl = a2->lpVtbl;
  v61 = 0;
  v34 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
          a2,
          &GUID_c9be252c_e386_425e_b33c_ca422112f51f,
          &v61);
  v7 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)(unsigned int)v34,
      v52);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v61);
    if ( v60 )
      WindowsDeleteString(v60);
    if ( v53 )
      WindowsDeleteString(v53);
    goto LABEL_33;
  }
  v35 = v61;
  v36 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v61 + 48LL);
  v37 = v60;
  if ( v60 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&string);
    WindowsDeleteString(v37);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&string);
  }
  v60 = 0;
  if ( v36(v35, &v60) < 0 || !v60 )
  {
    v41 = v58;
    v42 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v58 + 48);
    v43 = v53;
    if ( v53 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&string);
      WindowsDeleteString(v43);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&string);
    }
    v53 = 0;
    v44 = v42(v41, &v53);
    if ( v44 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x282,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
        (const char *)(unsigned int)v44,
        v52);
    v38 = CVirtualDesktopManager::AssignWallpaperToDesktop(
            (CVirtualDesktopManager *)a1,
            (struct IVirtualDesktop *)a2,
            v53);
    v39 = retaddr;
    if ( v38 >= 0 )
      goto LABEL_67;
    v40 = 643;
    goto LABEL_66;
  }
  v38 = CVirtualDesktopManager::SetDesktopWallpaperInternal(
          (CVirtualDesktopManager *)a1,
          (struct IVirtualDesktop *)a2,
          v60);
  v39 = retaddr;
  if ( v38 < 0 )
  {
    v40 = 637;
LABEL_66:
    wil::details::in1diag3::_Log_Hr(
      v39,
      (void *)v40,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)(unsigned int)v38,
      v52);
  }
LABEL_67:
  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v61);
  if ( v60 )
    WindowsDeleteString(v60);
  if ( v53 )
    WindowsDeleteString(v53);
  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v58);
  LockSetForegroundWindow(2u);
  v45 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *))(**(_QWORD **)(a1 + 136) + 24LL))(
          *(_QWORD *)(a1 + 136),
          a2);
  if ( v45 < 0 )
  {
    tip2::open_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_VDSlideAnimationPerfTest,_tip_VDSlideAnimationPerfTest>>>((struct wil::details::IFailureCallback *)v67);
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v68 + 2) )
    {
      v46 = v68;
      string = v68;
      if ( v68 )
        _InterlockedIncrement((volatile signed __int32 *)v68 + 88);
      tip2::details::shared_data<1,0,0>::begin_update(v46 + 2);
      *((_BYTE *)v46 + 280) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_VDSlideAnimationPerfTest,_tip_VDSlideAnimationPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_VDSlideAnimationPerfTest,_tip_VDSlideAnimationPerfTest>>(&string);
      tip2::details::shared_data<1,0,0>::complete_without_lock(v68 + 2);
    }
    tip2::test_watcher<tip2::details::merged_data<_tip_VDSlideAnimationPerfTest,_tip_VDSlideAnimationPerfTest>>::~test_watcher<tip2::details::merged_data<_tip_VDSlideAnimationPerfTest,_tip_VDSlideAnimationPerfTest>>(v67);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x294,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)(unsigned int)v45,
      v52);
  }
  v47 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *))(**(_QWORD **)(a1 + 144) + 32LL))(
          *(_QWORD *)(a1 + 144),
          a2);
  if ( v47 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x297,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)(unsigned int)v47,
      v52);
  v48 = (*(__int64 (__fastcall **)(_QWORD, struct IVirtualDesktop *, struct IUnknown *))(**(_QWORD **)(a1 + 128) + 80LL))(
          *(_QWORD *)(a1 + 128),
          v10,
          a2);
  if ( v48 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x298,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)(unsigned int)v48,
      v52);
  v49 = CVirtualDesktopManager::FireVirtualDesktopSwitchedEvent(a1, a2, v3);
  if ( v49 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x29A,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
      (const char *)(unsigned int)v49,
      v52);
  SwitcherType = CVirtualDesktopManager::GetSwitcherType(a1);
  VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity::Stop(v69, v10, a2, SwitcherType);
  std::vector<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>::_Tidy(&v63);
  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v54);
  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v56);
  VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity::~VirtualDesktopSwitchedActivity((VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity *)v69);
  v7 = 0;
LABEL_84:
  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v62);
  return v7;
}

```

## disassembly

```asm
0x180580384  mov     [rsp-8+arg_18], rbx
0x180580389  push    rbp
0x18058038a  push    rsi
0x18058038b  push    rdi
0x18058038c  push    r12
0x18058038e  push    r13
0x180580390  push    r14
0x180580392  push    r15
0x180580394  lea     rbp, [rsp-150h]
0x18058039c  sub     rsp, 250h
0x1805803a3  mov     rax, cs:__security_cookie
0x1805803aa  xor     rax, rsp
0x1805803ad  mov     [rbp+180h+var_40], rax
0x1805803b4  mov     r13d, r8d
0x1805803b7  mov     dword ptr [rsp+280h+var_250], r8d
0x1805803bc  mov     r15, rdx
0x1805803bf  mov     rsi, rcx
0x1805803c2  xor     r14d, r14d
0x1805803c5  mov     [rsp+280h+var_208], r14
0x1805803ca  add     rcx, 8; this
0x1805803ce  lea     rdx, [rsp+280h+var_208]; struct IVirtualDesktop **
0x1805803d3  call    ?GetCurrentDesktopInternal@CVirtualDesktopManager@@UEAAJPEAPEAUIVirtualDesktop@@@Z; CVirtualDesktopManager::GetCurrentDesktopInternal(IVirtualDesktop * *)
0x1805803d8  mov     ebx, eax
0x1805803da  test    eax, eax
0x1805803dc  jns     short loc_1805803FE
0x1805803de  mov     rcx, [rbp+188h]; this
0x1805803e5  mov     r9d, eax; char *
0x1805803e8  lea     r8, aPcshellTwinuiV_39; "pcshell\\twinui\\virtualdesktops\\lib\\"...
0x1805803ef  mov     edx, 240h; void *
0x1805803f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805803f9  jmp     loc_180580AFD
0x1805803fe  mov     rdx, [rsp+280h+var_208]; struct IUnknown *
0x180580403  mov     rcx, r15; struct IUnknown *
0x180580406  call    ?SHIsSameObject@@YAHPEAUIUnknown@@0@Z; SHIsSameObject(IUnknown *,IUnknown *)
0x18058040b  test    eax, eax
0x18058040d  jz      short loc_180580444
0x18058040f  mov     r8d, r13d
0x180580412  mov     rdx, r15
0x180580415  mov     rcx, rsi
0x180580418  call    ?FireVirtualDesktopSwitchedEvent@CVirtualDesktopManager@@AEAAJPEAUIVirtualDesktop@@W4VirtualDesktopSwitchType@@@Z; CVirtualDesktopManager::FireVirtualDesktopSwitchedEvent(IVirtualDesktop *,VirtualDesktopSwitchType)
0x18058041d  mov     rcx, [rbp+188h]; this
0x180580424  test    eax, eax
0x180580426  jns     short loc_18058043C
0x180580428  mov     r9d, eax; char *
0x18058042b  lea     r8, aPcshellTwinuiV_39; "pcshell\\twinui\\virtualdesktops\\lib\\"...
0x180580432  mov     edx, 244h; void *
0x180580437  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18058043c  mov     ebx, r14d
0x18058043f  jmp     loc_180580AFD
0x180580444  lea     rdx, aVirtualdesktop_7; "VirtualDesktopSwitchedActivity"
0x18058044b  lea     rcx, [rbp+180h+var_190]; struct wil::details::IFailureCallback *
0x18058044f  call    ??0?$ActivityBase@VWindowManagementLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WindowManagementLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WindowManagementLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180580454  lea     rax, ??_7VirtualDesktopSwitchedActivity@VirtualDesktopTelemetry@VirtualDesktop@@6B@; const VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity::`vftable'
0x18058045b  mov     [rbp+180h+var_190], rax
0x18058045f  lea     rcx, [rbp+180h+var_190]; this
0x180580463  call    ?StartActivity@VirtualDesktopSwitchedActivity@VirtualDesktopTelemetry@VirtualDesktop@@QEAAXXZ; VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity::StartActivity(void)
0x180580468  nop
0x180580469  cmp     [rsi+0CCh], r14d
0x180580470  jbe     short loc_1805804A1
0x180580472  mov     ebx, 8007139Fh
0x180580477  mov     edx, 249h; void *
0x18058047c  mov     rcx, [rbp+188h]; this
0x180580483  mov     r9d, ebx; char *
0x180580486  lea     r8, aPcshellTwinuiV_39; "pcshell\\twinui\\virtualdesktops\\lib\\"...
0x18058048d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180580492  nop
0x180580493  lea     rcx, [rbp+180h+var_190]; this
0x180580497  call    ??1VirtualDesktopSwitchedActivity@VirtualDesktopTelemetry@VirtualDesktop@@QEAA@XZ; VirtualDesktop::VirtualDesktopTelemetry::VirtualDesktopSwitchedActivity::~VirtualDesktopSwitchedActivity(void)
0x18058049c  jmp     loc_180580AFD
0x1805804a1  mov     rcx, [rsi+68h]
0x1805804a5  mov     rax, [rcx]
0x1805804a8  mov     rdx, r15
0x1805804ab  mov     rax, [rax+20h]
0x1805804af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805804b4  test    al, al
0x1805804b6  jnz     short loc_1805804C4
0x1805804b8  mov     ebx, 80070057h
0x1805804bd  mov     edx, 24Ah
0x1805804c2  jmp     short loc_18058047C
0x1805804c4  cmp     [rsi+70h], r14
0x1805804c8  jnz     short loc_1805804D6
0x1805804ca  mov     ebx, 80010108h
0x1805804cf  mov     edx, 24Bh
0x1805804d4  jmp     short loc_18058047C
0x1805804d6  lea     rdx, [rsp+280h+var_208]
0x1805804db  lea     rcx, [rsp+280h+var_238]
0x1805804e0  call    ??0?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>(wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy> const &)
0x1805804e5  nop
0x1805804e6  mov     r8, r15; struct IVirtualDesktop *
0x1805804e9  mov     rdi, [rsp+280h+var_238]
0x1805804ee  mov     rdx, rdi; struct IVirtualDesktop *
0x1805804f1  mov     rcx, rsi; this
0x1805804f4  call    ?UpdateCurrentDesktop@CVirtualDesktopManager@@AEAAJPEAUIVirtualDesktop@@0@Z; CVirtualDesktopManager::UpdateCurrentDesktop(IVirtualDesktop *,IVirtualDesktop *)
0x1805804f9  mov     [rsp+280h+var_248], r14
0x1805804fe  mov     rcx, [rsi+70h]
0x180580502  mov     rax, [rcx]
0x180580505  mov     [rsp+280h+var_248], r14
0x18058050a  lea     rdx, [rsp+280h+var_248]
0x18058050f  mov     rax, [rax+18h]
0x180580513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180580518  mov     ebx, eax
0x18058051a  test    eax, eax
0x18058051c  jns     short loc_180580554
0x18058051e  mov     edx, 251h; void *
0x180580523  lea     r8, aPcshellTwinuiV_39; "pcshell\\twinui\\virtualdesktops\\lib\\"...
0x18058052a  mov     r9d, eax; char *
0x18058052d  mov     rcx, [rbp+188h]; this
0x180580534  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180580539  nop
0x18058053a  lea     rcx, [rsp+280h+var_248]; void *
0x18058053f  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x180580544  nop
0x180580545  lea     rcx, [rsp+280h+var_238]; void *
0x18058054a  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x18058054f  jmp     loc_180580493
0x180580554  mov     [rsp+280h+var_230], r14d
0x180580559  mov     rcx, [rsp+280h+var_248]
0x18058055e  mov     rax, [rcx]
0x180580561  lea     rdx, [rsp+280h+var_230]
0x180580566  mov     rax, [rax+18h]
0x18058056a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18058056f  mov     ebx, eax
0x180580571  test    eax, eax
0x180580573  jns     short loc_18058057C
0x180580575  mov     edx, 254h
0x18058057a  jmp     short loc_180580523
0x18058057c  lea     rdx, [rbp+180h+var_200]
0x180580580  mov     rcx, rsi
0x180580583  call    ?GetCurrentDesktopCollection@CVirtualDesktopManager@@AEAA?AV?$vector@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@XZ; CVirtualDesktopManager::GetCurrentDesktopCollection(void)
0x180580588  nop
0x180580589  mov     r12d, r14d
0x18058058c  cmp     [rsp+280h+var_230], r14d
0x180580591  jbe     loc_18058066D
0x180580597  mov     [rsp+280h+var_220], r14
0x18058059c  mov     rcx, [rsp+280h+var_248]
0x1805805a1  mov     rax, [rcx]
0x1805805a4  mov     [rsp+280h+var_220], r14
0x1805805a9  lea     r9, [rsp+280h+var_220]
0x1805805ae  lea     r8, _GUID_372e1d3b_38d3_42e4_a15b_8ab2b178f513
0x1805805b5  mov     edx, r12d
0x1805805b8  mov     rax, [rax+20h]
0x1805805bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805805c1  mov     ebx, eax
0x1805805c3  test    eax, eax
0x1805805c5  js      loc_1805806D7
0x1805805cb  xorps   xmm0, xmm0
0x1805805ce  movdqu  [rbp+180h+var_1E8], xmm0
0x1805805d3  mov     [rbp+180h+var_1D8], r14
0x1805805d7  mov     rdx, [rbp+180h+var_1F8]
0x1805805db  sub     rdx, [rbp+180h+var_200]
0x1805805df  sar     rdx, 3
0x1805805e3  test    rdx, rdx
0x1805805e6  jz      short loc_180580635
0x1805805e8  lea     rcx, [rbp+180h+var_1E8]
0x1805805ec  call    ?_Buy_nonzero@?$vector@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAX_K@Z; std::vector<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>::_Buy_nonzero(unsigned __int64)
0x1805805f1  mov     r14, [rbp+180h+var_200]
0x1805805f5  mov     r13, [rbp+180h+var_1F8]
0x1805805f9  mov     rbx, qword ptr [rbp+180h+var_1E8]
0x1805805fd  jmp     short loc_18058060F
0x1805805ff  mov     rdx, r14
0x180580602  call    ??0?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>(wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy> const &)
0x180580607  add     rbx, 8
0x18058060b  add     r14, 8
0x18058060f  mov     rcx, rbx
0x180580612  cmp     r14, r13
0x180580615  jnz     short loc_1805805FF
0x180580617  mov     rdx, rbx
0x18058061a  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>>(wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy> *,wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>> &)
0x18058061f  mov     qword ptr [rbp+180h+var_1E8+8], rbx
0x180580623  xor     r14d, r14d
0x180580626  mov     [rsp+280h+string], r14
0x18058062b  lea     rcx, [rsp+280h+string]
0x180580630  call    ??1?$_Tidy_guard@V?$vector@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>>::~_Tidy_guard<std::vector<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>>(void)
0x180580635  lea     r8, [rbp+180h+var_1E8]
0x180580639  mov     rdx, [rsp+280h+var_220]
0x18058063e  mov     rcx, rsi
0x180580641  call    ?UpdateViewVisibility@CVirtualDesktopManager@@AEAAJPEAUIApplicationView@@V?$vector@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@Z; CVirtualDesktopManager::UpdateViewVisibility(IApplicationView *,std::vector<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>)
0x180580646  mov     ebx, eax
0x180580648  test    eax, eax
0x18058064a  js      loc_1805806D0
0x180580650  lea     rcx, [rsp+280h+var_220]; void *
0x180580655  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x18058065a  inc     r12d
0x18058065d  cmp     r12d, [rsp+280h+var_230]
0x180580662  jb      loc_180580597
0x180580668  mov     r13d, dword ptr [rsp+280h+var_250]
0x18058066d  mov     r8b, 3
0x180580670  mov     dl, 1
0x180580672  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VwUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VwUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VwUpdates> `wil::Feature<__WilFeatureTraits_Feature_VwUpdates>::GetImpl(void)'::`2'::impl
0x180580679  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_VwUpdates@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VwUpdates>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18058067e  mov     [rsp+280h+var_228], r14
0x180580683  mov     rax, [rdi]
0x180580686  mov     [rsp+280h+var_228], r14
0x18058068b  lea     r8, [rsp+280h+var_228]
0x180580690  lea     rdx, _GUID_c9be252c_e386_425e_b33c_ca422112f51f
0x180580697  mov     rcx, rdi
0x18058069a  mov     rax, [rax]
0x18058069d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805806a2  mov     ebx, eax
0x1805806a4  test    eax, eax
0x1805806a6  jns     short loc_18058070C
0x1805806a8  mov     rcx, [rbp+188h]; this
0x1805806af  mov     r9d, eax; char *
0x1805806b2  lea     r8, aPcshellTwinuiV_39; "pcshell\\twinui\\virtualdesktops\\lib\\"...
0x1805806b9  mov     edx, 26Ah; void *
0x1805806be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805806c3  nop
0x1805806c4  lea     rcx, [rsp+280h+var_228]; void *
0x1805806c9  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1805806ce  jmp     short loc_1805806FE
0x1805806d0  mov     edx, 25Ah
0x1805806d5  jmp     short loc_1805806DC
0x1805806d7  mov     edx, 259h; void *
0x1805806dc  lea     r8, aPcshellTwinuiV_39; "pcshell\\twinui\\virtualdesktops\\lib\\"...
0x1805806e3  mov     r9d, eax; char *
0x1805806e6  mov     rcx, [rbp+188h]; this
0x1805806ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805806f2  nop
0x1805806f3  lea     rcx, [rsp+280h+var_220]; void *
0x1805806f8  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1805806fd  nop
0x1805806fe  lea     rcx, [rbp+180h+var_200]
0x180580702  call    ?_Tidy@?$vector@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIVirtualDesktop@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>>::_Tidy(void)
0x180580707  jmp     loc_18058053A
0x18058070c  mov     [rsp+280h+var_250], r14
0x180580711  mov     rcx, [rsp+280h+var_228]
0x180580716  mov     rax, [rcx]
0x180580719  mov     [rsp+280h+var_250], r14
0x18058071e  lea     rdx, [rsp+280h+var_250]
0x180580723  mov     rax, [rax+30h]
0x180580727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18058072c  test    eax, eax
0x18058072e  js      short loc_180580739
0x180580730  cmp     [rsp+280h+var_250], r14
0x180580735  mov     bl, 1
0x180580737  jz      short loc_18058073C
0x180580739  mov     bl, r14b
0x18058073c  mov     dl, 1
0x18058073e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VwSotUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VwSotUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VwSotUpdates> `wil::Feature<__WilFeatureTraits_Feature_VwSotUpdates>::GetImpl(void)'::`2'::impl
0x180580745  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_VwSotUpdates@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VwSotUpdates>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18058074a  test    bl, bl
0x18058074c  jz      short loc_1805807B0
0x18058074e  call    ?IsSlideShowEnabled@CVirtualDesktopManager@@CA_NXZ; CVirtualDesktopManager::IsSlideShowEnabled(void)
0x180580753  test    al, al
0x180580755  jnz     short loc_1805807B0
0x180580757  mov     [rsp+280h+string], r14
0x18058075c  lea     rdx, [rsp+280h+string]; HSTRING *
0x180580761  call    ?GetCurrentRenderedWallpaperPath@CVirtualDesktopManager@@AEAAJPEAPEAUHSTRING__@@@Z; CVirtualDesktopManager::GetCurrentRenderedWallpaperPath(HSTRING__ * *)
0x180580766  mov     rbx, [rsp+280h+string]
0x18058076b  test    eax, eax
0x18058076d  js      short loc_1805807A2
0x18058076f  test    rbx, rbx
0x180580772  jz      short loc_1805807A2
0x180580774  mov     r8, rbx; HSTRING
0x180580777  mov     rdx, rdi; struct IVirtualDesktop *
0x18058077a  mov     rcx, rsi; this
0x18058077d  call    ?AssignWallpaperToDesktop@CVirtualDesktopManager@@AEAAJPEAUIVirtualDesktop@@PEAUHSTRING__@@@Z; CVirtualDesktopManager::AssignWallpaperToDesktop(IVirtualDesktop *,HSTRING__ *)
0x180580782  mov     rcx, [rbp+188h]; this
0x180580789  test    eax, eax
0x18058078b  jns     short loc_1805807A2
0x18058078d  mov     r9d, eax; char *
0x180580790  lea     r8, aPcshellTwinuiV_39; "pcshell\\twinui\\virtualdesktops\\lib\\"...
0x180580797  mov     edx, 273h; void *
0x18058079c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1805807a1  nop
0x1805807a2  test    rbx, rbx
0x1805807a5  jz      short loc_1805807B0
0x1805807a7  mov     rcx, rbx; string
0x1805807aa  call    cs:__imp_WindowsDeleteString
0x1805807b0  mov     [rsp+280h+var_218], r14
0x1805807b5  mov     rax, [r15]
0x1805807b8  mov     [rsp+280h+var_210], r14
0x1805807bd  lea     r8, [rsp+280h+var_210]
0x1805807c2  lea     rdx, _GUID_c9be252c_e386_425e_b33c_ca422112f51f
0x1805807c9  mov     rcx, r15
0x1805807cc  mov     rax, [rax]
0x1805807cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805807d4  mov     ebx, eax
0x1805807d6  test    eax, eax
0x1805807d8  jns     short loc_18058082B
0x1805807da  mov     rcx, [rbp+188h]; this
0x1805807e1  mov     r9d, eax; char *
0x1805807e4  lea     r8, aPcshellTwinuiV_39; "pcshell\\twinui\\virtualdesktops\\lib\\"...
0x1805807eb  mov     edx, 279h; void *
0x1805807f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805807f5  nop
0x1805807f6  lea     rcx, [rsp+280h+var_210]; void *
0x1805807fb  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x180580800  nop
0x180580801  mov     rcx, [rsp+280h+var_218]; string
0x180580806  test    rcx, rcx
0x180580809  jz      short loc_180580812
0x18058080b  call    cs:__imp_WindowsDeleteString
0x180580811  nop
0x180580812  mov     rcx, [rsp+280h+var_250]; string
0x180580817  test    rcx, rcx
0x18058081a  jz      loc_1805806C4
0x180580820  call    cs:__imp_WindowsDeleteString
0x180580826  jmp     loc_1805806C4
0x18058082b  mov     r14, [rsp+280h+var_210]
  ... truncated ...
```
