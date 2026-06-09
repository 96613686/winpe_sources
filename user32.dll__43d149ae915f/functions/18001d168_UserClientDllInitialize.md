# _UserClientDllInitialize

- ea: `0x18001d168`
- end: `0x18001dad1`
- name: `_UserClientDllInitialize`
- size: `2409`
- prototype: `__int64 __fastcall(HMODULE hLibModule)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d130`

## callees

- `0x180012b40`
- `0x180017ad0`
- `0x18001a2b8`
- `0x18001cf68`
- `0x18001cfb4`
- `0x18001d168`
- `0x18001dad8`
- `0x18001db90`
- `0x18001dcc8`
- `0x18001dcec`
- `0x18001dd74`
- `0x18001de68`
- `0x18001e248`
- `0x18001e308`
- `0x18001e360`
- `0x18001e3e8`
- `0x18001eb00`
- `0x18001f35c`
- `0x18006fec8`
- `0x18006ffd4`
- `0x18008288c`
- `0x180092660`
- `0x180092d04`
- `0x180096dc5`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserDisableProcessWindowFiltering` at `0x18001dac6`
- `win32u!NtUserDisableProcessWindowFiltering` at `0x18001dac6`
- `win32u!NtUserSetProcessUIAccessZorder` at `0x18001d943`
- `win32u!NtUserSetProcessUIAccessZorder` at `0x18001d943`
- `win32u!NtUserSetProcessMousewheelRoutingMode` at `0x18001d919`
- `win32u!NtUserSetProcessMousewheelRoutingMode` at `0x18001d919`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d38c`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d399`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3a6`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3b3`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3c0`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3cd`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3da`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3e7`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3f4`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d401`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d38c`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d399`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3a6`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3b3`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3c0`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3cd`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3da`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3e7`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3f4`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d401`
- `ntdll!RtlResetNtUserPfn` at `0x18001d37f`
- `ntdll!RtlResetNtUserPfn` at `0x18001d37f`
- `ntdll!RtlQueryInformationActiveActivationContext` at `0x18001da42`
- `ntdll!RtlQueryInformationActiveActivationContext` at `0x18001da42`
- `ntdll!RtlQueryElevationFlags` at `0x18001d6cb`
- `ntdll!RtlQueryElevationFlags` at `0x18001d6cb`
- `ntdll!NtQuerySystemInformation` at `0x18001d4c2`
- `ntdll!NtQuerySystemInformation` at `0x18001d4c2`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d221`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d230`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d241`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d252`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d263`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d274`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d285`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d296`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d2a7`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d2b8`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d2c9`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d49a`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d221`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d230`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d241`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d252`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d263`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d274`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d285`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d296`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d2a7`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d2b8`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d2c9`
- `ntdll!RtlInitializeCriticalSection` at `0x18001d49a`
- `ntdll!CsrClientConnectToServer` at `0x18001d537`
- `ntdll!CsrClientConnectToServer` at `0x18001d537`
- `ntdll!RtlFreeHeap` at `0x18009a07e`
- `ntdll!RtlFreeHeap` at `0x18009a07e`
- `ntdll!RtlAllocateHeap` at `0x18001d67b`
- `ntdll!RtlAllocateHeap` at `0x18001d67b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001da55`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001da60`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001da6b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001da55`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001da60`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001da6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d861`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d861`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001d214`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001d214`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18001da76`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18001da76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d9f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d9f3`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18001da09`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18001da09`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001d908`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001dab8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001d908`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001dab8`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x18001d8b2`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x18001d8ec`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x18001d8b2`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x18001d8ec`
- `api-ms-win-core-kernel32-private-l1-1-0!RegisterWaitForInputIdle` at `0x18001d635`
- `api-ms-win-core-kernel32-private-l1-1-0!RegisterWaitForInputIdle` at `0x18001d635`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18001d505`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18001d505`
- `GDI32!GdiDllInitialize` at `0x18001d826`
- `GDI32!GdiDllInitialize` at `0x18001d826`

## string_xrefs

- `0x18001d8dc`: `http://schemas.microsoft.com/SMI/2014/WindowsSettings`
- `0x18001d8a2`: `http://schemas.microsoft.com/SMI/2011/WindowsSettings`

## pseudocode

