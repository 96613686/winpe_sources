# WLGeneric_ShellStartup_Execute(_StateMachineCallContext *)

- ea: `0x1400727a0`
- end: `0x1400734a0`
- name: `?WLGeneric_ShellStartup_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `3328`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `36`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140002300`
- `0x14000260c`
- `0x1400057f4`
- `0x140006fc0`
- `0x140008550`
- `0x14000bb80`
- `0x14000fb30`
- `0x140013be8`
- `0x140016f30`
- `0x1400198e0`
- `0x14001a200`
- `0x14002f6e0`
- `0x1400333b0`
- `0x14003394c`
- `0x140035d84`
- `0x140035f30`
- `0x140037cf0`
- `0x140039458`
- `0x14003ba50`
- `0x14003c318`
- `0x14003de48`
- `0x14003f584`
- `0x140041c34`
- `0x140042d80`
- `0x140044800`
- `0x14004eb98`
- `0x140053720`
- `0x1400544e0`
- `0x140055158`
- `0x140056348`
- `0x14005eba8`
- `0x14005f3c4`
- `0x14006b64c`
- `0x14006c2e0`
- `0x14006e220`
- `0x1400727a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140072cff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140072cff`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x140072db0`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x140072db0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x140072d91`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1400731c1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x140072d91`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1400731c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140072945`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140072945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072e2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072e92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072f53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140073091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072e2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072e92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072f53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140073091`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14007304e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140073063`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14007304e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140073063`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140073085`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140073085`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140072ff6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140073009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140073191`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400731a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140072ff6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140073009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140073191`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400731a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140072c5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140072c5c`
- `ntdll!RtlPublishWnfStateData` at `0x1400729e3`
- `ntdll!RtlPublishWnfStateData` at `0x1400729e3`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x140072cc5`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x140072cc5`
- `ext-ms-win-session-winsta-l1-1-4!WinStationReportLoggedOnCompleted` at `0x140072877`
- `ext-ms-win-session-winsta-l1-1-4!WinStationReportLoggedOnCompleted` at `0x140072877`

## string_xrefs

- `0x140072b78`: `%SystemRoot%\system32\userinit.exe`

## pseudocode

