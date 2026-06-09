# LaunchDebugger(CToken *,ulong,ulong,unsigned __int64,ushort const *,SAFER_LEVEL_HANDLE__ *,ushort const *,ushort const *,Windows::Foundation::IdentityType,_PSM_ACTIVATE_BACKGROUND_TYPE,HSTRING__ *,_PROCESS_INFORMATION *)

- ea: `0x180103c08`
- end: `0x1801047e3`
- name: `?LaunchDebugger@@YAJPEAVCToken@@KK_KPEBGPEAUSAFER_LEVEL_HANDLE__@@22W4IdentityType@Foundation@Windows@@W4_PSM_ACTIVATE_BACKGROUND_TYPE@@PEAUHSTRING__@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `3035`
- prototype: ``
- caller_count: `3`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004c4b0`
- `0x18004e578`
- `0x18009007c`

## callees

- `0x18000b100`
- `0x18000c3f8`
- `0x18000ce5c`
- `0x18000fb8c`
- `0x18001037c`
- `0x1800158f8`
- `0x18001c624`
- `0x1800210f8`
- `0x180024590`
- `0x180025088`
- `0x180025950`
- `0x180034260`
- `0x180039a7c`
- `0x18003f468`
- `0x180040548`
- `0x18004c160`
- `0x18006bd64`
- `0x18006d3ec`
- `0x180070298`
- `0x1800710a4`
- `0x18008172c`
- `0x180093f20`
- `0x18009e160`
- `0x1800a780c`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800b8eac`
- `0x1800b90a0`
- `0x1800b90f4`
- `0x1800b96f0`
- `0x1800b9b90`
- `0x1800c9588`
- `0x1800f00f0`
- `0x180103c08`
- `0x180106480`

## import_xrefs

- `ntdll!RtlExpandEnvironmentStrings` at `0x1801044e3`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1801044e3`
- `ntdll!RtlQueryPackageIdentity` at `0x1801040ff`
- `ntdll!RtlQueryPackageIdentity` at `0x1801040ff`
- `ntdll!RtlNtStatusToDosError` at `0x1801044f1`
- `ntdll!RtlNtStatusToDosError` at `0x1801044f1`
- `ntdll!RtlIsMultiSessionSku` at `0x180103cef`
- `ntdll!RtlIsMultiSessionSku` at `0x180103cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010446e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010446e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180103e54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180103e54`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180103d77`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801045d4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180104762`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180103d77`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801045d4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180104762`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18010401e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18010401e`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18010407d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18010407d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18010443c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18010468e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18010443c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18010468e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180103fe7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180103fe7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180103f94`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180103f94`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801045e0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801046cb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801045e0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801046cb`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180104552`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180104552`
- `KERNELBASE!FormatApplicationUserModelId` at `0x18010417c`
- `KERNELBASE!FormatApplicationUserModelId` at `0x18010417c`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18010412c`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18010412c`
- `profapi!__imp_CreateEnvBlock` at `0x180103ec7`
- `profapi!__imp_CreateEnvBlock` at `0x180103ec7`
- `profapi!__imp_DestroyEnvBlock` at `0x1801045f6`
- `profapi!__imp_DestroyEnvBlock` at `0x1801046e1`
- `profapi!__imp_DestroyEnvBlock` at `0x180104778`
- `profapi!__imp_DestroyEnvBlock` at `0x1801045f6`
- `profapi!__imp_DestroyEnvBlock` at `0x1801046e1`
- `profapi!__imp_DestroyEnvBlock` at `0x180104778`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18010448a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18010448a`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x180103f12`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x180103f12`
- `ext-ms-win-com-psmregister-l1-2-0!PsmAdjustActivationToken` at `0x180104297`
- `ext-ms-win-com-psmregister-l1-2-0!PsmAdjustActivationToken` at `0x180104297`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180103d2c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180103d2c`

## string_xrefs

