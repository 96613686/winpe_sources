# WindowEventDispatcher::AppViewActivationRequested(Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *)

- ea: `0x180295440`
- end: `0x180296731`
- name: `?AppViewActivationRequested@WindowEventDispatcher@@UEAAJPEAUIAppViewActivationRequestedEventArgs@WindowManagement@ApplicationModel@Internal@Windows@@@Z`
- size: `4849`
- prototype: `__int64 __fastcall(WindowEventDispatcher *__hidden this, struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *)`
- caller_count: `0`
- callee_count: `54`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800134f8`
- `0x180019a38`
- `0x1800237c8`
- `0x180023b60`
- `0x180031c70`
- `0x1800358f0`
- `0x180040c14`
- `0x180041500`
- `0x180043f00`
- `0x180045dfc`
- `0x1800579dc`
- `0x18006c2dc`
- `0x18007b000`
- `0x18007b3e0`
- `0x18007f488`
- `0x1800912d0`
- `0x1800922a0`
- `0x1800c651c`
- `0x1800ecfc0`
- `0x1800edeb4`
- `0x1800f12f4`
- `0x1801132d0`
- `0x180160740`
- `0x18018212c`
- `0x1801a5050`
- `0x1801a512c`
- `0x1801a8b00`
- `0x1801cdc40`
- `0x1801e9504`
- `0x180274b28`
- `0x180292044`
- `0x1802931ec`
- `0x180293364`
- `0x180293e54`
- `0x1802948d4`
- `0x18029494c`
- `0x180294a4c`
- `0x180295440`
- `0x180296740`
- `0x1802967c0`
- `0x1802969a4`
- `0x1802969c0`
- `0x180296a4c`
- `0x180296ae4`
- `0x180296b00`
- `0x18031ac88`
- `0x18034b448`
- `0x180356360`
- `0x180356384`
- `0x180477a50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180296059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180296059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180295845`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1802959a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180295b7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180295845`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1802959a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180295b7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180295c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180295c4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180295eaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180295c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180295c4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180295eaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180295cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180295cf8`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
__int64 __fastcall WindowEventDispatcher::AppViewActivationRequested(
        WindowEventDispatcher *this,
        struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *a2)
{
  struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *v2; // r12
  WindowEventDispatcher *v4; // r13
  __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r8
  char v17; // al
  __int64 (__fastcall *v18)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, struct IWindowWrapperInternal **); // rbx
  int v19; // eax
  __int64 AppViewStatics; // rax
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, struct IWindowWrapperInternal *, void **); // rdi
  int v23; // eax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 (__fastcall *v27)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, __int64 *); // rbx
  int v28; // eax
  struct IWindowWrapperInternal *v29; // rbx
  __int64 v30; // rax
  __int64 v31; // r8
  bool v32; // sf
  unsigned __int8 v33; // r8
  char v34; // al
  __int64 CachedView; // rax
  __int64 v36; // rax
  int v37; // eax
  int v38; // eax
  __int64 v39; // rbx
  int v40; // eax
  char v41; // di
  __int64 v42; // rax
  __int64 v43; // rax
  int v44; // eax
  char v45; // r15
  __int64 v46; // rax
  RTL_SRWLOCK **StringWithDefault; // rax
  RTL_SRWLOCK *v48; // rsi
  bool v49; // r15
  struct Windows::Internal::ApplicationModel::WindowManagement::IAppView *v50; // rdi
  __int64 (__fastcall *v51)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppView *, void **); // rbx
  int v52; // eax
  int v53; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  unsigned int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // eax
  __int64 v61; // rax
  __int64 v62; // rdi
  __int64 v63; // rax
  __int64 EventRegistration; // rax
  __int64 v65; // rdi
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // r8
  std::_Ref_count_base *v69; // rdi
  RTL_SRWLOCK *v70; // rcx
  __int64 (__fastcall *v71)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, _QWORD); // rsi
  __int64 v72; // rax
  int v73; // eax
  int v74; // eax
  int v75; // eax
  int (__fastcall ***v76)(void *, GUID *, __int64 *); // rdi
  int v77; // eax
  const char *v78; // r9
  int (__fastcall *v79)(void *, GUID *, __int64 *); // rsi
  int v80; // eax
  unsigned int v81; // esi
  RTL_SRWLOCK *v82; // rdi
  RTL_SRWLOCK *v83; // rax
  RTL_SRWLOCK *v84; // r15
  __int64 v85; // r9
  int v86; // eax
  int View; // eax
  int v88; // eax
  int v89; // eax
  int v90; // eax
  __int64 v91; // rdx
  int v92; // eax
  __int64 v93; // r8
  __int64 v94; // rdx
  int v95; // eax
  int v96; // eax
  PSRWLOCK *v97; // [rsp+20h] [rbp-2E8h]
  char v98; // [rsp+50h] [rbp-2B8h] BYREF
  _BYTE v99[7]; // [rsp+51h] [rbp-2B7h] BYREF
  void *v100; // [rsp+58h] [rbp-2B0h] BYREF
  PSRWLOCK v101; // [rsp+60h] [rbp-2A8h] BYREF
  struct IWindowWrapperInternal *v102; // [rsp+68h] [rbp-2A0h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp-298h] BYREF
  PSRWLOCK v104; // [rsp+78h] [rbp-290h] BYREF
  void *v105; // [rsp+80h] [rbp-288h] BYREF
  unsigned int v106; // [rsp+88h] [rbp-280h] BYREF
  int v107[2]; // [rsp+90h] [rbp-278h] BYREF
  _BYTE v108[8]; // [rsp+98h] [rbp-270h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v109; // [rsp+A0h] [rbp-268h] BYREF
  struct Windows::Internal::ApplicationModel::WindowManagement::IAppView *v110; // [rsp+A8h] [rbp-260h] BYREF
  __int64 v111; // [rsp+B0h] [rbp-258h] BYREF
  int v112; // [rsp+B8h] [rbp-250h] BYREF
  int v113; // [rsp+BCh] [rbp-24Ch] BYREF
  __int64 v114; // [rsp+C0h] [rbp-248h] BYREF
  __int64 *v115; // [rsp+C8h] [rbp-240h] BYREF
  __int64 v116; // [rsp+D0h] [rbp-238h] BYREF
  __int64 v117; // [rsp+D8h] [rbp-230h] BYREF
  struct Windows::Internal::ApplicationModel::WindowManagement::IAppModel *v118; // [rsp+E0h] [rbp-228h] BYREF
  void *v119; // [rsp+E8h] [rbp-220h] BYREF
  void *v120; // [rsp+F0h] [rbp-218h] BYREF
  void *v121; // [rsp+F8h] [rbp-210h] BYREF
  struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *v122; // [rsp+100h] [rbp-208h]
  _QWORD v123[2]; // [rsp+108h] [rbp-200h] BYREF
  WindowEventDispatcher *v124; // [rsp+118h] [rbp-1F0h]
  HSTRING_HEADER v125; // [rsp+120h] [rbp-1E8h] BYREF
  __int64 v126; // [rsp+138h] [rbp-1D0h]
  void *v127; // [rsp+140h] [rbp-1C8h] BYREF
  std::_Ref_count_base *v128; // [rsp+148h] [rbp-1C0h]
  std::_Ref_count_base *v129[2]; // [rsp+160h] [rbp-1A8h] BYREF
  _BYTE v130[336]; // [rsp+180h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  v2 = a2;
  v122 = a2;
  LODWORD(v104) = 0;
  ViewManagerInteropTraceLogging::WindowEventDispatcher_AppViewActivationRequested::Start<>((ViewManagerInteropTraceLogging::WindowEventDispatcher_AppViewActivationRequested *)v130);
  v4 = (WindowEventDispatcher *)((char *)this - 16);
  v5 = *(_QWORD *)v2;
  if ( !*((_BYTE *)this + 480) )
  {
    v96 = (*(__int64 (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, __int64))(v5 + 112))(
            v2,
            2150039860LL);
    if ( v96 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x374,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
        (const char *)(unsigned int)v96,
        (int)v97);
    wil::ActivityBase<ViewManagerInteropLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v130, 2150039860LL);
    goto LABEL_141;
  }
  v124 = (WindowEventDispatcher *)((char *)this - 16);
  v115 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, GUID *, __int64 **))v5)(
         v2,
         &GUID_5c19477e_81ef_4d21_baa4_c3040ad2ea6b,
         &v115);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x253,
      (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
      (const char *)(unsigned int)v6,
      (int)v97);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v115);
    ViewManagerInteropTraceLogging::WindowEventDispatcher_AppViewActivationRequested::~WindowEventDispatcher_AppViewActivationRequested((ViewManagerInteropTraceLogging::WindowEventDispatcher_AppViewActivationRequested *)v130);
    return v7;
  }
  try
  {
    v110 = 0;
    v9 = *v115;
    v110 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, struct Windows::Internal::ApplicationModel::WindowManagement::IAppView **))(v9 + 48))(
            v115,
            &v110);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x258,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
        (const char *)(unsigned int)v10,
        (int)v97);
    v107[0] = 0;
    v118 = 0;
    if ( IsComponentAppViewAndGetKindAndModel(
           v110,
           (enum Windows::Internal::ApplicationModel::WindowManagement::AppModelKind *)v107,
           &v118) )
    {
      goto LABEL_136;
    }
    v106 = 0;
    v11 = (*(__int64 (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppView *, unsigned int *))(*(_QWORD *)v110 + 48LL))(
            v110,
            &v106);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25F,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
        (const char *)(unsigned int)v11,
        (int)v97);
    v12 = *(_QWORD *)v2;
    v109 = 0;
    v13 = (*(__int64 (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, struct Windows::Foundation::Collections::IPropertySet **))(v12 + 64))(
            v2,
            &v109);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x262,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
        (const char *)(unsigned int)v13,
        (int)v97);
    Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(
      (Windows::Internal::ShellHelpers::PropertySetHelper *)v108,
      v109);
    v112 = 0;
    LOBYTE(v14) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddSourceWindowFromViewNavigationRequested>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AddSourceWindowFromViewNavigationRequested>::GetImpl'::`2'::impl,
      v14);
    v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v129, off_180713F28);
    LODWORD(v104) = 1;
    if ( (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned int>(
                v108,
                *(_QWORD *)(v15 + 24),
                v16,
                &v112) < 0
      || (v17 = 0, !v112) )
    {
      v17 = 1;
    }
    if ( v17 )
    {
      v102 = 0;
      v18 = *(__int64 (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, struct IWindowWrapperInternal **))(*(_QWORD *)v2 + 56LL);
      wil::com_ptr_t<IUwpWindowWrapperInternal,wil::err_exception_policy>::reset(&v102);
      v19 = v18(v2, &v102);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x26E,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
          (const char *)(unsigned int)v19,
          (int)v97);
      if ( v102 )
      {
        v100 = 0;
        AppViewStatics = WindowEventDispatcher::GetAppViewStatics((char *)this - 16, &SRWLock);
        v21 = *(_QWORD *)AppViewStatics;
        v22 = *(__int64 (__fastcall **)(__int64, struct IWindowWrapperInternal *, void **))(**(_QWORD **)AppViewStatics
                                                                                          + 120LL);
        v100 = 0;
        v23 = v22(v21, v102, &v100);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x272,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v23,
            (int)v97);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&SRWLock);
        LODWORD(v104) = 0;
        v24 = (*(__int64 (__fastcall **)(void *, PSRWLOCK *))(*(_QWORD *)v100 + 48LL))(v100, &v104);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x275,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v24,
            (int)v97);
        Microsoft::WRL::Wrappers::SRWLock::LockShared(&SRWLock, (char *)this + 456);
        WindowEventDispatcher::GetCachedView((char *)this - 16, &v111, (unsigned int)v104);
        if ( v111 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 256LL))(v111);
          v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v129, off_180713F28);
          v26 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(
                  (Windows::Internal::ShellHelpers::PropertySetHelper *)v108,
                  *(HSTRING *)(v25 + 24));
          if ( v26 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x27E,
              (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
              (const char *)(unsigned int)v26,
              (int)v97);
        }
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v111);
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v100);
      }
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v102);
    }
    v117 = 0;
    v27 = *(__int64 (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, __int64 *))(*(_QWORD *)v2 + 80LL);
    wil::com_ptr_t<IUwpWindowWrapperInternal,wil::err_exception_policy>::reset(&v117);
    v28 = v27(v2, &v117);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x284,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
        (const char *)(unsigned int)v28,
        (int)v97);
    v99[0] = 0;
    v29 = 0;
    v102 = 0;
    *(_OWORD *)v129 = 0;
    v111 = 0;
    v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v125, &off_180713F30);
    v98 = 0;
    v32 = (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned char>(
                 v108,
                 *(_QWORD *)(v30 + 24),
                 v31,
                 &v98) < 0;
    v34 = 1;
    if ( !v32 )
      v34 = v98;
    if ( !v34 )
    {
      if ( v109 )
      {
        v44 = Windows::Internal::Shell::Desktop::ViewManagerInterop::SetAppActivationPolicy(
                (Windows::Internal::Shell::Desktop::ViewManagerInterop *)v108,
                0,
                v33);
        if ( v44 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2CE,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v44,
            (int)v97);
      }
      goto LABEL_59;
    }
    Microsoft::WRL::Wrappers::SRWLock::LockShared(&v101, (char *)this + 456);
    CachedView = WindowEventDispatcher::GetCachedView((char *)this - 16, &SRWLock, v106);
    wil::com_ptr_t<IWindowWrapperInternal,wil::err_exception_policy>::operator=(&v102, CachedView);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&SRWLock);
    v29 = v102;
    if ( v102 )
    {
      v36 = (*(__int64 (__fastcall **)(struct IWindowWrapperInternal *, HSTRING_HEADER *))(*(_QWORD *)v102 + 264LL))(
              v102,
              &v125);
      std::shared_ptr<KBViewInfo>::operator=(v129, v36);
      if ( *(_QWORD *)&v125.Reserved.Reserved2[8] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v125.Reserved.Reserved2[8]);
    }
    if ( v101 )
      ReleaseSRWLockShared(v101);
    if ( !v29 )
    {
LABEL_59:
      v45 = 0;
      wil::AcquireSRWLockExclusive(&v125, (char *)this + 456);
      if ( !v29 )
      {
        SRWLock = 0;
        v46 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v127, off_180750618);
        StringWithDefault = (RTL_SRWLOCK **)Windows::Internal::ShellHelpers::PropertySetHelper::GetStringWithDefault(
                                              v108,
                                              &v101,
                                              *(_QWORD *)(v46 + 24),
                                              L"Windows.Internal.ShellExperience.TopLevelApplication");
        v48 = *StringWithDefault;
        *StringWithDefault = 0;
        WindowsDeleteString(0);
        SRWLock = v48;
        WindowsDeleteString((HSTRING)v101);
        v49 = v107[0] == 0;
        v100 = 0;
        v50 = v110;
        v51 = *(__int64 (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppView *, void **))(*(_QWORD *)v110 + 64LL);
        wil::com_ptr_t<IUwpWindowWrapperInternal,wil::err_exception_policy>::reset(&v100);
        v52 = v51(v50, &v100);
        if ( v52 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2DE,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v52,
            (int)v97);
        LODWORD(v104) = 0;
        if ( v100 )
        {
          v53 = (*(__int64 (__fastcall **)(void *, PSRWLOCK *))(*(_QWORD *)v100 + 80LL))(v100, &v104);
          if ( v53 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2E2,
              (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
              (const char *)(unsigned int)v53,
              (int)v97);
        }
        LODWORD(v105) = 0;
        StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)v48, 0);
        if ( v49 )
        {
          v120 = (void *)StringRawBuffer;
          v121 = v100;
          v123[0] = v118;
          v119 = v110;
          v127 = v4;
          v55 = wil::MakeOrThrow<LegacyWindowWrapper,WindowEventDispatcher *,Windows::Internal::ApplicationModel::WindowManagement::IAppView *,Windows::Internal::ApplicationModel::WindowManagement::IAppModel *,enum Windows::Internal::ApplicationModel::WindowManagement::AppModelKind &,Windows::Internal::ApplicationModel::WindowManagement::AppViewId &,Windows::Internal::ApplicationModel::WindowManagement::IWindow *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &,unsigned short const *,enum WindowCreatedType>(
                  (unsigned int)&v101,
                  (unsigned int)&v127,
                  (unsigned int)&v119,
                  (unsigned int)v123,
                  (__int64)v107,
                  (__int64)&v106,
                  (__int64)&v121,
                  (__int64)&v104,
                  (__int64)&v120,
                  (__int64)&v105);
          wil::com_ptr_t<IWindowWrapperInternal,wil::err_exception_policy>::operator=<LegacyWindowWrapper,void>(
            &v102,
            v55);
          if ( v101 )
          {
            v101 = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,WindowWrapperBase,ILegacyViewWrapper>::Release();
          }
        }
        else
        {
          v127 = (void *)StringRawBuffer;
          v119 = v100;
          v123[0] = v118;
          v121 = v110;
          v120 = v4;
          v56 = wil::MakeOrThrow<WindowWrapper,WindowEventDispatcher *,Windows::Internal::ApplicationModel::WindowManagement::IAppView *,Windows::Internal::ApplicationModel::WindowManagement::IAppModel *,enum Windows::Internal::ApplicationModel::WindowManagement::AppModelKind &,Windows::Internal::ApplicationModel::WindowManagement::AppViewId &,Windows::Internal::ApplicationModel::WindowManagement::IWindow *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &,unsigned short const *,enum WindowCreatedType>(
                  (unsigned int)&v101,
                  (unsigned int)&v120,
                  (unsigned int)&v121,
                  (unsigned int)v123,
                  (__int64)v107,
                  (__int64)&v106,
                  (__int64)&v119,
                  (__int64)&v104,
                  (__int64)&v127,
                  (__int64)&v105);
          wil::com_ptr_t<IWindowWrapperInternal,wil::err_exception_policy>::operator=<LegacyWindowWrapper,void>(
            &v102,
            v56);
          if ( v101 )
          {
            v101 = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,WindowWrapperBase,IUAPViewWrapper,Windows::Internal::Shell::ViewManagerInterop::IViewWrapperSplashScreenSupport>::Release();
          }
        }
        v45 = 1;
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v100);
        if ( v48 )
          WindowsDeleteString((HSTRING)v48);
        v29 = v102;
      }
      v57 = (*(__int64 (__fastcall **)(struct IWindowWrapperInternal *))(*(_QWORD *)v29 + 288LL))(v29);
      v58 = (*(__int64 (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, _QWORD))(*(_QWORD *)v2 + 88LL))(
              v2,
              v57);
      if ( v58 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x305,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
          (const char *)(unsigned int)v58,
          (int)v97);
      v59 = (*(__int64 (__fastcall **)(struct IWindowWrapperInternal *, __int64))(*(_QWORD *)v29 + 152LL))(v29, v117);
      if ( v59 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x307,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
          (const char *)(unsigned int)v59,
          (int)v97);
      v60 = (*(__int64 (__fastcall **)(struct IWindowWrapperInternal *, struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *))(*(_QWORD *)v29 + 168LL))(
              v29,
              v2);
      if ( v60 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x308,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
          (const char *)(unsigned int)v60,
          (int)v97);
      v61 = *(_QWORD *)v29;
      if ( v45 )
      {
        v62 = (*(__int64 (__fastcall **)(struct IWindowWrapperInternal *))(v61 + 280))(v29);
        v63 = (*(__int64 (__fastcall **)(struct IWindowWrapperInternal *))(*(_QWORD *)v29 + 272LL))(v29);
        EventRegistration = WindowEventDispatcher::GetEventRegistration(v4, &v127, v63, v62);
        std::shared_ptr<KBViewInfo>::operator=(v129, EventRegistration);
        if ( v128 )
          std::_Ref_count_base::_Decref(v128);
        v65 = std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(v123, v129);
        v66 = wil::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>::com_ptr_t<IVirtualDesktop,wil::err_returncode_policy>(
                &v127,
                &v102);
        WindowEventDispatcher::CacheWindowWrapper(v4, v66, v65, 0);
      }
      else
      {
        v67 = (*(__int64 (__fastcall **)(struct IWindowWrapperInternal *, void **))(v61 + 264))(v29, &v127);
        std::shared_ptr<KBViewInfo>::operator=(v129, v67);
        if ( v128 )
          std::_Ref_count_base::_Decref(v128);
      }
      if ( v125.Reserved.Reserved1 )
        ReleaseSRWLockExclusive((PSRWLOCK)v125.Reserved.Reserved1);
      wil::com_ptr_t<IWindowWrapperInternal,wil::err_exception_policy>::query<Windows::Internal::Shell::ViewManagerInterop::IViewWrapper>(
        &v102,
        &v116);
      v113 = 0;
      v126 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &v125,
        L"AAMShim.ActivateOptionsInternal",
        0x20u,
        0x1Fu);
      if ( (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned int>(v108, v126, v68, &v113) >= 0
        && (v113 & 0x200000) != 0 )
      {
        v69 = v129[0];
        v70 = (RTL_SRWLOCK *)*((_QWORD *)v129[0] + 3);
        v101 = v70;
        if ( v70 )
          (*((void (__fastcall **)(RTL_SRWLOCK *))v70->Ptr + 1))(v70);
        WindowEventDispatcher::EnsureDuplicateViewDestroyed((__int64)v4, v116, (HSTRING *)&v101);
      }
      else
      {
        v69 = v129[0];
      }
      (*(void (__fastcall **)(struct IWindowWrapperInternal *))(*(_QWORD *)v29 + 360LL))(v29);
      if ( v45 )
      {
        v101 = (PSRWLOCK)*((_QWORD *)v69 + 3);
        if ( v101 )
          (*((void (__fastcall **)(PSRWLOCK))v101->Ptr + 1))(v101);
        v97 = &v101;
        WindowEventDispatcher::RaiseViewEventWithPropertySet(v4, v116, 0);
      }
      v71 = *(__int64 (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, _QWORD))(*(_QWORD *)v2 + 104LL);
      v125.Reserved.Reserved1 = (PVOID)(*(__int64 (__fastcall **)(struct IWindowWrapperInternal *))(*(_QWORD *)v29
                                                                                                  + 280LL))(v29);
      v72 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v127, &v125);
      v73 = v71(v2, *(_QWORD *)(v72 + 24));
      if ( v73 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x334,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
          (const char *)(unsigned int)v73,
          (int)v97);
      v125.Reserved.Reserved1 = v109;
      v105 = 0;
      v74 = Microsoft::WRL::Details::MakeAndInitialize<ViewEventArgsForNavigationRequest,Windows::Internal::Shell::ViewManagerInterop::IViewEventArgs,Windows::Foundation::Collections::IPropertySet *>(
              &v105,
              &v125);
      if ( v74 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x338,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
          (const char *)(unsigned int)v74,
          (int)v97);
      try
      {
        v100 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v100);
        v75 = AgileGitPtr::CopyLocal(
                (std::_Ref_count_base *)((char *)v69 + 24),
                &GUID_c1659867_0cf6_5f3b_99df_4f036280926c,
                &v100);
        if ( v75 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x33D,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v75,
            (int)v97);
        v76 = (int (__fastcall ***)(void *, GUID *, __int64 *))v105;
        v77 = (*(__int64 (__fastcall **)(void *, __int64, void *))(*(_QWORD *)v100 + 24LL))(v100, v116, v105);
        if ( v77 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x33F,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v77,
            (int)v97);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v100);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x341,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
          v78);
        v29 = v102;
        v76 = (int (__fastcall ***)(void *, GUID *, __int64 *))v105;
        v4 = v124;
        v2 = v122;
      }
      v114 = 0;
      v79 = **v76;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v114);
      if ( v79(v76, &GUID_a8d2a90c_a403_4593_95ff_012516ae9351, &v114) >= 0 )
      {
        LODWORD(v104) = 0;
        v80 = (*(__int64 (__fastcall **)(__int64, PSRWLOCK *))(*(_QWORD *)v114 + 48LL))(v114, &v104);
        if ( v80 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x348,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v80,
            (int)v97);
        v81 = (unsigned int)v104;
        v82 = 0;
        SRWLock = 0;
        v83 = (RTL_SRWLOCK *)operator new(0xB8u, (const struct std::nothrow_t *)std::nothrow);
        v101 = v83;
        v84 = 0;
        if ( v83 )
        {
          v84 = (RTL_SRWLOCK *)Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdEqualityPredicate,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId,1,1,0>>::Vector<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdEqualityPredicate,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId,1,1,0>>(v83);
          v101 = 0;
        }
        Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Core::CoreKeyboardManager *,Windows::UI::Internal::Text::Core::ICoreKeyboardManager *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Core::CoreKeyboardManagerHardwareKeyboardUIEnabledChangedEventArgs *,Windows::UI::Internal::Text::Core::ICoreKeyboardManagerHardwareKeyboardUIEnabledChangedEventArgs *>>::*)(Windows::UI::Internal::Text::Core::ICoreKeyboardManager *,Windows::UI::Internal::Text::Core::ICoreKeyboardManagerHardwareKeyboardUIEnabledChangedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardManager *,Windows::UI::Internal::Text::Core::CoreKeyboardManagerHardwareKeyboardUIEnabledChangedEventArgs *>,_lambda_3d673f836d44ef639fe032b9aedce249_,-1,Windows::UI::Internal::Text::Core::ICoreKeyboardManager *,Windows::UI::Internal::Text::Core::ICoreKeyboardManagerHardwareKeyboardUIEnabledChangedEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Core::CoreKeyboardManager *,Windows::UI::Internal::Text::Core::ICoreKeyboardManager *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Internal::Text::Core::CoreKeyboardManagerHardwareKeyboardUIEnabledChangedEventArgs *,Windows::UI::Internal::Text::Core::ICoreKeyboardManagerHardwareKeyboardUIEnabledChangedEventArgs *>>::*)(Windows::UI::Internal::Text::Core::ICoreKeyboardManager *,Windows::UI::Internal::Text::Core::ICoreKeyboardManagerHardwareKeyboardUIEnabledChangedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardManager *,Windows::UI::Internal::Text::Core::CoreKeyboardManagerHardwareKeyboardUIEnabledChangedEventArgs *>,_lambda_3d673f836d44ef639fe032b9aedce249_,-1,Windows::UI::Internal::Text::Core::ICoreKeyboardManager *,Windows::UI::Internal::Text::Core::ICoreKeyboardManagerHardwareKeyboardUIEnabledChangedEventArgs *>>(&v101);
        if ( v84 )
        {
          v85 = 0;
          v82 = v84;
          SRWLock = v84;
        }
        else
        {
          v85 = 2147942414LL;
          v84 = 0;
        }
        if ( (int)v85 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x34C,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)v85,
            (int)v97);
        LOBYTE(v85) = 1;
        v86 = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdEqualityPredicate,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId,1,1,0>>::InsertAtInternal(
                v82,
                0,
                v81,
                v85);
        if ( v86 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x34D,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v86,
            (int)v97);
        *(_QWORD *)v107 = 0;
        View = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdEqualityPredicate,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId,1,1,0>>::GetView(
                 v84,
                 v107);
        if ( View < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x350,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)View,
            (int)v97);
        v88 = (*(__int64 (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, _QWORD))(*(_QWORD *)v2 + 72LL))(
                v2,
                *(_QWORD *)v107);
        if ( v88 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x351,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v88,
            (int)v97);
        v98 = 0;
        v89 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v114 + 64LL))(v114, &v98);
        if ( v89 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x354,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v89,
            (int)v97);
        v100 = 0;
        v90 = (**(__int64 (__fastcall ***)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, GUID *, void **))v2)(
                v2,
                &GUID_266d6f6f_822f_4304_b3b6_9dc7fec054a5,
                &v100);
        if ( v90 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x357,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v90,
            (int)v97);
        LOBYTE(v91) = v98;
        v92 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v100 + 48LL))(v100, v91);
        if ( v92 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x358,
            (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
            (const char *)(unsigned int)v92,
            (int)v97);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v100);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v107);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::ObservableVector<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdEqualityPredicate,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdLifetimeTraits,1>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::ObservableVector<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdEqualityPredicate,Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionIdLifetimeTraits,1>,wil::err_exception_policy>(&SRWLock);
      }
      v99[0] = 0;
      v126 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &v125,
        L"ApplicationMultiviewActivationPolicy",
        0x25u,
        0x24u);
      Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned char>(v108, v126, v93, v99);
      if ( v99[0] )
        WindowEventDispatcher::QueuePendingActivation(v4, v29, v109, 1);
      (*(void (__fastcall **)(struct IWindowWrapperInternal *))(*(_QWORD *)v29 + 368LL))(v29);
      LOBYTE(v94) = 1;
      v95 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v115 + 72))(v115, v94);
      if ( v95 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x366,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
          (const char *)(unsigned int)v95,
          (int)v97);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v114);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v105);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v116);
      wil::com_ptr_t<ViewEventArgsForSelectTargetView,wil::err_exception_policy>::~com_ptr_t<ViewEventArgsForSelectTargetView,wil::err_exception_policy>(&v111);
      if ( v129[1] )
        std::_Ref_count_base::_Decref(v129[1]);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v102);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v117);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v108);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v109);