```c
__int64 __fastcall WLGeneric_ShellStartup_Execute(struct _StateMachineCallContext *a1)
{
  struct _WLSM_GLOBAL_CONTEXT *v2; // r13
  unsigned int started; // ebx
  unsigned __int16 *v4; // rdi
  CSession *v5; // rcx
  CMachine *v6; // rcx
  _DWORD *v7; // rdx
  int v8; // eax
  bool v9; // di
  int v10; // ecx
  bool v11; // r14
  char v12; // al
  int v13; // ebx
  int v14; // ecx
  const unsigned __int16 *v15; // rdx
  CGlobalStore *v16; // rcx
  unsigned int IsFirstToSetEvent; // eax
  __int64 v18; // rax
  bool v19; // bl
  __int64 v20; // rcx
  __int64 v21; // r8
  WCHAR *v22; // rdi
  CUser *v23; // rax
  char v24; // al
  CUser *v25; // rcx
  char v26; // al
  HANDLE hProcess; // rcx
  HANDLE *v28; // rsi
  HANDLE CurrentProcess; // rdi
  void *v30; // rbx
  HANDLE v31; // rax
  DWORD LastError; // eax
  CUser *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  int v36; // edi
  __int64 v37; // rcx
  int v38; // eax
  int v39; // ecx
  char v41; // [rsp+90h] [rbp-BF8h]
  char v42; // [rsp+91h] [rbp-BF7h]
  wchar_t *String; // [rsp+98h] [rbp-BF0h] BYREF
  char v44; // [rsp+A0h] [rbp-BE8h]
  unsigned int v45; // [rsp+A4h] [rbp-BE4h]
  char v46; // [rsp+A8h] [rbp-BE0h] BYREF
  char v47; // [rsp+A9h] [rbp-BDFh]
  char v48; // [rsp+AAh] [rbp-BDEh]
  char v49; // [rsp+ABh] [rbp-BDDh]
  bool v50; // [rsp+ACh] [rbp-BDCh] BYREF
  bool v51; // [rsp+ADh] [rbp-BDBh] BYREF
  char v52[2]; // [rsp+AEh] [rbp-BDAh] BYREF
  int v53; // [rsp+B0h] [rbp-BD8h] BYREF
  char v54; // [rsp+B4h] [rbp-BD4h]
  unsigned int v55; // [rsp+B8h] [rbp-BD0h] BYREF
  int v56; // [rsp+BCh] [rbp-BCCh] BYREF
  int v57; // [rsp+C0h] [rbp-BC8h] BYREF
  int v58; // [rsp+C8h] [rbp-BC0h] BYREF
  struct _WINLOGON_JOB *v59; // [rsp+D0h] [rbp-BB8h] BYREF
  int v60; // [rsp+D8h] [rbp-BB0h] BYREF
  int v61; // [rsp+DCh] [rbp-BACh] BYREF
  __int64 v62; // [rsp+E0h] [rbp-BA8h] BYREF
  struct _PROCESS_INFORMATION hObject; // [rsp+E8h] [rbp-BA0h] BYREF
  __int64 v64; // [rsp+100h] [rbp-B88h] BYREF
  struct _StateMachineCallContext *v65; // [rsp+108h] [rbp-B80h]
  wchar_t *Context; // [rsp+110h] [rbp-B78h] BYREF
  WCHAR *i; // [rsp+118h] [rbp-B70h]
  __int64 v68; // [rsp+120h] [rbp-B68h] BYREF
  _QWORD v69[3]; // [rsp+128h] [rbp-B60h] BYREF
  struct _STARTUPINFOW v70; // [rsp+140h] [rbp-B48h] BYREF
  __int128 v71; // [rsp+1B0h] [rbp-AD8h] BYREF
  __int64 v72; // [rsp+1C0h] [rbp-AC8h]
  __int128 v73; // [rsp+1C8h] [rbp-AC0h] BYREF
  _BYTE v74[754]; // [rsp+1E0h] [rbp-AA8h] BYREF
  _WORD v75[943]; // [rsp+4D2h] [rbp-7B6h] BYREF

  v65 = a1;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
  }
  v2 = (struct _WLSM_GLOBAL_CONTEXT *)*((_QWORD *)a1 + 1);
  v69[1] = v2;
  v45 = 87;
  memset_0(&v70, 0, sizeof(v70));
  memset(&hObject, 0, sizeof(hObject));
  started = 0;
  v4 = 0;
  String = 0;
  v59 = 0;
  v48 = 0;
  v47 = 0;
  v41 = 0;
  v44 = 0;
  if ( !(unsigned __int8)WinStationReportLoggedOnCompleted() )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
    }
  }
  if ( !(unsigned int)CSession::IsShellRequiredInSession(v5) )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        209,
        WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
        *(unsigned int *)(*((_QWORD *)v2 + 2) + 88LL));
    }
    goto LABEL_15;
  }
  if ( (unsigned int)CMachine::IsSiHostIntegrationEnabled(v6) )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
    }
    WaitForSingleObject(*(HANDLE *)(*((_QWORD *)v2 + 2) + 344LL), *(_DWORD *)(*((_QWORD *)v2 + 2) + 352LL));
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
    }
    v41 = 1;
    v49 = 1;
  }
  v7 = (_DWORD *)*((_QWORD *)v2 + 2);
  v8 = v7[50];
  v9 = v8 != 0;
  v10 = v7[94];
  v11 = v10 != 0;
  if ( v8 || (v12 = 1, !v10) )
    v12 = 0;
  v46 = v12;
  v58 = v7[22];
  v53 = RtlPublishWnfStateData(WNF_SHEL_LOCK_ON_LOGON, 0, &v46, 1, &v58);
  wil::srwlock::lock_shared(*(_QWORD *)v2 + 64LL, &v57);
  v64 = 0;
  if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*(_QWORD *)v2, &v64) >= 0 )
  {
    v13 = v64;
    if ( v64 )
    {
      v71 = 0;
      WLGetTSActivityId(&v71);
      if ( (unsigned int)dword_1400CF778 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x200000000000LL) )
        {
          v61 = v58;
          v50 = v11;
          v51 = v9;
          v52[0] = v46;
          v60 = v53;
          v68 = 0x1000000;
          v69[0] = &v71;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
            v14,
            (unsigned int)&unk_1400BB9F0,
            v13 + 8,
            (unsigned int)&v71,
            (__int64)v69,
            (__int64)&v68,
            (__int64)&v60,
            (__int64)v52,
            (__int64)&v51,
            (__int64)&v50,
            (__int64)&v61);
        }
      }
    }
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v57);
  v44 = 1;
  g_fShellStartupReached = 1;
  v45 = CGlobalStore::RegAllocAndQueryWinlogonSZ(v16, v15, &String);
  v4 = String;
  if ( v45 || !*String )
  {
    if ( String )
      UHHeapFree(&String);
    v4 = AllocAndExpandEnvironmentStrings(g_wszDefaultShellCommand);
    String = v4;
    if ( !v4 )
    {
      started = 14;
LABEL_15:
      v45 = started;
      goto LABEL_136;
    }
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v4);
  }
  WLEventWrite(&WLEvt_ExecuteShellCommandList_Start, v4);
  v53 = 0;
  IsFirstToSetEvent = _IsFirstToSetEvent(L"Global\\WinLogon_FirstShellLaunch", &v53);
  v45 = IsFirstToSetEvent;
  if ( IsFirstToSetEvent )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        213,
        WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
        IsFirstToSetEvent);
    }
    v45 = 0;
  }
  if ( v53 && (g_Diagnostics_Status & 4) == 0 )
  {
    WLEventWrite(&WLDiagEvt_UserShellLaunch_Info);
    g_Diagnostics_Status |= 4u;
  }
  GetSystemTimeAsFileTime((LPFILETIME)(*((_QWORD *)v2 + 2) + 64LL));
  v18 = *((_QWORD *)v2 + 2);
  v19 = *(_DWORD *)(v18 + 148) == 1;
  v42 = v19;
  if ( *(_DWORD *)(v18 + 148) != 1 )
  {
    memset_0(v74, 0, 0xA68u);
    v57 = 0;
    if ( (unsigned __int8)IsWinStationConnectAndLockDesktopPresent(v20) )
    {
      if ( (unsigned __int8)WinStationQueryInformationW(0, 0xFFFFFFFFLL, 1, v74, 2664, &v57) && v75[0] )
      {
        v21 = -1;
        do
          ++v21;
        while ( v75[v21] );
        if ( (unsigned int)_o__wcsnicmp(L"rdpinit.exe", v75, v21) )
        {
          v19 = 1;
          v42 = 1;
        }
        else
        {
          v47 = 1;
        }
      }
    }
  }
  v70.cb = 104;
  v70.dwFlags = 1;
  v70.wShowWindow = 2;
  v70.lpDesktop = L"Winsta0\\Default";
  if ( !(unsigned __int8)IsWinLogonExtPresent() && !*(_DWORD *)(*((_QWORD *)v2 + 2) + 376LL) )
  {
    v70.wShowWindow = 1;
    WLGeneric_DelayedSwitchDesktop_Enter(v65);
  }
  Context = 0;
  v22 = wcstok(v4, L",", &Context);
  for ( i = v22; ; i = v22 )
  {
    if ( !v22 )
    {
      if ( v41 )
        SetShellInformation(v2, 0, 0);
      WLEventWrite(&WLEvt_ExecuteShellCommandList_Stop);
      CUser::StartDeferredPostAuthenticationWork(*((CUser **)v2 + 4));
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
      }
      started = 0;
      goto LABEL_106;
    }
    while ( (unsigned int)_o_iswspace(*v22) )
      i = ++v22;
    started = CUser::CreateProcessW(*((CUser **)v2 + 4), 0, v22, v19 ? 4 : 0, &v70, &hObject, 1);
    v45 = started;
    if ( started )
      break;
LABEL_83:
    v19 = v42;
    if ( v42 )
    {
      started = StartProcessInJob(&hObject, 0, (struct _LUID **)&v59);
      v45 = started;
      if ( started )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, started);
        }
        goto LABEL_135;
      }
      hProcess = hObject.hProcess;
      if ( hObject.hProcess )
      {
        if ( v41 )
        {
          SetShellInformation(v2, v22, hObject.hProcess);
          v41 = 0;
          v49 = 0;
          hProcess = hObject.hProcess;
        }
        CloseHandle(hProcess);
      }
      if ( hObject.hThread )
        CloseHandle(hObject.hThread);
      if ( !v48 )
      {
        v48 = 1;
        v54 = 1;
        v28 = (HANDLE *)WLAlloc(0x28u);
        *(_QWORD *)&v71 = v28;
        if ( !v28 )
        {
          started = 14;
LABEL_106:
          v45 = started;
          goto LABEL_135;
        }
        CurrentProcess = GetCurrentProcess();
        v30 = (void *)*((_QWORD *)v59 + 4);
        v31 = GetCurrentProcess();
        if ( !DuplicateHandle(v31, v30, CurrentProcess, v28 + 2, 0, 0, 2u) )
        {
          LastError = GetLastError();
          started = LastError;
          v45 = LastError;
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_113;
          }
          v34 = 219;
          v35 = LastError;
          goto LABEL_112;
        }
        *v28 = (HANDLE)*((_QWORD *)v59 + 3);
        v28[3] = *(HANDLE *)v65;
        v28[1] = 0;
        v28[4] = v2;
        TSJobCallback(v28, 1u);
        if ( !v28[1] )
        {
          started = 1610;
          v45 = 1610;
          UHHeapFree(&v71);
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_113;
          }
          v34 = 220;
          v35 = 1610;
LABEL_112:
          WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v35);
          goto LABEL_113;
        }
      }
      v19 = v42;
    }
    else
    {
      if ( v41 )
      {
        SetShellInformation(v2, v22, hObject.hProcess);
        v41 = 0;
        v49 = 0;
      }
      if ( hObject.hProcess )
        CloseHandle(hObject.hProcess);
      if ( hObject.hThread )
        CloseHandle(hObject.hThread);
    }
    v22 = wcstok(0, L",", &Context);
  }
  if ( !v42 && !v47 && (*(_DWORD *)(*((_QWORD *)v2 + 4) + 152LL) || GetLastError() == 2) )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          216,
          (unsigned int)WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
          (_DWORD)v22,
          started);
        v23 = WPP_GLOBAL_Control;
      }
      if ( v23 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v23 + 7) & 0x1000) != 0 && *((_BYTE *)v23 + 25) >= 2u )
      {
        v24 = GetLastError();
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          217,
          (unsigned int)WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
          (_DWORD)v22,
          v24);
      }
    }
    v45 = 0;
    goto LABEL_83;
  }
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = GetLastError();
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        214,
        (unsigned int)WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
        (_DWORD)v22,
        v26);
      v25 = WPP_GLOBAL_Control;
    }
    if ( v25 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v25 + 7) & 0x1000) != 0 )
    {
      if ( *((_BYTE *)v25 + 25) >= 2u )
      {
        WPP_SF_SD(
          *((_QWORD *)v25 + 2),
          215,
          (unsigned int)WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
          (_DWORD)v22,
          started);
        goto LABEL_135;
      }
LABEL_113:
      v4 = String;
      goto LABEL_136;
    }
  }
LABEL_135:
  v4 = String;
LABEL_136:
  if ( v4 )
    UHHeapFree(&String);
  if ( v44 )
  {
    wil::srwlock::lock_shared(*(_QWORD *)v2 + 64LL, &v57);
    String = 0;
    if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*(_QWORD *)v2, &String) >= 0 )
    {
      v36 = (int)String;
      if ( String )
      {
        v73 = 0;
        WLGetTSActivityId(&v73);
        if ( (unsigned int)dword_1400CF778 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x200000000000LL) )
          {
            v55 = started;
            v56 = *(_DWORD *)(*((_QWORD *)v2 + 2) + 88LL);
            v62 = 0x1000000;
            String = (wchar_t *)&v73;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v56,
              (unsigned int)&byte_1400BB997,
              v36 + 8,
              (unsigned int)&v73,
              (__int64)&String,
              (__int64)&v62,
              (__int64)&v56,
              (__int64)&v55);
          }
        }
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v57);
  }
  if ( started )
  {
    if ( v59 )
    {
      TerminateJob(v59, 0x42Bu);
      DeletepJob(&v59, 0);
    }
    return WlStateMachineSetSignal(1u, 0);
  }
  else
  {
    v37 = *((_QWORD *)v2 + 2);
    if ( *(_DWORD *)(v37 + 376) )
    {
      v71 = 0;
      v72 = 0;
      v38 = 6;
      DWORD2(v71) = 6;
      v39 = *(_DWORD *)(v37 + 392);
      if ( v39 == 2 )
      {
        DWORD2(v71) = 7;
      }
      else
      {
        if ( v39 == 4 )
          v38 = 9;
        DWORD2(v71) = v38;
      }
      g_fIgnoreLockEvent = 1;
      WlStateMachineSetSignal(0xCu, (struct _StateMachineSignalData *)&v71);
    }
    else
    {
      started = WlStateMachineSetSignal(0, 0);
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
      }
      CUser::StartUserPresencePolling(*((CUser **)v2 + 4), 0);
      NotifyUserPresenceOnDesktopForDMAProtection(1, v2);
    }
  }
  return started;
}

```

