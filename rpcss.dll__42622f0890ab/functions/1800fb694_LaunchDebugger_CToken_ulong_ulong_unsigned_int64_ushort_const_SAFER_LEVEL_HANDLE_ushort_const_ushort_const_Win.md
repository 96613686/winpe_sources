# LaunchDebugger(CToken *,ulong,ulong,unsigned __int64,ushort const *,SAFER_LEVEL_HANDLE__ *,ushort const *,ushort const *,Windows::Foundation::IdentityType,_PSM_ACTIVATE_BACKGROUND_TYPE,HSTRING__ *,_PROCESS_INFORMATION *)

- ea: `0x1800fb694`
- end: `0x1800fc1b9`
- name: `?LaunchDebugger@@YAJPEAVCToken@@KK_KPEBGPEAUSAFER_LEVEL_HANDLE__@@22W4IdentityType@Foundation@Windows@@W4_PSM_ACTIVATE_BACKGROUND_TYPE@@PEAUHSTRING__@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `2853`
- prototype: `__int64 __fastcall(void **, unsigned int, unsigned int, __int64, __int64, SAFER_LEVEL_HANDLE LevelHandle, _WORD *lpValue, WCHAR *, int, unsigned int, HSTRING string, __int64)`
- caller_count: `3`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004c5bc`
- `0x18004cd64`
- `0x1800507c0`

## callees

- `0x18000b428`
- `0x18000bbe8`
- `0x180011954`
- `0x180018344`
- `0x18001ec28`
- `0x18002ba28`
- `0x18002ed28`
- `0x18002f058`
- `0x18002f8cc`
- `0x180034540`
- `0x180039068`
- `0x18004778c`
- `0x18004c570`
- `0x18005248c`
- `0x180059e50`
- `0x1800684b4`
- `0x18006b34c`
- `0x18006b5a4`
- `0x18006cb10`
- `0x18006e06c`
- `0x18007e3d4`
- `0x18008cd90`
- `0x180098b54`
- `0x1800a228c`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800b3bac`
- `0x1800b3da0`
- `0x1800b3df4`
- `0x1800b43f0`
- `0x1800b4890`
- `0x1800c3850`
- `0x1800e8984`
- `0x1800fb694`
- `0x1800fdcd8`

## import_xrefs

- `ntdll!RtlExpandEnvironmentStrings` at `0x1800fbefc`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1800fbefc`
- `ntdll!RtlQueryPackageIdentity` at `0x1800fbb48`
- `ntdll!RtlQueryPackageIdentity` at `0x1800fbb48`
- `ntdll!RtlNtStatusToDosError` at `0x1800fbf04`
- `ntdll!RtlNtStatusToDosError` at `0x1800fbf04`
- `ntdll!RtlIsMultiSessionSku` at `0x1800fb77b`
- `ntdll!RtlIsMultiSessionSku` at `0x1800fb77b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbe7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbe93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbe7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fbe93`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fb8c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fb8c7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800fb7f3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800fbfdb`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800fc145`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800fb7f3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800fbfdb`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800fc145`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800fba73`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800fba73`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800fbacc`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800fbacc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800fbe6d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800fc083`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800fbe6d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800fc083`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fba42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fba42`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800fb9f5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800fb9f5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800fbfe1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800fc0ba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800fbfe1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800fc0ba`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800fbf5f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800fbf5f`
- `KERNELBASE!FormatApplicationUserModelId` at `0x1800fbbb9`
- `KERNELBASE!FormatApplicationUserModelId` at `0x1800fbbb9`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x1800fbb6f`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x1800fbb6f`
- `profapi!__imp_CreateEnvBlock` at `0x1800fb934`
- `profapi!__imp_CreateEnvBlock` at `0x1800fb934`
- `profapi!__imp_DestroyEnvBlock` at `0x1800fbff1`
- `profapi!__imp_DestroyEnvBlock` at `0x1800fc0ca`
- `profapi!__imp_DestroyEnvBlock` at `0x1800fc155`
- `profapi!__imp_DestroyEnvBlock` at `0x1800fbff1`
- `profapi!__imp_DestroyEnvBlock` at `0x1800fc0ca`
- `profapi!__imp_DestroyEnvBlock` at `0x1800fc155`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800fbea9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800fbea9`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x1800fb979`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x1800fb979`
- `ext-ms-win-com-psmregister-l1-2-0!PsmAdjustActivationToken` at `0x1800fbcce`
- `ext-ms-win-com-psmregister-l1-2-0!PsmAdjustActivationToken` at `0x1800fbcce`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800fb7ae`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800fb7ae`

## string_xrefs

- `0x1800fb7cd`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fb98a`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fba89`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbb85`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbc11`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbc6b`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbcdf`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbd95`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbdaa`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbe04`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbf1f`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbf74`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbfb0`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fc098`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fc119`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800fbd76`: `No client package identity found for debugger (DCOMLaunch): %!STATUS!`
- `0x1800fbfa1`: `LaunchDebugger CreateProcessAsUser failed`
- `0x1800fbc54`: `Falling back on client's PSM activation type (%u) for an identity type other than AAA (%u) (DCOMLaunch)`
- `0x1800fbde5`: `IsPackageFamilyNameFromFullNamePresent is not present (DCOMLaunch)`

