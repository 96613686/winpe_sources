# SamIInitialize

- ea: `0x1800888c0`
- end: `0x180089405`
- name: `SamIInitialize`
- size: `2885`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180012a28`
- `0x18001f900`
- `0x180021400`
- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x1800378ac`
- `0x180039174`
- `0x180039ae0`
- `0x180053030`
- `0x18006e734`
- `0x180072b30`
- `0x1800730cc`
- `0x180073ce4`
- `0x180075a5c`
- `0x180076438`
- `0x1800781a0`
- `0x1800792dc`
- `0x180079428`
- `0x1800799a8`
- `0x18007b7d4`
- `0x18007bf14`
- `0x18007c584`
- `0x18007c768`
- `0x180088620`
- `0x1800888c0`
- `0x1800894a0`
- `0x18008f330`
- `0x18009373c`
- `0x1800975e0`
- `0x180098c94`
- `0x1800ac464`
- `0x1800b9c94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088a5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088a5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089276`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x180088a86`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x180088a86`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008926b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008926b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800892b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800892b8`
- `ntdll!RtlInitializeCriticalSection` at `0x1800889a9`
- `ntdll!RtlInitializeCriticalSection` at `0x1800889e4`
- `ntdll!RtlInitializeCriticalSection` at `0x1800889a9`
- `ntdll!RtlInitializeCriticalSection` at `0x1800889e4`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800889d0`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800889d0`
- `ntdll!RtlAllocateHeap` at `0x180088901`
- `ntdll!RtlAllocateHeap` at `0x180088901`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x180088a3d`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x180088a3d`
- `LSASRV!LsaISafeMode` at `0x180088cc7`
- `LSASRV!LsaISafeMode` at `0x180088f0c`
- `LSASRV!LsaISafeMode` at `0x180088f3b`
- `LSASRV!LsaISafeMode` at `0x1800892be`
- `LSASRV!LsaISafeMode` at `0x180088cc7`
- `LSASRV!LsaISafeMode` at `0x180088f0c`
- `LSASRV!LsaISafeMode` at `0x180088f3b`
- `LSASRV!LsaISafeMode` at `0x1800892be`
- `LSASRV!LsaIRegisterPolicyChangeNotificationCallback` at `0x180088ae5`
- `LSASRV!LsaIRegisterPolicyChangeNotificationCallback` at `0x180088ae5`
- `LSASRV!LsaIRegisterNotification` at `0x180088b60`
- `LSASRV!LsaIRegisterNotification` at `0x1800892e9`
- `LSASRV!LsaIRegisterNotification` at `0x180088b60`
- `LSASRV!LsaIRegisterNotification` at `0x1800892e9`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtPerformPromotePhase2` at `0x180089026`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtPerformPromotePhase2` at `0x180089026`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSignalStart` at `0x180089245`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSignalStart` at `0x180089245`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtCacheComputerObject` at `0x18008918d`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtCacheComputerObject` at `0x18008918d`

## string_xrefs

- `0x180088b98`: `SampInitAliasNameCache`
- `0x180088c89`: `SampInitializeSamKeyRegistryWatch`
- `0x180089117`: `SampApplyDomainUpdatesForAllDomains`
- `0x180089132`: `SampInitializeComponentRequestedUpdates`
- `0x1800891c0`: `SampExtCacheComputerObjectDs`
- `0x180089225`: `SampRODCRegistryWatch`
- `0x1800892a5`: `CreateThread(SampInitializeTrace)`

## pseudocode

```c
__int64 SamIInitialize()
{
  PUNICODE_STRING v0; // rcx
  unsigned int v1; // ebx
  int v2; // eax
  int v3; // edi
  DWORD LastError; // eax
  DWORD v5; // eax
  __int64 v6; // rdx
  PUNICODE_STRING v7; // rcx
  int v8; // eax
  PUNICODE_STRING v9; // rax
  int inited; // eax
  const char *v11; // rdx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  PUNICODE_STRING v19; // rcx
  int v20; // eax
  unsigned int v21; // ebx
  PUNICODE_STRING v22; // rcx
  int v23; // ebx
  int v24; // eax
  const char *v25; // rsi
  char v26; // al
  const char *v27; // r9
  __int64 v28; // rdx
  PUNICODE_STRING v29; // rcx
  unsigned int v30; // edi
  int v31; // eax
  unsigned int v32; // ebx
  const char *v33; // rdx
  int v34; // eax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  int v39; // eax
  int v40; // ebx
  int v41; // eax
  unsigned int v42; // ebx
  HANDLE v43; // rax
  DWORD v44; // eax
  DWORD v45; // ebx
  struct _SAMP_INIT_ERROR_INFO *v46; // rdx
  unsigned int v47; // ebx
  struct _SAMP_INIT_ERROR_INFO *v48; // rdx
  PUNICODE_STRING v49; // rcx
  PUNICODE_STRING v50; // rcx
  unsigned __int8 v52; // [rsp+90h] [rbp+48h] BYREF
  DWORD ThreadId; // [rsp+98h] [rbp+50h] BYREF
  unsigned int v54; // [rsp+A0h] [rbp+58h] BYREF
  unsigned int v55; // [rsp+A8h] [rbp+60h] BYREF

  v55 = 0;
  v52 = 0;
  SampErrorHistoryCount = 0;
  LOBYTE(ThreadId) = 0;
  gpSampErrorHistory = (struct _SAMP_INIT_ERROR_INFO *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x320u);
  v0 = WPP_GLOBAL_Control;
  v1 = gpSampErrorHistory == 0 ? 0xC0000017 : 0;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      228,
      WPP_6405431812663459a7a3c2922bf567cd_Traceguids,
      v1,
      gpSampErrorHistory == 0 ? 0xC0000017 : 0);
    v0 = WPP_GLOBAL_Control;
  }
  if ( (*(_BYTE *)(&v0[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v0[4].Length) >= 4u )
    WPP_SF_d(v0[3].Buffer, 37, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v1);
  SamIInitializeWPPAndAutoLoggerSession();
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 38, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
  RtlInitializeCriticalSection(&stru_1800F0CA0);
  RtlInitializeGenericTableAvl(&stru_1800F0CC8, compareLists, allocateEvntlogMap, freeEvntlogMap, 0);
  byte_1800F0D30 = 1;
  RtlInitializeCriticalSection(&g_SampEventProviderRegistrationCS);
  SafeAllocaInitialize();
  v2 = SampInitialize(&v55);
  v3 = v2;
  if ( v2 < 0 )
    SampSetErrorInfo((unsigned int)v2, "SampInitialize");
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 39, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v3);
  if ( !SetConsoleCtrlHandler(SampShutdownNotification, 1)
    && (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 3u )
  {
    LastError = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 40, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, LastError);
  }
  if ( !SetProcessShutdownParameters(0x1E1u, 1u)
    && (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 3u )
  {
    v5 = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 41, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v5);
  }
  if ( (unsigned __int8)SampUsingDsData() )
    goto LABEL_29;
  if ( v3 < 0 )
  {
LABEL_51:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_92;
  }
  v8 = LsaIRegisterPolicyChangeNotificationCallback(SampMachineNameChangeCallBack, 2);
  v3 = v8;
  if ( v8 < 0 )
    SampSetErrorInfo((unsigned int)v8, "LsaIRegisterPolicyChangeNotificationCallback(SampMachineNameChangeCallBack)");
  v9 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 42, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v3);
