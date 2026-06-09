# AssociationLaunchExecuteCommandBase::Execute(void)

- ea: `0x180054940`
- end: `0x180055082`
- name: `?Execute@AssociationLaunchExecuteCommandBase@@UEAAJXZ`
- size: `1858`
- prototype: `__int64 __fastcall(AssociationLaunchExecuteCommandBase *__hidden this)`
- caller_count: `0`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x1800210f8`
- `0x180042038`
- `0x18004966c`
- `0x18004be54`
- `0x18004be8c`
- `0x18004c62c`
- `0x180054940`
- `0x180055088`
- `0x1800550d8`
- `0x180055194`
- `0x1800551ec`
- `0x180055298`
- `0x1800552cc`
- `0x180055370`
- `0x180055490`
- `0x18005552c`
- `0x1800555e4`
- `0x1800556fc`
- `0x1800557cc`
- `0x18005587c`
- `0x18005591c`
- `0x1800559f8`
- `0x180055ac8`
- `0x18005cf50`
- `0x180075964`
- `0x180075b90`
- `0x18008a030`
- `0x1800ef8ec`
- `0x1800f0210`
- `0x180103a20`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054d13`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054d13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054c1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054c1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054a49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054b95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054ba6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054bb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054c38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054f2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054a49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054b95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054ba6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054bb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054c38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054f2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054cfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054cfd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054af9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054af9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054f93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054f93`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800549e6`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800549e6`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x180054b29`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x180054b29`

## string_xrefs

- `0x180054cf6`: `Windows.Protocol`
- `0x180054a1b`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x180054ac5`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x180054b0e`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x180054b3e`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x180054b6d`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x180054c7f`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x180054daf`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x180054dee`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x180054e39`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`
- `0x180054f65`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\associationlaunchexecutecommand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall AssociationLaunchExecuteCommandBase::Execute(AssociationLaunchExecuteCommandBase *this)
{
  _QWORD *v2; // rdi
  AssociationLaunchExecuteCommandBase *v3; // rcx
  int v4; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v6; // rbx
  int v7; // eax
  HRESULT Instance; // eax
  HRESULT v9; // eax
  struct IUnknown *v10; // r8
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  int v13; // eax
  int AssignedAccessTypeForUser_0; // ebx
  int v15; // ebx
  IUnknown *v16; // rbx
  struct IUnknownVtbl *lpVtbl; // rdi
  HRESULT v18; // eax
  void *v19; // rcx
  HSTRING *v20; // rax
  int v21; // eax
  __int64 (__fastcall *v22)(char *, HSTRING, void **); // rbx
  int v23; // eax
  void *v24; // rdi
  __int64 (__fastcall *v25)(void *, _QWORD, _QWORD, HSTRING_HEADER *); // rbx
  IUnknown *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  int ppv; // [rsp+20h] [rbp-238h]
  int ppva; // [rsp+20h] [rbp-238h]
  void *v32; // [rsp+50h] [rbp-208h] BYREF
  void *v33; // [rsp+58h] [rbp-200h] BYREF
  PCWSTR v34; // [rsp+60h] [rbp-1F8h] BYREF
  IUnknown *punk; // [rsp+68h] [rbp-1F0h] BYREF
  HSTRING string; // [rsp+70h] [rbp-1E8h] BYREF
  IUnknown *punkSite; // [rsp+78h] [rbp-1E0h] BYREF
  __int64 v38; // [rsp+80h] [rbp-1D8h] BYREF
  void *ppvOut; // [rsp+88h] [rbp-1D0h] BYREF
  void *v40; // [rsp+90h] [rbp-1C8h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-1C0h] BYREF
  HSTRING_HEADER hMem; // [rsp+A0h] [rbp-1B8h] BYREF
  HSTRING v43; // [rsp+B8h] [rbp-1A0h] BYREF
  void **v44; // [rsp+C0h] [rbp-198h] BYREF
  char v45[272]; // [rsp+C8h] [rbp-190h] BYREF
  char v46[8]; // [rsp+1D8h] [rbp-80h] BYREF
  char v47[48]; // [rsp+1E0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v44);
  v44 = &LauncherDesktopProvider::Execute::`vftable';
  LauncherDesktopProvider::Execute::StartActivity((LauncherDesktopProvider::Execute *)&v44);
  v2 = (_QWORD *)((char *)this - 40);
  LaunchExecuteCommandBase::GetSite((char *)this - 40, &v40);
  v38 = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
  if ( IUnknown_QueryService(
         *((IUnknown **)this - 1),
         (const GUID *const)&SID_ApplicationUserContextTokenInfo,
         &GUID_cb738c08_8b2d_4349_a14d_b969e62e964c,
         &ppvOut) >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &v38);
    v3 = retaddr;
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
        (const char *)(unsigned int)v4,
        ppv);
  }
  if ( AssociationLaunchExecuteCommandBase::IsSharedAppsEnabled(v3) )
  {
    winrt::Windows::Management::Deployment::Internal::PackageManagerInternal::PackageManagerInternal((winrt::Windows::Management::Deployment::Internal::PackageManagerInternal *)&v33);
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 24), 0);
    v6 = v38;
    winrt::param::hstring::hstring((winrt::param::hstring *)&hMem, StringRawBuffer);
    winrt::impl::consume_Windows_Management_Deployment_Internal_IPackageManagerInternal<winrt::Windows::Management::Deployment::Internal::IPackageManagerInternal>::EnsurePackageIsRegisteredForUser(
      &v33,
      &hMem,
      v6);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v33);
  }
  punkSite = 0;
  v33 = v40;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&punkSite);
  v7 = Microsoft::WRL::Details::MakeAndInitialize<CTargetViewSizePreference,CTargetViewSizePreference,enum APPLICATION_VIEW_SIZE_PREFERENCE &,IUnknown *>(
         &punkSite,
         (char *)this + 68,
         &v33);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  punk = 0;
  Instance = CoCreateInstance(
               &CLSID_ApplicationActivationManager,
               0,
               1u,
               &GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d,
               (LPVOID *)&punk);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v9 = IUnknown_SetSite(punk, punkSite);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
      (const char *)(unsigned int)v9,
      ppva);
  v11 = ViewSizePreferenceHelpers::PopulateViewValueSetFromSite((ViewSizePreferenceHelpers *)punkSite, punk, v10);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
      (const char *)(unsigned int)v11,
      ppva);
  LaunchExecuteCommandBase::GetCallerPackageFamilyName((char *)this - 40, &string);
  v33 = (void *)WindowsGetStringRawBuffer(*((HSTRING *)this + 24), 0);
  v32 = (void *)WindowsGetStringRawBuffer(*((HSTRING *)this + 6), 0);
  v34 = WindowsGetStringRawBuffer(string, 0);
  LauncherDesktopProvider::Execute::ActivateTarget<unsigned short const *,unsigned short const *,unsigned short const *>(
    &v44,
    &v34,
    &v32,
    &v33);
  memset(&hMem, 0, sizeof(hMem));
  if ( (int)GetSidStringFromToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, (LPWSTR *)&hMem) >= 0 )
  {
    AssignedAccessTypeForUser_0 = GetAssignedAccessTypeForUser_0(hMem.Reserved.Reserved1);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&hMem);
    if ( AssignedAccessTypeForUser_0 == 3 )
    {
      v15 = -2147024891;
      LODWORD(hMem.Reserved.Reserved1) = -2147024891;
      goto LABEL_36;
    }
  }
  else if ( hMem.Reserved.Reserved1 )
  {
    LocalFree(hMem.Reserved.Reserved1);
  }
  if ( *((_DWORD *)this + 16) == 1 )
  {
    v32 = 0;
    v33 = (void *)WindowsGetStringRawBuffer(string, 0);
    hMem.Reserved.Reserved1 = (PVOID)*((_QWORD *)this + 15);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v13 = Microsoft::WRL::Details::MakeAndInitialize<CProtocolActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,IShellItemArray *,unsigned short const *>(&v32);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
        (const char *)(unsigned int)v13,
        ppva);
    LODWORD(v34) = 0;
    v16 = punk;
    lpVtbl = punk->lpVtbl;
    v43 = 0;
    v18 = WindowsCreateStringReference(L"Windows.Protocol", 0x10u, &hMem, &v43);
    if ( v18 < 0 )
      RaiseException(v18, 1u, 0, 0);
    ppva = (int)v43;
    v15 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))lpVtbl[5].QueryInterface)(
            v16,
            *((_QWORD *)this + 24),
            *((_QWORD *)this + 22),
            0);
    LODWORD(hMem.Reserved.Reserved1) = v15;
    v19 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  else if ( *((_DWORD *)this + 16) == 2 )
  {
    if ( !v2[28] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
        (const char *)0x80070057LL,
        ppva);
    v33 = 0;
    v20 = Windows::Internal::StringReference::StringReference((HSTRING *)&hMem, (const unsigned __int16 (*)[66])v12);
    v21 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationStatics>>(
            *v20,
            &v33);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB6,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
        (const char *)(unsigned int)v21,
        ppva);
    v32 = 0;
    v22 = *(__int64 (__fastcall **)(char *, HSTRING, void **))(*v2 + 16LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v23 = v22((char *)this - 40, string, &v32);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
        (const char *)(unsigned int)v23,
        ppva);
    v34 = 0;
    v24 = v33;
    v25 = *(__int64 (__fastcall **)(void *, _QWORD, _QWORD, HSTRING_HEADER *))(*(_QWORD *)v33 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    *(_OWORD *)&hMem.Reserved.Reserved1 = ActivationType_LauncherServiceActivation;
    ppva = (int)v32;
    v15 = v25(v24, *((_QWORD *)this + 23), *((_QWORD *)this + 6), &hMem);
    LODWORD(hMem.Reserved.Reserved1) = v15;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  }
  else
  {
    v15 = AssociationLaunchExecuteCommandBase::ActivateApplicationForFile((AssociationLaunchExecuteCommandBase *)((char *)this - 40));
    LODWORD(hMem.Reserved.Reserved1) = v15;
  }
LABEL_36:
  TelemetryCorrelationVectorServiceProvider::Increment(&pv, *((_QWORD *)this - 1));
  v33 = pv;
  v32 = (void *)WindowsGetStringRawBuffer(*((HSTRING *)this + 6), 0);
  LauncherDesktopProvider::Execute::ActivationResult<long &,unsigned short const *,char *>(&v44, &hMem, &v32, &v33);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\associationlaunchexecutecommand.cpp",
      (const char *)(unsigned int)v15,
      ppva);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v44, 0);
  if ( pv )
    CoTaskMemFree(pv);
  WindowsDeleteString(string);
  string = 0;
  if ( punk )
    winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&punk);
  v26 = punkSite;
  if ( punkSite )
  {
    punkSite = 0;
    ((void (__fastcall *)(IUnknown *))v26->lpVtbl->Release)(v26);
  }
  v27 = ppvOut;
  if ( ppvOut )
  {
    ppvOut = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v44 = &LauncherDesktopProvider::Execute::`vftable';
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v44);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v47);
  wil::details::shared_object<wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v46);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>(v45);
  return 0;
}