- `0x180103d51`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180103f29`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18010403a`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180104148`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1801041da`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180104234`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1801042ae`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180104364`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180104379`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1801043d3`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180104512`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18010456d`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1801045a9`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1801046a9`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180104736`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180104345`: `No client package identity found for debugger (DCOMLaunch): %!STATUS!`
- `0x18010421d`: `Falling back on client's PSM activation type (%u) for an identity type other than AAA (%u) (DCOMLaunch)`
- `0x1801043b4`: `IsPackageFamilyNameFromFullNamePresent is not present (DCOMLaunch)`
- `0x18010459a`: `LaunchDebugger CreateProcessAsUser failed`

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
  PSIZE_T lpReturnSize; // [rsp+30h] [rbp-D0h]
  LPVOID lpEnvironment; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE InAccessToken; // [rsp+68h] [rbp-98h] BYREF
  void *OutAccessToken; // [rsp+70h] [rbp-90h] BYREF
  PWSTR ppszPathOut; // [rsp+78h] [rbp-88h] BYREF
  __int64 v69; // [rsp+80h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-78h] BYREF
  __int64 v71; // [rsp+90h] [rbp-70h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+98h] [rbp-68h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+B0h] [rbp-50h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+B4h] [rbp-4Ch] BYREF
  ULONG_PTR Size; // [rsp+B8h] [rbp-48h] BYREF
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v77[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v78[4]; // [rsp+E0h] [rbp-20h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+100h] [rbp+0h] BYREF
  _OWORD *v80; // [rsp+168h] [rbp+68h]
  _OWORD v81[3]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR CommandLine[296]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+3F0h] [rbp+2F0h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR packageFullName[128]; // [rsp+510h] [rbp+410h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+610h] [rbp+510h] BYREF
  WCHAR pszPathIn[264]; // [rsp+720h] [rbp+620h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+978h] [rbp+878h]

  v15 = a12;
  v69 = a5;
  ppszPathOut = a8;
  memset_0(CommandLine, 0, 0x244u);
  InAccessToken = 0;
  OutAccessToken = 0;
  lpEnvironment = 0;
  v71 = 0;
  Size = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  phkResult = 0;
  memset(v81, 0, sizeof(v81));
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
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v71);
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
    &v71,
    UserSid);
  v23 = v71;
  if ( !v71 )
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
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v71);
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
                          v69,
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
  if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v81, 1u, 0, &Size) )
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
  if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v81, 0, 0x20008u, lpValue, 2 * v39, 0, 0) )
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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_1801574B8 + 1)) )
      ComTraceMessageT<>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (unsigned int)"LaunchDebugger",
        827,
        1,
        (__int64)L"IsPackageFamilyNameFromFullNamePresent is not present (DCOMLaunch)");
    goto LABEL_77;
  }
  v78[0] = 256;
  *(_QWORD *)v77 = 132;
  lpReserveda = v77;
  PackageIdentity = RtlQueryPackageIdentity(a1[9], packageFullName, v78, packageRelativeApplicationId);
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
              (unsigned int)v77);
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
          && (dword_1801574B8
           || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_1801574B8 + 1))) )
        {
          v43 = a10;
          LODWORD(lpReturnSize) = a10;
          LODWORD(lpReserveda) = 1;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            "LaunchDebugger",
            842,
            lpReserveda,
            L"Falling back on client's PSM activation type (%u) for an identity type other than AAA (%u) (DCOMLaunch)",
            lpReturnSize,
            a9);
        }
        else
        {
          v43 = a10;
        }
      }
      v69 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v69,
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
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v69);
        goto LABEL_91;
      }
      v46 = v69;
      v69 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &OutAccessToken,
        v46);
      StartupInfo.cb = 112;
      v80 = v81;
      v32 = 525328;
      ProcessAttributes.lpSecurityDescriptor = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v69);
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
            (int)v77);
    goto LABEL_38;
  }
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_1801574B8 + 1)) )
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
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v71);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&OutAccessToken);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&InAccessToken);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v57);
  return 0;
}