LABEL_29:
    v9 = WPP_GLOBAL_Control;
  }
  if ( v3 < 0 )
    goto LABEL_92;
  if ( (unsigned __int8)SampUsingDsData() == 1 )
  {
    LsaIRegisterNotification(SampAlDelayedBuildAliasInformation, 0, 1, 0, 2, 150, 0);
    inited = SampInitAliasNameCache();
    v3 = inited;
    if ( inited < 0 )
    {
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control[3].Buffer,
          43,
          WPP_6405431812663459a7a3c2922bf567cd_Traceguids,
          (unsigned int)inited);
      v11 = "SampInitAliasNameCache";
LABEL_50:
      SampSetErrorInfo((unsigned int)v3, v11);
      goto LABEL_51;
    }
  }
  else
  {
    v12 = SampAlBuildAliasInformation();
    v13 = v12;
    if ( v12 < 0 )
    {
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 3u )
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 44, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v12);
      SampSetErrorInfo(v13, "SampAlBuildAliasInformation");
    }
  }
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 45, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
  v14 = SampUpgradeSamDatabase(v55);
  v3 = v14;
  if ( v14 < 0 )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 46, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v14);
    v11 = "SampUpgradeSamDatabase";
    goto LABEL_50;
  }
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 47, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
  v15 = SampInitializeSamKeyRegistryWatch();
  v16 = v15;
  if ( v15 < 0 )
  {
    SampSetErrorInfo((unsigned int)v15, "SampInitializeSamKeyRegistryWatch");
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 48, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v16);
  }
  if ( (unsigned int)ByPassCTAPolicy() || (unsigned __int8)LsaISafeMode() )
    goto LABEL_68;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 49, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
  v17 = SampInitializeCAMSupport();
  v18 = v17;
  if ( v17 >= 0 )
    goto LABEL_68;
  SampSetErrorInfo((unsigned int)v17, "SampInitializeCAMSupport");
  v19 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 )
    goto LABEL_72;
  if ( HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 50, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v18);