LABEL_136:
      wil::ActivityBase<ViewManagerInteropLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v130, 0);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v118);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v110);
      goto LABEL_144;
    }
    LODWORD(v104) = 0;
    SRWLock = (PSRWLOCK)v109;
    v111 = 0;
    v37 = Microsoft::WRL::Details::MakeAndInitialize<ViewEventArgsForSelectTargetView,ViewEventArgsForSelectTargetView,Windows::Foundation::Collections::IPropertySet *,int>(
            &v111,
            &SRWLock,
            &v104);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x29A,
        (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
        (const char *)(unsigned int)v37,
        (int)v97);
    wil::com_ptr_t<IWindowWrapperInternal,wil::err_exception_policy>::query<Windows::Internal::Shell::ViewManagerInterop::IViewWrapper>(
      &v102,
      &v101);
    v105 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v105);
    v38 = AgileGitPtr::CopyLocal(
            (std::_Ref_count_base *)((char *)v129[0] + 24),
            &GUID_c1659867_0cf6_5f3b_99df_4f036280926c,
            &v105);
    v39 = v111;
    if ( v38 >= 0 )
    {
      v40 = (*(__int64 (__fastcall **)(void *, PSRWLOCK, __int64))(*(_QWORD *)v105 + 24LL))(v105, v101, v111);
      if ( v40 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2A0,
          (unsigned int)"pcshell\\twinui\\viewmanagerinterop\\lib\\windoweventdispatcher.cpp",
          (const char *)(unsigned int)v40,
          (int)v97);
    }
    Microsoft::WRL::Wrappers::SRWLock::LockShared(&v104, (char *)this + 456);
    wil::com_ptr_t<IUwpWindowWrapperInternal,wil::err_exception_policy>::reset(&v102);
    *(_OWORD *)&v125.Reserved.Reserved1 = 0;
    std::shared_ptr<KBViewInfo>::operator=(v129, &v125);
    if ( *(_QWORD *)&v125.Reserved.Reserved2[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v125.Reserved.Reserved2[8]);
    v41 = 1;
    v100 = 0;
    if ( *(_BYTE *)(v39 + 96) )
    {
      if ( *(_DWORD *)(v39 + 100) )
      {
        v42 = WindowEventDispatcher::GetCachedView((char *)this - 16, &SRWLock);
        wil::com_ptr_t<IWindowWrapperInternal,wil::err_exception_policy>::operator=(&v100, v42);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&SRWLock);
        if ( v100 )
        {
LABEL_53:
          wil::com_ptr_t<ISnappedWindow,wil::err_returncode_policy>::operator=(&v102, &v100);
          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v100);
          if ( v104 )
            ReleaseSRWLockShared(v104);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v105);
          wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v101);
          v29 = v102;
          goto LABEL_59;
        }
      }
      else
      {
        v41 = 0;
      }
    }
    if ( v41 )
    {
      v43 = WindowEventDispatcher::GetCachedView((char *)this - 16, &SRWLock, v106);
      wil::com_ptr_t<IWindowWrapperInternal,wil::err_exception_policy>::operator=(&v100, v43);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&SRWLock);
    }
    goto LABEL_53;
  }
  catch ( ... )
  {
    (*(void (__fastcall **)(struct Windows::Internal::ApplicationModel::WindowManagement::IAppViewActivationRequestedEventArgs *, __int64))(*(_QWORD *)v122 + 112LL))(
      v122,
      2150039857LL);
  }