```

## disassembly

```asm
0x180103c08  mov     [rsp-8+arg_10], rbx
0x180103c0d  push    rbp
0x180103c0e  push    rsi
0x180103c0f  push    rdi
0x180103c10  push    r12
0x180103c12  push    r13
0x180103c14  push    r14
0x180103c16  push    r15
0x180103c18  lea     rbp, [rsp-840h]
0x180103c20  sub     rsp, 940h
0x180103c27  mov     rax, cs:__security_cookie
0x180103c2e  xor     rax, rsp
0x180103c31  mov     [rbp+870h+var_40], rax
0x180103c38  mov     rax, [rbp+870h+arg_20]
0x180103c3f  mov     esi, r8d
0x180103c42  mov     r12, [rbp+870h+LevelHandle]
0x180103c49  mov     r14d, edx
0x180103c4c  mov     r13, [rbp+870h+lpValue]
0x180103c53  mov     r15, rcx
0x180103c56  mov     rdi, [rbp+870h+arg_58]
0x180103c5d  lea     rcx, [rbp+870h+CommandLine]; void *
0x180103c64  mov     [rbp+870h+var_8F0], rax
0x180103c68  xor     edx, edx; Val
0x180103c6a  mov     rax, [rbp+870h+arg_38]
0x180103c71  mov     r8d, 244h; Size
0x180103c77  mov     [rsp+970h+ppszPathOut], rax
0x180103c7c  mov     rbx, r9
0x180103c7f  call    memset_0
0x180103c84  xor     ecx, ecx
0x180103c86  xor     eax, eax
0x180103c88  xorps   xmm0, xmm0
0x180103c8b  mov     [rsp+970h+InAccessToken], rcx
0x180103c90  mov     [rsp+970h+OutAccessToken], rcx
0x180103c95  xor     edx, edx; Val
0x180103c97  mov     [rsp+970h+var_910], rcx
0x180103c9c  mov     [rbp+870h+var_8E0], rcx
0x180103ca0  lea     r8d, [rax+68h]; Size
0x180103ca4  mov     [rbp+870h+Size], rcx
0x180103ca8  lea     rcx, [rbp+870h+StartupInfo.lpReserved]; void *
0x180103cac  movups  xmmword ptr [rbp+870h+ProcessInformation.hProcess], xmm0
0x180103cb0  mov     qword ptr [rbp+870h+ProcessInformation.dwProcessId], rax
0x180103cb4  movups  xmmword ptr [rbp+870h+ProcessAttributes.nLength], xmm0
0x180103cb8  mov     qword ptr [rbp+870h+ProcessAttributes.bInheritHandle], rax
0x180103cbc  mov     dword ptr [rbp+870h+StartupInfo+4], eax
0x180103cbf  call    memset_0
0x180103cc4  xorps   xmm0, xmm0
0x180103cc7  mov     [rbp+870h+phkResult], 0
0x180103ccf  movups  [rbp+870h+var_800], xmm0
0x180103cd3  mov     [rbp+870h+StartupInfo.cb], 68h ; 'h'
0x180103cda  movups  [rbp+870h+var_7F0], xmm0
0x180103ce1  mov     [rbp+870h+StartupInfo.dwFlags], 80h
0x180103ce8  movups  [rbp+870h+var_7E0], xmm0
0x180103cef  call    cs:__imp_RtlIsMultiSessionSku
0x180103cf6  nop     dword ptr [rax+rax+00h]
0x180103cfb  test    al, al
0x180103cfd  jnz     loc_180103DF0
0x180103d03  test    rbx, rbx
0x180103d06  jz      loc_180103D92
0x180103d0c  call    IsUMgrQueryUserContextPresent
0x180103d11  xor     r14d, r14d
0x180103d14  test    al, al
0x180103d16  jz      short loc_180103D88
0x180103d18  xor     edx, edx
0x180103d1a  lea     rcx, [rsp+970h+InAccessToken]
0x180103d1f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180103d24  lea     rdx, [rsp+970h+InAccessToken]
0x180103d29  mov     rcx, rbx
0x180103d2c  call    cs:__imp_UMgrQueryUserToken
0x180103d33  nop     dword ptr [rax+rax+00h]
0x180103d38  mov     ebx, eax
0x180103d3a  test    eax, eax
0x180103d3c  jns     loc_180103E1C
0x180103d42  mov     edx, 2A9h; void *
0x180103d47  mov     r9d, eax; char *
0x180103d4a  mov     rcx, [rbp+878h]; this
0x180103d51  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180103d58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103d5d  mov     rcx, [rbp+870h+string]; string
0x180103d64  lea     r9, [rbp+870h+CommandLine]; unsigned __int16 *
0x180103d6b  mov     edx, esi; unsigned int
0x180103d6d  call    ?LogDebuggerStartError@@YAXPEAUHSTRING__@@KPEAVCToken@@PEBG@Z; LogDebuggerStartError(HSTRING__ *,ulong,CToken *,ushort const *)
0x180103d72  mov     rcx, [rdi]; hProcess
0x180103d75  xor     edx, edx; uExitCode
0x180103d77  call    cs:__imp_TerminateProcess
0x180103d7e  nop     dword ptr [rax+rax+00h]
0x180103d83  jmp     loc_1801045EC
0x180103d88  mov     edx, 2AEh
0x180103d8d  jmp     loc_180103FA9
0x180103d92  mov     rcx, r15; this
0x180103d95  call    ?IsInteractiveUser@CToken@@QEAA_NXZ; CToken::IsInteractiveUser(void)
0x180103d9a  xor     edx, edx
0x180103d9c  lea     rcx, [rsp+970h+InAccessToken]
0x180103da1  test    al, al
0x180103da3  jz      short loc_180103DCB
0x180103da5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180103daa  mov     rcx, [r15+48h]; void *
0x180103dae  lea     rdx, [rsp+970h+InAccessToken]; void **
0x180103db3  call    ?GetUnmodifiedLogonTokenOfClientTokenUser@@YAJPEAXPEAPEAX@Z; GetUnmodifiedLogonTokenOfClientTokenUser(void *,void * *)
0x180103db8  xor     r14d, r14d
0x180103dbb  mov     ebx, eax
0x180103dbd  test    eax, eax
0x180103dbf  jns     short loc_180103E1C
0x180103dc1  mov     edx, 2B9h
0x180103dc6  jmp     loc_180103D47
0x180103dcb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180103dd0  lea     rdx, [rsp+970h+InAccessToken]; void **
0x180103dd5  mov     ecx, r14d; unsigned int
0x180103dd8  call    ?GetUserTokenForSession@@YAJKPEAPEAX@Z; GetUserTokenForSession(ulong,void * *)
0x180103ddd  xor     r14d, r14d
0x180103de0  mov     ebx, eax
0x180103de2  test    eax, eax
0x180103de4  jns     short loc_180103E1C
0x180103de6  mov     edx, 2C0h
0x180103deb  jmp     loc_180103D47
0x180103df0  xor     edx, edx
0x180103df2  lea     rcx, [rsp+970h+InAccessToken]
0x180103df7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180103dfc  lea     rdx, [rsp+970h+InAccessToken]; void **
0x180103e01  mov     ecx, r14d; unsigned int
0x180103e04  call    ?GetUserTokenForSession@@YAJKPEAPEAX@Z; GetUserTokenForSession(ulong,void * *)
0x180103e09  xor     r14d, r14d
0x180103e0c  mov     ebx, eax
0x180103e0e  test    eax, eax
0x180103e10  jns     short loc_180103E1C
0x180103e12  mov     edx, 2C6h
0x180103e17  jmp     loc_180103D47
0x180103e1c  mov     rcx, [rsp+970h+InAccessToken]; TokenHandle
0x180103e21  call    ?GetUserSid@@YAPEAXPEAX@Z; GetUserSid(void *)
0x180103e26  mov     rdx, rax
0x180103e29  lea     rcx, [rbp+870h+var_8E0]
0x180103e2d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?PrivMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180103e32  mov     rbx, [rbp+870h+var_8E0]
0x180103e36  test    rbx, rbx
0x180103e39  jnz     short loc_180103E45
0x180103e3b  mov     edx, 2CBh
0x180103e40  jmp     loc_18010472F
0x180103e45  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180103e4c  xor     edx, edx; dwFlags
0x180103e4e  mov     r8d, 0A0h; dwBytes
0x180103e54  call    cs:__imp_HeapAlloc
0x180103e5b  nop     dword ptr [rax+rax+00h]
0x180103e60  test    rax, rax
0x180103e63  jz      loc_18010472A
0x180103e69  mov     dword ptr [rsp+970h+lpReturnSize], r14d
0x180103e6e  mov     r9d, 1FFFFFh
0x180103e74  mov     dword ptr [rsp+970h+lpPreviousValue], r14d
0x180103e79  xor     r8d, r8d
0x180103e7c  xor     edx, edx
0x180103e7e  mov     dword ptr [rsp+970h+lpReserved], r14d
0x180103e83  mov     rcx, rax
0x180103e86  mov     [rax], rbx
0x180103e89  mov     [rax+8], r14
0x180103e8d  mov     [rax+10h], r14
0x180103e91  mov     [rax+18h], r14
0x180103e95  mov     [rax+20h], r14
0x180103e99  mov     [rax+28h], r14
0x180103e9d  call    ?IdentifyAccess@CAccessInfo@@QEAAPEAXW4SecurityDescriptorOwner@@KKKKK@Z; CAccessInfo::IdentifyAccess(SecurityDescriptorOwner,ulong,ulong,ulong,ulong,ulong)
0x180103ea2  test    rax, rax
0x180103ea5  jz      loc_180104723
0x180103eab  mov     rdx, [rsp+970h+InAccessToken]
0x180103eb0  lea     rcx, [rsp+970h+var_910]
0x180103eb5  xor     r8d, r8d
0x180103eb8  mov     [rbp+870h+ProcessAttributes.nLength], 18h
0x180103ebf  mov     [rbp+870h+ProcessAttributes.lpSecurityDescriptor], rax
0x180103ec3  mov     [rbp+870h+ProcessAttributes.bInheritHandle], r14d
0x180103ec7  call    cs:__imp_CreateEnvBlock
0x180103ece  nop     dword ptr [rax+rax+00h]
0x180103ed3  mov     ebx, eax
0x180103ed5  test    eax, eax
0x180103ed7  jns     short loc_180103EE3
0x180103ed9  mov     edx, 2DFh
0x180103ede  jmp     loc_180103D47
0x180103ee3  test    r12, r12
0x180103ee6  jz      short loc_180103F41
0x180103ee8  call    IsSaferCloseLevelPresent
0x180103eed  test    al, al
0x180103eef  jz      short loc_180103F41
0x180103ef1  xor     edx, edx
0x180103ef3  lea     rcx, [rsp+970h+OutAccessToken]
0x180103ef8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180103efd  mov     rdx, [rsp+970h+InAccessToken]; InAccessToken
0x180103f02  lea     r8, [rsp+970h+OutAccessToken]; OutAccessToken
0x180103f07  xor     r9d, r9d; dwFlags
0x180103f0a  mov     [rsp+970h+lpReserved], r14; lpReserved
0x180103f0f  mov     rcx, r12; LevelHandle
0x180103f12  call    cs:__imp_SaferComputeTokenFromLevel
0x180103f19  nop     dword ptr [rax+rax+00h]
0x180103f1e  test    eax, eax
0x180103f20  jnz     short loc_180103F55
0x180103f22  mov     rcx, [rbp+878h]; this
0x180103f29  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180103f30  mov     edx, 2E3h; void *
0x180103f35  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180103f3a  mov     ebx, eax
0x180103f3c  jmp     loc_180103D5D
0x180103f41  mov     rdx, [rsp+970h+InAccessToken]
0x180103f46  lea     rcx, [rsp+970h+OutAccessToken]
0x180103f4b  mov     [rsp+970h+InAccessToken], r14
0x180103f50  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180103f55  mov     eax, [rdi+14h]
0x180103f58  lea     r8, aSPDTidD; "%s -p %d -tid %d"
0x180103f5f  mov     r9, [rbp+870h+var_8F0]
0x180103f63  lea     rcx, [rbp+870h+CommandLine]; unsigned __int16 *
0x180103f6a  mov     dword ptr [rsp+970h+lpPreviousValue], eax
0x180103f6e  mov     edx, 122h; unsigned __int64
0x180103f73  mov     eax, [rdi+10h]
0x180103f76  mov     dword ptr [rsp+970h+lpReserved], eax
0x180103f7a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180103f7f  mov     ebx, eax
0x180103f81  test    eax, eax
0x180103f83  jns     short loc_180103F8F
0x180103f85  mov     edx, 2ECh
0x180103f8a  jmp     loc_180103D47
0x180103f8f  mov     rcx, [rsp+970h+OutAccessToken]; hToken
0x180103f94  call    cs:__imp_ImpersonateLoggedOnUser
0x180103f9b  nop     dword ptr [rax+rax+00h]
0x180103fa0  test    eax, eax
0x180103fa2  jnz     short loc_180103FB6
0x180103fa4  mov     edx, 2F2h
0x180103fa9  mov     ebx, 80070005h
0x180103fae  mov     r9d, ebx
0x180103fb1  jmp     loc_180103D4A
0x180103fb6  xor     edx, edx
0x180103fb8  lea     rcx, [rbp+870h+phkResult]
0x180103fbc  mov     r12d, 410h
0x180103fc2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180103fc7  lea     rax, [rbp+870h+phkResult]
0x180103fcb  mov     r9d, 20019h; samDesired
0x180103fd1  xor     r8d, r8d; ulOptions
0x180103fd4  mov     [rsp+970h+lpReserved], rax; phkResult
0x180103fd9  lea     rdx, aSystemAim; "System\\AIM"
0x180103fe0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180103fe7  call    cs:__imp_RegOpenKeyExW
0x180103fee  nop     dword ptr [rax+rax+00h]
0x180103ff3  mov     [rbp+870h+phkResult], r14
0x180103ff7  test    eax, eax
0x180103ff9  jnz     loc_1801043E4
0x180103fff  test    r13, r13
0x180104002  jz      loc_1801043E4
0x180104008  lea     r9, [rbp+870h+Size]; lpSize
0x18010400c  mov     [rbp+870h+Size], 30h ; '0'
0x180104014  xor     r8d, r8d; dwFlags
0x180104017  lea     edx, [rax+1]; dwAttributeCount
0x18010401a  lea     rcx, [rbp+870h+var_800]; lpAttributeList
0x18010401e  call    cs:__imp_InitializeProcThreadAttributeList
0x180104025  nop     dword ptr [rax+rax+00h]
0x18010402a  test    eax, eax
0x18010402c  jnz     short loc_18010404D
0x18010402e  mov     edx, 309h; void *
0x180104033  mov     rcx, [rbp+878h]; this
0x18010403a  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180104041  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180104046  mov     ebx, eax
0x180104048  jmp     loc_1801045BA
0x18010404d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180104051  inc     rax
0x180104054  cmp     [r13+rax*2+0], r14w
0x18010405a  jnz     short loc_180104051
0x18010405c  add     rax, rax
0x18010405f  mov     [rsp+970h+lpReturnSize], r14; lpReturnSize
0x180104064  mov     [rsp+970h+lpPreviousValue], r14; lpPreviousValue
0x180104069  lea     rcx, [rbp+870h+var_800]; lpAttributeList
0x18010406d  mov     r9, r13; lpValue
0x180104070  mov     [rsp+970h+lpReserved], rax; cbSize
0x180104075  xor     edx, edx; dwFlags
0x180104077  mov     r8d, 20008h; Attribute
0x18010407d  call    cs:__imp_UpdateProcThreadAttribute
0x180104084  nop     dword ptr [rax+rax+00h]
0x180104089  test    eax, eax
0x18010408b  jnz     short loc_180104094
0x18010408d  mov     edx, 30Eh
0x180104092  jmp     short loc_180104033
0x180104094  mov     r14d, [rbp+870h+arg_40]
0x18010409b  xor     ebx, ebx
0x18010409d  cmp     [rsp+970h+ppszPathOut], rbx
0x1801040a2  jnz     loc_18010419F
0x1801040a8  test    r14d, r14d
0x1801040ab  jnz     loc_1801043E1
0x1801040b1  call    IsPackageFamilyNameFromIdPresent
0x1801040b6  test    al, al
0x1801040b8  jz      loc_180104392
0x1801040be  call    IsGetStagedPackageOriginPresent
0x1801040c3  test    al, al
0x1801040c5  jz      loc_180104392
0x1801040cb  mov     [rbp+870h+var_890], 100h
0x1801040d3  lea     rax, [rbp+870h+var_898]
0x1801040d7  mov     qword ptr [rbp+870h+var_898], 84h
0x1801040df  lea     r9, [rbp+870h+packageRelativeApplicationId]
0x1801040e6  mov     rcx, [r15+48h]
0x1801040ea  lea     r8, [rbp+870h+var_890]
0x1801040ee  mov     [rsp+970h+lpPreviousValue], rbx
0x1801040f3  lea     rdx, [rbp+870h+packageFullName]
0x1801040fa  mov     [rsp+970h+lpReserved], rax; int
0x1801040ff  call    cs:__imp_RtlQueryPackageIdentity
0x180104106  nop     dword ptr [rax+rax+00h]
0x18010410b  test    eax, eax
0x18010410d  js      loc_18010430B
0x180104113  lea     r8, [rbp+870h+packageFamilyName]; packageFamilyName
0x18010411a  mov     [rbp+870h+packageFamilyNameLength], 82h
0x180104121  lea     rdx, [rbp+870h+packageFamilyNameLength]; packageFamilyNameLength
  ... truncated ...
```