LABEL_68:
    v19 = WPP_GLOBAL_Control;
  }
  if ( (*(_BYTE *)(&v19[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v19[4].Length) >= 4u )
    WPP_SF_(v19[3].Buffer, 51, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
LABEL_72:
  v20 = SampInitializeLAPS();
  v21 = v20;
  if ( v20 >= 0 )
  {
LABEL_76:
    v22 = WPP_GLOBAL_Control;
    goto LABEL_77;
  }
  SampSetErrorInfo((unsigned int)v20, "SampInitializeLAPS");
  v22 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 )
    goto LABEL_80;
  if ( HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 52, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v21);
    goto LABEL_76;
  }
LABEL_77:
  if ( (*(_BYTE *)(&v22[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v22[4].Length) >= 4u )
    WPP_SF_(v22[3].Buffer, 53, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
LABEL_80:
  v23 = SAAManager::StaticCreate((struct SAAManager **)v22);
  if ( v23 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_85;
    }
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 72, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids, (unsigned int)v23);
  }
  v9 = WPP_GLOBAL_Control;
LABEL_85:
  if ( (*(_DWORD *)(&v9[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(v9[3].Buffer, 73, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids, (unsigned int)v23, v23);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v23 < 0 )
  {
    SampSetErrorInfo((unsigned int)v23, "SampInitializeShadowAdminAccounts");
    v9 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 54, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v23);
      v9 = WPP_GLOBAL_Control;
    }
  }
  v3 = 0;
LABEL_92:
  SampServiceState = 2;
  if ( (*(_BYTE *)(&v9[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v9[4].Length) >= 4u )
  {
    WPP_SF_(v9[3].Buffer, 55, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v3 >= 0 )
  {
    v24 = SampPerformWAUUpgradeIfNecessary(&v52);
    v3 = v24;
    if ( v24 >= 0 )
    {
      v9 = WPP_GLOBAL_Control;
    }
    else
    {
      SampSetErrorInfo((unsigned int)v24, "SampPerformWAUUpgradeIfNecessary");
      v9 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 56, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v3);
        v9 = WPP_GLOBAL_Control;
      }
      v3 = 0;
    }
  }
  v25 = "TRUE";
  if ( (*(_BYTE *)(&v9[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v9[4].Length) >= 4u )
  {
    v26 = LsaISafeMode();
    v27 = "TRUE";
    if ( !v26 )
      v27 = "FALSE";
    WPP_SF_s(WPP_GLOBAL_Control[3].Buffer, 57, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v27);
  }
  if ( v3 >= 0 )
  {
    if ( (unsigned __int8)LsaISafeMode() )
    {
LABEL_152:
      v36 = SampInitializeComponentRequestedUpdates();
      v3 = v36;
      if ( v36 < 0 )
      {
        SampSetErrorInfo((unsigned int)v36, "SampInitializeComponentRequestedUpdates");
        v7 = WPP_GLOBAL_Control;
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 64, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v3);
        }
        v3 = 0;
      }
      goto LABEL_157;
    }
    v54 = 0;
    if ( (unsigned int)SampIsRebootAfterPromotion(&v54) )
    {
      v29 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 4u )
      {
        v30 = v54;
        goto LABEL_121;
      }
      v30 = v54;
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 58, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v54);
    }
    else
    {
      if ( (unsigned __int8)SampUsingDsData() && SampIsSetupInProgress((unsigned __int8 *)&ThreadId) && (_BYTE)ThreadId )
      {
        v30 = 1024;
        v29 = WPP_GLOBAL_Control;
        if ( !*((_BYTE *)SampDefinedDomains + 5378) )
          goto LABEL_122;
        v30 = 1025;
LABEL_121:
        if ( !v30 )
          goto LABEL_145;
LABEL_122:
        if ( (*(_BYTE *)(&v29[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v29[4].Length) >= 4u )
          WPP_SF_d(v29[3].Buffer, 59, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v30);
        if ( (v30 & 0x400) != 0 || (v30 & 0xC0) != 0 )
        {
          v34 = SampPerformInternalUpgradeDemotePhase2(v30, 0);
          v32 = v34;
          if ( v34 >= 0 )
            goto LABEL_142;
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control[3].Buffer,
              60,
              WPP_6405431812663459a7a3c2922bf567cd_Traceguids,
              (unsigned int)v34);
          }
          v33 = "SampPerformInternalUpgradeDemotePhase2";
        }
        else
        {
          v31 = SampShouldCallNtdsaApiSet();
          v32 = v31;
          if ( v31 == -1073741637 )
          {
            v32 = 0;
LABEL_142:
            if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
              && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 62, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v32);
            }
LABEL_145:
            LOBYTE(v28) = v52;
            v35 = SampApplyDomainUpdatesForAllDomains(0, v28);
            v3 = v35;
            if ( v35 < 0 )
            {
              if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
                && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
              {
                if ( !v52 )
                  v25 = "FALSE";
                WPP_SF_sD(
                  WPP_GLOBAL_Control[3].Buffer,
                  63,
                  (unsigned int)WPP_6405431812663459a7a3c2922bf567cd_Traceguids,
                  (_DWORD)v25,
                  v35);
              }
              SampSetErrorInfo((unsigned int)v3, "SampApplyDomainUpdatesForAllDomains");
              goto LABEL_157;
            }
            goto LABEL_152;
          }
          if ( v31 >= 0 )
            v32 = NtdsaExtPerformPromotePhase2(v30, 0);
          if ( (v32 & 0x80000000) == 0 )
            goto LABEL_142;
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 61, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v32);
          }
          v33 = "SampExtPerformPromotePhase2Ds";
        }
        SampSetErrorInfo(v32, v33);
        goto LABEL_142;
      }
      v30 = v54;
    }
    v29 = WPP_GLOBAL_Control;
    goto LABEL_121;
  }
