# LauncherService::LaunchUriForTargetPackageWithOptionalDataForResults(unsigned __int64,HSTRING__ *,HSTRING__ *,Windows::System::Internal::Launch::LaunchType,Windows::System::ILauncherUIOptions *,IInspectable *,IInspectable *,unsigned __int64,Windows::System::Internal::Launch::InternalLauncherOptions,HSTRING__ *,IInspectable * *)

- ea: `0x1800b79f0`
- end: `0x1800b8168`
- name: `?LaunchUriForTargetPackageWithOptionalDataForResults@LauncherService@@UEAAJ_KPEAUHSTRING__@@1W4LaunchType@Launch@Internal@System@Windows@@PEAUILauncherUIOptions@67@PEAUIInspectable@@4_KW4InternalLauncherOptions@4567@1PEAPEAU9@@Z`
- size: `1912`
- prototype: `__int64 __fastcall(__int64, __int64, HSTRING, HSTRING, unsigned int, __int64, __int64, __int64, __int64, int, HSTRING, __int64)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b7910`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180027a10`
- `0x18003c8a8`
- `0x18003cc70`
- `0x1800485a4`
- `0x180048848`
- `0x18004a820`
- `0x18004e550`
- `0x180075190`
- `0x1800809e0`
- `0x180081548`
- `0x18008a030`
- `0x1800af1d4`
- `0x1800af248`
- `0x1800b0410`
- `0x1800b04c0`
- `0x1800b1104`
- `0x1800b1bec`
- `0x1800b1d08`
- `0x1800b1d40`
- `0x1800b2074`
- `0x1800b2298`
- `0x1800b6270`
- `0x1800b79f0`
- `0x1800bafe0`
- `0x1800bb0ec`
- `0x1800bd54c`
- `0x1800bd80c`
- `0x1800bdd40`
- `0x1800c04b0`
- `0x1800c0cdc`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7fc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800b7b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800b7b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800b7b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800b7b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7bd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7c2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7cdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7bd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7c2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7cdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8010`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8031`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8010`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8031`

## string_xrefs

- `0x1800b808f`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b80a6`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b80c0`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b80d8`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b80ed`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b8101`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b8118`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b812c`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b8141`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b8155`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall LauncherService::LaunchUriForTargetPackageWithOptionalDataForResults(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        HSTRING a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int a10,
        HSTRING a11,
        __int64 a12)
{
  _QWORD *v14; // rax
  __int64 v15; // rdx
  UserAwareCallerIdentity *v16; // rcx
  void **v17; // r8
  int v18; // eax
  PCWSTR StringRawBuffer; // rdi
  __int64 v20; // rbx
  const WCHAR *v21; // rdx
  struct Windows::Foundation::IUriRuntimeClass *v22; // rdi
  __int64 (__fastcall *v23)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v24; // eax
  PCWSTR v25; // rdi
  __int64 v26; // rbx
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING, HSTRING, __int64 *); // rbx
  int v30; // eax
  unsigned int LaunchFlagsFromLaunchTypeAndRuntimeBehavior; // eax
  int v32; // eax
  _QWORD *v33; // rsi
  const WCHAR *v34; // rbx
  __int64 (__fastcall *v35)(const WCHAR *, GUID *, struct Windows::Foundation::IUriRuntimeClass **); // rdi
  int v36; // eax
  int v37; // eax
  __int64 v38; // rbx
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  const char *v41; // r9
  __int64 result; // rax
  int v43; // [rsp+20h] [rbp-548h]
  int v44; // [rsp+20h] [rbp-548h]
  int v45; // [rsp+20h] [rbp-548h]
  _BYTE v46[8]; // [rsp+50h] [rbp-518h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v47; // [rsp+58h] [rbp-510h] BYREF
  HSTRING string; // [rsp+60h] [rbp-508h] BYREF
  PCWSTR v49; // [rsp+68h] [rbp-500h] BYREF
  int v50[2]; // [rsp+70h] [rbp-4F8h] BYREF
  __int64 v51; // [rsp+78h] [rbp-4F0h] BYREF
  __int64 v52; // [rsp+80h] [rbp-4E8h] BYREF
  _QWORD *v53; // [rsp+88h] [rbp-4E0h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v54; // [rsp+90h] [rbp-4D8h] BYREF
  __int64 v55; // [rsp+98h] [rbp-4D0h] BYREF
  unsigned int v56[2]; // [rsp+A0h] [rbp-4C8h] BYREF
  __int64 v57; // [rsp+A8h] [rbp-4C0h]
  __int64 v58; // [rsp+B0h] [rbp-4B8h]
  HSTRING v59; // [rsp+B8h] [rbp-4B0h] BYREF
  _QWORD v60[2]; // [rsp+C0h] [rbp-4A8h] BYREF
  _BYTE v61[40]; // [rsp+D0h] [rbp-498h] BYREF
  HSTRING v62; // [rsp+F8h] [rbp-470h]
  _BYTE v63[56]; // [rsp+100h] [rbp-468h] BYREF
  __int64 v64; // [rsp+138h] [rbp-430h]
  _QWORD v65[39]; // [rsp+140h] [rbp-428h] BYREF
  _QWORD v66[42]; // [rsp+290h] [rbp-2D8h] BYREF
  _QWORD v67[42]; // [rsp+3E0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+0h]

  v55 = a2;
  v53 = (_QWORD *)a6;
  *(_QWORD *)v50 = a8;
  v59 = a11;
  v47 = 0;
  v14 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::ensure_data(&v47);
  tip2::details::shared_data<1,0,0>::start(*v14 + 8LL, v60);
  tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>((struct wil::details::IFailureCallback *)v63);
  wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>(&v47);
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v65);
  v65[0] = &LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::`vftable';
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v66);
  v66[0] = &LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::`vftable';
  LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::StartActivity((LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults *)v66);
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v67);
  v67[0] = &LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::`vftable';
  wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(
    v65,
    v66);
  LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::~LaunchUriForTargetPackageWithOptionalDataForResults((LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults *)v67);
  LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::~LaunchUriForTargetPackageWithOptionalDataForResults((LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults *)v66);
  try
  {
    v18 = VerifyCaller(v16, v15, v17);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v18,
        v43);
    if ( WindowsIsStringEmpty(a3) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x230,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)0x80070057LL,
        v43);
    if ( WindowsIsStringEmpty(a4) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x231,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)0x80070057LL,
        v43);
    StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
    v20 = v64;
    v49 = (PCWSTR)v64;
    if ( v64 )
      _InterlockedIncrement((volatile signed __int32 *)(v64 + 368));
    tip2::details::shared_data<1,0,0>::begin_update(v20 + 8);
    std::wstring::assign(v20 + 272, StringRawBuffer);
    tip2::test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::~test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(&v49);
    v49 = WindowsGetStringRawBuffer(a4, 0);
    LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::TargetPackageFamilyName<unsigned short const *>(
      v65,
      &v49);
    v56[0] = a5;
    v56[1] = 0;
    v57 = a7;
    v58 = *(_QWORD *)v50;
    string = 0;
    v21 = WindowsGetStringRawBuffer(a3, 0);
    CreateRuntimeUri(&v54, v21);
    v22 = v54;
    v23 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)v54 + 136LL);
    WindowsDeleteString(string);
    string = 0;
    v24 = v23(v22, &string);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x239,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v24,
        v43);
    v25 = WindowsGetStringRawBuffer(string, 0);
    v26 = v64;
    *(_QWORD *)v50 = v64;
    if ( v64 )
      _InterlockedIncrement((volatile signed __int32 *)(v64 + 368));
    tip2::details::shared_data<1,0,0>::begin_update(v26 + 8);
    std::wstring::assign(v26 + 336, v25);
    tip2::test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::~test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(v50);
    *(_QWORD *)v50 = WindowsGetStringRawBuffer(string, 0);
    LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::UriScheme<unsigned short const *>(
      v65,
      v50);
    CallerInformation::Capture(v61, v55, a9);
    v52 = 0;
    v51 = 0;
    v46[0] = 0;
    v55 = 0;
    *(_QWORD *)v50 = 0;
    v49 = 0;
    v47 = v54;
    v60[0] = v56;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    v27 = Microsoft::WRL::Details::MakeAndInitialize<CTargetAppResolver,ILauncherTargetResolver,LAUNCH_PARAMETERS const * &,IUnknown * &,Windows::Storage::Search::IStorageFileQueryResult * &,HSTRING__ * &,HSTRING__ * &,CallerInformation const &,bool const &,HSTRING__ * &>(
            (unsigned int)&v52,
            (unsigned int)v60,
            (unsigned int)&v47,
            (unsigned int)&v49,
            (__int64)v50,
            (__int64)&v55,
            (struct CallerInformation *)v61,
            (__int64)v46,
            (__int64)&v59);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x244,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v27,
        v44);
    v28 = v52;
    v29 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v52 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v30 = v29(v28, a3, a4, &v51);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x245,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v30,
        v44);
    if ( !v51 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)0x80070483LL,
        v44);
    LaunchFlagsFromLaunchTypeAndRuntimeBehavior = GetLaunchFlagsFromLaunchTypeAndRuntimeBehavior(v56[0]);
    v32 = LauncherService::LaunchUriWithParameters(
            (__int64)v61,
            a3,
            0,
            0,
            a10 | LaunchFlagsFromLaunchTypeAndRuntimeBehavior,
            (__int64)v53,
            v56,
            v51,
            0,
            a11);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24A,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v32,
        v45);
    if ( a12 && v56[0] == 3 )
    {
      v49 = 0;
      v33 = (_QWORD *)((v51 - 8) & -(__int64)(v51 != 0));
      v53 = v33;
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*v33 + 8LL))((v51 - 8) & -(__int64)(v51 != 0));
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v33 + 12);
      v34 = (const WCHAR *)v33[12];
      v49 = v34;
      v47 = 0;
      v35 = **(__int64 (__fastcall ***)(const WCHAR *, GUID *, struct Windows::Foundation::IUriRuntimeClass **))v34;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      v36 = v35(v34, &GUID_d581293a_6de9_4d28_9378_f86782e182bb, &v47);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x254,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v36,
          v45);
      v37 = Microsoft::WRL::ComPtr<Windows::System::IProtocolForResultsOperation>::CopyTo<IInspectable>(&v47, a12);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x256,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v37,
          v45);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      if ( v33 )
        (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    }
    v38 = v64;
    wil::EnterCriticalSection(&v53, v64 + 200);
    tip2::details::shared_data<1,0,0>::complete_helper(v38 + 8);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v53);
    ProcAddress = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
    if ( `TestControlReporting'::`2'::s_pfnTestControlReporting
      || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
          ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestControlReporting"),
          (`TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(_QWORD))ProcAddress)(0);
    }
    wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    WindowsDeleteString(v62);
    v62 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    WindowsDeleteString(string);
    string = 0;
    LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::~LaunchUriForTargetPackageWithOptionalDataForResults((LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults *)v65);
    tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::~test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(v63);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x25F,
                           (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
                           v41);
  }
  return result;
}

```

## disassembly

```asm
0x1800b79f0  mov     [rsp+arg_0], rbx
0x1800b79f5  mov     [rsp+arg_8], rsi
0x1800b79fa  push    rdi
0x1800b79fb  push    r12
0x1800b79fd  push    r13
0x1800b79ff  push    r14
0x1800b7a01  push    r15
0x1800b7a03  sub     rsp, 540h
0x1800b7a0a  mov     rax, cs:__security_cookie
0x1800b7a11  xor     rax, rsp
0x1800b7a14  mov     [rsp+568h+var_38], rax
0x1800b7a1c  mov     rsi, r9
0x1800b7a1f  mov     r14, r8
0x1800b7a22  mov     [rsp+568h+var_4D0], rdx
0x1800b7a2a  mov     rax, [rsp+568h+arg_28]
0x1800b7a32  mov     [rsp+568h+var_4E0], rax
0x1800b7a3a  mov     r13, [rsp+568h+arg_30]
0x1800b7a42  mov     rax, [rsp+568h+arg_38]
0x1800b7a4a  mov     qword ptr [rsp+568h+var_4F8], rax
0x1800b7a4f  mov     r12, [rsp+568h+arg_50]
0x1800b7a57  mov     [rsp+568h+var_4B0], r12
0x1800b7a5f  mov     r15, [rsp+568h+arg_58]
0x1800b7a67  mov     [rsp+568h+var_510], 0
0x1800b7a70  lea     rcx, [rsp+568h+var_510]
0x1800b7a75  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::ensure_data(void)
0x1800b7a7a  mov     rcx, [rax]
0x1800b7a7d  add     rcx, 8
0x1800b7a81  lea     rdx, [rsp+568h+var_4A8]
0x1800b7a89  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x1800b7a8e  lea     rdx, [rsp+568h+var_510]
0x1800b7a93  lea     rcx, [rsp+568h+var_468]; struct wil::details::IFailureCallback *
0x1800b7a9b  call    ??0?$test_watcher@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::test_watcher<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy> &)
0x1800b7aa0  lea     rcx, [rsp+568h+var_510]
0x1800b7aa5  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>,wil::err_returncode_policy>(void)
0x1800b7aaa  nop
0x1800b7aab  lea     rcx, [rsp+568h+var_428]; struct wil::details::IFailureCallback *
0x1800b7ab3  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800b7ab8  lea     rbx, ??_7LaunchUriForTargetPackageWithOptionalDataForResults@LauncherServiceProvider@@6B@; const LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::`vftable'
0x1800b7abf  mov     [rsp+568h+var_428], rbx
0x1800b7ac7  lea     rcx, [rsp+568h+var_2D8]; struct wil::details::IFailureCallback *
0x1800b7acf  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800b7ad4  mov     [rsp+568h+var_2D8], rbx
0x1800b7adc  lea     rcx, [rsp+568h+var_2D8]; this
0x1800b7ae4  call    ?StartActivity@LaunchUriForTargetPackageWithOptionalDataForResults@LauncherServiceProvider@@QEAAXXZ; LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::StartActivity(void)
0x1800b7ae9  cmp     [rsp+568h+var_2F0], 0
0x1800b7af1  setnz   r8b
0x1800b7af5  lea     rdx, [rsp+568h+var_428]
0x1800b7afd  lea     rcx, [rsp+568h+var_188]; struct wil::details::IFailureCallback *
0x1800b7b05  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x1800b7b0a  mov     [rsp+568h+var_188], rbx
0x1800b7b12  lea     rdx, [rsp+568h+var_2D8]
0x1800b7b1a  lea     rcx, [rsp+568h+var_428]
0x1800b7b22  call    ??4?$ActivityBase@VLauncherServiceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<LauncherServiceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x1800b7b27  lea     rcx, [rsp+568h+var_188]; this
0x1800b7b2f  call    ??1LaunchUriForTargetPackageWithOptionalDataForResults@LauncherServiceProvider@@QEAA@XZ; LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::~LaunchUriForTargetPackageWithOptionalDataForResults(void)
0x1800b7b34  lea     rcx, [rsp+568h+var_2D8]; this
0x1800b7b3c  call    ??1LaunchUriForTargetPackageWithOptionalDataForResults@LauncherServiceProvider@@QEAA@XZ; LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::~LaunchUriForTargetPackageWithOptionalDataForResults(void)
0x1800b7b41  call    VerifyCaller
0x1800b7b46  mov     rcx, [rsp+568h]; this
0x1800b7b4e  test    eax, eax
0x1800b7b50  js      loc_1800B808C
0x1800b7b56  mov     rbx, [rsp+568h]
0x1800b7b5e  mov     rcx, r14; string
0x1800b7b61  call    cs:__imp_WindowsIsStringEmpty
0x1800b7b67  test    eax, eax
0x1800b7b69  jnz     loc_1800B80A0
0x1800b7b6f  mov     rbx, [rsp+568h]
0x1800b7b77  mov     rcx, rsi; string
0x1800b7b7a  call    cs:__imp_WindowsIsStringEmpty
0x1800b7b80  test    eax, eax
0x1800b7b82  jnz     loc_1800B80BA
0x1800b7b88  xor     edx, edx; length
0x1800b7b8a  mov     rcx, rsi; string
0x1800b7b8d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b7b93  mov     rdi, rax
0x1800b7b96  mov     rbx, [rsp+568h+var_430]
0x1800b7b9e  mov     [rsp+568h+var_500], rbx
0x1800b7ba3  test    rbx, rbx
0x1800b7ba6  jz      short loc_1800B7BAF
0x1800b7ba8  lock inc dword ptr [rbx+170h]
0x1800b7baf  lea     rcx, [rbx+8]
0x1800b7bb3  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x1800b7bb8  nop
0x1800b7bb9  lea     rcx, [rbx+110h]
0x1800b7bc0  mov     rdx, rdi
0x1800b7bc3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800b7bc8  nop
0x1800b7bc9  lea     rcx, [rsp+568h+var_500]
0x1800b7bce  call    ??1?$test_data_control@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::~test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(void)
0x1800b7bd3  xor     edx, edx; length
0x1800b7bd5  mov     rcx, rsi; string
0x1800b7bd8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b7bde  mov     [rsp+568h+var_500], rax
0x1800b7be3  lea     rdx, [rsp+568h+var_500]
0x1800b7be8  lea     rcx, [rsp+568h+var_428]
0x1800b7bf0  call    ??$TargetPackageFamilyName@PEBG@LaunchUriForTargetPackageWithOptionalDataForResults@LauncherServiceProvider@@QEAAX$$QEAPEBG@Z; LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::TargetPackageFamilyName<ushort const *>(ushort const * &&)
0x1800b7bf5  mov     eax, [rsp+568h+arg_20]
0x1800b7bfc  mov     [rsp+568h+var_4C8], eax
0x1800b7c03  xor     eax, eax
0x1800b7c05  mov     [rsp+568h+var_4C4], eax
0x1800b7c0c  mov     [rsp+568h+var_4C0], r13
0x1800b7c14  mov     rax, qword ptr [rsp+568h+var_4F8]
0x1800b7c19  mov     [rsp+568h+var_4B8], rax
0x1800b7c21  xor     r13d, r13d
0x1800b7c24  mov     [rsp+568h+string], r13
0x1800b7c29  xor     edx, edx; length
0x1800b7c2b  mov     rcx, r14; string
0x1800b7c2e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b7c34  mov     rdx, rax; sourceString
0x1800b7c37  lea     rcx, [rsp+568h+var_4D8]; struct Windows::Foundation::IUriRuntimeClass **
0x1800b7c3f  call    ?CreateRuntimeUri@@YA?AV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEBG@Z; CreateRuntimeUri(ushort const *)
0x1800b7c44  nop
0x1800b7c45  mov     rdi, [rsp+568h+var_4D8]
0x1800b7c4d  mov     rax, [rdi]
0x1800b7c50  mov     rbx, [rax+88h]
0x1800b7c57  mov     rcx, [rsp+568h+string]; string
0x1800b7c5c  call    cs:__imp_WindowsDeleteString
0x1800b7c62  mov     [rsp+568h+string], r13
0x1800b7c67  lea     rdx, [rsp+568h+string]
0x1800b7c6c  mov     rcx, rdi
0x1800b7c6f  mov     rax, rbx
0x1800b7c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7c77  mov     rcx, [rsp+568h]; this
0x1800b7c7f  test    eax, eax
0x1800b7c81  js      loc_1800B80D5
0x1800b7c87  xor     edx, edx; length
0x1800b7c89  mov     rcx, [rsp+568h+string]; string
0x1800b7c8e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b7c94  mov     rdi, rax
0x1800b7c97  mov     rbx, [rsp+568h+var_430]
0x1800b7c9f  mov     qword ptr [rsp+568h+var_4F8], rbx
0x1800b7ca4  test    rbx, rbx
0x1800b7ca7  jz      short loc_1800B7CB0
0x1800b7ca9  lock inc dword ptr [rbx+170h]
0x1800b7cb0  lea     rcx, [rbx+8]
0x1800b7cb4  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x1800b7cb9  nop
0x1800b7cba  lea     rcx, [rbx+150h]
0x1800b7cc1  mov     rdx, rdi
0x1800b7cc4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800b7cc9  nop
0x1800b7cca  lea     rcx, [rsp+568h+var_4F8]
0x1800b7ccf  call    ??1?$test_data_control@V?$merged_data@U_tip_CentennialLaunchUriForResultsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>::~test_data_control<tip2::details::merged_data<_tip_CentennialLaunchUriForResultsTest,_tip_CentennialLaunchUriForResultsTest>>(void)
0x1800b7cd4  xor     edx, edx; length
0x1800b7cd6  mov     rcx, [rsp+568h+string]; string
0x1800b7cdb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b7ce1  mov     qword ptr [rsp+568h+var_4F8], rax
0x1800b7ce6  lea     rdx, [rsp+568h+var_4F8]
0x1800b7ceb  lea     rcx, [rsp+568h+var_428]
0x1800b7cf3  call    ??$UriScheme@PEBG@LaunchUriForTargetPackageWithOptionalDataForResults@LauncherServiceProvider@@QEAAX$$QEAPEBG@Z; LauncherServiceProvider::LaunchUriForTargetPackageWithOptionalDataForResults::UriScheme<ushort const *>(ushort const * &&)
0x1800b7cf8  mov     r8, [rsp+568h+arg_40]
0x1800b7d00  mov     rdx, [rsp+568h+var_4D0]
0x1800b7d08  lea     rcx, [rsp+568h+var_498]
0x1800b7d10  call    ?Capture@CallerInformation@@SA?AV1@_K0@Z; CallerInformation::Capture(unsigned __int64,unsigned __int64)
0x1800b7d15  nop
0x1800b7d16  mov     [rsp+568h+var_4E8], r13
0x1800b7d1e  mov     [rsp+568h+var_4F0], r13
0x1800b7d23  mov     [rsp+568h+var_518], r13b
0x1800b7d28  mov     [rsp+568h+var_4D0], r13
0x1800b7d30  mov     qword ptr [rsp+568h+var_4F8], r13
0x1800b7d35  mov     [rsp+568h+var_500], r13
0x1800b7d3a  mov     rax, [rsp+568h+var_4D8]
0x1800b7d42  mov     [rsp+568h+var_510], rax
0x1800b7d47  lea     rax, [rsp+568h+var_4C8]
0x1800b7d4f  mov     [rsp+568h+var_4A8], rax
0x1800b7d57  lea     rcx, [rsp+568h+var_4E8]
0x1800b7d5f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7d64  lea     rax, [rsp+568h+var_4B0]
0x1800b7d6c  mov     [rsp+568h+var_528], rax
0x1800b7d71  lea     rax, [rsp+568h+var_518]
0x1800b7d76  mov     [rsp+568h+var_530], rax
0x1800b7d7b  lea     rax, [rsp+568h+var_498]
0x1800b7d83  mov     [rsp+568h+var_538], rax
0x1800b7d88  lea     rax, [rsp+568h+var_4D0]
0x1800b7d90  mov     [rsp+568h+var_540], rax
0x1800b7d95  lea     rax, [rsp+568h+var_4F8]
0x1800b7d9a  mov     qword ptr [rsp+568h+var_548], rax; int
0x1800b7d9f  lea     r9, [rsp+568h+var_500]
0x1800b7da4  lea     r8, [rsp+568h+var_510]
0x1800b7da9  lea     rdx, [rsp+568h+var_4A8]
0x1800b7db1  lea     rcx, [rsp+568h+var_4E8]
0x1800b7db9  call    ??$MakeAndInitialize@VCTargetAppResolver@@UILauncherTargetResolver@@AEAPEBULAUNCH_PARAMETERS@@AEAPEAUIUnknown@@AEAPEAUIStorageFileQueryResult@Search@Storage@Windows@@AEAPEAUHSTRING__@@AEAPEAU9@AEBVCallerInformation@@AEB_NAEAPEAU9@@Details@WRL@Microsoft@@YAJPEAPEAUILauncherTargetResolver@@AEAPEBULAUNCH_PARAMETERS@@AEAPEAUIUnknown@@AEAPEAUIStorageFileQueryResult@Search@Storage@Windows@@AEAPEAUHSTRING__@@4AEBVCallerInformation@@AEB_N4@Z; Microsoft::WRL::Details::MakeAndInitialize<CTargetAppResolver,ILauncherTargetResolver,LAUNCH_PARAMETERS const * &,IUnknown * &,Windows::Storage::Search::IStorageFileQueryResult * &,HSTRING__ * &,HSTRING__ * &,CallerInformation const &,bool const &,HSTRING__ * &>(ILauncherTargetResolver * *,LAUNCH_PARAMETERS const * &,IUnknown * &,Windows::Storage::Search::IStorageFileQueryResult * &,HSTRING__ * &,HSTRING__ * &,CallerInformation const &,bool const &,HSTRING__ * &)
0x1800b7dbe  mov     rcx, [rsp+568h]; this
0x1800b7dc6  test    eax, eax
0x1800b7dc8  js      loc_1800B80EA
0x1800b7dce  mov     rdi, [rsp+568h+var_4E8]
0x1800b7dd6  mov     rax, [rdi]
0x1800b7dd9  mov     rbx, [rax+18h]
0x1800b7ddd  lea     rcx, [rsp+568h+var_4F0]
0x1800b7de2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7de7  lea     r9, [rsp+568h+var_4F0]
0x1800b7dec  mov     r8, rsi
0x1800b7def  mov     rdx, r14
0x1800b7df2  mov     rcx, rdi
0x1800b7df5  mov     rax, rbx
0x1800b7df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7dfd  mov     rcx, [rsp+568h]; this
0x1800b7e05  test    eax, eax
0x1800b7e07  js      loc_1800B80FE
0x1800b7e0d  mov     rdx, [rsp+568h+var_4F0]
0x1800b7e12  test    rdx, rdx
0x1800b7e15  setz    al
0x1800b7e18  mov     rcx, [rsp+568h]; this
0x1800b7e20  test    al, al
0x1800b7e22  jnz     loc_1800B8112
0x1800b7e28  mov     ecx, [rsp+568h+var_4C8]
0x1800b7e2f  call    GetLaunchFlagsFromLaunchTypeAndRuntimeBehavior
0x1800b7e34  mov     rcx, [rsp+568h+var_4F0]
0x1800b7e39  or      eax, [rsp+568h+arg_48]
0x1800b7e40  mov     [rsp+568h+var_520], r12
0x1800b7e45  mov     dword ptr [rsp+568h+var_528], r13d
0x1800b7e4a  mov     [rsp+568h+var_530], rcx
0x1800b7e4f  lea     rcx, [rsp+568h+var_4C8]
0x1800b7e57  mov     [rsp+568h+var_538], rcx
0x1800b7e5c  mov     rcx, [rsp+568h+var_4E0]
0x1800b7e64  mov     [rsp+568h+var_540], rcx
0x1800b7e69  mov     [rsp+568h+var_548], eax; int
0x1800b7e6d  xor     r9d, r9d
0x1800b7e70  xor     r8d, r8d
0x1800b7e73  mov     rdx, r14
0x1800b7e76  lea     rcx, [rsp+568h+var_498]
0x1800b7e7e  call    ?LaunchUriWithParameters@LauncherService@@SAJAEBVCallerInformation@@PEAUHSTRING__@@11W4InternalLauncherOptions@Launch@Internal@System@Windows@@PEAUILauncherUIOptions@78@PEBULAUNCH_PARAMETERS@@PEAUILauncherTarget@@H1@Z; LauncherService::LaunchUriWithParameters(CallerInformation const &,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::System::Internal::Launch::InternalLauncherOptions,Windows::System::ILauncherUIOptions *,LAUNCH_PARAMETERS const *,ILauncherTarget *,int,HSTRING__ *)
0x1800b7e83  mov     rcx, [rsp+568h]; this
0x1800b7e8b  test    eax, eax
0x1800b7e8d  js      loc_1800B8129
0x1800b7e93  test    r15, r15
0x1800b7e96  jz      loc_1800B7F7B
0x1800b7e9c  cmp     [rsp+568h+var_4C8], 3
0x1800b7ea4  jnz     loc_1800B7F7B
0x1800b7eaa  mov     [rsp+568h+var_500], r13
0x1800b7eaf  mov     rax, [rsp+568h+var_4F0]
0x1800b7eb4  lea     rcx, [rax-8]
0x1800b7eb8  neg     rax
0x1800b7ebb  sbb     rsi, rsi
0x1800b7ebe  and     rsi, rcx
0x1800b7ec1  mov     [rsp+568h+var_4E0], rsi
0x1800b7ec9  jz      short loc_1800B7EDB
0x1800b7ecb  mov     rax, [rsi]
0x1800b7ece  mov     rcx, rsi
0x1800b7ed1  mov     rax, [rax+8]
0x1800b7ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7eda  nop
0x1800b7edb  lea     rcx, [rsp+568h+var_500]
0x1800b7ee0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7ee5  lea     rcx, [rsi+60h]
0x1800b7ee9  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800b7eee  mov     rbx, [rsi+60h]
0x1800b7ef2  mov     [rsp+568h+var_500], rbx
0x1800b7ef7  mov     [rsp+568h+var_510], r13
0x1800b7efc  mov     rax, [rbx]
0x1800b7eff  mov     rdi, [rax]
0x1800b7f02  lea     rcx, [rsp+568h+var_510]
0x1800b7f07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7f0c  lea     r8, [rsp+568h+var_510]
0x1800b7f11  lea     rdx, _GUID_d581293a_6de9_4d28_9378_f86782e182bb
0x1800b7f18  mov     rcx, rbx
0x1800b7f1b  mov     rax, rdi
0x1800b7f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f23  nop
0x1800b7f24  mov     rcx, [rsp+568h]; this
0x1800b7f2c  test    eax, eax
0x1800b7f2e  js      loc_1800B813E
0x1800b7f34  mov     rdx, r15
0x1800b7f37  lea     rcx, [rsp+568h+var_510]
0x1800b7f3c  call    ??$CopyTo@UIInspectable@@@?$ComPtr@UIProtocolForResultsOperation@System@Windows@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<Windows::System::IProtocolForResultsOperation>::CopyTo<IInspectable>(IInspectable * *)
0x1800b7f41  mov     rcx, [rsp+568h]; this
0x1800b7f49  test    eax, eax
0x1800b7f4b  js      loc_1800B8152
0x1800b7f51  lea     rcx, [rsp+568h+var_510]
0x1800b7f56  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7f5b  nop
0x1800b7f5c  test    rsi, rsi
0x1800b7f5f  jz      short loc_1800B7F71
0x1800b7f61  mov     rax, [rsi]
0x1800b7f64  mov     rcx, rsi
0x1800b7f67  mov     rax, [rax+10h]
0x1800b7f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f70  nop
0x1800b7f71  lea     rcx, [rsp+568h+var_500]
0x1800b7f76  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7f7b  mov     rbx, [rsp+568h+var_430]
0x1800b7f83  lea     rdx, [rbx+0C8h]
0x1800b7f8a  lea     rcx, [rsp+568h+var_4E0]
0x1800b7f92  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800b7f97  lea     rcx, [rbx+8]
0x1800b7f9b  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestFlags@@W4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestFlags,TestQueryOptions)
0x1800b7fa0  lea     rcx, [rsp+568h+var_4E0]
0x1800b7fa8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800b7fad  mov     rax, cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x1800b7fb4  test    rax, rax
0x1800b7fb7  jnz     short loc_1800B7FDA
0x1800b7fb9  call    tip_details_GetKernelBaseModuleHandle
0x1800b7fbe  mov     rcx, rax; hModule
0x1800b7fc1  lea     rdx, aTestcontrolrep; "TestControlReporting"
0x1800b7fc8  call    cs:__imp_GetProcAddress
0x1800b7fce  mov     cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA, rax; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x1800b7fd5  test    rax, rax
0x1800b7fd8  jz      short loc_1800B7FE1
0x1800b7fda  xor     ecx, ecx
0x1800b7fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
