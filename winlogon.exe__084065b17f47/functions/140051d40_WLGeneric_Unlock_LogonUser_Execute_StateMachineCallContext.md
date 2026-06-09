# WLGeneric_Unlock_LogonUser_Execute(_StateMachineCallContext *)

- ea: `0x140051d40`
- end: `0x1400525fe`
- name: `?WLGeneric_Unlock_LogonUser_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `2238`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400057f4`
- `0x14001202c`
- `0x140013050`
- `0x140016f30`
- `0x1400374d4`
- `0x1400375a0`
- `0x140037608`
- `0x140037b00`
- `0x14003ba30`
- `0x14003bfec`
- `0x140041c34`
- `0x140041ddc`
- `0x14004327c`
- `0x140044830`
- `0x14004df08`
- `0x14004ed34`
- `0x140051d40`
- `0x140052604`
- `0x140052be8`
- `0x1400544e0`
- `0x140056348`
- `0x140059774`
- `0x14005dc80`
- `0x1400600a8`
- `0x1400608c4`
- `0x14007b75c`
- `0x14008b9f0`
- `0x14008c76c`
- `0x14009cc3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400520e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400520e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052514`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400520a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400520b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400520a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400520b3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400520d9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400520d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140052246`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140052246`
- `ext-ms-win-session-winsta-l1-1-0!WinStationTerminateGlassReplacementSession` at `0x14005248c`
- `ext-ms-win-session-winsta-l1-1-0!WinStationTerminateGlassReplacementSession` at `0x14005248c`
- `ext-ms-win-session-winsta-l1-1-2!WinStationPreCreateGlassReplacementSessionEx` at `0x140051ee8`
- `ext-ms-win-session-winsta-l1-1-2!WinStationPreCreateGlassReplacementSessionEx` at `0x140051ee8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSDisconnectSession` at `0x1400524ef`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSDisconnectSession` at `0x1400524ef`

## string_xrefs

- `0x140051e6e`: `%SYSTEMROOT%\System32\WinLogon.exe -UserSwitch`
- `0x1400525be`: `clientcore\ds\security\umstartup\winlogon\core\lock.cxx`
- `0x140051f03`: `winsta.dll`
- `0x140051f4e`: `winsta.dll`
- `0x1400524a3`: `winsta.dll`
- `0x140051f83`: `lsasrv.dll`
- `0x140051ffa`: `lsasrv.dll`
- `0x140052052`: `lsasrv.dll`

## pseudocode

```c
int __fastcall WLGeneric_Unlock_LogonUser_Execute(
        struct _StateMachineCallContext *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  CSession **v4; // r14
  int v5; // edi
  __int64 v6; // r12
  __int64 v7; // rax
  unsigned __int16 **v8; // rdx
  DWORD ComplexPassword; // ebx
  CUser *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  CSession *v13; // rax
  unsigned int v14; // edx
  __int64 v15; // r15
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // r9
  HANDLE CurrentProcess; // rbx
  void *v20; // rdi
  HANDLE v21; // rax
  DWORD v22; // eax
  unsigned __int16 *v23; // rdx
  unsigned __int16 *v25; // rbx
  __int64 v26; // rax
  unsigned int UserSwitchLogonInfoCollectedSyncEvent; // eax
  const unsigned __int16 *v28; // r13
  __int64 v29; // rax
  struct _MSV1_0_INTERACTIVE_PROFILE *v30; // r15
  CSession *v31; // rcx
  const unsigned __int16 *v32; // rdi
  struct _CRED_PROV_CREDENTIAL *v33; // r12
  unsigned __int16 *v34; // rdx
  DWORD LastError; // ebx
  __int64 v36; // r9
  DWORD v37; // eax
  CSession *v38; // rbx
  int IsBoundToConsole; // eax
  CSession *v40; // rdx
  int v41; // eax
  __int64 v42; // [rsp+0h] [rbp-188h] BYREF
  DWORD dwDesiredAccess[2]; // [rsp+20h] [rbp-168h]
  BOOL bInheritHandle[2]; // [rsp+28h] [rbp-160h]
  DWORD dwOptions[2]; // [rsp+30h] [rbp-158h]
  void *v46; // [rsp+38h] [rbp-150h]
  struct CGlobalStore::_SWITCH_USER_LOGON_INFO **v47; // [rsp+40h] [rbp-148h]
  int v48; // [rsp+50h] [rbp-138h]
  unsigned __int16 *v49; // [rsp+58h] [rbp-130h] BYREF
  __int64 v50; // [rsp+60h] [rbp-128h] BYREF
  HANDLE TargetHandle; // [rsp+68h] [rbp-120h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp-118h] BYREF
  _DWORD v53[4]; // [rsp+80h] [rbp-108h] BYREF
  __int64 v54; // [rsp+90h] [rbp-F8h]
  __int64 v55; // [rsp+98h] [rbp-F0h]
  __int128 v56; // [rsp+A0h] [rbp-E8h]
  __int128 v57; // [rsp+B0h] [rbp-D8h]
  __int128 v58; // [rsp+C0h] [rbp-C8h]
  int v59; // [rsp+D0h] [rbp-B8h]
  int v60; // [rsp+D4h] [rbp-B4h]
  unsigned __int16 *v61; // [rsp+D8h] [rbp-B0h]
  int v62; // [rsp+E0h] [rbp-A8h]
  LPWSTR v63; // [rsp+E8h] [rbp-A0h]
  unsigned int v64; // [rsp+F0h] [rbp-98h]
  __int64 v65; // [rsp+F8h] [rbp-90h]
  struct _MSV1_0_INTERACTIVE_PROFILE *v66; // [rsp+100h] [rbp-88h]
  int v67; // [rsp+108h] [rbp-80h]
  __int64 v68; // [rsp+110h] [rbp-78h]
  int v69; // [rsp+118h] [rbp-70h]
  struct _CRED_PROV_CREDENTIAL *v70; // [rsp+120h] [rbp-68h]
  __int64 *v71; // [rsp+130h] [rbp-58h]
  _BYTE v72[80]; // [rsp+138h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]
  unsigned int v74; // [rsp+190h] [rbp+8h] BYREF
  CSession *v75; // [rsp+198h] [rbp+10h] BYREF
  struct _CRED_PROV_CREDENTIAL *v76; // [rsp+1A0h] [rbp+18h] BYREF
  int v77; // [rsp+1A8h] [rbp+20h]

  v71 = &v42;
  v4 = (CSession **)*((_QWORD *)a1 + 1);
  v76 = (struct _CRED_PROV_CREDENTIAL *)*((_QWORD *)*v4 + 14);
  v5 = *(_DWORD *)v76 & 4;
  v77 = v5;
  v6 = -1;
  v74 = -1;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, a4);
  }
  v49 = 0;
  v7 = wil::out_param<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>(v72, &v49);
  ComplexPassword = SystemManagedAccountUtil::GenerateComplexPassword((SystemManagedAccountUtil *)(v7 + 8), v8);
  if ( (ComplexPassword & 0x1FFF0000) == 0x70000 )
    ComplexPassword = (unsigned __int16)ComplexPassword;
  v48 = ComplexPassword;
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>(v72);
  if ( ComplexPassword )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v11 = 109;
    goto LABEL_12;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v50);
  v13 = v4[2];
  bInheritHandle[0] = v5;
  dwDesiredAccess[0] = *((_DWORD *)v13 + 22);
  ComplexPassword = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &v50,
                      L"%ls %ls %ld %ld",
                      L"%SYSTEMROOT%\\System32\\WinLogon.exe -UserSwitch",
                      v49,
                      *(_QWORD *)dwDesiredAccess,
                      *(_QWORD *)bInheritHandle);
  if ( (ComplexPassword & 0x1FFF0000) == 0x70000 )
    ComplexPassword = (unsigned __int16)ComplexPassword;
  v48 = ComplexPassword;
  if ( ComplexPassword )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v11 = 110;
    goto LABEL_12;
  }
  if ( !(unsigned __int8)WinStationPreCreateGlassReplacementSessionEx(
                           v50,
                           *((unsigned int *)v4[2] + 22),
                           0xFFFFFFFFLL,
                           &v74) )
  {
    ComplexPassword = GetLastError();
    v48 = ComplexPassword;
    MicrosoftTelemetryAssertTriggeredArgs("winsta.dll", ComplexPassword, 0);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v11 = 111;
    goto LABEL_12;
  }
  v14 = v74;
  if ( (int)v74 <= 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs("winsta.dll", v74, 0);
    v14 = v74;
  }
  v15 = *((_QWORD *)*v4 + 17);
  v16 = SetSessionIdOnTokenAndLinkedToken(*(void **)(v15 + 16), v14);
  ComplexPassword = v16;
  v48 = v16;
  if ( v16 )
    MicrosoftTelemetryAssertTriggeredArgs("lsasrv.dll", v16, 0);
  if ( ComplexPassword )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v11 = 112;
    goto LABEL_12;
  }
  LODWORD(v75) = 0;
  v17 = ValidateSessionIdOnTokenAndLinkedToken(*(HANDLE *)(v15 + 16), v74, (int *)&v75);
  ComplexPassword = v17;
  v48 = v17;
  if ( v17 )
    MicrosoftTelemetryAssertTriggeredArgs("lsasrv.dll", v17, 0);
  if ( ComplexPassword )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_85;
    }
    v11 = 113;