LABEL_157:
  if ( (unsigned __int8)SampDsIsRunning(v7, v6) )
  {
    if ( v3 >= 0 )
    {
      v39 = SampShouldCallNtdsaApiSet();
      v40 = v39;
      if ( v39 != -1073741637 )
      {
        if ( v39 >= 0 )
          v40 = NtdsaExtCacheComputerObject();
        if ( v40 < 0 )
        {
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control[3].Buffer,
              65,
              WPP_6405431812663459a7a3c2922bf567cd_Traceguids,
              (unsigned int)v40);
          }
          SampSetErrorInfo((unsigned int)v40, "SampExtCacheComputerObjectDs");
        }
      }
      goto LABEL_168;
    }
LABEL_186:
    SampSetErrorInfo((unsigned int)v3, "SamIInitialize - final processing");
    goto LABEL_187;
  }
  if ( v3 < 0 )
    goto LABEL_186;
LABEL_168:
  if ( SampUseDsData )
  {
    if ( (SampQueryCapabilities(0, 0) & 5) == 1 )
    {
      v41 = SampRODCRegistryWatch(0);
      v42 = v41;
      if ( v41 < 0 )
      {
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 66, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v41);
        }
        SampSetErrorInfo(v42, "SampRODCRegistryWatch");
      }
    }
  }
  if ( (unsigned __int8)SampDsIsRunning(v38, v37) && (int)SampShouldCallNtdsaApiSet() >= 0 )
    NtdsaExtSignalStart();
  ThreadId = 0;
  v43 = CreateThread(0, 0, SampInitializeTrace, 0, 0, &ThreadId);
  if ( v43 )
  {
    CloseHandle(v43);
  }
  else
  {
    v44 = GetLastError();
    v45 = v44;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 67, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v44);
    SampSetErrorInfo(v45, "CreateThread(SampInitializeTrace)");
  }
  if ( (unsigned __int8)LsaISafeMode() )
    LsaIRegisterNotification(SampEventLogSafeModeBoot, 0, 1, 0, 2, 120, 0);
