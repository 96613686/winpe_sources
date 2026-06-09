# CInvokeCreateProcessVerb::CallCreateProcess(void)

- ea: `0x18014b590`
- end: `0x18014c0ce`
- name: `?CallCreateProcess@CInvokeCreateProcessVerb@@AEAAJXZ`
- size: `2878`
- prototype: `__int64 __fastcall(CInvokeCreateProcessVerb *__hidden this)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18014c3b8`

## callees

- `0x180009fc0`
- `0x18001adbc`
- `0x18001b3d8`
- `0x180038f50`
- `0x180077880`
- `0x18007ea3c`
- `0x180083c94`
- `0x1800899a4`
- `0x1800c8920`
- `0x1800ff160`
- `0x18014b590`
- `0x18014c0d4`
- `0x18014c0f4`
- `0x18014c1f0`
- `0x18014dc80`
- `0x1801720d0`
- `0x18019c0f0`
- `0x180228bcc`
- `0x180228c50`
- `0x180246148`
- `0x1802d07f0`
- `0x1802d4f88`
- `0x1802d5064`
- `0x1802fbff8`
- `0x18033f1b0`
- `0x18035fa60`
- `0x180369b98`
- `0x180370e34`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b4e40`
- `0x1803b69b9`
- `0x180609e28`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18014ba3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18014ba3a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18066b71a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18066b71a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18014bb1d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18014c0ac`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18014bb1d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18014c0ac`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18014bab6`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18014bab6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18014b730`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18014b730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014bf12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014bf23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014bfab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014c057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014c0bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014bf12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014bf23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014bfab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014c057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014c0bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18014b5e8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18014b5e8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x18014b5fe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x18014b5fe`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x18066b7a8`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x18066b7a8`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18066b8f4`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18066b8f4`
- `KERNELBASE!ParseApplicationUserModelId` at `0x18014bbfc`
- `KERNELBASE!ParseApplicationUserModelId` at `0x18014bbfc`
- `KERNELBASE!GetCurrentPackageFamilyName` at `0x18066bbc0`
- `KERNELBASE!GetCurrentPackageFamilyName` at `0x18066bbc0`
- `KERNELBASE!GetCurrentApplicationUserModelId` at `0x18066bbd7`
- `KERNELBASE!GetCurrentApplicationUserModelId` at `0x18066bbd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014bd11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014bd11`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18066b778`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18066b778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014b90a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014ba9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014bb78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014b90a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014ba9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014bb78`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18014b982`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18066ba73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18014b982`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18066ba73`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18014bf51`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18014bf51`
- `ext-ms-win-rtcore-ntuser-iam-l1-1-2!SetProcessLaunchForegroundPolicy` at `0x18014c086`
- `ext-ms-win-rtcore-ntuser-iam-l1-1-2!SetProcessLaunchForegroundPolicy` at `0x18014c086`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18014b6cd`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18014b6cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18066b829`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18066b829`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x18066bb03`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x18066bb03`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_ZoneCheckUrlExW` at `0x18066bb47`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_ZoneCheckUrlExW` at `0x18066bb47`
- `ext-ms-win-appcompat-pcacli-l1-1-0!PcaMonitorProcess2` at `0x18014c046`
- `ext-ms-win-appcompat-pcacli-l1-1-0!PcaMonitorProcess2` at `0x18014c046`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x18066b887`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x18066b887`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x18066b8c9`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x18066b8c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CInvokeCreateProcessVerb::CallCreateProcess(CInvokeCreateProcessVerb *this)
{
  UINT32 v2; // r12d
  const WCHAR *FileNameW; // rax
  const WCHAR *v4; // rbx
  DWORD v5; // edi
  HRESULT v6; // eax
  signed int v7; // r15d
  BOOL ProcessAsUserW; // eax
  int v9; // eax
  char v10; // di
  void *v11; // rbx
  char v12; // r13
  const unsigned __int16 *v13; // rsi
  int v14; // ecx
  char v15; // di
  DWORD v16; // ecx
  int v17; // eax
  unsigned int v18; // ebx
  void *v19; // rcx
  void *v21; // rcx
  HRESULT v22; // edi
  LPVOID v23; // rcx
  __int64 v24; // rcx
  void *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  void *v31; // rcx
  unsigned int v32; // eax
  void *v33; // rcx
  HRESULT v34; // ebx
  int v35; // eax
  LPVOID v36; // rax
  __int64 v37; // r9
  __int64 v38; // rdx
  unsigned int AicLaunchFlags; // eax
  unsigned __int64 v40; // r9
  int v41; // eax
  __int64 v42; // rdx
  unsigned __int64 i; // rcx
  int v44; // eax
  HRESULT v45; // eax
  LPVOID v46; // rsi
  __int64 (__fastcall *v47)(LPVOID, GUID *, GUID *, __int64 *); // rdi
  __int64 v48; // rax
  _DWORD *v49; // rcx
  unsigned int v50; // r12d
  int v51; // eax
  __int64 v52; // rdx
  int token_information; // eax
  void *v54; // rdi
  __int64 v55; // rsi
  const char *v56; // r9
  int LastError; // eax
  int v58; // eax
  __int64 v59; // rdx
  __int64 v60; // r9
  int v61; // eax
  __int64 v62; // rcx
  unsigned int v63; // edi
  BOOL v64; // eax
  __int64 v65; // rsi
  int (__fastcall *v66)(__int64, GUID *, GUID *, LPVOID *); // rdi
  WCHAR *v67; // rdi
  unsigned int v68; // eax
  unsigned __int64 v69; // r10
  void *v70; // r11
  WCHAR *v71; // r8
  WCHAR *v72; // rdx
  void *bInheritHandles; // [rsp+20h] [rbp-E0h]
  _BYTE *dwCreationFlags; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v75; // [rsp+70h] [rbp-90h]
  char v76; // [rsp+80h] [rbp-80h]
  unsigned int v77; // [rsp+84h] [rbp-7Ch]
  const unsigned __int16 *pszPath; // [rsp+88h] [rbp-78h]
  void *v79; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID *p_pguid; // [rsp+98h] [rbp-68h]
  unsigned __int64 *v81; // [rsp+A0h] [rbp-60h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+A8h] [rbp-58h] BYREF
  void *ppvOut; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp-48h] BYREF
  DWORD ReturnLength[2]; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v87; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int TokenInformation; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v89; // [rsp+DCh] [rbp-24h] BYREF
  int v90[2]; // [rsp+E0h] [rbp-20h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v92; // [rsp+F0h] [rbp-10h] BYREF
  GUID pguid; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v94; // [rsp+108h] [rbp+8h] BYREF
  char Parameter; // [rsp+110h] [rbp+10h] BYREF
  int v96; // [rsp+111h] [rbp+11h]
  __int16 v97; // [rsp+115h] [rbp+15h]
  char Data3_high; // [rsp+117h] [rbp+17h]
  CInvokeCreateProcessVerb *v99; // [rsp+118h] [rbp+18h]
  char v100; // [rsp+120h] [rbp+20h]
  _BYTE v101[1056]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+550h] [rbp+450h] BYREF
  WCHAR packageRelativeApplicationId[136]; // [rsp+5E0h] [rbp+4E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+748h] [rbp+648h]

  if ( *((_DWORD *)this + 106) == 2 && SHTestTokenMembership(0, 0x220u) )
    v2 = 0;
  else
    v2 = *((_DWORD *)this + 106);
  packageRelativeApplicationIdLength = v2;
  LauncherAppLaunchTelemetry::CallCreateProcess<unsigned int>(&packageRelativeApplicationIdLength);
  FileNameW = PathFindFileNameW(*((LPCWSTR *)this + 73));
  if ( PathMatchSpecW(FileNameW, L"*.CMD;*.BAT") )
    v4 = 0;
  else
    v4 = (const WCHAR *)*((_QWORD *)this + 73);
  pszPath = v4;
  *((_DWORD *)this + 58) = 112;
  *((_QWORD *)this + 42) = *((_QWORD *)this + 47);
  v5 = *((_DWORD *)this + 57) | 0x80004;
  v77 = v5;
  v92 = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
  if ( !memcmp_0(&SID_ApplicationUserContextTokenInfo, &Buf2, 0x10u) )
    v6 = CInvokeCreateProcessVerb::QueryInterface(this, &GUID_cb738c08_8b2d_4349_a14d_b969e62e964c, &ppvOut);
  else
    v6 = IUnknown_QueryService(
           *((IUnknown **)this + 1),
           (const GUID *const)&SID_ApplicationUserContextTokenInfo,
           &GUID_cb738c08_8b2d_4349_a14d_b969e62e964c,
           &ppvOut);
  if ( v6 >= 0 && ppvOut )
    (*(void (__fastcall **)(void *, unsigned __int64 *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &v92);
  v7 = 0;
  if ( CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(this) )
    goto LABEL_9;
  if ( v2 )
  {
    if ( v2 != 1 )
    {
LABEL_9:
      CInvokeCreateProcessVerb::DelegateSwitchToDesktopIfNeeded(this);
      goto LABEL_16;
    }
    ProcessAsUserW = CreateProcessAsUserW(
                       *((HANDLE *)this + 51),
                       v4,
                       *((LPWSTR *)this + 64),
                       0,
                       0,
                       *((_DWORD *)this + 118),
                       v5 | 0x2000000,
                       *((LPVOID *)this + 54),
                       *((LPCWSTR *)this + 10),
                       (LPSTARTUPINFOW)((char *)this + 232),
                       (LPPROCESS_INFORMATION)this + 16);
  }
  else
  {
    ProcessAsUserW = CreateProcessW(
                       v4,
                       *((LPWSTR *)this + 64),
                       0,
                       0,
                       *((_DWORD *)this + 118),
                       v5,
                       *((LPVOID *)this + 54),
                       *((LPCWSTR *)this + 10),
                       (LPSTARTUPINFOW)((char *)this + 232),
                       (LPPROCESS_INFORMATION)this + 16);
  }
  v9 = ResultFromWin32Bool(ProcessAsUserW);
  v7 = v9;
  if ( v9 >= 0 || v9 == -2147024156 )
    goto LABEL_9;
LABEL_16:
  v10 = 0;
  v76 = 0;
  v11 = 0;
  v79 = 0;
  v81 = 0;
  p_pguid = 0;
  v94 = 0;
  pguid = 0;
  hObject = 0;
  v12 = 1;
  if ( CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(this) && (*((_DWORD *)this + 138) & 0x800) != 0 )
  {
    v17 = CInvokeCreateProcessVerb::ResolvePackageFullNameIfNecessary(this, v92);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A0,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
        (const char *)(unsigned int)v17,
        (int)bInheritHandles);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v19 = ppvOut;
      if ( ppvOut )
      {
        ppvOut = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return v18;
    }
    memset_0(packageRelativeApplicationId, 0, 0x84u);
    packageRelativeApplicationIdLength = 66;
    memset_0(packageFamilyName, 0, 0x82u);
    packageFamilyNameLength = 65;
    v32 = ParseApplicationUserModelId(
            *((PCWSTR *)this + 66),
            &packageFamilyNameLength,
            packageFamilyName,
            &packageRelativeApplicationIdLength,
            packageRelativeApplicationId);
    if ( v32 )
    {
      v18 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x7A7,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
              (const char *)v32,
              (unsigned int)bInheritHandles);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v33 = ppvOut;
      if ( ppvOut )
      {
        ppvOut = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
      }
      return v18;
    }
    v89 = 464;
    v36 = CoTaskMemAlloc(0x1D0u);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v79,
      v36);
    v11 = v79;
    if ( !v79 )
    {
      v22 = -2147024882;
      v37 = 2147942414LL;
      v38 = 1963;
LABEL_102:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
        (const char *)v37,
        (int)bInheritHandles);
LABEL_94:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v79);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
      return (unsigned int)v22;
    }
    if ( v92 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        0);
      v45 = UMgrQueryUserToken(v92, &hObject);
      v22 = v45;
      if ( v45 < 0 )
      {
        v38 = 1969;
LABEL_138:
        v37 = (unsigned int)v45;
        goto LABEL_102;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        0);
      v45 = wil::open_current_access_token_nothrow(&hObject, 8, 1);
      v22 = v45;
      if ( v45 < 0 )
      {
        v38 = 1975;
        goto LABEL_138;
      }
    }
    v10 = 1;
    v76 = 1;
    if ( (*((_DWORD *)this + 138) & 0x1000) != 0 )
    {
      v45 = CoCreateGuid(&pguid);
      v22 = v45;
      if ( v45 < 0 )
      {
        v38 = 1987;
        goto LABEL_138;
      }
      bInheritHandles = &v89;
      v51 = PsmCreateKeyWithDynamicId(*((_QWORD *)this + 68), packageRelativeApplicationId, &pguid, v11);
      if ( v51 < 0 )
      {
        v52 = 1989;
LABEL_145:
        v22 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)v52,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
                (const char *)(unsigned int)v51,
                (int)bInheritHandles);
        goto LABEL_94;
      }
      ppv = 0;
      token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&ppv, hObject);
      v22 = token_information;
      if ( token_information < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7C8,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
          (const char *)(unsigned int)token_information,
          (int)&v89);
        if ( ppv )
          CZeroInitNew::operator delete(ppv);
        goto LABEL_94;
      }
      v54 = ppv;
      v55 = *(_QWORD *)ppv;
      TokenInformation = 0;
      ReturnLength[0] = 4;
      if ( !GetTokenInformation(hObject, TokenSessionId, &TokenInformation, 4u, ReturnLength) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x7CE,
                      (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
                      v56);
LABEL_91:
        v34 = LastError;
        if ( v54 )
          CZeroInitNew::operator delete(v54);
        v22 = v34;
        goto LABEL_94;
      }
      memset_0(v101, 0, 0x418u);
      dwCreationFlags = v101;
      bInheritHandles = 0;
      v58 = HamHostIdInitializeKey(v11, v55, TokenInformation, 0);
      if ( v58 < 0 )
      {
        v59 = 2002;
LABEL_151:
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)v59,
                      (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
                      (const char *)(unsigned int)v58,
                      0);
        goto LABEL_91;
      }
      v58 = HamHostIdFindOrCreate(v101, &v94);
      if ( v58 < 0 )
      {
        v59 = 2004;
        goto LABEL_151;
      }
      v81 = (unsigned __int64 *)&v94;
      p_pguid = &pguid;
      if ( v54 )
        CZeroInitNew::operator delete(v54);
      v10 = 1;
    }
    else
    {
      v51 = PsmCreateKey(*((_QWORD *)this + 68), packageRelativeApplicationId, v11, &v89);
      if ( v51 < 0 )
      {
        v52 = 2011;
        goto LABEL_145;
      }
    }
  }
  v87 = 0;
  if ( *((_QWORD *)this + 70) || v10 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v22 = CoCreateInstance(&CLSID_ShellServiceHost, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &ppv);
    if ( v22 >= 0 )
    {
      v46 = ppv;
      v47 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      v22 = v47(v46, &IID_IApplicationInstanceManager, &GUID_62a9407f_345a_4300_8cdd_4847dee60f48, &v87);
    }
    if ( v76 && v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7EE,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
        (const char *)(unsigned int)v22,
        (int)bInheritHandles);
      v23 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
      }
      v24 = v87;
      if ( v87 )
      {
        v87 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( v11 )
        CoTaskMemFree(v11);
      v25 = ppvOut;
      if ( ppvOut )
      {
        ppvOut = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
      }
      return (unsigned int)v22;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v10 = v76;
  }
  *(_QWORD *)v90 = 0;
  if ( v10 )
  {
    v60 = (*((_DWORD *)this + 138) >> 14) & 1 | 2u;
    if ( (*((_DWORD *)this + 138) & 0x8000) == 0 )
      v60 = (*((_DWORD *)this + 138) >> 14) & 1;
    bInheritHandles = v90;
    v61 = (*(__int64 (__fastcall **)(__int64, HANDLE, void *, __int64))(*(_QWORD *)v87 + 104LL))(v87, hObject, v11, v60);
    v22 = v61;
    if ( v61 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x800,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
        (const char *)(unsigned int)v61,
        (int)v90);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v90);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      goto LABEL_94;
    }
  }
  if ( !CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(this) || v2 )
  {
    v13 = pszPath;
  }
  else
  {
    AicLaunchFlags = CInvokeCreateProcessVerb::GetAicLaunchFlags(this, 0);
    v13 = pszPath;
    v41 = AicLaunchProcessWithIdentity(
            pszPath,
            *((unsigned __int16 **)this + 64),
            0,
            v77,
            *((const unsigned __int16 **)this + 10),
            (struct _STARTUPINFOW *)((char *)this + 232),
            *((const unsigned __int16 **)this + 67),
            *((const unsigned __int16 **)this + 66),
            *((HWND *)this + 24),
            AicLaunchFlags,
            *((void **)this + 52),
            v40,
            v81,
            p_pguid,
            v75,
            (struct _PROCESS_INFORMATION *)this + 16);
    v7 = v41;
    if ( v41 > 0 )
      v7 = (unsigned __int16)v41 | 0x80070000;
  }
  if ( v7 != -2147024156 )
  {
    v14 = 0;
    if ( v2 != 2 )
      goto LABEL_24;
  }
  if ( (*((_BYTE *)this + 504) & 2) != 0 )
  {
    v89 = 0;
    ReturnLength[0] = 0;
    if ( AicCheckAdminApp(v13, *((unsigned __int16 **)this + 64), &v89, (enum ELEVATION_REASON *)ReturnLength) )
      goto LABEL_168;
    v63 = v89;
    if ( v89 - 16 > 2 )
      goto LABEL_168;
    packageRelativeApplicationIdLength = 0;
    if ( v89 >= 3 )
      v63 = v89 - 16;
    TokenInformation = 0;
    if ( (int)LUAGetUserType(v62, &TokenInformation) < 0
      || (int)LUAShouldElevate(TokenInformation, v63, &packageRelativeApplicationIdLength) < 0
      || packageRelativeApplicationIdLength )
    {
LABEL_168:
      v7 = -2147024156;
      goto LABEL_62;
    }
  }
  v64 = v7 != -2147024156;
  v50 = v64 | *((_DWORD *)this + 126) & 0x10;
  if ( !(v64 & 0x10 | *((_BYTE *)this + 504) & 0x10) )
  {
    CRPCTimeout::CRPCTimeout(&Parameter, 0x1388u);
    *(_QWORD *)ReturnLength = 0;
    ppv = 0;
    packageRelativeApplicationIdLength = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ReturnLength);
    if ( CoCreateInstance(
           &CLSID_ImmersiveShell,
           0,
           4u,
           &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
           (LPVOID *)ReturnLength) >= 0 )
    {
      v65 = *(_QWORD *)ReturnLength;
      v66 = *(int (__fastcall **)(__int64, GUID *, GUID *, LPVOID *))(**(_QWORD **)ReturnLength + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      if ( v66(v65, &IID_IImmersiveSystemMode, &GUID_ea9aac7d_0cac_4ceb_981c_4545a28bada2, &ppv) >= 0
        && (*(int (__fastcall **)(LPVOID, UINT32 *))(*(_QWORD *)ppv + 24LL))(ppv, &packageRelativeApplicationIdLength) >= 0
        && packageRelativeApplicationIdLength == -1 )
      {
        v50 |= 0x40u;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ReturnLength);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
    v13 = pszPath;
  }
  if ( PathIsNetworkPathW(v13) )
  {
    packageRelativeApplicationIdLength = 0;
    ReturnLength[0] = 0;
    LODWORD(dwCreationFlags) = 6162;
    LODWORD(bInheritHandles) = 4;
    if ( (int)ZoneCheckUrlExW(
                v13,
                &packageRelativeApplicationIdLength,
                4,
                ReturnLength,
                bInheritHandles,
                dwCreationFlags,
                4611,
                0) >= 0
      && (packageRelativeApplicationIdLength & 0xF) != 0 )
    {
      v50 |= 0x80u;
    }
  }
  if ( CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(this) )
  {
    memset_0(packageFamilyName, 0, 0x82u);
    memset_0(packageRelativeApplicationId, 0, 0x104u);
    v67 = (WCHAR *)*((_QWORD *)this + 67);
    if ( !v67 )
    {
      ReturnLength[0] = 65;
      packageFamilyNameLength = 130;
      GetCurrentPackageFamilyName(ReturnLength, packageFamilyName);
      GetCurrentApplicationUserModelId(&packageFamilyNameLength, packageRelativeApplicationId);
      v67 = (WCHAR *)*((_QWORD *)this + 67);
    }
    v68 = CInvokeCreateProcessVerb::GetAicLaunchFlags(this, 1);
    v71 = packageRelativeApplicationId;
    if ( *((_QWORD *)this + 66) )
      v71 = (WCHAR *)*((_QWORD *)this + 66);
    v72 = packageFamilyName;
    if ( v67 )
      v72 = v67;
    v35 = AicLaunchProcessWithIdentity(
            v13,
            *((unsigned __int16 **)this + 64),
            v50,
            v77,
            *((const unsigned __int16 **)this + 10),
            (struct _STARTUPINFOW *)((char *)this + 232),
            v72,
            v71,
            *((HWND *)this + 24),
            v68,
            v70,
            v69,
            v81,
            p_pguid,
            v75,
            (struct _PROCESS_INFORMATION *)this + 16);
  }
  else
  {
    for ( i = 0; i < *((_QWORD *)this + 44); ++i )
    {
      v42 = 3 * i;
      if ( *(_QWORD *)(*((_QWORD *)this + 43) + 24 * i) == 131089 )
      {
        _mm_lfence();
        v48 = *((_QWORD *)this + 43);
        v49 = *(_DWORD **)(v48 + 24 * i + 8);
        if ( v49 && *(_QWORD *)(v48 + 8 * v42 + 16) == 524 )
        {
          if ( (*v49 & 0x22) == 2 || (*(_BYTE *)v49 & 0x50) != 0 )
            v50 |= 0x100u;
          else
            v50 |= 0x800u;
        }
        break;
      }
    }
    ReturnLength[0] = 0;
    v35 = AicLaunchAdminProcess(
            v13,
            *((unsigned __int16 **)this + 64),
            v50,
            v77,
            *((const unsigned __int16 **)this + 10),
            *((HWND *)this + 24),
            (struct _STARTUPINFOW *)((char *)this + 232),
            (struct _PROCESS_INFORMATION *)this + 16,
            (enum ELEVATION_REASON *)ReturnLength);
  }
  v7 = v35;
  if ( v35 > 0 )
    v7 = (unsigned __int16)v35 | 0x80070000;
  if ( v7 >= 0 )
  {
    v14 = 2;
LABEL_24:
    if ( v7 >= 0 )
    {
      v15 = v76;
      Parameter = v76;
      v96 = *(unsigned int *)((char *)&pguid.Data1 + 1);
      v97 = *(unsigned __int16 *)((char *)&pguid.Data2 + 1);
      Data3_high = HIBYTE(pguid.Data3);
      v99 = this;
      v100 = 1;
      if ( (*((_BYTE *)this + 504) & 1) != 0 || v14 )
      {
        bInheritHandles = (void *)*((_QWORD *)this + 10);
        PcaMonitorProcess2(*((_QWORD *)this + 48), 1, v13, *((_QWORD *)this + 64));
      }
      if ( *((_QWORD *)this + 70) )
      {
        if ( v87 )
        {
          v44 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 96LL))(v87, *((_QWORD *)this + 48));
          if ( v44 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8BD,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
              (const char *)(unsigned int)v44,
              (int)bInheritHandles);
        }
      }
      if ( v76 )
      {
        v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v87 + 112LL))(
                v87,
                *((_QWORD *)this + 48),
                *(_QWORD *)v90);
        v22 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8C2,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
            (const char *)(unsigned int)v28,
            (int)bInheritHandles);
          TerminateProcess(*((HANDLE *)this + 48), 0x80004005);
          v29 = *(_QWORD *)v90;
          if ( *(_QWORD *)v90 )
          {
            *(_QWORD *)v90 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          }
          v30 = v87;
          if ( v87 )
          {
            v87 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          if ( v11 )
            CoTaskMemFree(v11);
          v31 = ppvOut;
          if ( ppvOut )
          {
            ppvOut = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
          }
          return (unsigned int)v22;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v90);
        v15 = v76;
      }
      if ( (unsigned __int8)IsSetProcessLaunchForegroundPolicyPresent() && (*((_BYTE *)this + 504) & 0x20) != 0 )
        SetProcessLaunchForegroundPolicy(*((unsigned int *)this + 100), 4);
      if ( (*((_BYTE *)this + 228) & 4) != 0 || ResumeThread(*((HANDLE *)this + 49)) != -1 )
        v12 = 0;
      if ( v12 && v15 )
        TerminateProcess(*((HANDLE *)this + 48), 0x80004005);
    }
  }
  if ( (v7 & 0x1FFF0000) == 0x70000 )
  {
LABEL_62:
    v16 = (unsigned __int16)v7;
    goto LABEL_63;
  }
  v16 = v7;
LABEL_63:
  SetLastError(v16);
  v26 = *(_QWORD *)v90;
  if ( *(_QWORD *)v90 )
  {
    *(_QWORD *)v90 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v87;
  if ( v87 )
  {
    v87 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( v11 )
    CoTaskMemFree(v11);
  v21 = ppvOut;
  if ( ppvOut )
  {
    ppvOut = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18014b590  push    rbp
0x18014b592  push    rbx
0x18014b593  push    rsi
0x18014b594  push    rdi
0x18014b595  push    r12
0x18014b597  push    r13
0x18014b599  push    r14
0x18014b59b  push    r15
0x18014b59d  lea     rbp, [rsp-608h]
0x18014b5a5  sub     rsp, 708h
0x18014b5ac  mov     rax, cs:__security_cookie
0x18014b5b3  xor     rax, rsp
0x18014b5b6  mov     [rbp+640h+var_50], rax
0x18014b5bd  mov     r14, rcx
0x18014b5c0  cmp     dword ptr [rcx+1A8h], 2
0x18014b5c7  jz      loc_18014BED4
0x18014b5cd  mov     r12d, [r14+1A8h]
0x18014b5d4  mov     [rbp+640h+packageRelativeApplicationIdLength], r12d
0x18014b5d8  lea     rcx, [rbp+640h+packageRelativeApplicationIdLength]
0x18014b5dc  call    ??$CallCreateProcess@I@LauncherAppLaunchTelemetry@@SAX$$QEAI@Z; LauncherAppLaunchTelemetry::CallCreateProcess<uint>(uint &&)
0x18014b5e1  mov     rcx, [r14+248h]; pszPath
0x18014b5e8  call    cs:__imp_PathFindFileNameW
0x18014b5ef  nop     dword ptr [rax+rax+00h]
0x18014b5f4  lea     rdx, aCmdBat; "*.CMD;*.BAT"
0x18014b5fb  mov     rcx, rax; pszFile
0x18014b5fe  call    cs:__imp_PathMatchSpecW
0x18014b605  nop     dword ptr [rax+rax+00h]
0x18014b60a  test    eax, eax
0x18014b60c  jnz     loc_18014B6DB
0x18014b612  mov     rbx, [r14+248h]
0x18014b619  mov     [rbp+640h+pszPath], rbx
0x18014b61d  lea     rsi, [r14+0E8h]
0x18014b624  mov     dword ptr [rsi], 70h ; 'p'
0x18014b62a  mov     rax, [r14+178h]
0x18014b631  mov     [r14+150h], rax
0x18014b638  mov     edi, [r14+0E4h]
0x18014b63f  or      edi, 80004h
0x18014b645  mov     [rbp+640h+var_6BC], edi
0x18014b648  mov     [rbp+640h+var_650], 0
0x18014b650  mov     [rbp+640h+ppvOut], 0
0x18014b658  lea     rcx, [rbp+640h+ppvOut]
0x18014b65c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014b661  mov     r8d, 10h; Size
0x18014b667  lea     rdx, Buf2; Buf2
0x18014b66e  lea     rcx, SID_ApplicationUserContextTokenInfo; Buf1
0x18014b675  call    memcmp_0
0x18014b67a  test    eax, eax
0x18014b67c  jnz     short loc_18014B6B7
0x18014b67e  lea     r8, [rbp+640h+ppvOut]; ppv
0x18014b682  lea     rdx, _GUID_cb738c08_8b2d_4349_a14d_b969e62e964c; riid
0x18014b689  mov     rcx, r14; this
0x18014b68c  call    ?QueryInterface@CInvokeCreateProcessVerb@@UEAAJAEBU_GUID@@PEAPEAX@Z; CInvokeCreateProcessVerb::QueryInterface(_GUID const &,void * *)
0x18014b691  test    eax, eax
0x18014b693  jns     loc_18014BEF0
0x18014b699  xor     r15d, r15d
0x18014b69c  mov     rcx, r14; this
0x18014b69f  call    ?IsLaunchingWithPackageIdentity@CInvokeCreateProcessVerb@@AEBA_NXZ; CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(void)
0x18014b6a4  test    al, al
0x18014b6a6  jz      short loc_18014B6E2
0x18014b6a8  xor     esi, esi
0x18014b6aa  mov     rcx, r14; this
0x18014b6ad  call    ?DelegateSwitchToDesktopIfNeeded@CInvokeCreateProcessVerb@@AEAAXXZ; CInvokeCreateProcessVerb::DelegateSwitchToDesktopIfNeeded(void)
0x18014b6b2  jmp     loc_18014B75B
0x18014b6b7  lea     r9, [rbp+640h+ppvOut]; ppvOut
0x18014b6bb  lea     r8, _GUID_cb738c08_8b2d_4349_a14d_b969e62e964c; riid
0x18014b6c2  lea     rdx, SID_ApplicationUserContextTokenInfo; guidService
0x18014b6c9  mov     rcx, [r14+8]; punk
0x18014b6cd  call    cs:__imp_IUnknown_QueryService
0x18014b6d4  nop     dword ptr [rax+rax+00h]
0x18014b6d9  jmp     short loc_18014B691
0x18014b6db  xor     ebx, ebx
0x18014b6dd  jmp     loc_18014B619
0x18014b6e2  test    r12d, r12d
0x18014b6e5  jnz     loc_18066B6BA
0x18014b6eb  lea     rax, [r14+180h]
0x18014b6f2  mov     [rsp+740h+lpProcessInformation], rax; lpProcessInformation
0x18014b6f7  mov     [rsp+740h+lpStartupInfo], rsi; lpStartupInfo
0x18014b6fc  mov     rax, [r14+50h]
0x18014b700  mov     [rsp+740h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18014b705  mov     rax, [r14+1B0h]
0x18014b70c  mov     [rsp+740h+lpEnvironment], rax; lpEnvironment
0x18014b711  mov     [rsp+740h+dwCreationFlags], edi; dwCreationFlags
0x18014b715  mov     eax, [r14+1D8h]
0x18014b71c  mov     [rsp+740h+bInheritHandles], eax; int
0x18014b720  xor     r9d, r9d; lpThreadAttributes
0x18014b723  xor     r8d, r8d; lpProcessAttributes
0x18014b726  mov     rdx, [r14+200h]; lpCommandLine
0x18014b72d  mov     rcx, rbx; lpApplicationName
0x18014b730  call    cs:__imp_CreateProcessW
0x18014b737  nop     dword ptr [rax+rax+00h]
0x18014b73c  xor     esi, esi
0x18014b73e  mov     ecx, eax; int
0x18014b740  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18014b745  mov     r15d, eax
0x18014b748  test    eax, eax
0x18014b74a  jns     loc_18014B6AA
0x18014b750  cmp     eax, 800702E4h
0x18014b755  jz      loc_18014B6AA
0x18014b75b  mov     dil, sil
0x18014b75e  mov     [rbp+640h+var_6C0], sil
0x18014b762  mov     rbx, rsi
0x18014b765  mov     [rbp+640h+var_6B0], rbx
0x18014b769  mov     [rbp+640h+var_6A0], rsi
0x18014b76d  mov     [rbp+640h+var_6A8], rsi
0x18014b771  mov     [rbp+640h+var_638], rsi
0x18014b775  xorps   xmm0, xmm0
0x18014b778  movups  xmmword ptr [rbp+640h+pguid.Data1], xmm0
0x18014b77c  mov     [rbp+640h+hObject], rsi
0x18014b780  mov     rcx, r14; this
0x18014b783  call    ?IsLaunchingWithPackageIdentity@CInvokeCreateProcessVerb@@AEBA_NXZ; CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(void)
0x18014b788  mov     r13d, 1
0x18014b78e  test    al, al
0x18014b790  jnz     loc_18014B894
0x18014b796  mov     [rbp+640h+var_670], rsi
0x18014b79a  cmp     [r14+230h], rsi
0x18014b7a1  jnz     loc_18014B958
0x18014b7a7  test    dil, dil
0x18014b7aa  jnz     loc_18014B958
0x18014b7b0  mov     qword ptr [rbp+640h+var_660], rsi
0x18014b7b4  test    dil, dil
0x18014b7b7  jnz     loc_18066B90D
0x18014b7bd  mov     rcx, r14; this
0x18014b7c0  call    ?IsLaunchingWithPackageIdentity@CInvokeCreateProcessVerb@@AEBA_NXZ; CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(void)
0x18014b7c5  test    al, al
0x18014b7c7  jnz     loc_18014BFCE
0x18014b7cd  mov     rsi, [rbp+640h+pszPath]
0x18014b7d1  cmp     r15d, 800702E4h
0x18014b7d8  jz      loc_18066B990
0x18014b7de  xor     ecx, ecx
0x18014b7e0  cmp     r12d, 2
0x18014b7e4  jz      loc_18066B990
0x18014b7ea  xor     r12d, r12d
0x18014b7ed  test    r15d, r15d
0x18014b7f0  js      loc_18014B879
0x18014b7f6  mov     dil, [rbp+640h+var_6C0]
0x18014b7fa  mov     [rbp+640h+Parameter], dil
0x18014b7fe  mov     eax, [rbp+640h+pguid.Data1+1]
0x18014b801  mov     [rbp+640h+var_62F], eax
0x18014b804  movzx   eax, [rbp+640h+pguid.Data2+1]
0x18014b808  mov     [rbp+640h+var_62B], ax
0x18014b80c  mov     al, byte ptr [rbp+640h+pguid.Data3+1]
0x18014b80f  mov     [rbp+640h+var_629], al
0x18014b812  mov     [rbp+640h+var_628], r14
0x18014b816  mov     [rbp+640h+var_620], r13b
0x18014b81a  test    [r14+1F8h], r13b
0x18014b821  jnz     loc_18014C025
0x18014b827  test    ecx, ecx
0x18014b829  jnz     loc_18014C022
0x18014b82f  mov     r8, [r14+230h]
0x18014b836  test    r8, r8
0x18014b839  jnz     loc_18014BE35
0x18014b83f  test    dil, dil
0x18014b842  jnz     loc_18014BAD0
0x18014b848  call    IsSetProcessLaunchForegroundPolicyPresent
0x18014b84d  test    al, al
0x18014b84f  jz      short loc_18014B85F
0x18014b851  test    byte ptr [r14+1F8h], 20h
0x18014b859  jnz     loc_18014C07A
0x18014b85f  test    byte ptr [r14+0E4h], 4
0x18014b867  jz      loc_18014BAAF
0x18014b86d  mov     r13b, r12b
0x18014b870  test    r13b, r13b
0x18014b873  jnz     loc_18014C097
0x18014b879  mov     eax, r15d
0x18014b87c  and     eax, 1FFF0000h
0x18014b881  cmp     eax, 70000h
0x18014b886  jz      loc_18014BA36
0x18014b88c  mov     ecx, r15d
0x18014b88f  jmp     loc_18014BA3A
0x18014b894  test    dword ptr [r14+228h], 800h
0x18014b89f  jz      loc_18014B796
0x18014b8a5  mov     rdx, [rbp+640h+var_650]; unsigned __int64
0x18014b8a9  mov     rcx, r14; this
0x18014b8ac  call    ?ResolvePackageFullNameIfNecessary@CInvokeCreateProcessVerb@@AEAAJ_K@Z; CInvokeCreateProcessVerb::ResolvePackageFullNameIfNecessary(unsigned __int64)
0x18014b8b1  mov     ebx, eax
0x18014b8b3  test    eax, eax
0x18014b8b5  jns     loc_18014BBA4
0x18014b8bb  mov     rcx, [rbp+648h]; this
0x18014b8c2  mov     r9d, eax; char *
0x18014b8c5  lea     r8, aOnecoreuapShel_59; "onecoreuap\\shell\\windows.storage\\exe"...
0x18014b8cc  mov     edx, 7A0h; void *
0x18014b8d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014b8d6  nop
0x18014b8d7  mov     rcx, [rbp+640h+hObject]; hObject
0x18014b8db  lea     rdx, [rcx-1]
0x18014b8df  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18014b8e3  jbe     loc_18014BF12
0x18014b8e9  mov     rcx, [rbp+640h+ppvOut]
0x18014b8ed  test    rcx, rcx
0x18014b8f0  jz      short loc_18014B903
0x18014b8f2  mov     [rbp+640h+ppvOut], rsi
0x18014b8f6  mov     rax, [rcx]
0x18014b8f9  mov     rax, [rax+10h]
0x18014b8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014b902  nop
0x18014b903  mov     eax, ebx
0x18014b905  jmp     short loc_18014B934
0x18014b907  mov     rcx, rbx; pv
0x18014b90a  call    cs:__imp_CoTaskMemFree
0x18014b911  nop     dword ptr [rax+rax+00h]
0x18014b916  nop
0x18014b917  mov     rcx, [rbp+640h+ppvOut]
0x18014b91b  test    rcx, rcx
0x18014b91e  jz      short loc_18014B931
0x18014b920  mov     [rbp+640h+ppvOut], r12
0x18014b924  mov     rdx, [rcx]
0x18014b927  mov     rax, [rdx+10h]
0x18014b92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014b930  nop
0x18014b931  mov     eax, r15d
0x18014b934  mov     rcx, [rbp+640h+var_50]
0x18014b93b  xor     rcx, rsp; StackCookie
0x18014b93e  call    __security_check_cookie
0x18014b943  add     rsp, 708h
0x18014b94a  pop     r15
0x18014b94c  pop     r14
0x18014b94e  pop     r13
0x18014b950  pop     r12
0x18014b952  pop     rdi
0x18014b953  pop     rsi
0x18014b954  pop     rbx
0x18014b955  pop     rbp
0x18014b956  retn
0x18014b958  mov     [rbp+640h+ppv], rsi
0x18014b95c  lea     rcx, [rbp+640h+ppv]
0x18014b960  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014b965  lea     rax, [rbp+640h+ppv]
0x18014b969  mov     qword ptr [rsp+740h+bInheritHandles], rax; int
0x18014b96e  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18014b975  xor     edx, edx; pUnkOuter
0x18014b977  lea     r8d, [rdx+4]; dwClsContext
0x18014b97b  lea     rcx, CLSID_ShellServiceHost; rclsid
0x18014b982  call    cs:__imp_CoCreateInstance
0x18014b989  nop     dword ptr [rax+rax+00h]
0x18014b98e  mov     edi, eax
0x18014b990  test    eax, eax
0x18014b992  jns     loc_18014BF71
0x18014b998  cmp     [rbp+640h+var_6C0], sil
0x18014b99c  jz      loc_18014BFBC
0x18014b9a2  test    edi, edi
0x18014b9a4  jns     loc_18014BFBC
0x18014b9aa  mov     rcx, [rbp+648h]; this
0x18014b9b1  mov     r9d, edi; char *
0x18014b9b4  lea     r8, aOnecoreuapShel_59; "onecoreuap\\shell\\windows.storage\\exe"...
0x18014b9bb  mov     edx, 7EEh; void *
0x18014b9c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014b9c5  nop
0x18014b9c6  mov     rcx, [rbp+640h+ppv]
0x18014b9ca  test    rcx, rcx
0x18014b9cd  jz      short loc_18014B9E0
0x18014b9cf  mov     [rbp+640h+ppv], rsi
0x18014b9d3  mov     rax, [rcx]
0x18014b9d6  mov     rax, [rax+10h]
0x18014b9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014b9df  nop
0x18014b9e0  mov     rcx, [rbp+640h+var_670]
0x18014b9e4  test    rcx, rcx
0x18014b9e7  jz      short loc_18014B9FA
0x18014b9e9  mov     [rbp+640h+var_670], rsi
0x18014b9ed  mov     rax, [rcx]
0x18014b9f0  mov     rax, [rax+10h]
0x18014b9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014b9f9  nop
0x18014b9fa  mov     rcx, [rbp+640h+hObject]; hObject
0x18014b9fe  lea     rax, [rcx-1]
0x18014ba02  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18014ba06  jbe     loc_18014BFAB
0x18014ba0c  test    rbx, rbx
0x18014ba0f  jnz     loc_18014BA9B
0x18014ba15  mov     rcx, [rbp+640h+ppvOut]
0x18014ba19  test    rcx, rcx
0x18014ba1c  jz      short loc_18014BA2F
0x18014ba1e  mov     [rbp+640h+ppvOut], rsi
0x18014ba22  mov     rax, [rcx]
0x18014ba25  mov     rax, [rax+10h]
0x18014ba29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ba2e  nop
0x18014ba2f  mov     eax, edi
0x18014ba31  jmp     loc_18014B934
0x18014ba36  movzx   ecx, r15w; dwErrCode
0x18014ba3a  call    cs:__imp_SetLastError
0x18014ba41  nop     dword ptr [rax+rax+00h]
0x18014ba46  nop
0x18014ba47  mov     rcx, qword ptr [rbp+640h+var_660]
0x18014ba4b  test    rcx, rcx
0x18014ba4e  jz      short loc_18014BA61
0x18014ba50  mov     qword ptr [rbp+640h+var_660], r12
0x18014ba54  mov     rax, [rcx]
0x18014ba57  mov     rax, [rax+10h]
0x18014ba5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ba60  nop
0x18014ba61  mov     rcx, [rbp+640h+var_670]
0x18014ba65  test    rcx, rcx
0x18014ba68  jz      short loc_18014BA7B
0x18014ba6a  mov     [rbp+640h+var_670], r12
0x18014ba6e  mov     rax, [rcx]
0x18014ba71  mov     rax, [rax+10h]
0x18014ba75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ba7a  nop
0x18014ba7b  mov     rcx, [rbp+640h+hObject]; hObject
  ... truncated ...
```
