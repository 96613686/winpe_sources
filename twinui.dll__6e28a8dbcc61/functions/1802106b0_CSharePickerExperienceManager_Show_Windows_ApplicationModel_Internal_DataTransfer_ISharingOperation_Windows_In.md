# CSharePickerExperienceManager::Show(Windows::ApplicationModel::Internal::DataTransfer::ISharingOperation *,Windows::Internal::Shell::Share::IShareExperienceCallbacks *,HSTRING__ *)

- ea: `0x1802106b0`
- end: `0x180210da0`
- name: `?Show@CSharePickerExperienceManager@@UEAAJPEAUISharingOperation@DataTransfer@Internal@ApplicationModel@Windows@@PEAUIShareExperienceCallbacks@Share@Shell@46@PEAUHSTRING__@@@Z`
- size: `1776`
- prototype: `__int64 __fastcall(CSharePickerExperienceManager *__hidden this, struct Windows::ApplicationModel::Internal::DataTransfer::ISharingOperation *, struct Windows::Internal::Shell::Share::IShareExperienceCallbacks *, HSTRING)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18003c5e4`
- `0x180061e58`
- `0x1800a1e90`
- `0x1800e6974`
- `0x1800e9fb0`
- `0x1801047e0`
- `0x18013d330`
- `0x1801604fc`
- `0x180168c14`
- `0x18016b7a4`
- `0x180209148`
- `0x180209b98`
- `0x18020a580`
- `0x18020a6a8`
- `0x18020a708`
- `0x18020a9d4`
- `0x18020aa64`
- `0x18020ab2c`
- `0x18020cb44`
- `0x18020cf50`
- `0x18020e098`
- `0x1802106b0`
- `0x180211518`
- `0x180211564`
- `0x1802115b0`
- `0x180211a90`
- `0x180211b50`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021096e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180210d45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021096e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180210d45`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021073e`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021087f`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1802109e5`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180210b34`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021073e`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18021087f`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1802109e5`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180210b34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180210703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18021078f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180210c8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180210703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18021078f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180210c8d`
- `USER32!GetPropA` at `0x1802107fc`
- `USER32!GetPropA` at `0x1802107fc`
- `api-ms-win-rtcore-ntuser-shell-l1-1-0!GetShellWindow` at `0x180210807`
- `api-ms-win-rtcore-ntuser-shell-l1-1-0!GetShellWindow` at `0x180210807`

## string_xrefs

- `0x180210a66`: `%S(%d) SharePicker in state=%d, returning retry to let current operation complete. ThreadId=%u`
- `0x180210a43`: `%S(%d) State changed to Hiding during dismiss. ThreadId=%u`
- `0x180210a21`: `%S(%d) Failed to re-acquire lock after dismiss. ThreadId=%u`
- `0x1802108fd`: `%S(%d) State=Hiding. ThreadId=%u`
- `0x1802108b9`: `%S(%d) Failed to acquire frame lock. ThreadId=%u`
- `0x1802107a4`: `%S(%d) Acquired m_shareLaunchLock. ThreadId=%u`
- `0x180210719`: `%S(%d) Rapid click detected - already launching, returning retry immediately. ThreadId=%u`
- `0x180210cad`: `%S(%d) PersistentShareShow failed hr=0x%08X State=%d ThreadId=%u`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSharePickerExperienceManager::Show(
        CSharePickerExperienceManager *this,
        struct Windows::ApplicationModel::Internal::DataTransfer::ISharingOperation *a2,
        struct Windows::Internal::Shell::Share::IShareExperienceCallbacks *a3,
        HSTRING a4)
{
  DWORD CurrentThreadId; // eax
  DWORD v8; // r14d
  int v9; // eax
  int v10; // ebx
  HWND ShellWindow; // r12
  HWND v12; // rdx
  int ShouldWindowBeAllowedToPerformPrivilegedOperation; // eax
  int v14; // r15d
  int v15; // r9d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rdx
  __int64 v23; // rbx
  DWORD v24; // eax
  int v25; // eax
  FARPROC v26; // rax
  HMODULE v27; // rax
  int v28; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  char *v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  HWND hWnd; // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Internal::Shell::Share::IShareExperienceCallbacks *v34; // [rsp+58h] [rbp-A8h]
  HSTRING v35; // [rsp+60h] [rbp-A0h]
  _BYTE v36[64]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v37[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[32]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v35 = a4;
  v34 = a3;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl)
    && *((_DWORD *)this + 171) == 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    NearbyShareUXTraceLogging::TraceLoggingInfo(
      "%S(%d) Rapid click detected - already launching, returning retry immediately. ThreadId=%u",
      (const wchar_t *)"CSharePickerExperienceManager::Show",
      385,
      CurrentThreadId);
    return 2147549450LL;
  }
  v32 = 0;
  v29 = ((unsigned __int64)this + 832) & -(__int64)(TryAcquireSRWLockExclusive((PSRWLOCK)this + 104) != 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
    &v32,
    &v29);
  CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v29);
  if ( !v32 )
    goto LABEL_18;
  v8 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl) )
  {
    v8 = GetCurrentThreadId();
    NearbyShareUXTraceLogging::TraceLoggingInfo(
      "%S(%d) Acquired m_shareLaunchLock. ThreadId=%u",
      (const wchar_t *)"CSharePickerExperienceManager::Show",
      401,
      v8);
  }
  hWnd = 0;
  v9 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::Internal::DataTransfer::ISharingOperation *, HWND *))(*(_QWORD *)a2 + 72LL))(
         a2,
         &hWnd);
  v10 = v9;
  if ( v9 >= 0 )
  {
    ShellWindow = hWnd;
    if ( GetPropA(hWnd, "AttachToDesktop") )
    {
      ShellWindow = GetShellWindow();
    }
    else
    {
      ShouldWindowBeAllowedToPerformPrivilegedOperation = DesktopApiPolicyChecker::ShouldWindowBeAllowedToPerformPrivilegedOperation(
                                                            ShellWindow,
                                                            v12);
      v14 = ShouldWindowBeAllowedToPerformPrivilegedOperation;
      v10 = -2147019873;
      if ( ShouldWindowBeAllowedToPerformPrivilegedOperation == -2147019873 )
        goto LABEL_68;
      if ( ShouldWindowBeAllowedToPerformPrivilegedOperation < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
          (const char *)(unsigned int)ShouldWindowBeAllowedToPerformPrivilegedOperation,
          v28);
        v10 = v14;
        goto LABEL_68;
      }
    }
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>((struct wil::details::IFailureCallback *)v36);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl) )
    {
      v30 = 0;
      v29 = ((unsigned __int64)this + 840) & -(__int64)(TryAcquireSRWLockExclusive((PSRWLOCK)this + 105) != 0);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
        &v30,
        &v29);
      CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v29);
      if ( !v30 )
      {
        NearbyShareUXTraceLogging::TraceLoggingInfo(
          "%S(%d) Failed to acquire frame lock. ThreadId=%u",
          "CSharePickerExperienceManager::Show",
          433,
          v8);
LABEL_17:
        CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v30);
        tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(v36);
LABEL_18:
        v10 = -2147417846;
        goto LABEL_68;
      }
      if ( CSharePickerExperienceManager::IsDestroyInProgress(this) )
      {
        NearbyShareUXTraceLogging::TraceLoggingInfo(
          "%S(%d) State=Hiding. ThreadId=%u",
          "CSharePickerExperienceManager::Show",
          438,
          v8);
        goto LABEL_17;
      }
      v15 = *((_DWORD *)this + 171);
      if ( v15 == 2 )
      {
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
          &v30,
          0);
        v10 = CSharePickerExperienceManager::TryDismissShareExperience(this);
        if ( v10 < 0 )
        {
          tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(&v29);
          if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator bool(&v29) )
          {
            tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v29);
            ProcAddress = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
            if ( `TestControlReporting'::`2'::s_pfnTestControlReporting
              || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
                  ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestControlReporting"),
                  (`TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)ProcAddress) != 0) )
            {
              ((void (__fastcall *)(_QWORD))ProcAddress)(0);
            }
          }
          wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(&v29);
          CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v30);
          goto LABEL_67;
        }
        tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(&v29);
        if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator bool(&v29) )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(
                                  &v29,
                                  &v31)
                   + 272LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(&v31);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(&v29);
        v29 = ((unsigned __int64)this + 840) & -(__int64)(TryAcquireSRWLockExclusive((PSRWLOCK)this + 105) != 0);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
          &v30,
          &v29);
        CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v29);
        if ( !v30 )
        {
          NearbyShareUXTraceLogging::TraceLoggingInfo(
            "%S(%d) Failed to re-acquire lock after dismiss. ThreadId=%u",
            "CSharePickerExperienceManager::Show",
            470,
            v8);
          goto LABEL_17;
        }
        if ( CSharePickerExperienceManager::IsDestroyInProgress(this) )
        {
          NearbyShareUXTraceLogging::TraceLoggingInfo(
            "%S(%d) State changed to Hiding during dismiss. ThreadId=%u",
            "CSharePickerExperienceManager::Show",
            477,
            v8);
          goto LABEL_17;
        }
      }
      else
      {
        if ( (v15 & 0xFFFFFFFB) != 0 )
        {
          NearbyShareUXTraceLogging::TraceLoggingInfo(
            "%S(%d) SharePicker in state=%d, returning retry to let current operation complete. ThreadId=%u",
            (const wchar_t *)"CSharePickerExperienceManager::Show",
            484,
            v15,
            v8);
          goto LABEL_17;
        }
        tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(&v29);
        if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator bool(&v29) )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(
                                  &v29,
                                  &v31)
                   + 272LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(&v31);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(&v29);
      }
      *((_DWORD *)this + 171) = 1;
    }
    else
    {
      v10 = CSharePickerExperienceManager::TryDismissShareExperience(this);
      if ( v10 < 0 )
      {
        tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(&v29);
        if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator bool(&v29) )
        {
          tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v29);
          v26 = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
          if ( `TestControlReporting'::`2'::s_pfnTestControlReporting
            || (v27 = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
                v26 = GetProcAddress(v27, "TestControlReporting"),
                (`TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)v26) != 0) )
          {
            ((void (__fastcall *)(_QWORD))v26)(0);
          }
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(&v29);
        goto LABEL_67;
      }
      tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(&v29);
      if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator bool(&v29) )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(
                                &v29,
                                &v31)
                 + 272LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(&v31);
      }
      wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(&v29);
      v30 = 0;
      v29 = ((unsigned __int64)this + 840) & -(__int64)(TryAcquireSRWLockExclusive((PSRWLOCK)this + 105) != 0);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
        &v30,
        &v29);
      CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v29);
      if ( !v30 )
        goto LABEL_17;
    }
    CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v30);
    v31 = (char *)this + 592;
    v18 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v31);
    v19 = Microsoft::WRL::AsWeak<IFileSavePickerEventSink>(a2, v18);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = 531;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
        (const char *)(unsigned int)v19,
        v28);
LABEL_67:
      tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(v36);
      goto LABEL_68;
    }
    v31 = (char *)this + 600;
    v21 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v31);
    v19 = Microsoft::WRL::AsWeak<IFileSavePickerEventSink>(v34, v21);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = 532;
      goto LABEL_46;
    }
    HSTRINGtoUTF8(v37, v35);
    v22 = v37;
    if ( v37[3] > 0xFu )
      v22 = (_QWORD *)v37[0];
    v23 = ExtendCorrelationVector(v38, v22);
    if ( (CSharePickerExperienceManager *)((char *)this + 608) != (CSharePickerExperienceManager *)v23 )
    {
      std::string::_Tidy_deallocate((char *)this + 608);
      *((_OWORD *)this + 38) = *(_OWORD *)v23;
      *((_OWORD *)this + 39) = *(_OWORD *)(v23 + 16);
      *(_QWORD *)(v23 + 16) = 0;
      *(_QWORD *)(v23 + 24) = 15;
      *(_BYTE *)v23 = 0;
    }
    std::string::_Tidy_deallocate(v38);
    *((_QWORD *)this + 12) = ShellWindow;
    *((_BYTE *)this + 120) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl) )
    {
      v10 = CSharePickerExperienceManager::PersistentShareShow(this, a2, ShellWindow);
      if ( v10 < 0 )
      {
        if ( *((_DWORD *)this + 171) == 1 )
          *((_DWORD *)this + 171) = 4;
        v24 = GetCurrentThreadId();
        NearbyShareUXTraceLogging::TraceLoggingError(
          "%S(%d) PersistentShareShow failed hr=0x%08X State=%d ThreadId=%u",
          (const wchar_t *)"CSharePickerExperienceManager::Show",
          550,
          v10,
          *((_DWORD *)this + 171),
          v24);
        goto LABEL_60;
      }
    }
    else
    {
      v25 = CSharePickerExperienceManager::PersistentShareShow(this, a2, ShellWindow);
      v10 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22C,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
          (const char *)(unsigned int)v25,
          v28);
LABEL_60:
        std::string::_Tidy_deallocate(v37);
        goto LABEL_67;
      }
    }
    std::string::_Tidy_deallocate(v37);
    tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(v36);
    CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x195,
    (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
    (const char *)(unsigned int)v9,
    v28);
LABEL_68:
  CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v32);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1802106b0  push    rbp
0x1802106b2  push    rbx
0x1802106b3  push    rsi
0x1802106b4  push    rdi
0x1802106b5  push    r12
0x1802106b7  push    r13
0x1802106b9  push    r14
0x1802106bb  push    r15
0x1802106bd  lea     rbp, [rsp-8]
0x1802106c2  sub     rsp, 108h
0x1802106c9  mov     rax, cs:__security_cookie
0x1802106d0  xor     rax, rsp
0x1802106d3  mov     [rbp+40h+var_50], rax
0x1802106d7  mov     [rsp+140h+var_E0], r9
0x1802106dc  mov     [rsp+140h+var_E8], r8
0x1802106e1  mov     r13, rdx
0x1802106e4  mov     rdi, rcx
0x1802106e7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IVCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest> `wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl(void)'::`2'::impl
0x1802106ee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(void)
0x1802106f3  xor     r15d, r15d
0x1802106f6  test    al, al
0x1802106f8  jz      short loc_18021072F
0x1802106fa  cmp     dword ptr [rdi+2ACh], 1
0x180210701  jnz     short loc_18021072F
0x180210703  call    cs:__imp_GetCurrentThreadId
0x180210709  mov     r9d, eax
0x18021070c  mov     r8d, 181h
0x180210712  lea     rdx, aCsharepickerex_9; "CSharePickerExperienceManager::Show"
0x180210719  lea     rcx, aSDRapidClickDe; "%S(%d) Rapid click detected - already l"...
0x180210720  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x180210725  mov     eax, 8001010Ah
0x18021072a  jmp     loc_180210D80
0x18021072f  mov     [rsp+140h+var_F8], r15
0x180210734  lea     rbx, [rdi+340h]
0x18021073b  mov     rcx, rbx; SRWLock
0x18021073e  call    cs:__imp_TryAcquireSRWLockExclusive
0x180210744  neg     al
0x180210746  sbb     rcx, rcx
0x180210749  and     rcx, rbx
0x18021074c  mov     [rsp+140h+var_110], rcx
0x180210751  lea     rdx, [rsp+140h+var_110]
0x180210756  lea     rcx, [rsp+140h+var_F8]
0x18021075b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x180210760  lea     rcx, [rsp+140h+var_110]; this
0x180210765  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x18021076a  cmp     [rsp+140h+var_F8], r15
0x18021076f  jz      loc_1802108E1
0x180210775  mov     r14d, r15d
0x180210778  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IVCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest> `wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl(void)'::`2'::impl
0x18021077f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(void)
0x180210784  lea     rsi, aCsharepickerex_9; "CSharePickerExperienceManager::Show"
0x18021078b  test    al, al
0x18021078d  jz      short loc_1802107B0
0x18021078f  call    cs:__imp_GetCurrentThreadId
0x180210795  mov     r14d, eax
0x180210798  mov     r9d, eax
0x18021079b  mov     r8d, 191h
0x1802107a1  mov     rdx, rsi
0x1802107a4  lea     rcx, aSDAcquiredMSha; "%S(%d) Acquired m_shareLaunchLock. Thre"...
0x1802107ab  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x1802107b0  mov     [rsp+140h+hWnd], r15
0x1802107b5  mov     rcx, [r13+0]
0x1802107b9  mov     rax, [rcx+48h]
0x1802107bd  lea     rdx, [rsp+140h+hWnd]
0x1802107c2  mov     rcx, r13
0x1802107c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802107ca  mov     ebx, eax
0x1802107cc  test    eax, eax
0x1802107ce  jns     short loc_1802107ED
0x1802107d0  mov     rcx, [rbp+48h]; this
0x1802107d4  mov     r9d, eax; char *
0x1802107d7  lea     r8, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x1802107de  mov     edx, 195h; void *
0x1802107e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802107e8  jmp     loc_180210D74
0x1802107ed  mov     r12, [rsp+140h+hWnd]
0x1802107f2  lea     rdx, aAttachtodeskto; "AttachToDesktop"
0x1802107f9  mov     rcx, r12; hWnd
0x1802107fc  call    cs:__imp_GetPropA
0x180210802  test    rax, rax
0x180210805  jz      short loc_180210812
0x180210807  call    cs:__imp_GetShellWindow
0x18021080d  mov     r12, rax
0x180210810  jmp     short loc_180210851
0x180210812  mov     rcx, r12; hWnd
0x180210815  call    ?ShouldWindowBeAllowedToPerformPrivilegedOperation@DesktopApiPolicyChecker@@YAJPEAUHWND__@@@Z; DesktopApiPolicyChecker::ShouldWindowBeAllowedToPerformPrivilegedOperation(HWND__ *)
0x18021081a  mov     r15d, eax
0x18021081d  mov     ebx, 8007139Fh
0x180210822  cmp     eax, ebx
0x180210824  jz      loc_180210D74
0x18021082a  test    eax, eax
0x18021082c  jns     short loc_18021084E
0x18021082e  mov     rcx, [rbp+48h]; this
0x180210832  mov     r9d, eax; char *
0x180210835  lea     r8, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x18021083c  mov     edx, 1A6h; void *
0x180210841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180210846  mov     ebx, r15d
0x180210849  jmp     loc_180210D74
0x18021084e  xor     r15d, r15d
0x180210851  lea     rcx, [rsp+140h+var_D0]; struct wil::details::IFailureCallback *
0x180210856  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18021085b  nop
0x18021085c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IVCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest> `wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl(void)'::`2'::impl
0x180210863  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(void)
0x180210868  test    al, al
0x18021086a  jz      loc_180210ACE
0x180210870  mov     [rsp+140h+var_108], r15
0x180210875  lea     r15, [rdi+348h]
0x18021087c  mov     rcx, r15; SRWLock
0x18021087f  call    cs:__imp_TryAcquireSRWLockExclusive
0x180210885  neg     al
0x180210887  sbb     rcx, rcx
0x18021088a  and     rcx, r15
0x18021088d  mov     [rsp+140h+var_110], rcx
0x180210892  lea     rdx, [rsp+140h+var_110]
0x180210897  lea     rcx, [rsp+140h+var_108]
0x18021089c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x1802108a1  lea     rcx, [rsp+140h+var_110]; this
0x1802108a6  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x1802108ab  cmp     [rsp+140h+var_108], 0
0x1802108b1  jnz     short loc_1802108EB
0x1802108b3  mov     r8d, 1B1h
0x1802108b9  lea     rcx, aSDFailedToAcqu; "%S(%d) Failed to acquire frame lock. Th"...
0x1802108c0  mov     rdx, rsi
0x1802108c3  mov     r9d, r14d
0x1802108c6  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x1802108cb  nop
0x1802108cc  lea     rcx, [rsp+140h+var_108]; this
0x1802108d1  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x1802108d6  nop
0x1802108d7  lea     rcx, [rsp+140h+var_D0]
0x1802108dc  call    ??1?$test_watcher@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(void)
0x1802108e1  mov     ebx, 8001010Ah
0x1802108e6  jmp     loc_180210D74
0x1802108eb  mov     rcx, rdi; this
0x1802108ee  call    ?IsDestroyInProgress@CSharePickerExperienceManager@@AEBA_NXZ; CSharePickerExperienceManager::IsDestroyInProgress(void)
0x1802108f3  test    al, al
0x1802108f5  jz      short loc_180210906
0x1802108f7  mov     r8d, 1B6h
0x1802108fd  lea     rcx, aSDStateHidingT; "%S(%d) State=Hiding. ThreadId=%u"
0x180210904  jmp     short loc_1802108C0
0x180210906  mov     r9d, [rdi+2ACh]
0x18021090d  cmp     r9d, 2
0x180210911  jnz     loc_180210A4F
0x180210917  xor     edx, edx
0x180210919  lea     rcx, [rsp+140h+var_108]
0x18021091e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180210923  mov     rcx, rdi; this
0x180210926  call    ?TryDismissShareExperience@CSharePickerExperienceManager@@AEAAJXZ; CSharePickerExperienceManager::TryDismissShareExperience(void)
0x18021092b  mov     ebx, eax
0x18021092d  lea     rcx, [rsp+140h+var_110]
0x180210932  test    eax, eax
0x180210934  jns     short loc_1802109A1
0x180210936  call    ??$open@V?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(void)
0x18021093b  lea     rcx, [rsp+140h+var_110]
0x180210940  call    ??B?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator bool(void)
0x180210945  test    al, al
0x180210947  jz      short loc_180210987
0x180210949  lea     rcx, [rsp+140h+var_110]
0x18021094e  call    ?complete@?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(void)
0x180210953  mov     rax, cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x18021095a  test    rax, rax
0x18021095d  jnz     short loc_180210980
0x18021095f  call    tip_details_GetKernelBaseModuleHandle
0x180210964  mov     rcx, rax; hModule
0x180210967  lea     rdx, aTestcontrolrep; "TestControlReporting"
0x18021096e  call    cs:__imp_GetProcAddress
0x180210974  mov     cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA, rax; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x18021097b  test    rax, rax
0x18021097e  jz      short loc_180210987
0x180210980  xor     ecx, ecx
0x180210982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180210987  lea     rcx, [rsp+140h+var_110]
0x18021098c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(void)
0x180210991  nop
0x180210992  lea     rcx, [rsp+140h+var_108]; this
0x180210997  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x18021099c  jmp     loc_180210D69
0x1802109a1  call    ??$open@V?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(void)
0x1802109a6  lea     rcx, [rsp+140h+var_110]
0x1802109ab  call    ??B?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator bool(void)
0x1802109b0  test    al, al
0x1802109b2  jz      short loc_1802109D7
0x1802109b4  lea     rdx, [rsp+140h+var_100]
0x1802109b9  lea     rcx, [rsp+140h+var_110]
0x1802109be  call    ??C?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(void)
0x1802109c3  mov     rcx, [rax]
0x1802109c6  mov     byte ptr [rcx+110h], 1
0x1802109cd  lea     rcx, [rsp+140h+var_100]
0x1802109d2  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(void)
0x1802109d7  lea     rcx, [rsp+140h+var_110]
0x1802109dc  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(void)
0x1802109e1  nop
0x1802109e2  mov     rcx, r15; SRWLock
0x1802109e5  call    cs:__imp_TryAcquireSRWLockExclusive
0x1802109eb  neg     al
0x1802109ed  sbb     rcx, rcx
0x1802109f0  and     rcx, r15
0x1802109f3  mov     [rsp+140h+var_110], rcx
0x1802109f8  lea     rdx, [rsp+140h+var_110]
0x1802109fd  lea     rcx, [rsp+140h+var_108]
0x180210a02  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x180210a07  lea     rcx, [rsp+140h+var_110]; this
0x180210a0c  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x180210a11  xor     r15d, r15d
0x180210a14  cmp     [rsp+140h+var_108], r15
0x180210a19  jnz     short loc_180210A2D
0x180210a1b  mov     r8d, 1D6h
0x180210a21  lea     rcx, aSDFailedToReAc; "%S(%d) Failed to re-acquire lock after "...
0x180210a28  jmp     loc_1802108C0
0x180210a2d  mov     rcx, rdi; this
0x180210a30  call    ?IsDestroyInProgress@CSharePickerExperienceManager@@AEBA_NXZ; CSharePickerExperienceManager::IsDestroyInProgress(void)
0x180210a35  test    al, al
0x180210a37  jz      loc_180210ABF
0x180210a3d  mov     r8d, 1DDh
0x180210a43  lea     rcx, aSDStateChanged; "%S(%d) State changed to Hiding during d"...
0x180210a4a  jmp     loc_1802108C0
0x180210a4f  test    r9d, 0FFFFFFFBh
0x180210a56  jz      short loc_180210A77
0x180210a58  mov     [rsp+140h+var_120], r14d
0x180210a5d  mov     r8d, 1E4h
0x180210a63  mov     rdx, rsi
0x180210a66  lea     rcx, aSDSharepickerI; "%S(%d) SharePicker in state=%d, returni"...
0x180210a6d  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x180210a72  jmp     loc_1802108CC
0x180210a77  lea     rcx, [rsp+140h+var_110]
0x180210a7c  call    ??$open@V?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(void)
0x180210a81  lea     rcx, [rsp+140h+var_110]
0x180210a86  call    ??B?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator bool(void)
0x180210a8b  xor     r15d, r15d
0x180210a8e  test    al, al
0x180210a90  jz      short loc_180210AB5
0x180210a92  lea     rdx, [rsp+140h+var_100]
0x180210a97  lea     rcx, [rsp+140h+var_110]
0x180210a9c  call    ??C?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(void)
0x180210aa1  mov     rcx, [rax]
0x180210aa4  mov     byte ptr [rcx+110h], 1
0x180210aab  lea     rcx, [rsp+140h+var_100]
0x180210ab0  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(void)
0x180210ab5  lea     rcx, [rsp+140h+var_110]
0x180210aba  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(void)
0x180210abf  mov     dword ptr [rdi+2ACh], 1
0x180210ac9  jmp     loc_180210B6B
0x180210ace  mov     rcx, rdi; this
0x180210ad1  call    ?TryDismissShareExperience@CSharePickerExperienceManager@@AEAAJXZ; CSharePickerExperienceManager::TryDismissShareExperience(void)
0x180210ad6  mov     ebx, eax
0x180210ad8  lea     rcx, [rsp+140h+var_110]
0x180210add  test    eax, eax
0x180210adf  js      loc_180210D0D
0x180210ae5  call    ??$open@V?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>>(void)
0x180210aea  lea     rcx, [rsp+140h+var_110]
0x180210aef  call    ??B?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator bool(void)
0x180210af4  test    al, al
0x180210af6  jz      short loc_180210B1B
0x180210af8  lea     rdx, [rsp+140h+var_100]
0x180210afd  lea     rcx, [rsp+140h+var_110]
0x180210b02  call    ??C?$tip_test@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::operator->(void)
0x180210b07  mov     rcx, [rax]
0x180210b0a  mov     byte ptr [rcx+110h], 1
0x180210b11  lea     rcx, [rsp+140h+var_100]
0x180210b16  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>>(void)
0x180210b1b  lea     rcx, [rsp+140h+var_110]
0x180210b20  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShareSheetViewCreationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShareSheetViewCreationTest,_tip_ShareSheetViewCreationTest>,wil::err_returncode_policy>(void)
0x180210b25  mov     [rsp+140h+var_108], r15
0x180210b2a  lea     rbx, [rdi+348h]
0x180210b31  mov     rcx, rbx; SRWLock
0x180210b34  call    cs:__imp_TryAcquireSRWLockExclusive
0x180210b3a  neg     al
0x180210b3c  sbb     rcx, rcx
0x180210b3f  and     rcx, rbx
0x180210b42  mov     [rsp+140h+var_110], rcx
0x180210b47  lea     rdx, [rsp+140h+var_110]
0x180210b4c  lea     rcx, [rsp+140h+var_108]
0x180210b51  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x180210b56  lea     rcx, [rsp+140h+var_110]; this
0x180210b5b  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x180210b60  cmp     [rsp+140h+var_108], r15
0x180210b65  jz      loc_1802108CC
0x180210b6b  lea     rcx, [rsp+140h+var_108]; this
0x180210b70  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x180210b75  lea     rax, [rdi+250h]
0x180210b7c  mov     [rsp+140h+var_100], rax
0x180210b81  lea     rcx, [rsp+140h+var_100]
0x180210b86  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180210b8b  mov     rdx, rax
0x180210b8e  mov     rcx, r13
0x180210b91  call    ??$AsWeak@UIFileSavePickerEventSink@@@WRL@Microsoft@@YAJPEAUIFileSavePickerEventSink@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IFileSavePickerEventSink>(IFileSavePickerEventSink *,Microsoft::WRL::WeakRef *)
0x180210b96  mov     ebx, eax
0x180210b98  test    eax, eax
0x180210b9a  jns     short loc_180210BB9
0x180210b9c  mov     edx, 213h; void *
0x180210ba1  lea     r8, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x180210ba8  mov     r9d, eax; char *
0x180210bab  mov     rcx, [rbp+48h]; this
0x180210baf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180210bb4  jmp     loc_180210D69
0x180210bb9  lea     rax, [rdi+258h]
0x180210bc0  mov     [rsp+140h+var_100], rax
0x180210bc5  lea     rcx, [rsp+140h+var_100]
  ... truncated ...
```