## pseudocode

```c
__int64 __fastcall LaunchDebugger(
        void **a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        SAFER_LEVEL_HANDLE LevelHandle,
        _WORD *lpValue,
        WCHAR *a8,
        int a9,
        unsigned int a10,
        HSTRING string,
        __int64 a12)
{
  __int64 v15; // rdi
  int UserTokenForSession; // eax
  unsigned int LastError; // ebx
  __int64 v19; // rdx
  __int64 v20; // r9
  struct CToken *v21; // r8
  void *UserSid; // rax
  __int64 v23; // rbx
  __int64 v24; // rdx
  _QWORD *v25; // rax
  void *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE v31; // rdx
  DWORD v32; // r12d
  LSTATUS v33; // eax
  struct _PROCESS_INFORMATION *v34; // rdx
  const char *v35; // r9
  __int64 v36; // rdx
  int v37; // eax
  struct CToken *v38; // r8
  __int64 v39; // rax
  int PackageIdentity; // eax
  unsigned int v41; // eax
  __int64 v42; // rdx
  unsigned int v43; // ebx
  int PsmActivationType; // eax
  int v45; // eax
  __int64 v46; // rdx
  unsigned int v47; // r8d
  signed int v48; // eax
  NTSTATUS v49; // eax
  signed int v50; // eax
  bool v51; // sf
  HRESULT v52; // eax
  struct _PROCESS_INFORMATION *v53; // rdx
  struct _PROCESS_INFORMATION *v54; // rdx
  const char *v56; // r9
  struct _PROCESS_INFORMATION *v57; // rdx
  struct CToken *v58; // r8
  struct _PROCESS_INFORMATION *v59; // rdx
  LPVOID lpReserved; // [rsp+20h] [rbp-E0h]
  unsigned int *lpReserveda; // [rsp+20h] [rbp-E0h]
  int lpReservedb; // [rsp+20h] [rbp-E0h]
  PWSTR *lpPreviousValue; // [rsp+28h] [rbp-D8h]
  LPVOID lpEnvironment; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE InAccessToken; // [rsp+68h] [rbp-98h] BYREF
  void *OutAccessToken; // [rsp+70h] [rbp-90h] BYREF
  PWSTR ppszPathOut; // [rsp+78h] [rbp-88h] BYREF
  __int64 v68; // [rsp+80h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-78h] BYREF
  __int64 v70; // [rsp+90h] [rbp-70h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+98h] [rbp-68h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+B0h] [rbp-50h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+B4h] [rbp-4Ch] BYREF
  ULONG_PTR Size; // [rsp+B8h] [rbp-48h] BYREF
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v76[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v77[4]; // [rsp+E0h] [rbp-20h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+100h] [rbp+0h] BYREF
  _OWORD *v79; // [rsp+168h] [rbp+68h]
  _OWORD v80[3]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR CommandLine[296]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+3F0h] [rbp+2F0h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR packageFullName[128]; // [rsp+510h] [rbp+410h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+610h] [rbp+510h] BYREF
  WCHAR pszPathIn[264]; // [rsp+720h] [rbp+620h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+978h] [rbp+878h]

  v15 = a12;
  v68 = a5;
  ppszPathOut = a8;
  memset_0(CommandLine, 0, 0x244u);
  InAccessToken = 0;
  OutAccessToken = 0;
  lpEnvironment = 0;
  v70 = 0;
  Size = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  phkResult = 0;
  memset(v80, 0, sizeof(v80));
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 128;
  if ( (unsigned __int8)RtlIsMultiSessionSku() )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &InAccessToken,
      0);
    UserTokenForSession = GetUserTokenForSession(a2, &InAccessToken);
    LastError = UserTokenForSession;
    if ( UserTokenForSession < 0 )
    {
      v19 = 710;
      goto LABEL_6;
    }
  }
  else if ( a4 )
  {
    if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
    {
      v19 = 686;
LABEL_32:
      LastError = -2147024891;
      v20 = 2147942405LL;
      goto LABEL_7;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &InAccessToken,
      0);
    UserTokenForSession = UMgrQueryUserToken(a4, &InAccessToken);
    LastError = UserTokenForSession;
    if ( UserTokenForSession < 0 )
    {
      v19 = 681;
LABEL_6:
      v20 = (unsigned int)UserTokenForSession;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)v20,
        (int)lpReserved);
LABEL_8:
      LogDebuggerStartError(string, a3, v21, CommandLine);
      TerminateProcess(*(HANDLE *)v15, 0);
LABEL_92:
      if ( lpEnvironment )
        DestroyEnvBlock();
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v70);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&OutAccessToken);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&InAccessToken);
      wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v54);
      return LastError;
    }
  }
  else if ( CToken::IsInteractiveUser((CToken *)a1) )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &InAccessToken,
      0);
    UserTokenForSession = GetUnmodifiedLogonTokenOfClientTokenUser(a1[9], &InAccessToken);
    LastError = UserTokenForSession;
    if ( UserTokenForSession < 0 )
    {
      v19 = 697;
      goto LABEL_6;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &InAccessToken,
      0);
    UserTokenForSession = GetUserTokenForSession(a2, &InAccessToken);
    LastError = UserTokenForSession;
    if ( UserTokenForSession < 0 )
    {
      v19 = 704;
      goto LABEL_6;
    }
  }
  UserSid = GetUserSid(InAccessToken);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v70,
    UserSid);
  v23 = v70;
  if ( !v70 )
  {
    v24 = 715;
LABEL_102:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)0x8007000ELL,
      (int)lpReserved);
    LogDebuggerStartError(string, a3, v58, CommandLine);
    TerminateProcess(*(HANDLE *)v15, 0);
    if ( lpEnvironment )
      DestroyEnvBlock();
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v70);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&OutAccessToken);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&InAccessToken);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v59);
    return 2147942414LL;
  }
  v25 = HeapAlloc(g_hHeap, 0, 0xA0u);
  if ( !v25 )
  {
    v24 = 720;
    goto LABEL_102;
  }
  LODWORD(lpReserved) = 0;
  *v25 = v23;
  v25[1] = 0;
  v25[2] = 0;
  v25[3] = 0;
  v25[4] = 0;
  v25[5] = 0;
  v26 = (void *)CAccessInfo::IdentifyAccess(v25, 0, 0, 0x1FFFFF);
  if ( !v26 )
  {
    v24 = 732;
    goto LABEL_102;
  }
  ProcessAttributes.nLength = 24;
  ProcessAttributes.lpSecurityDescriptor = v26;
  ProcessAttributes.bInheritHandle = 0;
  UserTokenForSession = CreateEnvBlock(&lpEnvironment, InAccessToken, 0);
  LastError = UserTokenForSession;
  if ( UserTokenForSession < 0 )
  {
    v19 = 735;
    goto LABEL_6;
  }
  if ( LevelHandle && (unsigned __int8)IsSaferCloseLevelPresent(v28, v27, v29) )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &OutAccessToken,
      0);
    if ( !SaferComputeTokenFromLevel(LevelHandle, InAccessToken, &OutAccessToken, 0, 0) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2E3,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                    v30);
      goto LABEL_8;
    }
  }
  else
  {
    v31 = InAccessToken;
    InAccessToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &OutAccessToken,
      v31);
  }
  LODWORD(lpReserved) = *(_DWORD *)(v15 + 16);
  UserTokenForSession = StringCchPrintfW(
                          CommandLine,
                          0x122u,
                          L"%s -p %d -tid %d",
                          v68,
                          lpReserved,
                          *(_DWORD *)(v15 + 20),
                          0);
  LastError = UserTokenForSession;
  if ( UserTokenForSession < 0 )
  {
    v19 = 748;
    goto LABEL_6;
  }
  if ( !ImpersonateLoggedOnUser(OutAccessToken) )
  {
    v19 = 754;
    goto LABEL_32;
  }
  v32 = 1040;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v33 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\AIM", 0, 0x20019u, &phkResult);
  phkResult = 0;
  if ( v33 || !lpValue )
    goto LABEL_77;
  Size = 48;
  if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v80, 1u, 0, &Size) )
  {
    v36 = 777;
LABEL_37:
    v37 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v36,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            v35);
LABEL_38:
    LastError = v37;
LABEL_91:
    LogDebuggerStartError(string, a3, v38, CommandLine);
    TerminateProcess(*(HANDLE *)v15, 0);
    RevertToSelf();
    goto LABEL_92;
  }
  v39 = -1;
  do
    ++v39;
  while ( lpValue[v39] );
  if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v80, 0, 0x20008u, lpValue, 2 * v39, 0, 0) )
  {
    v36 = 782;
    goto LABEL_37;
  }
  if ( ppszPathOut )
    goto LABEL_54;
  if ( a9 )
    goto LABEL_77;
  if ( !(unsigned __int8)IsPackageFamilyNameFromIdPresent() || !(unsigned __int8)IsGetStagedPackageOriginPresent() )
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1)) )
      ComTraceMessageT<>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (unsigned int)"LaunchDebugger",
        827,
        1,
        (__int64)L"IsPackageFamilyNameFromFullNamePresent is not present (DCOMLaunch)");
    goto LABEL_77;
  }
  v77[0] = 256;
  *(_QWORD *)v76 = 132;
  lpReserveda = v76;
  PackageIdentity = RtlQueryPackageIdentity(a1[9], packageFullName, v77, packageRelativeApplicationId);
  if ( PackageIdentity >= 0 )
  {
    packageFamilyNameLength = 130;
    v41 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
    if ( v41 )
    {
      v42 = 808;
LABEL_50:
      v37 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v42,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
              (const char *)v41,
              (unsigned int)v76);
      goto LABEL_38;
    }
    applicationUserModelIdLength = 262;
    v41 = FormatApplicationUserModelId(
            packageFamilyName,
            packageRelativeApplicationId,
            &applicationUserModelIdLength,
            applicationUserModelId);
    if ( v41 )
    {
      v42 = 811;
      goto LABEL_50;
    }
    ppszPathOut = applicationUserModelId;
LABEL_54:
    if ( (unsigned __int8)IsPsmAdjustActivationTokenPresent() )
    {
      v43 = a10;
      if ( a10 == 4 )
      {
        PsmActivationType = CToken::GetPsmActivationType((CToken *)a1, (enum _PSM_ACTIVATE_BACKGROUND_TYPE *)&a10);
        LastError = PsmActivationType;
        if ( PsmActivationType < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x346,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)PsmActivationType,
            (int)lpReserveda);
          goto LABEL_91;
        }
        if ( a9
          && (dword_18014E4B8
           || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1))) )
        {
          v43 = a10;
          ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx", "LaunchDebugger", 842);
        }
        else
        {
          v43 = a10;
        }
      }
      v68 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v68,
        0);
      lpReservedb = (int)ppszPathOut;
      v45 = PsmAdjustActivationToken(OutAccessToken, 1, v43, lpValue);
      if ( v45 < 0 )
      {
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x353,
                      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                      (const char *)(unsigned int)v45,
                      lpReservedb);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
        goto LABEL_91;
      }
      v46 = v68;
      v68 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &OutAccessToken,
        v46);
      StartupInfo.cb = 112;
      v79 = v80;
      v32 = 525328;
      ProcessAttributes.lpSecurityDescriptor = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
    }
    goto LABEL_77;
  }
  v47 = -1073741275;
  if ( PackageIdentity != -1073741275 )
  {
    v37 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x335,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)PackageIdentity,
            (int)v76);
    goto LABEL_38;
  }
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1)) )
    ComTraceMessageT<long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (unsigned int)"LaunchDebugger",
      817,
      1,
      (__int64)L"No client package identity found for debugger (DCOMLaunch): %!STATUS!",
      v47);
LABEL_77:
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v34);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessAsUserW(
          OutAccessToken,
          0,
          CommandLine,
          &ProcessAttributes,
          0,
          0,
          v32,
          lpEnvironment,
          0,
          &StartupInfo,
          &ProcessInformation) )
  {
    v48 = GetLastError();
    LastError = v48;
    if ( v48 > 0 )
      LastError = (unsigned __int16)v48 | 0x80070000;
    if ( GetLastError() == 2 && PathIsRelativeW(CommandLine) )
    {
      memset_0(pszPathIn, 0, 0x20Au);
      lpPreviousValue = &ppszPathOut;
      ppszPathOut = 0;
      v49 = RtlExpandEnvironmentStrings(lpEnvironment, L"%localappdata%\\Microsoft\\WindowsApps", 36, pszPathIn);
      v50 = RtlNtStatusToDosError(v49);
      v51 = v50 < 0;
      if ( v50 > 0 )
      {
        v50 = (unsigned __int16)v50 | 0x80070000;
        v51 = v50 < 0;
      }
      if ( v51 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x36D,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)v50,
          261);
      }
      else
      {
        ppszPathOut = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &ppszPathOut,
          0);
        v52 = PathAllocCombine(pszPathIn, CommandLine, 1u, &ppszPathOut);
        if ( v52 >= 0 )
        {
          wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v53);
          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
          if ( !CreateProcessAsUserW(
                  OutAccessToken,
                  0,
                  ppszPathOut,
                  &ProcessAttributes,
                  0,
                  0,
                  v32,
                  lpEnvironment,
                  0,
                  &StartupInfo,
                  &ProcessInformation) )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x375,
                          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                          v56);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
            goto LABEL_91;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x371,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)v52,
            261);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      }
    }
    if ( (LastError & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x379,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)LastError,
        (int)"LaunchDebugger CreateProcessAsUser failed",
        (const char *)lpPreviousValue);
      goto LABEL_91;
    }
  }
  RevertToSelf();
  if ( lpEnvironment )
    DestroyEnvBlock();
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v70);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&OutAccessToken);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&InAccessToken);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v57);
  return 0;
}

```