```c
_BOOL8 __fastcall UserClientDllInitialize(HMODULE hLibModule, unsigned int a2)
{
  void (*v4)(HWND); // rdx
  wchar_t *v5; // rcx
  wchar_t v6; // ax
  ULONG SessionId; // r14d
  NTSTATUS v8; // ebx
  int v9; // edi
  int v10; // ebx
  int v11; // edi
  int v12; // ebx
  int v13; // edi
  int v14; // ebx
  int v15; // edi
  int v16; // ebx
  void *v18; // rcx
  int v19; // eax
  WCHAR *v20; // rcx
  __int64 *v21; // rax
  char *v22; // rcx
  __int64 v23; // rdx
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  HMODULE ModuleHandleW; // rdx
  __int64 (__fastcall **v35)(); // rbx
  PVOID ProcessHeap; // rcx
  PVOID Heap; // rax
  void *v38; // rdx
  _OWORD *v39; // rcx
  __int64 v40; // rax
  int inited; // eax
  int v42; // ebx
  unsigned int v43; // edx
  HANDLE CurrentProcess; // rax
  _QWORD *v45; // r8
  __int128 v46; // xmm1
  _QWORD *v47; // rbx
  signed __int32 v48[8]; // [rsp+0h] [rbp-100h] BYREF
  PBOOLEAN ServerToServerCall; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+40h] [rbp-C0h] BYREF
  int v51; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v52; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE ConnectionInfo[8]; // [rsp+60h] [rbp-A0h] BYREF
  char v54; // [rsp+68h] [rbp-98h] BYREF
  __int64 v55; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v56; // [rsp+2B8h] [rbp+1B8h]
  _BYTE SystemInformation[40]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v58; // [rsp+2E8h] [rbp+1E8h]
  WCHAR pvBuffer[8]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR String1[8]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR ModuleName[264]; // [rsp+320h] [rbp+220h] BYREF

  memset_0(SystemInformation, 0, 0x40u);
  v51 = 0;
  v55 = 0;
  v56 = 0;
  if ( a2 == 1 )
  {
    v5 = szDummyGlobalForZeroPadding;
    do
    {
      v6 = *v5;
      *v5 = *v5;
      ++v5;
    }
    while ( v6 );
    memset_0(ConnectionInfo, 0, 0x248u);
    v52 = 0;
    SessionId = NtCurrentPeb()->SessionId;
    DisableThreadLibraryCalls(hLibModule);
    v8 = RtlInitializeCriticalSection(&gcsClipboard);
    v9 = v8 | RtlInitializeCriticalSection(&gcsLookaside);
    v10 = v9 | RtlInitializeCriticalSection(&gcsHdc);
    v11 = v10 | RtlInitializeCriticalSection(&gcsAccelCache);
    v12 = v11 | RtlInitializeCriticalSection(&gcsDDEML);
    v13 = v12 | RtlInitializeCriticalSection(&gcsUserApiHook);
    v14 = v13 | RtlInitializeCriticalSection(&gcsDManipHook);
    v15 = v14 | RtlInitializeCriticalSection(&gcsMPH);
    v16 = v15 | RtlInitializeCriticalSection(&gcsClassRegister);
    if ( (v16 | RtlInitializeCriticalSection(&gcsAvrt)) < 0 )
      return 0;
    if ( RtlInitializeCriticalSection(&stru_1800C9C80) < 0 )
    {
      dword_1800C9CC0 = 0;
      return 0;
    }
    dword_1800C9CC0 = 1;
    if ( RtlInitializeCriticalSection(&CriticalSection) < 0 )
    {
      dword_1800C9C70 = 0;
      return 0;
    }
    dword_1800C9C70 = 1;
    if ( NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0) < 0 )
      return 0;
    gHighestUserAddress = v58;
    if ( !(unsigned int)InitializeNtdllUserPfn() )
      return 0;
    if ( (NtCurrentPeb()->BitField & 2) != 0 && (NtCurrentPeb()->BitField & 0x40) == 0 )
    {
      LODWORD(v52) = 576;
      *((_QWORD *)&v52 + 1) = &gSharedInfo;
      NtCurrentPeb()->KernelCallbackTable = (char *)&v52 + 1;
    }
    v19 = WTSGetServiceSessionId();
    v20 = (WCHAR *)L"\\Windows";
    if ( SessionId != v19 )
    {
      LODWORD(ServerToServerCall) = SessionId;
      StringCchPrintfW(ModuleName, 0x100u, L"%ws\\%ld%ws", L"\\Sessions", ServerToServerCall, L"\\Windows");
      v20 = ModuleName;
    }
    if ( CsrClientConnectToServer(v20, 3u, ConnectionInfo, (PULONG)0x248, &gfServerProcess) < 0 )
      return 0;
    if ( *(_DWORD *)&gfServerProcess )
    {
      if ( !(unsigned int)InitializeCsrUserPfn() )
        return 0;
    }
    else
    {
      if ( (NtCurrentPeb()->BitField & 2) == 0 || (NtCurrentPeb()->BitField & 0x40) != 0 )
      {
        v21 = &gSharedInfo;
        v22 = &v54;
        v23 = 4;
        do
        {
          v24 = *((_OWORD *)v22 + 1);
          *(_OWORD *)v21 = *(_OWORD *)v22;
          v25 = *((_OWORD *)v22 + 2);
          *((_OWORD *)v21 + 1) = v24;
          v26 = *((_OWORD *)v22 + 3);
          *((_OWORD *)v21 + 2) = v25;
          v27 = *((_OWORD *)v22 + 4);
          *((_OWORD *)v21 + 3) = v26;
          v28 = *((_OWORD *)v22 + 5);
          *((_OWORD *)v21 + 4) = v27;
          v29 = *((_OWORD *)v22 + 6);
          *((_OWORD *)v21 + 5) = v28;
          v30 = *((_OWORD *)v22 + 7);
          v22 += 128;
          *((_OWORD *)v21 + 6) = v29;
          *((_OWORD *)v21 + 7) = v30;
          v21 += 16;
          --v23;
        }
        while ( v23 );
        v31 = *((_OWORD *)v22 + 1);
        *(_OWORD *)v21 = *(_OWORD *)v22;
        v32 = *((_OWORD *)v22 + 2);
        *((_OWORD *)v21 + 1) = v31;
        v33 = *((_OWORD *)v22 + 3);
        *((_OWORD *)v21 + 2) = v32;
        *((_OWORD *)v21 + 3) = v33;
      }
      else
      {
        if ( NtCurrentPeb()->KernelCallbackTable )
          return 0;
        _InterlockedOr(v48, 0);
      }
      ModuleHandleW = 0;
      gpsi = gSharedInfo;
      if ( (*(_BYTE *)gSharedInfo & 4) != 0 )
      {
        bImmInitializing = 1;
        _InitializeImmEntryTable();
        GetImmFileName(ModuleName, v43);
        ModuleHandleW = GetModuleHandleW(ModuleName);
      }
      ((void (__fastcall *)(__int64 *, HMODULE))off_1800C85F0[0])(&gSharedInfo, ModuleHandleW);
    }
    v35 = apfnDispatch;
    NtCurrentPeb()->KernelCallbackTable = apfnDispatch;
    NtCurrentPeb()->PostProcessInitRoutine = 0;
    RegisterWaitForInputIdle(WaitForInputIdle);
    hmodUser = hLibModule;
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    pUserHeap = ProcessHeap;
    if ( g_systemCallFilterId == 7 )
    {
      v50 = 0;
      CurrentProcess = GetCurrentProcess();
      if ( (unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v50, 4) )
      {
        ProcessHeap = (PVOID)(v50 & 0xF);
        _InterlockedCompareExchange((volatile signed __int32 *)&g_systemCallFilterId, (signed __int32)ProcessHeap, 7);
      }
    }
    if ( g_systemCallFilterId == 5 )
    {
      Heap = RtlAllocateHeap(pUserHeap, 0, 0x460u);
      v38 = Heap;
      if ( !Heap )
        return 0;
      v39 = Heap;
      v40 = 8;
      do
      {
        *v39 = *(_OWORD *)v35;
        v39[1] = *((_OWORD *)v35 + 1);
        v39[2] = *((_OWORD *)v35 + 2);
        v39[3] = *((_OWORD *)v35 + 3);
        v39[4] = *((_OWORD *)v35 + 4);
        v39[5] = *((_OWORD *)v35 + 5);
        v39[6] = *((_OWORD *)v35 + 6);
        v46 = *((_OWORD *)v35 + 7);
        v35 += 16;
        v39[7] = v46;
        v39 += 8;
        --v40;
      }
      while ( v40 );
      *v39 = *(_OWORD *)v35;
      v39[1] = *((_OWORD *)v35 + 1);
      v39[2] = *((_OWORD *)v35 + 2);
      v39[3] = *((_OWORD *)v35 + 3);
      v39[4] = *((_OWORD *)v35 + 4);
      v39[5] = *((_OWORD *)v35 + 5);
      NtCurrentPeb()->KernelCallbackTable = v38;
      *((_QWORD *)NtCurrentPeb()->KernelCallbackTable + 123) = _AllocAndInitClientWindowInfo;
      *((_QWORD *)NtCurrentPeb()->KernelCallbackTable + 124) = _CleanupClientWindowInfoAndFree;
      UserWindowPropMangerClassA::InitWinpropManager();
      UserWindowPropMangerClassW::InitWinpropManager();
    }
    if ( *(_DWORD *)&gfServerProcess )
      inited = 0;
    else
      inited = InitInstrument((unsigned int *)ProcessHeap);
    gdwRegisteredClassesMask |= 0xFFFFu;
    gfEMIEnable = inited;
    if ( (int)RtlQueryElevationFlags(&v51) >= 0
      && (v51 & 1) == 0
      && RtlQueryInformationActiveActivationContext(5u, &v55, 0xCu, 0) >= 0
      && v56 )
    {
      NtUserSetProcessUIAccessZorder();
    }
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800C87A8);
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800C8770);
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&qword_1800C8738);
    qword_1800C9B18 = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_NtUserTraceGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    qword_1800C9B20 = 1;
    WppInitUm();
    g_wil_details_ensureSubscribedToFeatureConfigurationChanges = (__int64)wil::details::EnsureSubscribedToFeatureConfigurationChanges;
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges = (__int64)&wil::details::SubscribeFeatureStateCacheToConfigurationChanges;
    g_wil_details_internalGetFeatureEnabledState = (__int64)wil::details::WilApiImpl_GetFeatureEnabledState;
    g_wil_details_internalRecordFeatureUsage = (__int64)wil::details::WilApiImpl_RecordFeatureUsage;
    g_wil_details_internalSubscribeFeatureStateChangeNotification = (__int64)wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification;
    g_wil_details_internalUnsubscribeFeatureStateChangeNotification = (__int64)wil::details::WilApiImpl_UnsubscribeFeatureStateChangeNotification;
    g_wil_details_realtimeFeatureUsageHook = (__int64)wil_StagingConfig_LogStagedFeatureUsage;
    g_wil_details_featureProcessUsageHook = (__int64)CheckBannedOneCoreTransformApi;
    wil::details::g_pfnGetModuleName = (__int64)wil::details::GetCurrentModuleName;
    wil::details::g_pfnDebugBreak = (__int64)wil::details::DebugBreak;
    wil::details::g_pfnRaiseFailFastException = (void (*)(struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int))wil::details::WilDynamicLoadRaiseFailFastException;
    wil::details::g_pfnFormatNtStatusMsg = (void (*)(int, unsigned __int16 *, unsigned int))wil::details::FormatNtStatusMsg;
    wil::details::g_pfnNotifyFailure = (__int64)wil::details::MicrosoftInternalNotifyFailure;
    wil::details::g_pfnRtlNtStatusToDosErrorNoTeb = (__int64)wil::details::RtlNtStatusToDosErrorNoTeb;
    wil::details::g_pfnDllShutdownInProgress = (__int64)wil::details::RtlDllShutdownInProgress;
    wil::WilInitialize_Result(0);
    InitProcessGdiScaling();
    InitProcessSystemDpiBehavior();
  }
  else if ( !a2 )
  {
    if ( ghImm32 )
      FreeLibrary(ghImm32);
    if ( ghinstOLE )
      FreeLibrary(ghinstOLE);
    if ( ghmodAvrt )
      FreeLibrary(ghmodAvrt);
    if ( gEventSource )
      EventUnregister(gEventSource);
    if ( g_systemCallFilterId == 5 )
    {
      UserWindowPropMangerClassA::CleanupWinpropManager();
      UserWindowPropMangerClassW::CleanupWinpropManager();
      v45 = P;
      if ( P )
      {
        do
        {
          v47 = (_QWORD *)v45[2];
          RtlFreeHeap(pUserHeap, 0, v45);
          v45 = v47;
        }
        while ( v47 );
      }
    }
    if ( lpModuleName )
    {
      WindowServicesCommon::ReleaseModuleReference(lpModuleName, v4);
      lpModuleName = 0;
      dword_1800CA048 = 0;
    }
    RtlResetNtUserPfn();
    RtlDeleteCriticalSection(&gcsClipboard);
    RtlDeleteCriticalSection(&gcsLookaside);
    RtlDeleteCriticalSection(&gcsHdc);
    RtlDeleteCriticalSection(&gcsAccelCache);
    RtlDeleteCriticalSection(&gcsDDEML);
    RtlDeleteCriticalSection(&gcsUserApiHook);
    RtlDeleteCriticalSection(&gcsDManipHook);
    RtlDeleteCriticalSection(&gcsMPH);
    RtlDeleteCriticalSection(&gcsClassRegister);
    RtlDeleteCriticalSection(&gcsAvrt);
    UninitializeUMHandleList((struct tagUMHANDLELIST *)&stru_1800C9C80);
    UninitializeUMHandleList((struct tagUMHANDLELIST *)&CriticalSection);
    WppCleanupUm();
    TraceLoggingUnregister_EventUnregister(&dword_1800C87A8);
    TraceLoggingUnregister_EventUnregister(&dword_1800C8770);
    TraceLoggingUnregister_EventUnregister(&qword_1800C8738);
    if ( wil::details_abi::g_pProcessLocalData )
    {
      v18 = *(void **)(wil::details_abi::g_pProcessLocalData + 8);
      if ( v18 )
        wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(v18);
      wil::details_abi::g_pProcessLocalData = 0;
    }
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>();
      wil::details::g_pThreadFailureCallbacks = 0;
    }
  }
  v42 = GdiDllInitialize(hLibModule, a2);
  if ( a2 == 1 )
  {
    if ( v42 < 0 )
      return 0;
    InitProcessDpiAwareness();
    if ( QueryActCtxSettingsW(
           0,
           0,
           L"http://schemas.microsoft.com/SMI/2011/WindowsSettings",
           L"disableWindowFiltering",
           pvBuffer,
           8u,
           0)
      && !lstrcmpiW(pvBuffer, L"true") )
    {
      NtUserDisableProcessWindowFiltering();
    }
    if ( QueryActCtxSettingsW(
           0,
           0,
           L"http://schemas.microsoft.com/SMI/2014/WindowsSettings",
           L"forceFocusBasedMouseWheel",
           String1,
           8u,
           0) )
    {
      if ( !lstrcmpiW(String1, L"true") )
        NtUserSetProcessMousewheelRoutingMode(1);
    }
  }
  return v42 >= 0;
}

```