LABEL_12:
    v12 = ComplexPassword;
    goto LABEL_13;
  }
  if ( !(_DWORD)v75 )
  {
    MicrosoftTelemetryAssertTriggeredArgs("lsasrv.dll", 0, 0);
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v18);
    }
    ComplexPassword = 6;
    v48 = 6;
    goto LABEL_85;
  }
  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v20 = *(void **)(v15 + 16);
  v21 = GetCurrentProcess();
  if ( DuplicateHandle(v21, v20, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    *((_QWORD *)*v4 + 20) = TargetHandle;
    memset_0(v53, 0, 0xA8u);
    v53[0] = *((_DWORD *)v4[2] + 22);
    v53[1] = v74;
    v53[2] = *(_DWORD *)v15;
    v53[3] = *(_DWORD *)(v15 + 4);
    v54 = *(_QWORD *)(v15 + 8);
    v55 = *(_QWORD *)(v15 + 24);
    v56 = *(_OWORD *)(v15 + 32);
    v57 = *(_OWORD *)(v15 + 48);
    v58 = *(_OWORD *)(v15 + 64);
    v59 = *(_DWORD *)(v15 + 80);
    v25 = v49;
    v61 = v49;
    v26 = -1;
    do
      ++v26;
    while ( v49[v26] );
    v60 = 2 * v26 + 2;
    StringSid = 0;
    if ( ConvertSidToStringSidW(*(PSID *)(v15 + 88), &StringSid) )
    {
      v28 = StringSid;
      v29 = -1;
      do
        ++v29;
      while ( StringSid[v29] );
      v62 = 2 * v29 + 2;
      v63 = StringSid;
      v64 = *(_DWORD *)(v15 + 100);
      v65 = v64;
      v30 = *(struct _MSV1_0_INTERACTIVE_PROFILE **)(v15 + 104);
      v66 = v30;
      v31 = *v4;
      v75 = v31;
      v32 = (const unsigned __int16 *)*((_QWORD *)v31 + 15);
      if ( v32 )
      {
        v68 = *((_QWORD *)v31 + 15);
        do
          ++v6;
        while ( v32[v6] );
        v67 = 2 * v6 + 2;
      }
      else
      {
        v67 = 0;
        v68 = 0;
        v32 = 0;
      }
      v33 = v76;
      v69 = *((_DWORD *)v76 + 2) + 24;
      v70 = v76;
      LODWORD(v76) = 0;
      CGlobalStore::FreeSwitchUserLogonInfo(v31);
      UserSwitchLogonInfoCollectedSyncEvent = CGlobalStore::CopySwitchUserLogonInfoIntoContiguousBuffer(
                                                (struct CGlobalStore::_SWITCH_USER_LOGON_INFO *)v53,
                                                v25,
                                                v28,
                                                v30,
                                                (unsigned __int64)v30,
                                                v32,
                                                v33,
                                                *((void **)v33 + 2),
                                                (struct CGlobalStore::_SWITCH_USER_LOGON_INFO **)v75 + 19,
                                                (unsigned int *)&v76);
      ComplexPassword = UserSwitchLogonInfoCollectedSyncEvent;
      v48 = UserSwitchLogonInfoCollectedSyncEvent;
      if ( UserSwitchLogonInfoCollectedSyncEvent )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_85;
        }
        v11 = 117;
      }
      else
      {
        UserSwitchLogonInfoCollectedSyncEvent = CSession::CreateUserSwitchLogonInfoCollectedSyncEvent(v4[2]);
        ComplexPassword = UserSwitchLogonInfoCollectedSyncEvent;
        v48 = UserSwitchLogonInfoCollectedSyncEvent;
        if ( !UserSwitchLogonInfoCollectedSyncEvent )
        {
          if ( v77 )
            WlAccessibilitySessionSwitchPreSwitch((struct _WLSM_GLOBAL_CONTEXT *)v4);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v50);
          v34 = v49;
          v49 = 0;
          if ( v34 )
            wil::cotaskmem_secure_deleter::operator()<unsigned short>();
          goto LABEL_85;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_85:
          if ( ComplexPassword )
          {
            CGlobalStore::FreeSwitchUserLogonInfo(*v4);
            CGlobalStore::FreeSwitchUserTokenHandle(*v4);
            if ( v74 != -1 )
            {
              if ( (unsigned __int8)IsWinStationConnectAndLockDesktopPresent() )
              {
                if ( !(unsigned __int8)WinStationTerminateGlassReplacementSession(v74) )
                {
                  LastError = GetLastError();
                  MicrosoftTelemetryAssertTriggeredArgs("winsta.dll", LastError, 0);
                  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_DD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      119,
                      WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids,
                      v74,
                      LastError);
                  }
                }
              }
            }
          }
          if ( !WTSDisconnectSession(0, 0xFFFFFFFF, 0) )
          {
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v37 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v37);
            }
            *((_DWORD *)v4[1] + 23) = 0;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v36);
            }
          }
          v38 = *v4;
          IsBoundToConsole = CSession::IsBoundToConsole(v4[2]);
          v40 = v4[2];
          LODWORD(v47) = 0;
          LODWORD(v46) = 0;
          dwOptions[0] = 0;
          bInheritHandle[0] = 0;
          dwDesiredAccess[0] = IsBoundToConsole == 0;
          v41 = CGlobalStore::StopAndDeleteGlobalTraceLoggingActivity(v38, *((unsigned int *)v40 + 22), 2, 2);
          if ( v41 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xAFF,
              (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\lock.cxx",
              (const char *)(unsigned int)v41,
              dwDesiredAccess[0]);
          CGlobalStore::FreeCredentials(*v4);
          CGlobalStore::FreeCredentialContext(*v4, 0);
          CGlobalStore::FreeInternalSwitchUserLogonInfo(
            *v4,
            (struct CGlobalStore::_INTERNAL_SWITCH_USER_LOGON_INFO **)*v4 + 17);
          return WlStateMachineSetSignal(0, 0);
        }
        v11 = 118;
      }
    }
    else
    {
      UserSwitchLogonInfoCollectedSyncEvent = GetLastError();
      ComplexPassword = UserSwitchLogonInfoCollectedSyncEvent;
      v48 = UserSwitchLogonInfoCollectedSyncEvent;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      v11 = 116;
    }
    v12 = UserSwitchLogonInfoCollectedSyncEvent;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v12);
    goto LABEL_85;
  }
  v22 = GetLastError();
  v48 = v22;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v22);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v50);
  v23 = v49;
  v49 = 0;
  if ( v23 )
    wil::cotaskmem_secure_deleter::operator()<unsigned short>();
  local_unwind_0(v71, &loc_14005215A);
  return v48;
}