## disassembly

```asm
0x1800fb694  mov     [rsp-8+arg_10], rbx
0x1800fb699  push    rbp
0x1800fb69a  push    rsi
0x1800fb69b  push    rdi
0x1800fb69c  push    r12
0x1800fb69e  push    r13
0x1800fb6a0  push    r14
0x1800fb6a2  push    r15
0x1800fb6a4  lea     rbp, [rsp-840h]
0x1800fb6ac  sub     rsp, 940h
0x1800fb6b3  mov     rax, cs:__security_cookie
0x1800fb6ba  xor     rax, rsp
0x1800fb6bd  mov     [rbp+870h+var_40], rax
0x1800fb6c4  mov     rax, [rbp+870h+arg_20]
0x1800fb6cb  mov     esi, r8d
0x1800fb6ce  mov     r12, [rbp+870h+LevelHandle]
0x1800fb6d5  mov     r14d, edx
0x1800fb6d8  mov     r13, [rbp+870h+lpValue]
0x1800fb6df  mov     r15, rcx
0x1800fb6e2  mov     rdi, [rbp+870h+arg_58]
0x1800fb6e9  lea     rcx, [rbp+870h+CommandLine]; void *
0x1800fb6f0  mov     [rbp+870h+var_8F0], rax
0x1800fb6f4  xor     edx, edx; Val
0x1800fb6f6  mov     rax, [rbp+870h+arg_38]
0x1800fb6fd  mov     r8d, 244h; Size
0x1800fb703  mov     [rsp+970h+ppszPathOut], rax
0x1800fb708  mov     rbx, r9
0x1800fb70b  call    memset_0
0x1800fb710  xor     ecx, ecx
0x1800fb712  xor     eax, eax
0x1800fb714  xorps   xmm0, xmm0
0x1800fb717  mov     [rsp+970h+InAccessToken], rcx
0x1800fb71c  mov     [rsp+970h+OutAccessToken], rcx
0x1800fb721  xor     edx, edx; Val
0x1800fb723  mov     [rsp+970h+var_910], rcx
0x1800fb728  mov     [rbp+870h+var_8E0], rcx
0x1800fb72c  lea     r8d, [rax+68h]; Size
0x1800fb730  mov     [rbp+870h+Size], rcx
0x1800fb734  lea     rcx, [rbp+870h+StartupInfo.lpReserved]; void *
0x1800fb738  movups  xmmword ptr [rbp+870h+ProcessInformation.hProcess], xmm0
0x1800fb73c  mov     qword ptr [rbp+870h+ProcessInformation.dwProcessId], rax
0x1800fb740  movups  xmmword ptr [rbp+870h+ProcessAttributes.nLength], xmm0
0x1800fb744  mov     qword ptr [rbp+870h+ProcessAttributes.bInheritHandle], rax
0x1800fb748  mov     dword ptr [rbp+870h+StartupInfo+4], eax
0x1800fb74b  call    memset_0
0x1800fb750  xorps   xmm0, xmm0
0x1800fb753  mov     [rbp+870h+phkResult], 0
0x1800fb75b  movups  [rbp+870h+var_800], xmm0
0x1800fb75f  mov     [rbp+870h+StartupInfo.cb], 68h ; 'h'
0x1800fb766  movups  [rbp+870h+var_7F0], xmm0
0x1800fb76d  mov     [rbp+870h+StartupInfo.dwFlags], 80h
0x1800fb774  movups  [rbp+870h+var_7E0], xmm0
0x1800fb77b  call    cs:__imp_RtlIsMultiSessionSku
0x1800fb781  test    al, al
0x1800fb783  jnz     loc_1800FB863
0x1800fb789  test    rbx, rbx
0x1800fb78c  jz      short loc_1800FB808
0x1800fb78e  call    IsUMgrQueryUserContextPresent
0x1800fb793  xor     r14d, r14d
0x1800fb796  test    al, al
0x1800fb798  jz      short loc_1800FB7FE
0x1800fb79a  xor     edx, edx
0x1800fb79c  lea     rcx, [rsp+970h+InAccessToken]
0x1800fb7a1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800fb7a6  lea     rdx, [rsp+970h+InAccessToken]
0x1800fb7ab  mov     rcx, rbx
0x1800fb7ae  call    cs:__imp_UMgrQueryUserToken
0x1800fb7b4  mov     ebx, eax
0x1800fb7b6  test    eax, eax
0x1800fb7b8  jns     loc_1800FB88F
0x1800fb7be  mov     edx, 2A9h; void *
0x1800fb7c3  mov     r9d, eax; char *
0x1800fb7c6  mov     rcx, [rbp+878h]; this
0x1800fb7cd  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800fb7d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb7d9  mov     rcx, [rbp+870h+string]; string
0x1800fb7e0  lea     r9, [rbp+870h+CommandLine]; unsigned __int16 *
0x1800fb7e7  mov     edx, esi; unsigned int
0x1800fb7e9  call    ?LogDebuggerStartError@@YAXPEAUHSTRING__@@KPEAVCToken@@PEBG@Z; LogDebuggerStartError(HSTRING__ *,ulong,CToken *,ushort const *)
0x1800fb7ee  mov     rcx, [rdi]; hProcess
0x1800fb7f1  xor     edx, edx; uExitCode
0x1800fb7f3  call    cs:__imp_TerminateProcess
0x1800fb7f9  jmp     loc_1800FBFE7
0x1800fb7fe  mov     edx, 2AEh
0x1800fb803  jmp     loc_1800FBA04
0x1800fb808  mov     rcx, r15; this
0x1800fb80b  call    ?IsInteractiveUser@CToken@@QEAA_NXZ; CToken::IsInteractiveUser(void)
0x1800fb810  xor     edx, edx
0x1800fb812  lea     rcx, [rsp+970h+InAccessToken]
0x1800fb817  test    al, al
0x1800fb819  jz      short loc_1800FB83E
0x1800fb81b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800fb820  mov     rcx, [r15+48h]; void *
0x1800fb824  lea     rdx, [rsp+970h+InAccessToken]; void **
0x1800fb829  call    ?GetUnmodifiedLogonTokenOfClientTokenUser@@YAJPEAXPEAPEAX@Z; GetUnmodifiedLogonTokenOfClientTokenUser(void *,void * *)
0x1800fb82e  xor     r14d, r14d
0x1800fb831  mov     ebx, eax
0x1800fb833  test    eax, eax
0x1800fb835  jns     short loc_1800FB88F
0x1800fb837  mov     edx, 2B9h
0x1800fb83c  jmp     short loc_1800FB7C3
0x1800fb83e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800fb843  lea     rdx, [rsp+970h+InAccessToken]; void **
0x1800fb848  mov     ecx, r14d; unsigned int
0x1800fb84b  call    ?GetUserTokenForSession@@YAJKPEAPEAX@Z; GetUserTokenForSession(ulong,void * *)
0x1800fb850  xor     r14d, r14d
0x1800fb853  mov     ebx, eax
0x1800fb855  test    eax, eax
0x1800fb857  jns     short loc_1800FB88F
0x1800fb859  mov     edx, 2C0h
0x1800fb85e  jmp     loc_1800FB7C3
0x1800fb863  xor     edx, edx
0x1800fb865  lea     rcx, [rsp+970h+InAccessToken]
0x1800fb86a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800fb86f  lea     rdx, [rsp+970h+InAccessToken]; void **
0x1800fb874  mov     ecx, r14d; unsigned int
0x1800fb877  call    ?GetUserTokenForSession@@YAJKPEAPEAX@Z; GetUserTokenForSession(ulong,void * *)
0x1800fb87c  xor     r14d, r14d
0x1800fb87f  mov     ebx, eax
0x1800fb881  test    eax, eax
0x1800fb883  jns     short loc_1800FB88F
0x1800fb885  mov     edx, 2C6h
0x1800fb88a  jmp     loc_1800FB7C3
0x1800fb88f  mov     rcx, [rsp+970h+InAccessToken]; TokenHandle
0x1800fb894  call    ?GetUserSid@@YAPEAXPEAX@Z; GetUserSid(void *)
0x1800fb899  mov     rdx, rax
0x1800fb89c  lea     rcx, [rbp+870h+var_8E0]
0x1800fb8a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?PrivMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800fb8a5  mov     rbx, [rbp+870h+var_8E0]
0x1800fb8a9  test    rbx, rbx
0x1800fb8ac  jnz     short loc_1800FB8B8
0x1800fb8ae  mov     edx, 2CBh
0x1800fb8b3  jmp     loc_1800FC112
0x1800fb8b8  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800fb8bf  xor     edx, edx; dwFlags
0x1800fb8c1  mov     r8d, 0A0h; dwBytes
0x1800fb8c7  call    cs:__imp_HeapAlloc
0x1800fb8cd  test    rax, rax
0x1800fb8d0  jz      loc_1800FC10D
0x1800fb8d6  mov     dword ptr [rsp+970h+lpReturnSize], r14d
0x1800fb8db  mov     r9d, 1FFFFFh
0x1800fb8e1  mov     dword ptr [rsp+970h+lpPreviousValue], r14d
0x1800fb8e6  xor     r8d, r8d
0x1800fb8e9  xor     edx, edx
0x1800fb8eb  mov     dword ptr [rsp+970h+lpReserved], r14d
0x1800fb8f0  mov     rcx, rax
0x1800fb8f3  mov     [rax], rbx
0x1800fb8f6  mov     [rax+8], r14
0x1800fb8fa  mov     [rax+10h], r14
0x1800fb8fe  mov     [rax+18h], r14
0x1800fb902  mov     [rax+20h], r14
0x1800fb906  mov     [rax+28h], r14
0x1800fb90a  call    ?IdentifyAccess@CAccessInfo@@QEAAPEAXW4SecurityDescriptorOwner@@KKKKK@Z; CAccessInfo::IdentifyAccess(SecurityDescriptorOwner,ulong,ulong,ulong,ulong,ulong)
0x1800fb90f  test    rax, rax
0x1800fb912  jz      loc_1800FC106
0x1800fb918  mov     rdx, [rsp+970h+InAccessToken]
0x1800fb91d  lea     rcx, [rsp+970h+var_910]
0x1800fb922  xor     r8d, r8d
0x1800fb925  mov     [rbp+870h+ProcessAttributes.nLength], 18h
0x1800fb92c  mov     [rbp+870h+ProcessAttributes.lpSecurityDescriptor], rax
0x1800fb930  mov     [rbp+870h+ProcessAttributes.bInheritHandle], r14d
0x1800fb934  call    cs:__imp_CreateEnvBlock
0x1800fb93a  mov     ebx, eax
0x1800fb93c  test    eax, eax
0x1800fb93e  jns     short loc_1800FB94A
0x1800fb940  mov     edx, 2DFh
0x1800fb945  jmp     loc_1800FB7C3
0x1800fb94a  test    r12, r12
0x1800fb94d  jz      short loc_1800FB9A2
0x1800fb94f  call    IsSaferCloseLevelPresent
0x1800fb954  test    al, al
0x1800fb956  jz      short loc_1800FB9A2
0x1800fb958  xor     edx, edx
0x1800fb95a  lea     rcx, [rsp+970h+OutAccessToken]
0x1800fb95f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800fb964  mov     rdx, [rsp+970h+InAccessToken]; InAccessToken
0x1800fb969  lea     r8, [rsp+970h+OutAccessToken]; OutAccessToken
0x1800fb96e  xor     r9d, r9d; dwFlags
0x1800fb971  mov     [rsp+970h+lpReserved], r14; lpReserved
0x1800fb976  mov     rcx, r12; LevelHandle
0x1800fb979  call    cs:__imp_SaferComputeTokenFromLevel
0x1800fb97f  test    eax, eax
0x1800fb981  jnz     short loc_1800FB9B6
0x1800fb983  mov     rcx, [rbp+878h]; this
0x1800fb98a  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800fb991  mov     edx, 2E3h; void *
0x1800fb996  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fb99b  mov     ebx, eax
0x1800fb99d  jmp     loc_1800FB7D9
0x1800fb9a2  mov     rdx, [rsp+970h+InAccessToken]
0x1800fb9a7  lea     rcx, [rsp+970h+OutAccessToken]
0x1800fb9ac  mov     [rsp+970h+InAccessToken], r14
0x1800fb9b1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800fb9b6  mov     eax, [rdi+14h]
0x1800fb9b9  lea     r8, aSPDTidD; "%s -p %d -tid %d"
0x1800fb9c0  mov     r9, [rbp+870h+var_8F0]
0x1800fb9c4  lea     rcx, [rbp+870h+CommandLine]; unsigned __int16 *
0x1800fb9cb  mov     dword ptr [rsp+970h+lpPreviousValue], eax
0x1800fb9cf  mov     edx, 122h; unsigned __int64
0x1800fb9d4  mov     eax, [rdi+10h]
0x1800fb9d7  mov     dword ptr [rsp+970h+lpReserved], eax
0x1800fb9db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fb9e0  mov     ebx, eax
0x1800fb9e2  test    eax, eax
0x1800fb9e4  jns     short loc_1800FB9F0
0x1800fb9e6  mov     edx, 2ECh
0x1800fb9eb  jmp     loc_1800FB7C3
0x1800fb9f0  mov     rcx, [rsp+970h+OutAccessToken]; hToken
0x1800fb9f5  call    cs:__imp_ImpersonateLoggedOnUser
0x1800fb9fb  test    eax, eax
0x1800fb9fd  jnz     short loc_1800FBA11
0x1800fb9ff  mov     edx, 2F2h
0x1800fba04  mov     ebx, 80070005h
0x1800fba09  mov     r9d, ebx
0x1800fba0c  jmp     loc_1800FB7C6
0x1800fba11  xor     edx, edx
0x1800fba13  lea     rcx, [rbp+870h+phkResult]
0x1800fba17  mov     r12d, 410h
0x1800fba1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800fba22  lea     rax, [rbp+870h+phkResult]
0x1800fba26  mov     r9d, 20019h; samDesired
0x1800fba2c  xor     r8d, r8d; ulOptions
0x1800fba2f  mov     [rsp+970h+lpReserved], rax; phkResult
0x1800fba34  lea     rdx, aSystemAim; "System\\AIM"
0x1800fba3b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800fba42  call    cs:__imp_RegOpenKeyExW
0x1800fba48  mov     [rbp+870h+phkResult], r14
0x1800fba4c  test    eax, eax
0x1800fba4e  jnz     loc_1800FBE15
0x1800fba54  test    r13, r13
0x1800fba57  jz      loc_1800FBE15
0x1800fba5d  lea     r9, [rbp+870h+Size]; lpSize
0x1800fba61  mov     [rbp+870h+Size], 30h ; '0'
0x1800fba69  xor     r8d, r8d; dwFlags
0x1800fba6c  lea     edx, [rax+1]; dwAttributeCount
0x1800fba6f  lea     rcx, [rbp+870h+var_800]; lpAttributeList
0x1800fba73  call    cs:__imp_InitializeProcThreadAttributeList
0x1800fba79  test    eax, eax
0x1800fba7b  jnz     short loc_1800FBA9C
0x1800fba7d  mov     edx, 309h; void *
0x1800fba82  mov     rcx, [rbp+878h]; this
0x1800fba89  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800fba90  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fba95  mov     ebx, eax
0x1800fba97  jmp     loc_1800FBFC1
0x1800fba9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800fbaa0  inc     rax
0x1800fbaa3  cmp     [r13+rax*2+0], r14w
0x1800fbaa9  jnz     short loc_1800FBAA0
0x1800fbaab  add     rax, rax
0x1800fbaae  mov     [rsp+970h+lpReturnSize], r14; lpReturnSize
0x1800fbab3  mov     [rsp+970h+lpPreviousValue], r14; lpPreviousValue
0x1800fbab8  lea     rcx, [rbp+870h+var_800]; lpAttributeList
0x1800fbabc  mov     r9, r13; lpValue
0x1800fbabf  mov     [rsp+970h+lpReserved], rax; cbSize
0x1800fbac4  xor     edx, edx; dwFlags
0x1800fbac6  mov     r8d, 20008h; Attribute
0x1800fbacc  call    cs:__imp_UpdateProcThreadAttribute
0x1800fbad2  test    eax, eax
0x1800fbad4  jnz     short loc_1800FBADD
0x1800fbad6  mov     edx, 30Eh
0x1800fbadb  jmp     short loc_1800FBA82
0x1800fbadd  mov     r14d, [rbp+870h+arg_40]
0x1800fbae4  xor     ebx, ebx
0x1800fbae6  cmp     [rsp+970h+ppszPathOut], rbx
0x1800fbaeb  jnz     loc_1800FBBD6
0x1800fbaf1  test    r14d, r14d
0x1800fbaf4  jnz     loc_1800FBE12
0x1800fbafa  call    IsPackageFamilyNameFromIdPresent
0x1800fbaff  test    al, al
0x1800fbb01  jz      loc_1800FBDC3
0x1800fbb07  call    IsGetStagedPackageOriginPresent
0x1800fbb0c  test    al, al
0x1800fbb0e  jz      loc_1800FBDC3
0x1800fbb14  mov     [rbp+870h+var_890], 100h
0x1800fbb1c  lea     rax, [rbp+870h+var_898]
0x1800fbb20  mov     qword ptr [rbp+870h+var_898], 84h
0x1800fbb28  lea     r9, [rbp+870h+packageRelativeApplicationId]
0x1800fbb2f  mov     rcx, [r15+48h]
0x1800fbb33  lea     r8, [rbp+870h+var_890]
0x1800fbb37  mov     [rsp+970h+lpPreviousValue], rbx
0x1800fbb3c  lea     rdx, [rbp+870h+packageFullName]
0x1800fbb43  mov     [rsp+970h+lpReserved], rax; int
0x1800fbb48  call    cs:__imp_RtlQueryPackageIdentity
0x1800fbb4e  test    eax, eax
0x1800fbb50  js      loc_1800FBD3C
0x1800fbb56  lea     r8, [rbp+870h+packageFamilyName]; packageFamilyName
0x1800fbb5d  mov     [rbp+870h+packageFamilyNameLength], 82h
0x1800fbb64  lea     rdx, [rbp+870h+packageFamilyNameLength]; packageFamilyNameLength
0x1800fbb68  lea     rcx, [rbp+870h+packageFullName]; packageFullName
0x1800fbb6f  call    cs:__imp_PackageFamilyNameFromFullName
0x1800fbb75  test    eax, eax
0x1800fbb77  jz      short loc_1800FBB99
0x1800fbb79  mov     edx, 328h; void *
0x1800fbb7e  mov     rcx, [rbp+878h]; this
0x1800fbb85  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800fbb8c  mov     r9d, eax; char *
0x1800fbb8f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800fbb94  jmp     loc_1800FBA95
0x1800fbb99  lea     r9, [rbp+870h+applicationUserModelId]; applicationUserModelId
  ... truncated ...
```