## disassembly

```asm
0x18001d168  mov     [rsp-8+arg_10], rbx
0x18001d16d  mov     [rsp-8+arg_18], rsi
0x18001d172  push    rbp
0x18001d173  push    rdi
0x18001d174  push    r12
0x18001d176  push    r14
0x18001d178  push    r15
0x18001d17a  lea     rbp, [rsp-440h]
0x18001d182  sub     rsp, 540h
0x18001d189  mov     rax, cs:__security_cookie
0x18001d190  xor     rax, rsp
0x18001d193  mov     [rbp+460h+var_30], rax
0x18001d19a  mov     esi, edx
0x18001d19c  mov     r15, rcx
0x18001d19f  xor     edx, edx; Val
0x18001d1a1  lea     rcx, [rbp+460h+SystemInformation]; void *
0x18001d1a8  lea     r8d, [rdx+40h]; Size
0x18001d1ac  call    memset_0
0x18001d1b1  xor     eax, eax
0x18001d1b3  xor     r12d, r12d
0x18001d1b6  mov     [rsp+560h+var_51C], r12d
0x18001d1bb  mov     [rbp+460h+var_2B0], rax
0x18001d1c2  mov     [rbp+460h+var_2A8], eax
0x18001d1c8  cmp     esi, 1
0x18001d1cb  jnz     loc_18001D30B
0x18001d1d1  lea     rcx, szDummyGlobalForZeroPadding; "Dummy string"
0x18001d1d8  movzx   eax, word ptr [rcx]
0x18001d1db  mov     [rcx], ax
0x18001d1de  lea     rcx, [rcx+2]
0x18001d1e2  test    ax, ax
0x18001d1e5  jnz     short loc_18001D1D8
0x18001d1e7  xor     edx, edx; Val
0x18001d1e9  lea     rcx, [rsp+560h+ConnectionInfo]; void *
0x18001d1ee  mov     r8d, 248h; Size
0x18001d1f4  call    memset_0
0x18001d1f9  xorps   xmm0, xmm0
0x18001d1fc  mov     rcx, r15; hLibModule
0x18001d1ff  movups  [rsp+560h+var_518], xmm0
0x18001d204  mov     rax, gs:60h
0x18001d20d  mov     r14d, [rax+2C0h]
0x18001d214  call    cs:__imp_DisableThreadLibraryCalls
0x18001d21a  lea     rcx, ?gcsClipboard@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d221  call    cs:__imp_RtlInitializeCriticalSection
0x18001d227  lea     rcx, ?gcsLookaside@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d22e  mov     ebx, eax
0x18001d230  call    cs:__imp_RtlInitializeCriticalSection
0x18001d236  mov     edi, eax
0x18001d238  lea     rcx, ?gcsHdc@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d23f  or      edi, ebx
0x18001d241  call    cs:__imp_RtlInitializeCriticalSection
0x18001d247  mov     ebx, eax
0x18001d249  lea     rcx, ?gcsAccelCache@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d250  or      ebx, edi
0x18001d252  call    cs:__imp_RtlInitializeCriticalSection
0x18001d258  mov     edi, eax
0x18001d25a  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d261  or      edi, ebx
0x18001d263  call    cs:__imp_RtlInitializeCriticalSection
0x18001d269  mov     ebx, eax
0x18001d26b  lea     rcx, ?gcsUserApiHook@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d272  or      ebx, edi
0x18001d274  call    cs:__imp_RtlInitializeCriticalSection
0x18001d27a  mov     edi, eax
0x18001d27c  lea     rcx, ?gcsDManipHook@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d283  or      edi, ebx
0x18001d285  call    cs:__imp_RtlInitializeCriticalSection
0x18001d28b  mov     ebx, eax
0x18001d28d  lea     rcx, ?gcsMPH@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d294  or      ebx, edi
0x18001d296  call    cs:__imp_RtlInitializeCriticalSection
0x18001d29c  mov     edi, eax
0x18001d29e  lea     rcx, ?gcsClassRegister@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d2a5  or      edi, ebx
0x18001d2a7  call    cs:__imp_RtlInitializeCriticalSection
0x18001d2ad  mov     ebx, eax
0x18001d2af  lea     rcx, ?gcsAvrt@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d2b6  or      ebx, edi
0x18001d2b8  call    cs:__imp_RtlInitializeCriticalSection
0x18001d2be  or      eax, ebx
0x18001d2c0  jl      short loc_18001D2DE
0x18001d2c2  lea     rcx, stru_1800C9C80; CriticalSection
0x18001d2c9  call    cs:__imp_RtlInitializeCriticalSection
0x18001d2cf  test    eax, eax
0x18001d2d1  jns     loc_18001D489
0x18001d2d7  mov     cs:dword_1800C9CC0, r12d
0x18001d2de  xor     eax, eax
0x18001d2e0  mov     rcx, [rbp+460h+var_30]
0x18001d2e7  xor     rcx, rsp; StackCookie
0x18001d2ea  call    __security_check_cookie
0x18001d2ef  lea     r11, [rsp+560h+var_20]
0x18001d2f7  mov     rbx, [r11+40h]
0x18001d2fb  mov     rsi, [r11+48h]
0x18001d2ff  mov     rsp, r11
0x18001d302  pop     r15
0x18001d304  pop     r14
0x18001d306  pop     r12
0x18001d308  pop     rdi
0x18001d309  pop     rbp
0x18001d30a  retn
0x18001d30b  test    esi, esi
0x18001d30d  jnz     loc_18001D821
0x18001d313  mov     rcx, cs:?ghImm32@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001d31a  test    rcx, rcx
0x18001d31d  jnz     loc_18001DA55
0x18001d323  mov     rcx, cs:?ghinstOLE@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001d32a  test    rcx, rcx
0x18001d32d  jnz     loc_18001DA60
0x18001d333  mov     rcx, cs:?ghmodAvrt@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001d33a  test    rcx, rcx
0x18001d33d  jnz     loc_18001DA6B
0x18001d343  mov     rcx, cs:?gEventSource@@3_KA; RegHandle
0x18001d34a  test    rcx, rcx
0x18001d34d  jnz     loc_18001DA76
0x18001d353  cmp     cs:?g_systemCallFilterId@@3KA, 5; ulong g_systemCallFilterId
0x18001d35a  jz      loc_18001DA81
0x18001d360  mov     rcx, cs:lpModuleName; lpModuleName
0x18001d367  test    rcx, rcx
0x18001d36a  jz      short loc_18001D37F
0x18001d36c  call    ?ReleaseModuleReference@WindowServicesCommon@@YAXP6AXPEAUHWND__@@@Z@Z; WindowServicesCommon::ReleaseModuleReference(void (*)(HWND__ *))
0x18001d371  mov     cs:lpModuleName, r12
0x18001d378  mov     cs:dword_1800CA048, r12d
0x18001d37f  call    cs:__imp_RtlResetNtUserPfn
0x18001d385  lea     rcx, ?gcsClipboard@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d38c  call    cs:__imp_RtlDeleteCriticalSection
0x18001d392  lea     rcx, ?gcsLookaside@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d399  call    cs:__imp_RtlDeleteCriticalSection
0x18001d39f  lea     rcx, ?gcsHdc@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d3a6  call    cs:__imp_RtlDeleteCriticalSection
0x18001d3ac  lea     rcx, ?gcsAccelCache@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d3b3  call    cs:__imp_RtlDeleteCriticalSection
0x18001d3b9  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d3c0  call    cs:__imp_RtlDeleteCriticalSection
0x18001d3c6  lea     rcx, ?gcsUserApiHook@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d3cd  call    cs:__imp_RtlDeleteCriticalSection
0x18001d3d3  lea     rcx, ?gcsDManipHook@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d3da  call    cs:__imp_RtlDeleteCriticalSection
0x18001d3e0  lea     rcx, ?gcsMPH@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d3e7  call    cs:__imp_RtlDeleteCriticalSection
0x18001d3ed  lea     rcx, ?gcsClassRegister@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d3f4  call    cs:__imp_RtlDeleteCriticalSection
0x18001d3fa  lea     rcx, ?gcsAvrt@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001d401  call    cs:__imp_RtlDeleteCriticalSection
0x18001d407  lea     rcx, stru_1800C9C80; struct tagUMHANDLELIST *
0x18001d40e  call    ?UninitializeUMHandleList@@YAXPEAUtagUMHANDLELIST@@@Z; UninitializeUMHandleList(tagUMHANDLELIST *)
0x18001d413  lea     rcx, CriticalSection; struct tagUMHANDLELIST *
0x18001d41a  call    ?UninitializeUMHandleList@@YAXPEAUtagUMHANDLELIST@@@Z; UninitializeUMHandleList(tagUMHANDLELIST *)
0x18001d41f  call    WppCleanupUm
0x18001d424  lea     rcx, dword_1800C87A8
0x18001d42b  call    TraceLoggingUnregister_EventUnregister
0x18001d430  lea     rcx, dword_1800C8770
0x18001d437  call    TraceLoggingUnregister_EventUnregister
0x18001d43c  lea     rcx, qword_1800C8738
0x18001d443  call    TraceLoggingUnregister_EventUnregister
0x18001d448  mov     rcx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001d44f  test    rcx, rcx
0x18001d452  jz      short loc_18001D468
0x18001d454  mov     rcx, [rcx+8]; lpMem
0x18001d458  test    rcx, rcx
0x18001d45b  jnz     loc_18001DAA0
0x18001d461  mov     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, r12; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001d468  mov     rcx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001d46f  test    rcx, rcx
0x18001d472  jz      loc_18001D821
0x18001d478  call    ??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)
0x18001d47d  mov     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r12; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001d484  jmp     loc_18001D821
0x18001d489  lea     rcx, CriticalSection; CriticalSection
0x18001d490  mov     cs:dword_1800C9CC0, 1
0x18001d49a  call    cs:__imp_RtlInitializeCriticalSection
0x18001d4a0  test    eax, eax
0x18001d4a2  js      loc_18001D69A
0x18001d4a8  xor     r9d, r9d; ReturnLength
0x18001d4ab  mov     cs:dword_1800C9C70, 1
0x18001d4b5  lea     rdx, [rbp+460h+SystemInformation]; SystemInformation
0x18001d4bc  xor     ecx, ecx; SystemInformationClass
0x18001d4be  lea     r8d, [r9+40h]; SystemInformationLength
0x18001d4c2  call    cs:__imp_NtQuerySystemInformation
0x18001d4c8  test    eax, eax
0x18001d4ca  js      loc_18001D2DE
0x18001d4d0  mov     rax, [rbp+460h+var_278]
0x18001d4d7  mov     cs:gHighestUserAddress, rax
0x18001d4de  call    ?InitializeNtdllUserPfn@@YAHXZ; InitializeNtdllUserPfn(void)
0x18001d4e3  test    eax, eax
0x18001d4e5  jz      loc_18001D2DE
0x18001d4eb  mov     rax, gs:60h
0x18001d4f4  lea     rbx, gSharedInfo
0x18001d4fb  test    byte ptr [rax+3], 2
0x18001d4ff  jnz     loc_18001D94E
0x18001d505  call    cs:__imp_WTSGetServiceSessionId
0x18001d50b  lea     rcx, ObjectDirectory; "\\Windows"
0x18001d512  cmp     r14d, eax
0x18001d515  jnz     loc_18001D989
0x18001d51b  lea     rax, gfServerProcess
0x18001d522  mov     r9d, 248h; ConnectionInfoSize
0x18001d528  lea     r8, [rsp+560h+ConnectionInfo]; ConnectionInfo
0x18001d52d  mov     [rsp+560h+ServerToServerCall], rax; ServerToServerCall
0x18001d532  mov     edx, 3; ServerId
0x18001d537  call    cs:__imp_CsrClientConnectToServer
0x18001d53d  test    eax, eax
0x18001d53f  js      loc_18001D2DE
0x18001d545  cmp     cs:gfServerProcess, r12d
0x18001d54c  mov     edi, 80h
0x18001d551  lea     r14d, [rdi-7Ch]
0x18001d555  jnz     loc_18001D924
0x18001d55b  mov     rax, gs:60h
0x18001d564  test    byte ptr [rax+3], 2
0x18001d568  jnz     loc_18001D9BE
0x18001d56e  mov     rax, rbx
0x18001d571  lea     rcx, [rsp+560h+var_4F8]
0x18001d576  mov     rdx, r14
0x18001d579  movups  xmm0, xmmword ptr [rcx]
0x18001d57c  movups  xmm1, xmmword ptr [rcx+10h]
0x18001d580  movups  xmmword ptr [rax], xmm0
0x18001d583  movups  xmm0, xmmword ptr [rcx+20h]
0x18001d587  movups  xmmword ptr [rax+10h], xmm1
0x18001d58b  movups  xmm1, xmmword ptr [rcx+30h]
0x18001d58f  movups  xmmword ptr [rax+20h], xmm0
0x18001d593  movups  xmm0, xmmword ptr [rcx+40h]
0x18001d597  movups  xmmword ptr [rax+30h], xmm1
0x18001d59b  movups  xmm1, xmmword ptr [rcx+50h]
0x18001d59f  movups  xmmword ptr [rax+40h], xmm0
0x18001d5a3  movups  xmm0, xmmword ptr [rcx+60h]
0x18001d5a7  movups  xmmword ptr [rax+50h], xmm1
0x18001d5ab  movups  xmm1, xmmword ptr [rcx+70h]
0x18001d5af  add     rcx, rdi
0x18001d5b2  movups  xmmword ptr [rax+60h], xmm0
0x18001d5b6  movups  xmmword ptr [rax+70h], xmm1
0x18001d5ba  add     rax, rdi
0x18001d5bd  sub     rdx, 1
0x18001d5c1  jnz     short loc_18001D579
0x18001d5c3  movups  xmm0, xmmword ptr [rcx]
0x18001d5c6  movups  xmm1, xmmword ptr [rcx+10h]
0x18001d5ca  movups  xmmword ptr [rax], xmm0
0x18001d5cd  movups  xmm0, xmmword ptr [rcx+20h]
0x18001d5d1  movups  xmmword ptr [rax+10h], xmm1
0x18001d5d5  movups  xmm1, xmmword ptr [rcx+30h]
0x18001d5d9  movups  xmmword ptr [rax+20h], xmm0
0x18001d5dd  movups  xmmword ptr [rax+30h], xmm1
0x18001d5e1  mov     rax, cs:gSharedInfo
0x18001d5e8  mov     rdx, r12
0x18001d5eb  mov     cs:gpsi, rax
0x18001d5f2  test    [rax], r14b
0x18001d5f5  jnz     loc_18001D83F
0x18001d5fb  mov     rax, cs:off_1800C85F0
0x18001d602  mov     rcx, rbx
0x18001d605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d60a  mov     rax, gs:60h
0x18001d613  lea     rbx, apfnDispatch
0x18001d61a  lea     rcx, WaitForInputIdle
0x18001d621  mov     [rax+58h], rbx
0x18001d625  mov     rax, gs:60h
0x18001d62e  mov     [rax+230h], r12
0x18001d635  call    cs:__imp_RegisterWaitForInputIdle
0x18001d63b  mov     cs:hmodUser, r15
0x18001d642  mov     rax, gs:60h
0x18001d64b  cmp     cs:?g_systemCallFilterId@@3KA, 7; ulong g_systemCallFilterId
0x18001d652  mov     rcx, [rax+30h]; unsigned int *
0x18001d656  mov     cs:pUserHeap, rcx
0x18001d65d  jz      loc_18001D9EE
0x18001d663  cmp     cs:?g_systemCallFilterId@@3KA, 5; ulong g_systemCallFilterId
0x18001d66a  jnz     short loc_18001D6A6
0x18001d66c  mov     rcx, cs:pUserHeap; HeapHandle
0x18001d673  xor     edx, edx; Flags
0x18001d675  mov     r8d, 460h; Size
0x18001d67b  call    cs:__imp_RtlAllocateHeap
0x18001d681  mov     rdx, rax
0x18001d684  test    rax, rax
0x18001d687  jz      loc_18001D2DE
0x18001d68d  mov     rcx, rax
0x18001d690  mov     eax, 8
0x18001d695  jmp     loc_180099FA6
0x18001d69a  mov     cs:dword_1800C9C70, r12d
0x18001d6a1  jmp     loc_18001D2DE
0x18001d6a6  cmp     cs:gfServerProcess, r12d
0x18001d6ad  jz      loc_18001D86F
0x18001d6b3  mov     eax, r12d
0x18001d6b6  or      cs:?gdwRegisteredClassesMask@@3KA, 0FFFFh; ulong gdwRegisteredClassesMask
0x18001d6c0  lea     rcx, [rsp+560h+var_51C]
0x18001d6c5  mov     cs:?gfEMIEnable@@3HA, eax; int gfEMIEnable
0x18001d6cb  call    cs:__imp_RtlQueryElevationFlags
0x18001d6d1  test    eax, eax
0x18001d6d3  js      short loc_18001D6E0
0x18001d6d5  test    byte ptr [rsp+560h+var_51C], 1
0x18001d6da  jz      loc_18001DA30
0x18001d6e0  lea     rcx, dword_1800C87A8; CallbackContext
0x18001d6e7  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001d6ec  lea     rcx, dword_1800C8770; CallbackContext
0x18001d6f3  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001d6f8  lea     rcx, qword_1800C8738; CallbackContext
0x18001d6ff  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001d704  lea     rax, WPP_ThisDir_CTLGUID_NtUserTraceGuid
0x18001d70b  mov     cs:qword_1800C9B18, r12
0x18001d712  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001d719  lea     rax, WPP_MAIN_CB
0x18001d720  mov     cs:WPP_GLOBAL_Control, rax
0x18001d727  mov     cs:WPP_MAIN_CB, r12
0x18001d72e  mov     cs:qword_1800C9B20, 1
0x18001d739  call    WppInitUm
0x18001d73e  lea     rax, ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d745  xor     ecx, ecx
  ... truncated ...
```