```

## disassembly

```asm
0x180054940  push    rbx
0x180054942  push    rsi
0x180054943  push    rdi
0x180054944  push    r12
0x180054946  push    r14
0x180054948  push    r15
0x18005494a  sub     rsp, 228h
0x180054951  mov     rax, cs:__security_cookie
0x180054958  xor     rax, rsp
0x18005495b  mov     [rsp+258h+var_48], rax
0x180054963  mov     rsi, rcx
0x180054966  lea     rdx, aExecute; "Execute"
0x18005496d  lea     rcx, [rsp+258h+var_198]; struct wil::details::IFailureCallback *
0x180054975  call    ??0?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005497a  lea     r14, ??_7Execute@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::Execute::`vftable'
0x180054981  mov     [rsp+258h+var_198], r14
0x180054989  lea     rcx, [rsp+258h+var_198]; this
0x180054991  call    ?StartActivity@Execute@LauncherDesktopProvider@@QEAAXXZ; LauncherDesktopProvider::Execute::StartActivity(void)
0x180054996  nop
0x180054997  lea     rdi, [rsi-28h]
0x18005499b  lea     rdx, [rsp+258h+var_1C8]
0x1800549a3  mov     rcx, rdi
0x1800549a6  call    ?GetSite@LaunchExecuteCommandBase@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; LaunchExecuteCommandBase::GetSite(void)
0x1800549ab  nop
0x1800549ac  xor     r12d, r12d
0x1800549af  mov     [rsp+258h+var_1D8], r12
0x1800549b7  mov     [rsp+258h+ppvOut], r12
0x1800549bf  lea     rcx, [rsp+258h+ppvOut]
0x1800549c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800549cc  lea     r9, [rsp+258h+ppvOut]; ppvOut
0x1800549d4  lea     r8, _GUID_cb738c08_8b2d_4349_a14d_b969e62e964c; riid
0x1800549db  lea     rdx, SID_ApplicationUserContextTokenInfo; guidService
0x1800549e2  mov     rcx, [rsi-8]; punk
0x1800549e6  call    cs:__imp_IUnknown_QueryService
0x1800549ec  test    eax, eax
0x1800549ee  js      short loc_180054A2C
0x1800549f0  mov     rcx, [rsp+258h+ppvOut]
0x1800549f8  mov     rax, [rcx]
0x1800549fb  lea     rdx, [rsp+258h+var_1D8]
0x180054a03  mov     rax, [rax+18h]
0x180054a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a0c  mov     rcx, [rsp+258h]; this
0x180054a14  test    eax, eax
0x180054a16  jns     short loc_180054A2C
0x180054a18  mov     r9d, eax; char *
0x180054a1b  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x180054a22  lea     edx, [r12+74h]; void *
0x180054a27  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054a2c  call    ?IsSharedAppsEnabled@AssociationLaunchExecuteCommandBase@@AEAA_NXZ; AssociationLaunchExecuteCommandBase::IsSharedAppsEnabled(void)
0x180054a31  test    al, al
0x180054a33  jz      short loc_180054A87
0x180054a35  lea     rcx, [rsp+258h+var_200]; this
0x180054a3a  call    ??0PackageManagerInternal@Internal@Deployment@Management@Windows@winrt@@QEAA@XZ; winrt::Windows::Management::Deployment::Internal::PackageManagerInternal::PackageManagerInternal(void)
0x180054a3f  nop
0x180054a40  xor     edx, edx; length
0x180054a42  mov     rcx, [rsi+0C0h]; string
0x180054a49  call    cs:__imp_WindowsGetStringRawBuffer
0x180054a4f  mov     rbx, [rsp+258h+var_1D8]
0x180054a57  mov     rdx, rax; unsigned __int16 *
0x180054a5a  lea     rcx, [rsp+258h+hMem]; this
0x180054a62  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180054a67  mov     r8, rbx
0x180054a6a  lea     rdx, [rsp+258h+hMem]
0x180054a72  lea     rcx, [rsp+258h+var_200]
0x180054a77  call    ?EnsurePackageIsRegisteredForUser@?$consume_Windows_Management_Deployment_Internal_IPackageManagerInternal@UIPackageManagerInternal@Internal@Deployment@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_K@Z; winrt::impl::consume_Windows_Management_Deployment_Internal_IPackageManagerInternal<winrt::Windows::Management::Deployment::Internal::IPackageManagerInternal>::EnsurePackageIsRegisteredForUser(winrt::param::hstring const &,unsigned __int64)
0x180054a7c  nop
0x180054a7d  lea     rcx, [rsp+258h+var_200]; this
0x180054a82  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180054a87  mov     [rsp+258h+punkSite], r12
0x180054a8c  mov     rax, [rsp+258h+var_1C8]
0x180054a94  mov     [rsp+258h+var_200], rax
0x180054a99  lea     rcx, [rsp+258h+punkSite]
0x180054a9e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180054aa3  lea     rdx, [rsi+44h]
0x180054aa7  lea     r8, [rsp+258h+var_200]
0x180054aac  lea     rcx, [rsp+258h+punkSite]
0x180054ab1  call    ??$MakeAndInitialize@VCTargetViewSizePreference@@V1@AEAW4APPLICATION_VIEW_SIZE_PREFERENCE@@PEAUIUnknown@@@Details@WRL@Microsoft@@YAJPEAPEAVCTargetViewSizePreference@@AEAW4APPLICATION_VIEW_SIZE_PREFERENCE@@$$QEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CTargetViewSizePreference,CTargetViewSizePreference,APPLICATION_VIEW_SIZE_PREFERENCE &,IUnknown *>(CTargetViewSizePreference * *,APPLICATION_VIEW_SIZE_PREFERENCE &,IUnknown * &&)
0x180054ab6  mov     rcx, [rsp+258h]; this
0x180054abe  test    eax, eax
0x180054ac0  jns     short loc_180054AD6
0x180054ac2  mov     r9d, eax; char *
0x180054ac5  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x180054acc  mov     edx, 81h; void *
0x180054ad1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054ad6  mov     [rsp+258h+punk], r12
0x180054adb  lea     rax, [rsp+258h+punk]
0x180054ae0  mov     [rsp+258h+ppv], rax; int
0x180054ae5  lea     r9, _GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d; riid
0x180054aec  xor     edx, edx; pUnkOuter
0x180054aee  lea     r8d, [rdx+1]; dwClsContext
0x180054af2  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x180054af9  call    cs:__imp_CoCreateInstance
0x180054aff  mov     rcx, [rsp+258h]; this
0x180054b07  test    eax, eax
0x180054b09  jns     short loc_180054B1F
0x180054b0b  mov     r9d, eax; char *
0x180054b0e  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x180054b15  mov     edx, 86h; void *
0x180054b1a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054b1f  mov     rdx, [rsp+258h+punkSite]; punkSite
0x180054b24  mov     rcx, [rsp+258h+punk]; punk
0x180054b29  call    cs:__imp_IUnknown_SetSite
0x180054b2f  mov     rcx, [rsp+258h]; this
0x180054b37  test    eax, eax
0x180054b39  jns     short loc_180054B4F
0x180054b3b  mov     r9d, eax; char *
0x180054b3e  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x180054b45  mov     edx, 87h; void *
0x180054b4a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054b4f  mov     rdx, [rsp+258h+punk]; struct IUnknown *
0x180054b54  mov     rcx, [rsp+258h+punkSite]; this
0x180054b59  call    ?PopulateViewValueSetFromSite@ViewSizePreferenceHelpers@@YAJPEAUIUnknown@@0@Z; ViewSizePreferenceHelpers::PopulateViewValueSetFromSite(IUnknown *,IUnknown *)
0x180054b5e  mov     rcx, [rsp+258h]; this
0x180054b66  test    eax, eax
0x180054b68  jns     short loc_180054B7E
0x180054b6a  mov     r9d, eax; char *
0x180054b6d  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x180054b74  mov     edx, 95h; void *
0x180054b79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054b7e  lea     rdx, [rsp+258h+string]
0x180054b83  mov     rcx, rdi
0x180054b86  call    ?GetCallerPackageFamilyName@LaunchExecuteCommandBase@@IEAA?AVHString@Wrappers@WRL@Microsoft@@XZ; LaunchExecuteCommandBase::GetCallerPackageFamilyName(void)
0x180054b8b  nop
0x180054b8c  xor     edx, edx; length
0x180054b8e  mov     rcx, [rsi+0C0h]; string
0x180054b95  call    cs:__imp_WindowsGetStringRawBuffer
0x180054b9b  mov     [rsp+258h+var_200], rax
0x180054ba0  xor     edx, edx; length
0x180054ba2  mov     rcx, [rsi+30h]; string
0x180054ba6  call    cs:__imp_WindowsGetStringRawBuffer
0x180054bac  mov     [rsp+258h+var_208], rax
0x180054bb1  xor     edx, edx; length
0x180054bb3  mov     rcx, [rsp+258h+string]; string
0x180054bb8  call    cs:__imp_WindowsGetStringRawBuffer
0x180054bbe  mov     [rsp+258h+var_1F8], rax
0x180054bc3  lea     r9, [rsp+258h+var_200]
0x180054bc8  lea     r8, [rsp+258h+var_208]
0x180054bcd  lea     rdx, [rsp+258h+var_1F8]
0x180054bd2  lea     rcx, [rsp+258h+var_198]
0x180054bda  call    ??$ActivateTarget@PEBGPEBGPEBG@Execute@LauncherDesktopProvider@@QEAAX$$QEAPEBG00@Z; LauncherDesktopProvider::Execute::ActivateTarget<ushort const *,ushort const *,ushort const *>(ushort const * &&,ushort const * &&,ushort const * &&)
0x180054bdf  mov     [rsp+258h+hMem], r12
0x180054be7  mov     [rsp+258h+hMem+8], r12
0x180054bef  mov     [rsp+258h+var_1A8], r12
0x180054bf7  lea     rdx, [rsp+258h+hMem]; StringSid
0x180054bff  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180054c06  call    GetSidStringFromToken
0x180054c0b  mov     rcx, [rsp+258h+hMem]; hMem
0x180054c13  test    eax, eax
0x180054c15  jns     short loc_180054C91
0x180054c17  test    rcx, rcx
0x180054c1a  jz      short loc_180054C22
0x180054c1c  call    cs:__imp_LocalFree
0x180054c22  cmp     dword ptr [rsi+40h], 1
0x180054c26  jnz     loc_180054D8E
0x180054c2c  mov     [rsp+258h+var_208], r12
0x180054c31  xor     edx, edx; length
0x180054c33  mov     rcx, [rsp+258h+string]; string
0x180054c38  call    cs:__imp_WindowsGetStringRawBuffer
0x180054c3e  mov     [rsp+258h+var_200], rax
0x180054c43  mov     rax, [rsi+78h]
0x180054c47  mov     [rsp+258h+hMem], rax
0x180054c4f  lea     rcx, [rsp+258h+var_208]
0x180054c54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054c59  lea     r8, [rsp+258h+var_200]
0x180054c5e  lea     rdx, [rsp+258h+hMem]
0x180054c66  lea     rcx, [rsp+258h+var_208]; void **
0x180054c6b  call    ??$MakeAndInitialize@VCProtocolActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIShellItemArray@@PEBG@Details@WRL@Microsoft@@YAJPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@$$QEAPEAUIShellItemArray@@$$QEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<CProtocolActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,IShellItemArray *,ushort const *>(Windows::ApplicationModel::Activation::IActivatedEventArgs * *,IShellItemArray * &&,ushort const * &&)
0x180054c70  mov     rcx, [rsp+258h]; this
0x180054c78  test    eax, eax
0x180054c7a  jns     short loc_180054CBF
0x180054c7c  mov     r9d, eax; char *
0x180054c7f  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x180054c86  mov     edx, 0A3h; void *
0x180054c8b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054c91  call    GetAssignedAccessTypeForUser_0
0x180054c96  mov     ebx, eax
0x180054c98  lea     rcx, [rsp+258h+hMem]
0x180054ca0  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180054ca5  cmp     ebx, 3
0x180054ca8  jnz     loc_180054C22
0x180054cae  mov     ebx, 80070005h
0x180054cb3  mov     dword ptr [rsp+258h+hMem], ebx
0x180054cba  jmp     loc_180054F07
0x180054cbf  mov     dword ptr [rsp+258h+var_1F8], r12d
0x180054cc4  mov     rbx, [rsp+258h+punk]
0x180054cc9  mov     rdi, [rbx]
0x180054ccc  mov     r14, [rsp+258h+var_1D8]
0x180054cd4  mov     r15, [rsp+258h+var_208]
0x180054cd9  mov     [rsp+258h+var_1A0], r12
0x180054ce1  lea     r9, [rsp+258h+var_1A0]; string
0x180054ce9  lea     r8, [rsp+258h+hMem]; hstringHeader
0x180054cf1  mov     edx, 10h; length
0x180054cf6  lea     rcx, aWindowsProtoco; "Windows.Protocol"
0x180054cfd  call    cs:__imp_WindowsCreateStringReference
0x180054d03  test    eax, eax
0x180054d05  jns     short loc_180054D1A
0x180054d07  xor     r9d, r9d; lpArguments
0x180054d0a  xor     r8d, r8d; nNumberOfArguments
0x180054d0d  lea     edx, [r9+1]; dwExceptionFlags
0x180054d11  mov     ecx, eax; dwExceptionCode
0x180054d13  call    cs:__imp_RaiseException
0x180054d19  nop
0x180054d1a  lea     rax, [rsp+258h+var_1F8]
0x180054d1f  mov     [rsp+258h+var_218], rax
0x180054d24  mov     [rsp+258h+var_220], r14
0x180054d29  mov     dword ptr [rsp+258h+var_228], r12d
0x180054d2e  mov     [rsp+258h+var_230], r15
0x180054d33  mov     rdx, [rsp+258h+var_1A0]
0x180054d3b  mov     [rsp+258h+ppv], rdx
0x180054d40  xor     r9d, r9d
0x180054d43  mov     r8, [rsi+0B0h]
0x180054d4a  mov     rdx, [rsi+0C0h]
0x180054d51  mov     rcx, rbx
0x180054d54  mov     rax, [rdi+78h]
0x180054d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d5d  mov     ebx, eax
0x180054d5f  mov     dword ptr [rsp+258h+hMem], eax
0x180054d66  mov     rcx, [rsp+258h+var_208]
0x180054d6b  test    rcx, rcx
0x180054d6e  jz      short loc_180054D82
0x180054d70  mov     [rsp+258h+var_208], r12
0x180054d75  mov     rax, [rcx]
0x180054d78  mov     rax, [rax+10h]
0x180054d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d81  nop
0x180054d82  lea     r14, ??_7Execute@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::Execute::`vftable'
0x180054d89  jmp     loc_180054F07
0x180054d8e  cmp     dword ptr [rsi+40h], 2
0x180054d92  jnz     loc_180054EE4
0x180054d98  mov     rcx, [rsp+258h]; this
0x180054da0  cmp     [rdi+0E0h], r12
0x180054da7  jnz     short loc_180054DC0
0x180054da9  mov     r9d, 80070057h; char *
0x180054daf  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x180054db6  mov     edx, 0B3h; void *
0x180054dbb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054dc0  mov     [rsp+258h+var_200], r12
0x180054dc5  lea     rcx, [rsp+258h+hMem]; string
0x180054dcd  call    ??$?0$0EC@@StringReference@Internal@Windows@@QEAA@AEAY0EC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[66])
0x180054dd2  lea     rdx, [rsp+258h+var_200]
0x180054dd7  mov     rcx, [rax]
0x180054dda  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationActivationStatics@Private@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationActivationStatics@Private@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationStatics>>)
0x180054ddf  mov     rcx, [rsp+258h]; this
0x180054de7  test    eax, eax
0x180054de9  jns     short loc_180054DFF
0x180054deb  mov     r9d, eax; char *
0x180054dee  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x180054df5  mov     edx, 0B6h; void *
0x180054dfa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054dff  mov     [rsp+258h+var_208], r12
0x180054e04  mov     rax, [rdi]
0x180054e07  mov     rbx, [rax+10h]
0x180054e0b  lea     rcx, [rsp+258h+var_208]
0x180054e10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054e15  lea     r8, [rsp+258h+var_208]
0x180054e1a  mov     rdx, [rsp+258h+string]
0x180054e1f  mov     rcx, rdi
0x180054e22  mov     rax, rbx
0x180054e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e2a  mov     rcx, [rsp+258h]; this
0x180054e32  test    eax, eax
0x180054e34  jns     short loc_180054E4A
0x180054e36  mov     r9d, eax; char *
0x180054e39  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\windows.system.launc"...
0x180054e40  mov     edx, 0B9h; void *
0x180054e45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054e4a  mov     [rsp+258h+var_1F8], r12
0x180054e4f  mov     rdi, [rsp+258h+var_200]
0x180054e54  mov     rax, [rdi]
0x180054e57  mov     rbx, [rax+48h]
0x180054e5b  lea     rcx, [rsp+258h+var_1F8]
0x180054e60  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054e65  mov     rdx, [rsp+258h+var_1D8]
0x180054e6d  mov     r8, [rsp+258h+var_208]
0x180054e72  movups  xmm0, cs:ActivationType_LauncherServiceActivation
0x180054e79  movdqu  xmmword ptr [rsp+258h+hMem], xmm0
0x180054e82  lea     rax, [rsp+258h+var_1F8]
0x180054e87  mov     [rsp+258h+var_220], rax
0x180054e8c  mov     [rsp+258h+var_228], rdx
0x180054e91  mov     [rsp+258h+var_230], r12
0x180054e96  mov     [rsp+258h+ppv], r8
0x180054e9b  lea     r9, [rsp+258h+hMem]
0x180054ea3  mov     r8, [rsi+30h]
0x180054ea7  mov     rdx, [rsi+0B8h]
0x180054eae  mov     rcx, rdi
0x180054eb1  mov     rax, rbx
0x180054eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054eb9  mov     ebx, eax
0x180054ebb  mov     dword ptr [rsp+258h+hMem], eax
0x180054ec2  lea     rcx, [rsp+258h+var_1F8]
0x180054ec7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054ecc  nop
0x180054ecd  lea     rcx, [rsp+258h+var_208]
0x180054ed2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054ed7  nop
0x180054ed8  lea     rcx, [rsp+258h+var_200]
0x180054edd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054ee2  jmp     short loc_180054F07
0x180054ee4  mov     r9, [rsp+258h+var_1D8]
0x180054eec  lea     r8, [rsp+258h+string]
  ... truncated ...
```