LABEL_144:
  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v115);
LABEL_141:
  ViewManagerInteropTraceLogging::WindowEventDispatcher_AppViewActivationRequested::~WindowEventDispatcher_AppViewActivationRequested((ViewManagerInteropTraceLogging::WindowEventDispatcher_AppViewActivationRequested *)v130);
  return 0;
}

```

## disassembly

```asm
0x180295440  mov     [rsp+arg_10], rbx
0x180295445  mov     [rsp+arg_18], rsi
0x18029544a  push    rdi
0x18029544b  push    r12
0x18029544d  push    r13
0x18029544f  push    r14
0x180295451  push    r15
0x180295453  sub     rsp, 2E0h
0x18029545a  mov     rax, cs:__security_cookie
0x180295461  xor     rax, rsp
0x180295464  mov     [rsp+308h+var_38], rax
0x18029546c  mov     r12, rdx
0x18029546f  mov     rsi, rcx
0x180295472  mov     [rsp+308h+var_208], rdx
0x18029547a  xor     r14d, r14d
0x18029547d  mov     dword ptr [rsp+308h+var_290], r14d
0x180295482  lea     rcx, [rsp+308h+var_188]; this
0x18029548a  call    ??$Start@$$V@WindowEventDispatcher_AppViewActivationRequested@ViewManagerInteropTraceLogging@@SA?AV01@XZ; ViewManagerInteropTraceLogging::WindowEventDispatcher_AppViewActivationRequested::Start<>(void)
0x18029548f  nop
0x180295490  lea     r13, [rsi-10h]
0x180295494  mov     rax, [r12]
0x180295498  cmp     [r13+1F0h], r14b
0x18029549f  jz      loc_1802966B2
0x1802954a5  mov     [rsp+308h+var_1F0], r13
0x1802954ad  mov     [rsp+308h+var_240], r14
0x1802954b5  lea     r8, [rsp+308h+var_240]
0x1802954bd  lea     rdx, _GUID_5c19477e_81ef_4d21_baa4_c3040ad2ea6b
0x1802954c4  mov     rcx, r12
0x1802954c7  mov     rax, [rax]
0x1802954ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802954cf  mov     ebx, eax
0x1802954d1  test    eax, eax
0x1802954d3  jns     short loc_180295514
0x1802954d5  mov     rcx, [rsp+308h]; this
0x1802954dd  mov     r9d, eax; char *
0x1802954e0  lea     r8, aPcshellTwinuiV_35; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1802954e7  mov     edx, 253h; void *
0x1802954ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802954f1  nop
0x1802954f2  lea     rcx, [rsp+308h+var_240]; void *
0x1802954fa  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1802954ff  nop
0x180295500  lea     rcx, [rsp+308h+var_188]; this
0x180295508  call    ??1WindowEventDispatcher_AppViewActivationRequested@ViewManagerInteropTraceLogging@@QEAA@XZ; ViewManagerInteropTraceLogging::WindowEventDispatcher_AppViewActivationRequested::~WindowEventDispatcher_AppViewActivationRequested(void)
0x18029550d  mov     eax, ebx
0x18029550f  jmp     loc_180296704
0x180295514  mov     [rsp+308h+var_260], r14
0x18029551c  mov     rcx, [rsp+308h+var_240]
0x180295524  mov     rax, [rcx]
0x180295527  mov     [rsp+308h+var_260], r14
0x18029552f  lea     rdx, [rsp+308h+var_260]
0x180295537  mov     rax, [rax+30h]
0x18029553b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180295540  mov     rcx, [rsp+308h]; this
0x180295548  test    eax, eax
0x18029554a  jns     short loc_180295560
0x18029554c  mov     r9d, eax; char *
0x18029554f  lea     r8, aPcshellTwinuiV_35; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x180295556  mov     edx, 258h; void *
0x18029555b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180295560  mov     [rsp+308h+var_278], r14d
0x180295568  mov     [rsp+308h+var_228], r14
0x180295570  lea     r8, [rsp+308h+var_228]; struct Windows::Internal::ApplicationModel::WindowManagement::IAppModel **
0x180295578  lea     rdx, [rsp+308h+var_278]; enum Windows::Internal::ApplicationModel::WindowManagement::AppModelKind *
0x180295580  mov     rcx, [rsp+308h+var_260]; struct Windows::Internal::ApplicationModel::WindowManagement::IAppView *
0x180295588  call    ?IsComponentAppViewAndGetKindAndModel@@YAEPEAUIAppView@WindowManagement@ApplicationModel@Internal@Windows@@PEAW4AppModelKind@2345@PEAPEAUIAppModel@2345@@Z; IsComponentAppViewAndGetKindAndModel(Windows::Internal::ApplicationModel::WindowManagement::IAppView *,Windows::Internal::ApplicationModel::WindowManagement::AppModelKind *,Windows::Internal::ApplicationModel::WindowManagement::IAppModel * *)
0x18029558d  test    al, al
0x18029558f  jnz     loc_180296675
0x180295595  mov     [rsp+308h+var_280], r14d
0x18029559d  mov     rcx, [rsp+308h+var_260]
0x1802955a5  mov     rax, [rcx]
0x1802955a8  lea     rdx, [rsp+308h+var_280]
0x1802955b0  mov     rax, [rax+30h]
0x1802955b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802955b9  mov     rcx, [rsp+308h]; this
0x1802955c1  test    eax, eax
0x1802955c3  jns     short loc_1802955DA
0x1802955c5  mov     r9d, eax; char *
0x1802955c8  lea     r8, aPcshellTwinuiV_35; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1802955cf  mov     edx, 25Fh; void *
0x1802955d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802955da  mov     rax, [r12]
0x1802955de  mov     [rsp+308h+var_268], r14
0x1802955e6  lea     rdx, [rsp+308h+var_268]
0x1802955ee  mov     rcx, r12
0x1802955f1  mov     rax, [rax+40h]
0x1802955f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802955fa  mov     rcx, [rsp+308h]; this
0x180295602  test    eax, eax
0x180295604  jns     short loc_18029561A
0x180295606  mov     r9d, eax; char *
0x180295609  lea     r8, aPcshellTwinuiV_35; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x180295610  mov     edx, 262h; void *
0x180295615  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029561a  mov     rdx, [rsp+308h+var_268]; struct Windows::Foundation::Collections::IPropertySet *
0x180295622  lea     rcx, [rsp+308h+var_270]; this
0x18029562a  call    ??0PropertySetHelper@ShellHelpers@Internal@Windows@@QEAA@PEAUIPropertySet@Collections@Foundation@3@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x18029562f  nop
0x180295630  mov     [rsp+308h+var_250], r14d
0x180295638  mov     dl, 1
0x18029563a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddSourceWindowFromViewNavigationRequested@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddSourceWindowFromViewNavigationRequested@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddSourceWindowFromViewNavigationRequested> `wil::Feature<__WilFeatureTraits_Feature_AddSourceWindowFromViewNavigationRequested>::GetImpl(void)'::`2'::impl
0x180295641  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AddSourceWindowFromViewNavigationRequested@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddSourceWindowFromViewNavigationRequested>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180295646  lea     rdx, off_180713F28; "ViewSizePreferences.SourceWindow"
0x18029564d  lea     rcx, [rsp+308h+var_1A8]
0x180295655  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18029565a  nop
0x18029565b  mov     dword ptr [rsp+308h+var_290], 1
0x180295663  lea     r9, [rsp+308h+var_250]
0x18029566b  mov     rdx, [rax+18h]
0x18029566f  lea     rcx, [rsp+308h+var_270]
0x180295677  call    ??$GetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAI@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uint *),uint *)
0x18029567c  test    eax, eax
0x18029567e  js      short loc_18029568D
0x180295680  cmp     [rsp+308h+var_250], r14d
0x180295688  mov     al, r14b
0x18029568b  jnz     short loc_18029568F
0x18029568d  mov     al, 1
0x18029568f  test    al, al
0x180295691  jz      loc_180295861
0x180295697  mov     [rsp+308h+var_2A0], r14
0x18029569c  mov     rax, [r12]
0x1802956a0  mov     rbx, [rax+38h]
0x1802956a4  lea     rcx, [rsp+308h+var_2A0]
0x1802956a9  call    ?reset@?$com_ptr_t@UIUwpWindowWrapperInternal@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUwpWindowWrapperInternal,wil::err_exception_policy>::reset(void)
0x1802956ae  lea     rdx, [rsp+308h+var_2A0]
0x1802956b3  mov     rcx, r12
0x1802956b6  mov     rax, rbx
0x1802956b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802956be  mov     rcx, [rsp+308h]; this
0x1802956c6  test    eax, eax
0x1802956c8  jns     short loc_1802956DE
0x1802956ca  mov     r9d, eax; char *
0x1802956cd  lea     r8, aPcshellTwinuiV_35; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1802956d4  mov     edx, 26Eh; void *
0x1802956d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802956de  cmp     [rsp+308h+var_2A0], r14
0x1802956e3  jz      loc_180295857
0x1802956e9  mov     [rsp+308h+var_2B0], r14
0x1802956ee  lea     rdx, [rsp+308h+SRWLock]
0x1802956f3  mov     rcx, r13
0x1802956f6  call    ?GetAppViewStatics@WindowEventDispatcher@@AEAA?AV?$com_ptr_t@UIAppViewStatics@WindowManagement@ApplicationModel@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@XZ; WindowEventDispatcher::GetAppViewStatics(void)
0x1802956fb  nop
0x1802956fc  mov     rbx, [rax]
0x1802956ff  mov     rax, [rbx]
0x180295702  mov     rdi, [rax+78h]
0x180295706  mov     rcx, [rsp+308h+var_2B0]
0x18029570b  mov     [rsp+308h+var_2B0], r14
0x180295710  test    rcx, rcx
0x180295713  jz      short loc_180295722
0x180295715  mov     rdx, [rcx]
0x180295718  mov     rax, [rdx+10h]
0x18029571c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180295721  nop
0x180295722  lea     r8, [rsp+308h+var_2B0]
0x180295727  mov     rdx, [rsp+308h+var_2A0]
0x18029572c  mov     rcx, rbx
0x18029572f  mov     rax, rdi
0x180295732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180295737  mov     rcx, [rsp+308h]; this
0x18029573f  test    eax, eax
0x180295741  jns     short loc_180295758
0x180295743  mov     r9d, eax; char *
0x180295746  lea     r8, aPcshellTwinuiV_35; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x18029574d  mov     edx, 272h; void *
0x180295752  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180295758  lea     rcx, [rsp+308h+SRWLock]; void *
0x18029575d  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x180295762  mov     dword ptr [rsp+308h+var_290], r14d
0x180295767  mov     rcx, [rsp+308h+var_2B0]
0x18029576c  mov     rax, [rcx]
0x18029576f  lea     rdx, [rsp+308h+var_290]
0x180295774  mov     rax, [rax+30h]
0x180295778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029577d  mov     rcx, [rsp+308h]; this
0x180295785  test    eax, eax
0x180295787  jns     short loc_18029579D
0x180295789  mov     r9d, eax; char *
0x18029578c  lea     r8, aPcshellTwinuiV_35; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x180295793  mov     edx, 275h; void *
0x180295798  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029579d  lea     rdx, [rsi+1C8h]
0x1802957a4  lea     rcx, [rsp+308h+SRWLock]
0x1802957a9  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1802957ae  nop
0x1802957af  mov     r8d, dword ptr [rsp+308h+var_290]
0x1802957b4  lea     rdx, [rsp+308h+var_258]
0x1802957bc  mov     rcx, r13
0x1802957bf  call    ?GetCachedView@WindowEventDispatcher@@AEAA?AV?$com_ptr_t@UIWindowWrapperInternal@@Uerr_exception_policy@wil@@@wil@@UAppViewId@WindowManagement@ApplicationModel@Internal@Windows@@@Z; WindowEventDispatcher::GetCachedView(Windows::Internal::ApplicationModel::WindowManagement::AppViewId)
0x1802957c4  nop
0x1802957c5  mov     rcx, [rsp+308h+var_258]
0x1802957cd  test    rcx, rcx
0x1802957d0  jz      short loc_18029582D
0x1802957d2  mov     rax, [rcx]
0x1802957d5  mov     rax, [rax+100h]
0x1802957dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802957e1  mov     ebx, eax
0x1802957e3  lea     rdx, off_180713F28; "ViewSizePreferences.SourceWindow"
0x1802957ea  lea     rcx, [rsp+308h+var_1A8]
0x1802957f2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802957f7  nop
0x1802957f8  mov     r9d, ebx
0x1802957fb  mov     rdx, [rax+18h]; HSTRING
0x1802957ff  lea     rcx, [rsp+308h+var_270]; this
0x180295807  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x18029580c  mov     rcx, [rsp+308h]; this
0x180295814  test    eax, eax
0x180295816  jns     short loc_18029582D
0x180295818  mov     r9d, eax; char *
0x18029581b  lea     r8, aPcshellTwinuiV_35; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x180295822  mov     edx, 27Eh; void *
0x180295827  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18029582c  nop
0x18029582d  lea     rcx, [rsp+308h+var_258]; void *
0x180295835  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x18029583a  nop
0x18029583b  mov     rcx, [rsp+308h+SRWLock]; SRWLock
0x180295840  test    rcx, rcx
0x180295843  jz      short loc_18029584C
0x180295845  call    cs:__imp_ReleaseSRWLockShared
0x18029584b  nop
0x18029584c  lea     rcx, [rsp+308h+var_2B0]; void *
0x180295851  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x180295856  nop
0x180295857  lea     rcx, [rsp+308h+var_2A0]; void *
0x18029585c  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x180295861  mov     [rsp+308h+var_230], r14
0x180295869  mov     rax, [r12]
0x18029586d  mov     rbx, [rax+50h]
0x180295871  lea     rcx, [rsp+308h+var_230]
0x180295879  call    ?reset@?$com_ptr_t@UIUwpWindowWrapperInternal@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUwpWindowWrapperInternal,wil::err_exception_policy>::reset(void)
0x18029587e  lea     rdx, [rsp+308h+var_230]
0x180295886  mov     rcx, r12
0x180295889  mov     rax, rbx
0x18029588c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180295891  mov     rcx, [rsp+308h]; this
0x180295899  test    eax, eax
0x18029589b  jns     short loc_1802958B1
0x18029589d  mov     r9d, eax; char *
0x1802958a0  lea     r8, aPcshellTwinuiV_35; "pcshell\\twinui\\viewmanagerinterop\\li"...
0x1802958a7  mov     edx, 284h; void *
0x1802958ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802958b1  mov     [rsp+308h+var_2B7], r14b
0x1802958b6  mov     rbx, r14
0x1802958b9  mov     [rsp+308h+var_2A0], rbx
0x1802958be  xorps   xmm0, xmm0
0x1802958c1  movdqu  xmmword ptr [rsp+308h+var_1A8], xmm0
0x1802958ca  mov     [rsp+308h+var_258], r14
0x1802958d2  lea     rdx, off_180713F30; "AllowWindowReuse"
0x1802958d9  lea     rcx, [rsp+308h+var_1E8]
0x1802958e1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802958e6  nop
0x1802958e7  mov     [rsp+308h+var_2B8], r14b
0x1802958ec  lea     r9, [rsp+308h+var_2B8]
0x1802958f1  mov     rdx, [rax+18h]
0x1802958f5  lea     rcx, [rsp+308h+var_270]
0x1802958fd  call    ??$GetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAE@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uchar *),uchar *)
0x180295902  test    eax, eax
0x180295904  mov     al, 1
0x180295906  js      short loc_18029590C
0x180295908  mov     al, [rsp+308h+var_2B8]
0x18029590c  test    al, al
0x18029590e  jz      loc_180295BA1
0x180295914  lea     rdi, [rsi+1C8h]
0x18029591b  mov     rdx, rdi
0x18029591e  lea     rcx, [rsp+308h+var_2A8]
0x180295923  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180295928  nop
0x180295929  mov     r8d, [rsp+308h+var_280]
0x180295931  lea     rdx, [rsp+308h+SRWLock]
0x180295936  mov     rcx, r13
0x180295939  call    ?GetCachedView@WindowEventDispatcher@@AEAA?AV?$com_ptr_t@UIWindowWrapperInternal@@Uerr_exception_policy@wil@@@wil@@UAppViewId@WindowManagement@ApplicationModel@Internal@Windows@@@Z; WindowEventDispatcher::GetCachedView(Windows::Internal::ApplicationModel::WindowManagement::AppViewId)
0x18029593e  mov     rdx, rax
0x180295941  lea     rcx, [rsp+308h+var_2A0]
0x180295946  call    ??4?$com_ptr_t@UIWindowWrapperInternal@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<IWindowWrapperInternal,wil::err_exception_policy>::operator=(wil::com_ptr_t<IWindowWrapperInternal,wil::err_exception_policy> &&)
0x18029594b  lea     rcx, [rsp+308h+SRWLock]; void *
0x180295950  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x180295955  mov     rbx, [rsp+308h+var_2A0]
0x18029595a  test    rbx, rbx
0x18029595d  jz      short loc_18029599C
0x18029595f  mov     rax, [rbx]
0x180295962  lea     rdx, [rsp+308h+var_1E8]
0x18029596a  mov     rcx, rbx
0x18029596d  mov     rax, [rax+108h]
0x180295974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180295979  mov     rdx, rax
0x18029597c  lea     rcx, [rsp+308h+var_1A8]
0x180295984  call    ??4?$shared_ptr@UKBViewInfo@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<KBViewInfo>::operator=(std::shared_ptr<KBViewInfo> &&)
0x180295989  mov     rcx, qword ptr [rsp+308h+var_1E8+8]; this
0x180295991  test    rcx, rcx
0x180295994  jz      short loc_18029599C
0x180295996  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18029599b  nop
0x18029599c  mov     rcx, [rsp+308h+var_2A8]; SRWLock
0x1802959a1  test    rcx, rcx
0x1802959a4  jz      short loc_1802959AC
0x1802959a6  call    cs:__imp_ReleaseSRWLockShared
0x1802959ac  test    rbx, rbx
0x1802959af  jz      loc_180295BDA
0x1802959b5  mov     dword ptr [rsp+308h+var_290], r14d
0x1802959ba  mov     rax, [rsp+308h+var_268]
  ... truncated ...
```