```

## disassembly

```asm
0x140051d40  mov     r11, rsp
0x140051d43  push    rbx
0x140051d44  push    rsi
0x140051d45  push    rdi
0x140051d46  push    r12
0x140051d48  push    r13
0x140051d4a  push    r14
0x140051d4c  push    r15
0x140051d4e  sub     rsp, 150h
0x140051d55  mov     [rsp+188h+var_58], rsp
0x140051d5d  mov     r14, [rcx+8]
0x140051d61  mov     rax, [r14]
0x140051d64  mov     rdi, [rax+70h]
0x140051d68  mov     [rsp+188h+arg_10], rdi
0x140051d70  mov     edi, [rdi]
0x140051d72  and     edi, 4
0x140051d75  mov     [rsp+188h+arg_18], edi
0x140051d7c  or      r12, 0FFFFFFFFFFFFFFFFh
0x140051d80  mov     [r11+8], r12d
0x140051d84  lea     r15, WPP_GLOBAL_Control
0x140051d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140051d92  cmp     rcx, r15
0x140051d95  jz      short loc_140051DC0
0x140051d97  test    dword ptr [rcx+1Ch], 100h
0x140051d9e  jz      short loc_140051DC0
0x140051da0  cmp     byte ptr [rcx+19h], 4
0x140051da4  jb      short loc_140051DC0
0x140051da6  lea     edx, [r12+6Dh]
0x140051dab  lea     rsi, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x140051db2  mov     r8, rsi
0x140051db5  mov     rcx, [rcx+10h]
0x140051db9  call    WPP_SF_
0x140051dbe  jmp     short loc_140051DC7
0x140051dc0  lea     rsi, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x140051dc7  xor     r13d, r13d
0x140051dca  mov     [rsp+188h+var_130], r13
0x140051dcf  lea     rdx, [rsp+188h+var_130]
0x140051dd4  lea     rcx, [rsp+188h+var_50]
0x140051ddc  call    ??$out_param@V?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@@wil@@YA?AU?$out_param_t@V?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@@details@0@AEAV?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@@Z; wil::out_param<wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>>(wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter> &)
0x140051de1  lea     rcx, [rax+8]; this
0x140051de5  call    ?GenerateComplexPassword@SystemManagedAccountUtil@@YAJPEAPEAG@Z; SystemManagedAccountUtil::GenerateComplexPassword(ushort * *)
0x140051dea  mov     ebx, eax
0x140051dec  and     eax, 1FFF0000h
0x140051df1  cmp     eax, 70000h
0x140051df6  jnz     short loc_140051DFB
0x140051df8  movzx   ebx, bx
0x140051dfb  mov     [rsp+188h+var_138], ebx
0x140051dff  lea     rcx, [rsp+188h+var_50]
0x140051e07  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>>(void)
0x140051e0c  test    ebx, ebx
0x140051e0e  jz      short loc_140051E50
0x140051e10  mov     rcx, cs:WPP_GLOBAL_Control
0x140051e17  cmp     rcx, r15
0x140051e1a  jz      loc_14005245A
0x140051e20  test    dword ptr [rcx+1Ch], 1000h
0x140051e27  jz      loc_14005245A
0x140051e2d  cmp     byte ptr [rcx+19h], 2
0x140051e31  jb      loc_14005245A
0x140051e37  mov     edx, 6Dh ; 'm'
0x140051e3c  mov     r9d, ebx
0x140051e3f  mov     r8, rsi
0x140051e42  mov     rcx, [rcx+10h]
0x140051e46  call    WPP_SF_d
0x140051e4b  jmp     loc_14005245A
0x140051e50  lea     rcx, [rsp+188h+var_128]
0x140051e55  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x140051e5a  mov     rax, [r14+10h]
0x140051e5e  mov     [rsp+188h+bInheritHandle], edi
0x140051e62  mov     eax, [rax+58h]
0x140051e65  mov     [rsp+188h+dwDesiredAccess], eax
0x140051e69  mov     r9, [rsp+188h+var_130]
0x140051e6e  lea     r8, aSystemrootSyst; "%SYSTEMROOT%\\System32\\WinLogon.exe -U"...
0x140051e75  lea     rdx, aLsLsLdLd; "%ls %ls %ld %ld"
0x140051e7c  lea     rcx, [rsp+188h+var_128]
0x140051e81  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x140051e86  mov     ebx, eax
0x140051e88  and     eax, 1FFF0000h
0x140051e8d  cmp     eax, 70000h
0x140051e92  jnz     short loc_140051E97
0x140051e94  movzx   ebx, bx
0x140051e97  mov     [rsp+188h+var_138], ebx
0x140051e9b  test    ebx, ebx
0x140051e9d  jz      short loc_140051ED0
0x140051e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140051ea6  cmp     rcx, r15
0x140051ea9  jz      loc_14005245A
0x140051eaf  test    dword ptr [rcx+1Ch], 1000h
0x140051eb6  jz      loc_14005245A
0x140051ebc  cmp     byte ptr [rcx+19h], 2
0x140051ec0  jb      loc_14005245A
0x140051ec6  mov     edx, 6Eh ; 'n'
0x140051ecb  jmp     loc_140051E3C
0x140051ed0  mov     rdx, [r14+10h]
0x140051ed4  lea     r9, [rsp+188h+arg_0]
0x140051edc  or      r8d, 0FFFFFFFFh
0x140051ee0  mov     edx, [rdx+58h]
0x140051ee3  mov     rcx, [rsp+188h+var_128]
0x140051ee8  call    cs:__imp_WinStationPreCreateGlassReplacementSessionEx
0x140051eee  test    al, al
0x140051ef0  jnz     short loc_140051F40
0x140051ef2  call    cs:__imp_GetLastError
0x140051ef8  mov     ebx, eax
0x140051efa  mov     [rsp+188h+var_138], eax
0x140051efe  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "FALSE", "WinStationPreCreateGlassReplacementSessionEx")
0x140051f01  mov     edx, eax
0x140051f03  lea     rcx, aWinstaDll; "winsta.dll"
0x140051f0a  call    MicrosoftTelemetryAssertTriggeredArgs
0x140051f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140051f16  cmp     rcx, r15
0x140051f19  jz      loc_14005245A
0x140051f1f  test    dword ptr [rcx+1Ch], 1000h
0x140051f26  jz      loc_14005245A
0x140051f2c  cmp     byte ptr [rcx+19h], 2
0x140051f30  jb      loc_14005245A
0x140051f36  mov     edx, 6Fh ; 'o'
0x140051f3b  jmp     loc_140051E3C
0x140051f40  mov     edx, [rsp+188h+arg_0]
0x140051f47  test    edx, edx
0x140051f49  jg      short loc_140051F61
0x140051f4b  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "targetSessionId > 0", "WinStationPreCreateGlassReplacementSessionEx returned SessionId <= 0")
0x140051f4e  lea     rcx, aWinstaDll; "winsta.dll"
0x140051f55  call    MicrosoftTelemetryAssertTriggeredArgs
0x140051f5a  mov     edx, [rsp+188h+arg_0]; unsigned int
0x140051f61  mov     rax, [r14]
0x140051f64  mov     r15, [rax+88h]
0x140051f6b  mov     rcx, [r15+10h]; void *
0x140051f6f  call    ?SetSessionIdOnTokenAndLinkedToken@@YAKPEAXK@Z; SetSessionIdOnTokenAndLinkedToken(void *,ulong)
0x140051f74  mov     ebx, eax
0x140051f76  mov     [rsp+188h+var_138], eax
0x140051f7a  test    eax, eax
0x140051f7c  jz      short loc_140051F8F
0x140051f7e  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "ERROR_SUCCESS == dwRet", "SetSessionIdOnTokenAndLinkedToken")
0x140051f81  mov     edx, eax
0x140051f83  lea     rcx, aLsasrvDll; "lsasrv.dll"
0x140051f8a  call    MicrosoftTelemetryAssertTriggeredArgs
0x140051f8f  test    ebx, ebx
0x140051f91  jz      short loc_140051FCB
0x140051f93  mov     rcx, cs:WPP_GLOBAL_Control
0x140051f9a  lea     r15, WPP_GLOBAL_Control
0x140051fa1  cmp     rcx, r15
0x140051fa4  jz      loc_14005245A
0x140051faa  test    dword ptr [rcx+1Ch], 1000h
0x140051fb1  jz      loc_14005245A
0x140051fb7  cmp     byte ptr [rcx+19h], 2
0x140051fbb  jb      loc_14005245A
0x140051fc1  mov     edx, 70h ; 'p'
0x140051fc6  jmp     loc_140051E3C
0x140051fcb  mov     dword ptr [rsp+188h+arg_8], r13d
0x140051fd3  lea     r8, [rsp+188h+arg_8]; int *
0x140051fdb  mov     edx, [rsp+188h+arg_0]; unsigned int
0x140051fe2  mov     rcx, [r15+10h]; TokenHandle
0x140051fe6  call    ?ValidateSessionIdOnTokenAndLinkedToken@@YAKPEAXKPEAH@Z; ValidateSessionIdOnTokenAndLinkedToken(void *,ulong,int *)
0x140051feb  mov     ebx, eax
0x140051fed  mov     [rsp+188h+var_138], eax
0x140051ff1  test    eax, eax
0x140051ff3  jz      short loc_140052006
0x140051ff5  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "ERROR_SUCCESS == dwRet", "ValidateSessionIdOnTokenAndLinkedToken")
0x140051ff8  mov     edx, eax
0x140051ffa  lea     rcx, aLsasrvDll; "lsasrv.dll"
0x140052001  call    MicrosoftTelemetryAssertTriggeredArgs
0x140052006  test    ebx, ebx
0x140052008  jz      short loc_140052042
0x14005200a  mov     rcx, cs:WPP_GLOBAL_Control
0x140052011  lea     r15, WPP_GLOBAL_Control
0x140052018  cmp     rcx, r15
0x14005201b  jz      loc_14005245A
0x140052021  test    dword ptr [rcx+1Ch], 1000h
0x140052028  jz      loc_14005245A
0x14005202e  cmp     byte ptr [rcx+19h], 2
0x140052032  jb      loc_14005245A
0x140052038  mov     edx, 71h ; 'q'
0x14005203d  jmp     loc_140051E3C
0x140052042  mov     ebx, dword ptr [rsp+188h+arg_8]
0x140052049  test    ebx, ebx
0x14005204b  jnz     short loc_1400520A1
0x14005204d  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "matched", "ValidateSessionIdOnTokenAndLinkedToken.matched")
0x140052050  xor     edx, edx
0x140052052  lea     rcx, aLsasrvDll; "lsasrv.dll"
0x140052059  call    MicrosoftTelemetryAssertTriggeredArgs
0x14005205e  test    ebx, ebx
0x140052060  jnz     short loc_1400520A1
0x140052062  mov     rcx, cs:WPP_GLOBAL_Control
0x140052069  lea     r15, WPP_GLOBAL_Control
0x140052070  cmp     rcx, r15
0x140052073  jz      short loc_140052093
0x140052075  test    dword ptr [rcx+1Ch], 1000h
0x14005207c  jz      short loc_140052093
0x14005207e  cmp     byte ptr [rcx+19h], 2
0x140052082  jb      short loc_140052093
0x140052084  lea     edx, [rbx+72h]
0x140052087  mov     r8, rsi
0x14005208a  mov     rcx, [rcx+10h]
0x14005208e  call    WPP_SF_
0x140052093  mov     ebx, 6
0x140052098  mov     [rsp+188h+var_138], ebx
0x14005209c  jmp     loc_14005245A
0x1400520a1  mov     [rsp+188h+TargetHandle], r13
0x1400520a6  call    cs:__imp_GetCurrentProcess
0x1400520ac  mov     rbx, rax
0x1400520af  mov     rdi, [r15+10h]
0x1400520b3  call    cs:__imp_GetCurrentProcess
0x1400520b9  mov     [rsp+188h+dwOptions], 2; dwOptions
0x1400520c1  mov     [rsp+188h+bInheritHandle], r13d; bInheritHandle
0x1400520c6  mov     [rsp+188h+dwDesiredAccess], r13d; dwDesiredAccess
0x1400520cb  lea     r9, [rsp+188h+TargetHandle]; lpTargetHandle
0x1400520d0  mov     r8, rbx; hTargetProcessHandle
0x1400520d3  mov     rdx, rdi; hSourceHandle
0x1400520d6  mov     rcx, rax; hSourceProcessHandle
0x1400520d9  call    cs:__imp_DuplicateHandle
0x1400520df  test    eax, eax
0x1400520e1  jnz     loc_140052171
0x1400520e7  call    cs:__imp_GetLastError
0x1400520ed  mov     [rsp+188h+var_138], eax
0x1400520f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400520f8  lea     rdx, WPP_GLOBAL_Control
0x1400520ff  cmp     rcx, rdx
0x140052102  jz      short loc_140052127
0x140052104  test    dword ptr [rcx+1Ch], 1000h
0x14005210b  jz      short loc_140052127
0x14005210d  cmp     byte ptr [rcx+19h], 2
0x140052111  jb      short loc_140052127
0x140052113  mov     edx, 73h ; 's'
0x140052118  mov     r9d, eax
0x14005211b  mov     r8, rsi
0x14005211e  mov     rcx, [rcx+10h]
0x140052122  call    WPP_SF_d
0x140052127  lea     rcx, [rsp+188h+var_128]
0x14005212c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140052131  mov     rdx, [rsp+188h+var_130]
0x140052136  mov     [rsp+188h+var_130], r13
0x14005213b  test    rdx, rdx
0x14005213e  jz      short loc_140052145
0x140052140  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x140052145  lea     rdx, loc_14005215A
0x14005214c  mov     rcx, [rsp+188h+var_58]
0x140052154  call    _local_unwind_0
0x140052159  nop
0x14005215a  mov     eax, [rsp+188h+var_138]
0x14005215e  add     rsp, 150h
0x140052165  pop     r15
0x140052167  pop     r14
0x140052169  pop     r13
0x14005216b  pop     r12
0x14005216d  pop     rdi
0x14005216e  pop     rsi
0x14005216f  pop     rbx
0x140052170  retn
0x140052171  mov     rcx, [r14]
0x140052174  mov     rax, [rsp+188h+TargetHandle]
0x140052179  mov     [rcx+0A0h], rax
0x140052180  xor     edx, edx; Val
0x140052182  mov     r8d, 0A8h; Size
0x140052188  lea     rcx, [rsp+188h+var_108]; void *
0x140052190  call    memset_0
0x140052195  mov     rax, [r14+10h]
0x140052199  mov     ecx, [rax+58h]
0x14005219c  mov     [rsp+188h+var_108], ecx
0x1400521a3  mov     eax, [rsp+188h+arg_0]
0x1400521aa  mov     [rsp+188h+var_104], eax
0x1400521b1  mov     eax, [r15]
0x1400521b4  mov     [rsp+188h+var_100], eax
0x1400521bb  mov     eax, [r15+4]
0x1400521bf  mov     [rsp+188h+var_FC], eax
0x1400521c6  mov     rax, [r15+8]
0x1400521ca  mov     [rsp+188h+var_F8], rax
0x1400521d2  mov     rax, [r15+18h]
0x1400521d6  mov     [rsp+188h+var_F0], rax
0x1400521de  movups  xmm0, xmmword ptr [r15+20h]
0x1400521e3  movaps  [rsp+188h+var_E8], xmm0
0x1400521eb  movups  xmm1, xmmword ptr [r15+30h]
0x1400521f0  movaps  [rsp+188h+var_D8], xmm1
0x1400521f8  movups  xmm0, xmmword ptr [r15+40h]
0x1400521fd  movaps  [rsp+188h+var_C8], xmm0
0x140052205  mov     eax, [r15+50h]
0x140052209  mov     [rsp+188h+var_B8], eax
0x140052210  mov     rbx, [rsp+188h+var_130]
0x140052215  mov     [rsp+188h+var_B0], rbx
0x14005221d  mov     rax, r12
0x140052220  inc     rax
0x140052223  cmp     [rbx+rax*2], r13w
0x140052228  jnz     short loc_140052220
0x14005222a  lea     eax, ds:2[rax*2]
0x140052231  mov     [rsp+188h+var_B4], eax
0x140052238  mov     [rsp+188h+StringSid], r13
0x14005223d  lea     rdx, [rsp+188h+StringSid]; StringSid
0x140052242  mov     rcx, [r15+58h]; Sid
0x140052246  call    cs:__imp_ConvertSidToStringSidW
0x14005224c  test    eax, eax
0x14005224e  jnz     short loc_140052297
0x140052250  call    cs:__imp_GetLastError
0x140052256  mov     ebx, eax
0x140052258  mov     [rsp+188h+var_138], eax
0x14005225c  mov     rcx, cs:WPP_GLOBAL_Control
0x140052263  lea     r15, WPP_GLOBAL_Control
0x14005226a  cmp     rcx, r15
0x14005226d  jz      loc_14005245A
0x140052273  test    dword ptr [rcx+1Ch], 1000h
0x14005227a  jz      loc_14005245A
0x140052280  cmp     byte ptr [rcx+19h], 2
0x140052284  jb      loc_14005245A
  ... truncated ...
```