LABEL_187:
  v47 = SampErrorHistoryCount;
  SampLogServiceStartupErrorsToEventLog(v3, v46, SampErrorHistoryCount);
  SampTraceServiceStartupErrors(v3, v48, v47);
  if ( v3 >= 0 )
    goto LABEL_197;
  v49 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 )
  {
    if ( HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 68, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v3);
      v49 = WPP_GLOBAL_Control;
    }
    if ( (*(_BYTE *)(&v49[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v49[4].Length) >= 2u )
      WPP_SF_(v49[3].Buffer, 69, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
  }
  SampPerformInitializeFailurePopup(v3);
  v50 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 )
  {
    if ( HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
LABEL_198:
      if ( (*(_BYTE *)(&v50[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v50[4].Length) >= 4u )
      {
        WPP_SF_d(v50[3].Buffer, 71, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v3);
        v50 = WPP_GLOBAL_Control;
      }
      goto LABEL_201;
    }
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 70, WPP_6405431812663459a7a3c2922bf567cd_Traceguids);
LABEL_197:
    v50 = WPP_GLOBAL_Control;
    goto LABEL_198;
  }
LABEL_201:
  if ( v3 >= 0 )
  {
    SamITeardownAutoLoggerSession();
    v50 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v50[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v50[3].Buffer, 72, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)v3, v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800888c0  push    rbp
0x1800888c2  push    rbx
0x1800888c3  push    rsi
0x1800888c4  push    rdi
0x1800888c5  push    r12
0x1800888c7  push    r13
0x1800888c9  push    r14
0x1800888cb  push    r15
0x1800888cd  mov     rbp, rsp
0x1800888d0  sub     rsp, 48h
0x1800888d4  xor     r14d, r14d
0x1800888d7  mov     r8d, 320h; Size
0x1800888dd  mov     [rbp+arg_18], r14d
0x1800888e1  mov     [rbp+arg_0], r14b
0x1800888e5  mov     cs:?SampErrorHistoryCount@@3KA, r14d; ulong SampErrorHistoryCount
0x1800888ec  mov     rcx, gs:60h
0x1800888f5  lea     edx, [r14+8]; Flags
0x1800888f9  mov     byte ptr [rbp+ThreadId], r14b
0x1800888fd  mov     rcx, [rcx+30h]; HeapHandle
0x180088901  call    cs:__imp_RtlAllocateHeap
0x180088907  mov     cs:?gpSampErrorHistory@@3PEAU_SAMP_INIT_ERROR_INFO@@EA, rax; _SAMP_INIT_ERROR_INFO * gpSampErrorHistory
0x18008890e  mov     rcx, cs:WPP_GLOBAL_Control
0x180088915  lea     r12, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18008891c  neg     rax
0x18008891f  sbb     ebx, ebx
0x180088921  not     ebx
0x180088923  and     ebx, 0C0000017h
0x180088929  test    dword ptr [rcx+44h], 20000h
0x180088930  jz      short loc_180088951
0x180088932  mov     rcx, [rcx+38h]
0x180088936  mov     edx, 0E4h
0x18008893b  mov     r9d, ebx
0x18008893e  mov     dword ptr [rsp+48h+TableContext], ebx
0x180088942  mov     r8, r12
0x180088945  call    WPP_SF_Dd
0x18008894a  mov     rcx, cs:WPP_GLOBAL_Control
0x180088951  mov     r15d, 1
0x180088957  mov     sil, 4
0x18008895a  test    [rcx+44h], r15b
0x18008895e  jz      short loc_180088979
0x180088960  cmp     [rcx+41h], sil
0x180088964  jb      short loc_180088979
0x180088966  mov     rcx, [rcx+38h]
0x18008896a  lea     edx, [r15+24h]
0x18008896e  mov     r9d, ebx
0x180088971  mov     r8, r12
0x180088974  call    WPP_SF_d
0x180088979  call    ?SamIInitializeWPPAndAutoLoggerSession@@YAXXZ; SamIInitializeWPPAndAutoLoggerSession(void)
0x18008897e  mov     rcx, cs:WPP_GLOBAL_Control
0x180088985  test    [rcx+44h], r15b
0x180088989  jz      short loc_1800889A2
0x18008898b  cmp     [rcx+41h], sil
0x18008898f  jb      short loc_1800889A2
0x180088991  mov     rcx, [rcx+38h]
0x180088995  mov     edx, 26h ; '&'
0x18008899a  mov     r8, r12
0x18008899d  call    WPP_SF_
0x1800889a2  lea     rcx, stru_1800F0CA0; CriticalSection
0x1800889a9  call    cs:__imp_RtlInitializeCriticalSection
0x1800889af  lea     r9, freeEvntlogMap; FreeRoutine
0x1800889b6  mov     [rsp+48h+TableContext], r14; TableContext
0x1800889bb  lea     r8, allocateEvntlogMap; AllocateRoutine
0x1800889c2  lea     rdx, compareLists; CompareRoutine
0x1800889c9  lea     rcx, stru_1800F0CC8; Table
0x1800889d0  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800889d6  lea     rcx, ?g_SampEventProviderRegistrationCS@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800889dd  mov     cs:byte_1800F0D30, r15b
0x1800889e4  call    cs:__imp_RtlInitializeCriticalSection
0x1800889ea  call    SafeAllocaInitialize
0x1800889ef  lea     rcx, [rbp+arg_18]; unsigned int *
0x1800889f3  call    ?SampInitialize@@YAJPEAK@Z; SampInitialize(ulong *)
0x1800889f8  mov     edi, eax
0x1800889fa  test    eax, eax
0x1800889fc  jns     short loc_180088A0C
0x1800889fe  lea     rdx, aSampinitialize_3; "SampInitialize"
0x180088a05  mov     ecx, eax
0x180088a07  call    SampSetErrorInfo
0x180088a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180088a13  test    [rcx+44h], r15b
0x180088a17  jz      short loc_180088A33
0x180088a19  cmp     [rcx+41h], sil
0x180088a1d  jb      short loc_180088A33
0x180088a1f  mov     rcx, [rcx+38h]
0x180088a23  mov     edx, 27h ; '''
0x180088a28  mov     r9d, edi
0x180088a2b  mov     r8, r12
0x180088a2e  call    WPP_SF_d
0x180088a33  mov     edx, r15d; Add
0x180088a36  lea     rcx, ?SampShutdownNotification@@YAHK@Z; HandlerRoutine
0x180088a3d  call    cs:__imp_SetConsoleCtrlHandler
0x180088a43  mov     sil, 3
0x180088a46  test    eax, eax
0x180088a48  jnz     short loc_180088A7E
0x180088a4a  mov     rax, cs:WPP_GLOBAL_Control
0x180088a51  test    [rax+44h], r15b
0x180088a55  jz      short loc_180088A7E
0x180088a57  cmp     [rax+41h], sil
0x180088a5b  jb      short loc_180088A7E
0x180088a5d  call    cs:__imp_GetLastError
0x180088a63  mov     rcx, cs:WPP_GLOBAL_Control
0x180088a6a  mov     edx, 28h ; '('
0x180088a6f  mov     r9d, eax
0x180088a72  mov     r8, r12
0x180088a75  mov     rcx, [rcx+38h]
0x180088a79  call    WPP_SF_d
0x180088a7e  mov     edx, r15d; dwFlags
0x180088a81  mov     ecx, 1E1h; dwLevel
0x180088a86  call    cs:__imp_SetProcessShutdownParameters
0x180088a8c  test    eax, eax
0x180088a8e  jnz     short loc_180088AC4
0x180088a90  mov     rax, cs:WPP_GLOBAL_Control
0x180088a97  test    [rax+44h], r15b
0x180088a9b  jz      short loc_180088AC4
0x180088a9d  cmp     [rax+41h], sil
0x180088aa1  jb      short loc_180088AC4
0x180088aa3  call    cs:__imp_GetLastError
0x180088aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180088ab0  mov     edx, 29h ; ')'
0x180088ab5  mov     r9d, eax
0x180088ab8  mov     r8, r12
0x180088abb  mov     rcx, [rcx+38h]
0x180088abf  call    WPP_SF_d
0x180088ac4  call    SampUsingDsData
0x180088ac9  mov     r13d, 2
0x180088acf  test    al, al
0x180088ad1  jnz     short loc_180088B26
0x180088ad3  test    edi, edi
0x180088ad5  js      loc_180088C4E
0x180088adb  mov     edx, r13d
0x180088ade  lea     rcx, ?SampMachineNameChangeCallBack@@YAXW4_POLICY_NOTIFICATION_INFORMATION_CLASS@@@Z; SampMachineNameChangeCallBack(_POLICY_NOTIFICATION_INFORMATION_CLASS)
0x180088ae5  call    cs:__imp_LsaIRegisterPolicyChangeNotificationCallback
0x180088aeb  mov     edi, eax
0x180088aed  test    eax, eax
0x180088aef  jns     short loc_180088AFF
0x180088af1  lea     rdx, aLsairegisterpo; "LsaIRegisterPolicyChangeNotificationCal"...
0x180088af8  mov     ecx, eax
0x180088afa  call    SampSetErrorInfo
0x180088aff  mov     rax, cs:WPP_GLOBAL_Control
0x180088b06  test    [rax+44h], r15b
0x180088b0a  jz      short loc_180088B2D
0x180088b0c  cmp     byte ptr [rax+41h], 4
0x180088b10  jb      short loc_180088B2D
0x180088b12  mov     rcx, [rax+38h]
0x180088b16  mov     edx, 2Ah ; '*'
0x180088b1b  mov     r9d, edi
0x180088b1e  mov     r8, r12
0x180088b21  call    WPP_SF_d
0x180088b26  mov     rax, cs:WPP_GLOBAL_Control
0x180088b2d  test    edi, edi
0x180088b2f  js      loc_180088E6C
0x180088b35  call    SampUsingDsData
0x180088b3a  cmp     al, r15b
0x180088b3d  jnz     short loc_180088BA4
0x180088b3f  mov     [rsp+48h+var_18], r14
0x180088b44  lea     rcx, ?SampAlDelayedBuildAliasInformation@@YAJPEAX@Z; SampAlDelayedBuildAliasInformation(void *)
0x180088b4b  mov     dword ptr [rsp+48h+lpThreadId], 96h
0x180088b53  xor     r9d, r9d
0x180088b56  mov     r8d, r15d
0x180088b59  mov     dword ptr [rsp+48h+TableContext], r13d
0x180088b5e  xor     edx, edx
0x180088b60  call    cs:__imp_LsaIRegisterNotification
0x180088b66  call    ?SampInitAliasNameCache@@YAJXZ; SampInitAliasNameCache(void)
0x180088b6b  mov     edi, eax
0x180088b6d  test    eax, eax
0x180088b6f  jns     short loc_180088BE4
0x180088b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180088b78  test    [rcx+44h], r15b
0x180088b7c  jz      short loc_180088B98
0x180088b7e  cmp     [rcx+41h], r13b
0x180088b82  jb      short loc_180088B98
0x180088b84  mov     rcx, [rcx+38h]
0x180088b88  mov     edx, 2Bh ; '+'
0x180088b8d  mov     r9d, eax
0x180088b90  mov     r8, r12
0x180088b93  call    WPP_SF_d
0x180088b98  lea     rdx, aSampinitaliasn; "SampInitAliasNameCache"
0x180088b9f  jmp     loc_180088C47
0x180088ba4  call    ?SampAlBuildAliasInformation@@YAJXZ; SampAlBuildAliasInformation(void)
0x180088ba9  mov     ebx, eax
0x180088bab  test    eax, eax
0x180088bad  jns     short loc_180088BE4
0x180088baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180088bb6  test    [rcx+44h], r15b
0x180088bba  jz      short loc_180088BD6
0x180088bbc  cmp     [rcx+41h], sil
0x180088bc0  jb      short loc_180088BD6
0x180088bc2  mov     rcx, [rcx+38h]
0x180088bc6  mov     edx, 2Ch ; ','
0x180088bcb  mov     r9d, eax
0x180088bce  mov     r8, r12
0x180088bd1  call    WPP_SF_d
0x180088bd6  lea     rdx, aSampalbuildali; "SampAlBuildAliasInformation"
0x180088bdd  mov     ecx, ebx
0x180088bdf  call    SampSetErrorInfo
0x180088be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180088beb  mov     sil, 4
0x180088bee  test    [rcx+44h], r15b
0x180088bf2  jz      short loc_180088C0B
0x180088bf4  cmp     [rcx+41h], sil
0x180088bf8  jb      short loc_180088C0B
0x180088bfa  mov     rcx, [rcx+38h]
0x180088bfe  mov     edx, 2Dh ; '-'
0x180088c03  mov     r8, r12
0x180088c06  call    WPP_SF_
0x180088c0b  mov     ecx, [rbp+arg_18]; unsigned int
0x180088c0e  call    ?SampUpgradeSamDatabase@@YAJK@Z; SampUpgradeSamDatabase(ulong)
0x180088c13  mov     edi, eax
0x180088c15  test    eax, eax
0x180088c17  jns     short loc_180088C5A
0x180088c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180088c20  test    [rcx+44h], r15b
0x180088c24  jz      short loc_180088C40
0x180088c26  cmp     [rcx+41h], r13b
0x180088c2a  jb      short loc_180088C40
0x180088c2c  mov     rcx, [rcx+38h]
0x180088c30  mov     edx, 2Eh ; '.'
0x180088c35  mov     r9d, eax
0x180088c38  mov     r8, r12
0x180088c3b  call    WPP_SF_d
0x180088c40  lea     rdx, aSampupgradesam; "SampUpgradeSamDatabase"
0x180088c47  mov     ecx, edi
0x180088c49  call    SampSetErrorInfo
0x180088c4e  mov     rax, cs:WPP_GLOBAL_Control
0x180088c55  jmp     loc_180088E6C
0x180088c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180088c61  test    [rcx+44h], r15b
0x180088c65  jz      short loc_180088C7E
0x180088c67  cmp     [rcx+41h], sil
0x180088c6b  jb      short loc_180088C7E
0x180088c6d  mov     rcx, [rcx+38h]
0x180088c71  mov     edx, 2Fh ; '/'
0x180088c76  mov     r8, r12
0x180088c79  call    WPP_SF_
0x180088c7e  call    ?SampInitializeSamKeyRegistryWatch@@YAJXZ; SampInitializeSamKeyRegistryWatch(void)
0x180088c83  mov     ebx, eax
0x180088c85  test    eax, eax
0x180088c87  jns     short loc_180088CBE
0x180088c89  lea     rdx, aSampinitialize_1; "SampInitializeSamKeyRegistryWatch"
0x180088c90  mov     ecx, eax
0x180088c92  call    SampSetErrorInfo
0x180088c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180088c9e  test    [rcx+44h], r15b
0x180088ca2  jz      short loc_180088CBE
0x180088ca4  cmp     [rcx+41h], r13b
0x180088ca8  jb      short loc_180088CBE
0x180088caa  mov     rcx, [rcx+38h]
0x180088cae  mov     edx, 30h ; '0'
0x180088cb3  mov     r9d, ebx
0x180088cb6  mov     r8, r12
0x180088cb9  call    WPP_SF_d
0x180088cbe  call    ?ByPassCTAPolicy@@YAHXZ; ByPassCTAPolicy(void)
0x180088cc3  test    eax, eax
0x180088cc5  jnz     short loc_180088D35
0x180088cc7  call    cs:__imp_LsaISafeMode
0x180088ccd  test    al, al
0x180088ccf  jnz     short loc_180088D35
0x180088cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180088cd8  test    [rcx+44h], r15b
0x180088cdc  jz      short loc_180088CF5
0x180088cde  cmp     [rcx+41h], sil
0x180088ce2  jb      short loc_180088CF5
0x180088ce4  mov     rcx, [rcx+38h]
0x180088ce8  mov     edx, 31h ; '1'
0x180088ced  mov     r8, r12
0x180088cf0  call    WPP_SF_
0x180088cf5  call    ?SampInitializeCAMSupport@@YAJXZ; SampInitializeCAMSupport(void)
0x180088cfa  mov     ebx, eax
0x180088cfc  test    eax, eax
0x180088cfe  jns     short loc_180088D35
0x180088d00  lea     rdx, aSampinitialize_12; "SampInitializeCAMSupport"
0x180088d07  mov     ecx, eax
0x180088d09  call    SampSetErrorInfo
0x180088d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180088d15  test    [rcx+44h], r15b
0x180088d19  jz      short loc_180088D59
0x180088d1b  cmp     [rcx+41h], r13b
0x180088d1f  jb      short loc_180088D3C
0x180088d21  mov     rcx, [rcx+38h]
0x180088d25  mov     edx, 32h ; '2'
0x180088d2a  mov     r9d, ebx
0x180088d2d  mov     r8, r12
0x180088d30  call    WPP_SF_d
0x180088d35  mov     rcx, cs:WPP_GLOBAL_Control
0x180088d3c  test    [rcx+44h], r15b
0x180088d40  jz      short loc_180088D59
0x180088d42  cmp     [rcx+41h], sil
0x180088d46  jb      short loc_180088D59
0x180088d48  mov     rcx, [rcx+38h]
0x180088d4c  mov     edx, 33h ; '3'
0x180088d51  mov     r8, r12
0x180088d54  call    WPP_SF_
0x180088d59  call    ?SampInitializeLAPS@@YAJXZ; SampInitializeLAPS(void)
0x180088d5e  mov     ebx, eax
0x180088d60  test    eax, eax
0x180088d62  jns     short loc_180088D99
0x180088d64  lea     rdx, aSampinitialize_11; "SampInitializeLAPS"
0x180088d6b  mov     ecx, eax
0x180088d6d  call    SampSetErrorInfo
0x180088d72  mov     rcx, cs:WPP_GLOBAL_Control
0x180088d79  test    [rcx+44h], r15b
  ... truncated ...
```