## disassembly

```asm
0x1400727a0  mov     [rsp+arg_8], rbx
0x1400727a5  mov     [rsp+arg_10], rsi
0x1400727aa  push    rdi
0x1400727ab  push    r12
0x1400727ad  push    r13
0x1400727af  push    r14
0x1400727b1  push    r15
0x1400727b3  sub     rsp, 0C30h
0x1400727ba  mov     rax, cs:__security_cookie
0x1400727c1  xor     rax, rsp
0x1400727c4  mov     [rsp+0C58h+var_38], rax
0x1400727cc  mov     rbx, rcx
0x1400727cf  mov     [rsp+0C58h+var_B80], rcx
0x1400727d7  lea     r14, WPP_GLOBAL_Control
0x1400727de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400727e5  cmp     rcx, r14
0x1400727e8  jz      short loc_140072813
0x1400727ea  test    dword ptr [rcx+1Ch], 100h
0x1400727f1  jz      short loc_140072813
0x1400727f3  lea     r15, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x1400727fa  cmp     byte ptr [rcx+19h], 4
0x1400727fe  jb      short loc_14007281A
0x140072800  mov     edx, 0CFh
0x140072805  mov     r8, r15
0x140072808  mov     rcx, [rcx+10h]
0x14007280c  call    WPP_SF_
0x140072811  jmp     short loc_14007281A
0x140072813  lea     r15, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x14007281a  mov     r13, [rbx+8]
0x14007281e  mov     [rsp+0C58h+var_B58], r13
0x140072826  mov     [rsp+0C58h+var_BE4], 57h ; 'W'
0x14007282e  xor     edx, edx; Val
0x140072830  lea     r8d, [rdx+68h]; Size
0x140072834  lea     rcx, [rsp+0C58h+var_B48]; void *
0x14007283c  call    memset_0
0x140072841  xorps   xmm0, xmm0
0x140072844  xor     eax, eax
0x140072846  movups  xmmword ptr [rsp+0C58h+hObject], xmm0
0x14007284e  mov     [rsp+0C58h+var_B90], rax
0x140072856  xor     ebx, ebx
0x140072858  mov     edi, ebx
0x14007285a  mov     [rsp+0C58h+String], rbx
0x14007285f  mov     [rsp+0C58h+var_BB8], rbx
0x140072867  mov     [rsp+0C58h+var_BDE], bl
0x14007286b  mov     [rsp+0C58h+var_BDF], bl
0x14007286f  mov     [rsp+0C58h+var_BF8], bl
0x140072873  mov     [rsp+0C58h+var_BE8], bl
0x140072877  call    cs:__imp_WinStationReportLoggedOnCompleted
0x14007287d  test    al, al
0x14007287f  jnz     short loc_1400728B0
0x140072881  mov     rcx, cs:WPP_GLOBAL_Control
0x140072888  cmp     rcx, r14
0x14007288b  jz      short loc_1400728B0
0x14007288d  mov     esi, 1000h
0x140072892  test    [rcx+1Ch], esi
0x140072895  jz      short loc_1400728B5
0x140072897  cmp     byte ptr [rcx+19h], 4
0x14007289b  jb      short loc_1400728B5
0x14007289d  mov     edx, 0D0h
0x1400728a2  mov     r8, r15
0x1400728a5  mov     rcx, [rcx+10h]
0x1400728a9  call    WPP_SF_
0x1400728ae  jmp     short loc_1400728B5
0x1400728b0  mov     esi, 1000h
0x1400728b5  call    ?IsShellRequiredInSession@CSession@@QEAAHXZ; CSession::IsShellRequiredInSession(void)
0x1400728ba  test    eax, eax
0x1400728bc  jnz     short loc_140072903
0x1400728be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400728c5  cmp     rcx, r14
0x1400728c8  jz      short loc_1400728EE
0x1400728ca  test    [rcx+1Ch], esi
0x1400728cd  jz      short loc_1400728EE
0x1400728cf  cmp     byte ptr [rcx+19h], 4
0x1400728d3  jb      short loc_1400728EE
0x1400728d5  mov     r9, [r13+10h]
0x1400728d9  mov     edx, 0D1h
0x1400728de  mov     r9d, [r9+58h]
0x1400728e2  mov     r8, r15
0x1400728e5  mov     rcx, [rcx+10h]
0x1400728e9  call    WPP_SF_d
0x1400728ee  mov     r12d, 1
0x1400728f4  mov     [rsp+0C58h+var_BE4], ebx
0x1400728f8  mov     r14d, 2
0x1400728fe  jmp     loc_14007324B
0x140072903  call    ?IsSiHostIntegrationEnabled@CMachine@@QEAAHXZ; CMachine::IsSiHostIntegrationEnabled(void)
0x140072908  test    eax, eax
0x14007290a  jz      short loc_140072988
0x14007290c  mov     rcx, cs:WPP_GLOBAL_Control
0x140072913  cmp     rcx, r14
0x140072916  jz      short loc_140072934
0x140072918  test    [rcx+1Ch], esi
0x14007291b  jz      short loc_140072934
0x14007291d  cmp     byte ptr [rcx+19h], 4
0x140072921  jb      short loc_140072934
0x140072923  mov     edx, 0D2h
0x140072928  mov     r8, r15
0x14007292b  mov     rcx, [rcx+10h]
0x14007292f  call    WPP_SF_
0x140072934  mov     rcx, [r13+10h]
0x140072938  mov     edx, [rcx+160h]; dwMilliseconds
0x14007293e  mov     rcx, [rcx+158h]; hHandle
0x140072945  call    cs:__imp_WaitForSingleObject
0x14007294b  mov     rcx, cs:WPP_GLOBAL_Control
0x140072952  cmp     rcx, r14
0x140072955  jz      short loc_140072973
0x140072957  test    [rcx+1Ch], esi
0x14007295a  jz      short loc_140072973
0x14007295c  cmp     byte ptr [rcx+19h], 4
0x140072960  jb      short loc_140072973
0x140072962  mov     edx, 0D3h
0x140072967  mov     r8, r15
0x14007296a  mov     rcx, [rcx+10h]
0x14007296e  call    WPP_SF_
0x140072973  mov     r12d, 1
0x140072979  mov     bl, r12b
0x14007297c  mov     [rsp+0C58h+var_BF8], bl
0x140072980  mov     [rsp+0C58h+var_BDD], bl
0x140072984  xor     ebx, ebx
0x140072986  jmp     short loc_14007298E
0x140072988  mov     r12d, 1
0x14007298e  mov     rdx, [r13+10h]
0x140072992  mov     eax, [rdx+0C8h]
0x140072998  test    eax, eax
0x14007299a  setnz   dil
0x14007299e  mov     ecx, [rdx+178h]
0x1400729a4  test    ecx, ecx
0x1400729a6  setnz   r14b
0x1400729aa  test    eax, eax
0x1400729ac  jnz     short loc_1400729B5
0x1400729ae  test    ecx, ecx
0x1400729b0  mov     al, r12b
0x1400729b3  jnz     short loc_1400729B7
0x1400729b5  mov     al, bl
0x1400729b7  mov     [rsp+0C58h+var_BE0], al
0x1400729bb  mov     eax, [rdx+58h]
0x1400729be  mov     [rsp+0C58h+var_BC0], eax
0x1400729c5  lea     rax, [rsp+0C58h+var_BC0]
0x1400729cd  mov     qword ptr [rsp+0C58h+dwDesiredAccess], rax
0x1400729d2  mov     r9d, r12d
0x1400729d5  lea     r8, [rsp+0C58h+var_BE0]
0x1400729da  xor     edx, edx
0x1400729dc  mov     rcx, cs:WNF_SHEL_LOCK_ON_LOGON
0x1400729e3  call    cs:__imp_RtlPublishWnfStateData
0x1400729e9  mov     [rsp+0C58h+var_BD8], eax
0x1400729f0  mov     rcx, [r13+0]
0x1400729f4  add     rcx, 40h ; '@'
0x1400729f8  lea     rdx, [rsp+0C58h+var_BC8]
0x140072a00  call    ?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_shared(void)
0x140072a05  mov     [rsp+0C58h+var_B88], rbx
0x140072a0d  lea     rdx, [rsp+0C58h+var_B88]
0x140072a15  mov     rcx, [r13+0]
0x140072a19  call    ?GetGlobalTraceLoggingActivity@CGlobalStore@@QEAAJPEAPEAV?$TraceLoggingActivity@$1?g_WinlogonProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@@Z; CGlobalStore::GetGlobalTraceLoggingActivity(TraceLoggingActivity<&_tlgProvider_t const * const g_WinlogonProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> * *)
0x140072a1e  test    eax, eax
0x140072a20  js      loc_140072B30
0x140072a26  mov     rbx, [rsp+0C58h+var_B88]
0x140072a2e  test    rbx, rbx
0x140072a31  jz      loc_140072B30
0x140072a37  xorps   xmm0, xmm0
0x140072a3a  movups  [rsp+0C58h+var_AD8], xmm0
0x140072a42  lea     rcx, [rsp+0C58h+var_AD8]
0x140072a4a  call    WLGetTSActivityId
0x140072a4f  mov     eax, cs:dword_1400CF778
0x140072a55  cmp     eax, 5
0x140072a58  jbe     loc_140072B30
0x140072a5e  mov     rdx, 200000000000h
0x140072a68  lea     rcx, dword_1400CF778
0x140072a6f  call    _tlgKeywordOn
0x140072a74  test    al, al
0x140072a76  jz      loc_140072B30
0x140072a7c  mov     eax, [rsp+0C58h+var_BC0]
0x140072a83  mov     [rsp+0C58h+var_BAC], eax
0x140072a8a  mov     [rsp+0C58h+var_BDC], r14b
0x140072a8f  mov     [rsp+0C58h+var_BDB], dil
0x140072a94  mov     al, [rsp+0C58h+var_BE0]
0x140072a98  mov     [rsp+0C58h+var_BDA], al
0x140072a9c  mov     eax, [rsp+0C58h+var_BD8]
0x140072aa3  mov     [rsp+0C58h+var_BB0], eax
0x140072aaa  mov     [rsp+0C58h+var_B68], 1000000h
0x140072ab6  lea     rax, [rsp+0C58h+var_AD8]
0x140072abe  mov     [rsp+0C58h+var_B60], rax
0x140072ac6  lea     r8, [rbx+8]
0x140072aca  lea     rax, [rsp+0C58h+var_BAC]
0x140072ad2  mov     [rsp+0C58h+var_C08], rax
0x140072ad7  lea     rax, [rsp+0C58h+var_BDC]
0x140072adc  mov     [rsp+0C58h+var_C10], rax
0x140072ae1  lea     rax, [rsp+0C58h+var_BDB]
0x140072ae6  mov     [rsp+0C58h+var_C18], rax
0x140072aeb  lea     rax, [rsp+0C58h+var_BDA]
0x140072af0  mov     [rsp+0C58h+var_C20], rax
0x140072af5  lea     rax, [rsp+0C58h+var_BB0]
0x140072afd  mov     qword ptr [rsp+0C58h+dwOptions], rax
0x140072b02  lea     rax, [rsp+0C58h+var_B68]
0x140072b0a  mov     qword ptr [rsp+0C58h+bInheritHandle], rax
0x140072b0f  lea     rax, [rsp+0C58h+var_B60]
0x140072b17  mov     qword ptr [rsp+0C58h+dwDesiredAccess], rax
0x140072b1c  lea     r9, [rsp+0C58h+var_AD8]
0x140072b24  lea     rdx, unk_1400BB9F0
0x140072b2b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U4@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@665@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x140072b30  lea     rcx, [rsp+0C58h+var_BC8]
0x140072b38  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140072b3d  mov     [rsp+0C58h+var_BE8], r12b
0x140072b42  mov     cs:?g_fShellStartupReached@@3HA, r12d; int g_fShellStartupReached
0x140072b49  lea     r8, [rsp+0C58h+String]; unsigned __int16 **
0x140072b4e  call    ?RegAllocAndQueryWinlogonSZ@CGlobalStore@@QEAAKPEBGPEAPEAG@Z; CGlobalStore::RegAllocAndQueryWinlogonSZ(ushort const *,ushort * *)
0x140072b53  mov     [rsp+0C58h+var_BE4], eax
0x140072b57  xor     r14d, r14d
0x140072b5a  mov     rdi, [rsp+0C58h+String]
0x140072b5f  test    eax, eax
0x140072b61  jnz     short loc_140072B69
0x140072b63  cmp     r14w, [rdi]
0x140072b67  jnz     short loc_140072B99
0x140072b69  test    rdi, rdi
0x140072b6c  jz      short loc_140072B78
0x140072b6e  lea     rcx, [rsp+0C58h+String]
0x140072b73  call    UHHeapFree
0x140072b78  lea     rcx, ?g_wszDefaultShellCommand@@3PAGA; "%SystemRoot%\\system32\\userinit.exe"
0x140072b7f  call    ?AllocAndExpandEnvironmentStrings@@YAPEAGPEBG@Z; AllocAndExpandEnvironmentStrings(ushort const *)
0x140072b84  mov     rdi, rax
0x140072b87  mov     [rsp+0C58h+String], rax
0x140072b8c  test    rax, rax
0x140072b8f  jnz     short loc_140072B99
0x140072b91  lea     ebx, [rax+0Eh]
0x140072b94  jmp     loc_1400728F4
0x140072b99  mov     rcx, cs:WPP_GLOBAL_Control
0x140072ba0  lea     rbx, WPP_GLOBAL_Control
0x140072ba7  cmp     rcx, rbx
0x140072baa  jz      short loc_140072BCB
0x140072bac  test    [rcx+1Ch], esi
0x140072baf  jz      short loc_140072BCB
0x140072bb1  cmp     byte ptr [rcx+19h], 4
0x140072bb5  jb      short loc_140072BCB
0x140072bb7  mov     edx, 0D4h
0x140072bbc  mov     r9, rdi
0x140072bbf  mov     r8, r15
0x140072bc2  mov     rcx, [rcx+10h]
0x140072bc6  call    WPP_SF_S
0x140072bcb  mov     rdx, rdi; unsigned __int16 *
0x140072bce  lea     rcx, WLEvt_ExecuteShellCommandList_Start; struct _EVENT_DESCRIPTOR *
0x140072bd5  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@PEBG@Z; WLEventWrite(_EVENT_DESCRIPTOR const &,ushort const *)
0x140072bda  mov     [rsp+0C58h+var_BD8], r14d
0x140072be2  lea     rdx, [rsp+0C58h+var_BD8]; int *
0x140072bea  lea     rcx, aGlobalWinlogon_2; "Global\\WinLogon_FirstShellLaunch"
0x140072bf1  call    ?_IsFirstToSetEvent@@YAKPEBGAEAH@Z; _IsFirstToSetEvent(ushort const *,int &)
0x140072bf6  mov     [rsp+0C58h+var_BE4], eax
0x140072bfa  test    eax, eax
0x140072bfc  jz      short loc_140072C2E
0x140072bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140072c05  cmp     rcx, rbx
0x140072c08  jz      short loc_140072C29
0x140072c0a  test    [rcx+1Ch], esi
0x140072c0d  jz      short loc_140072C29
0x140072c0f  cmp     byte ptr [rcx+19h], 3
0x140072c13  jb      short loc_140072C29
0x140072c15  mov     edx, 0D5h
0x140072c1a  mov     r9d, eax
0x140072c1d  mov     r8, r15
0x140072c20  mov     rcx, [rcx+10h]
0x140072c24  call    WPP_SF_d
0x140072c29  mov     [rsp+0C58h+var_BE4], r14d
0x140072c2e  cmp     [rsp+0C58h+var_BD8], r14d
0x140072c36  jz      short loc_140072C54
0x140072c38  test    cs:?g_Diagnostics_Status@@3UDiagnostics_Status@@A, 4; Diagnostics_Status g_Diagnostics_Status
0x140072c3f  jnz     short loc_140072C54
0x140072c41  lea     rcx, WLDiagEvt_UserShellLaunch_Info; struct _EVENT_DESCRIPTOR *
0x140072c48  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140072c4d  or      cs:?g_Diagnostics_Status@@3UDiagnostics_Status@@A, 4; Diagnostics_Status g_Diagnostics_Status
0x140072c54  mov     rcx, [r13+10h]
0x140072c58  add     rcx, 40h ; '@'; lpSystemTimeAsFileTime
0x140072c5c  call    cs:__imp_GetSystemTimeAsFileTime
0x140072c62  mov     rax, [r13+10h]
0x140072c66  cmp     [rax+94h], r12d
0x140072c6d  setz    bl
0x140072c70  mov     [rsp+0C58h+var_BF7], bl
0x140072c74  jz      loc_140072D17
0x140072c7a  xor     edx, edx; Val
0x140072c7c  mov     r8d, 0A68h; Size
0x140072c82  lea     rcx, [rsp+0C58h+var_AA8]; void *
0x140072c8a  call    memset_0
0x140072c8f  mov     [rsp+0C58h+var_BC8], r14d
0x140072c97  call    IsWinStationConnectAndLockDesktopPresent
0x140072c9c  test    al, al
0x140072c9e  jz      short loc_140072D17
0x140072ca0  lea     rax, [rsp+0C58h+var_BC8]
0x140072ca8  mov     qword ptr [rsp+0C58h+bInheritHandle], rax
0x140072cad  mov     [rsp+0C58h+dwDesiredAccess], 0A68h
0x140072cb5  lea     r9, [rsp+0C58h+var_AA8]
0x140072cbd  mov     r8d, r12d
0x140072cc0  or      edx, 0FFFFFFFFh
0x140072cc3  xor     ecx, ecx
0x140072cc5  call    cs:__imp_WinStationQueryInformationW
0x140072ccb  test    al, al
0x140072ccd  jz      short loc_140072D17
0x140072ccf  cmp     r14w, [rsp+0C58h+var_7B6]
0x140072cd8  jz      short loc_140072D17
0x140072cda  lea     rax, [rsp+0C58h+var_7B6]
0x140072ce2  or      r8, 0FFFFFFFFFFFFFFFFh
0x140072ce6  inc     r8
0x140072ce9  cmp     [rax+r8*2], r14w
0x140072cee  jnz     short loc_140072CE6
0x140072cf0  lea     rdx, [rsp+0C58h+var_7B6]
  ... truncated ...
```
