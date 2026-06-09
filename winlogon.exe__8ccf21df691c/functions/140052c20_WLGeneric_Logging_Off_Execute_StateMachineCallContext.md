# WLGeneric_Logging_Off_Execute(_StateMachineCallContext *)

- ea: `0x140052c20`
- end: `0x14005338f`
- name: `?WLGeneric_Logging_Off_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `1903`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400057f4`
- `0x1400060d0`
- `0x140006970`
- `0x14000be30`
- `0x140016f30`
- `0x140025738`
- `0x14002aae0`
- `0x14002ab60`
- `0x14002ba10`
- `0x1400333b0`
- `0x140034158`
- `0x140034270`
- `0x14003be1c`
- `0x14003d7d8`
- `0x14003e630`
- `0x14003eb18`
- `0x14003fbcc`
- `0x1400403d8`
- `0x140041b5c`
- `0x140041c34`
- `0x14004341c`
- `0x140050984`
- `0x140052c20`
- `0x140054590`
- `0x140055104`
- `0x140055158`
- `0x1400560f4`
- `0x140056230`
- `0x140056bd8`
- `0x14005b630`
- `0x14005d698`
- `0x140089844`
- `0x14008b244`
- `0x14008b3a4`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140052e93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140052e93`
- `ntdll!WinSqmEndSession` at `0x1400532d9`
- `ntdll!WinSqmEndSession` at `0x1400532d9`
- `ext-ms-win-gui-uxinit-l1-1-0!ThemesOnLogoff` at `0x140053009`
- `ext-ms-win-gui-uxinit-l1-1-0!ThemesOnLogoff` at `0x140053009`
- `ext-ms-win-session-winlogon-l1-1-1!ConfigureUserArso` at `0x14005315a`
- `ext-ms-win-session-winlogon-l1-1-1!ConfigureUserArso` at `0x14005315a`
- `ext-ms-win-session-winlogon-l1-1-0!NotifyInteractiveSessionLogoff` at `0x140053287`
- `ext-ms-win-session-winlogon-l1-1-0!NotifyInteractiveSessionLogoff` at `0x140053287`
- `ext-ms-win-ntuser-private-l1-1-0!UpdatePerUserSystemParameters` at `0x14005336a`
- `ext-ms-win-ntuser-private-l1-1-0!UpdatePerUserSystemParameters` at `0x14005336a`
- `ext-ms-win-ntuser-private-l1-1-0!SetWindowStationUser` at `0x140052e56`
- `ext-ms-win-ntuser-private-l1-1-0!SetWindowStationUser` at `0x140052e56`
- `ext-ms-win-ntuser-private-l1-1-1!LockWindowStation` at `0x140052cf3`
- `ext-ms-win-ntuser-private-l1-1-1!LockWindowStation` at `0x140052cf3`
- `ext-ms-win-ntuser-private-l1-1-1!UnlockWindowStation` at `0x140052ce5`
- `ext-ms-win-ntuser-private-l1-1-1!UnlockWindowStation` at `0x140052ce5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrInformUserLogoff` at `0x140052ddc`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrInformUserLogoff` at `0x140052ddc`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamCleanupDisardedCandidateAccounts` at `0x140053333`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamCleanupDisardedCandidateAccounts` at `0x140053333`
- `ext-ms-win-composition-init-l1-1-0!DwmpNotifyUserLogoff` at `0x140052f8f`
- `ext-ms-win-composition-init-l1-1-0!DwmpNotifyUserLogoff` at `0x140052fa1`
- `ext-ms-win-composition-init-l1-1-0!DwmpNotifyUserLogoff` at `0x140052f8f`
- `ext-ms-win-composition-init-l1-1-0!DwmpNotifyUserLogoff` at `0x140052fa1`
- `MPR!WNetClearConnections` at `0x140052ed6`
- `MPR!WNetClearConnections` at `0x140052ed6`

## pseudocode

```c
unsigned int __fastcall WLGeneric_Logging_Off_Execute(struct _StateMachineCallContext *a1)
{
  __int64 v2; // rbx
  unsigned int LogoffFlags; // r15d
  unsigned int v4; // eax
  int v5; // eax
  unsigned int v6; // esi
  int v7; // esi
  __int64 v8; // rdx
  void *v9; // rcx
  unsigned int v10; // eax
  void *NotifyConfig; // rax
  unsigned int v12; // eax
  CUser *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  CloudPCHelpers *v16; // rcx
  unsigned int v17; // eax
  ULONG v18; // eax
  unsigned __int8 v19; // dl
  unsigned int v20; // esi
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  unsigned int v22; // eax
  _DWORD v24[20]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v25; // [rsp+90h] [rbp+8h] BYREF
  int v26; // [rsp+98h] [rbp+10h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids);
  }
  v27 = 0;
  v2 = *((_QWORD *)a1 + 1);
  LogoffFlags = CGlobalStore::GetLogoffFlags(*(CGlobalStore **)v2);
  v26 = 0;
  AsyncLogoffSupportSetUser(0);
  CUser::GenerateLogoffInitiatedAudit(*(CUser **)(v2 + 32));
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids);
  }
  CUser::CloseHKeyCurrentUser(*(CUser **)(v2 + 32));
  UnlockWindowStation(*(_QWORD *)(*(_QWORD *)(v2 + 16) + 96LL));
  LockWindowStation(*(_QWORD *)(*(_QWORD *)(v2 + 16) + 96LL));
  v4 = WlAccessibilityOnLogoff((struct _WLSM_GLOBAL_CONTEXT *)v2);
  if ( v4
    && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids, v4);
  }
  v5 = WlSecureDesktopiShutdown();
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids,
        (unsigned int)v5);
    }
  }
  else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids);
  }
  if ( (unsigned __int8)IsUMgrLaunchShellInfrastructureHostPresent() )
  {
    RecordBlackboxInfo(L"UMgrInformUserLogoff", 1, (struct _WLSM_GLOBAL_CONTEXT *)v2);
    v6 = UMgrInformUserLogoff(*(_QWORD *)(*(_QWORD *)(v2 + 32) + 136LL));
    RecordBlackboxInfo(L"UMgrInformUserLogoff", 0, (struct _WLSM_GLOBAL_CONTEXT *)v2);
    if ( (v6 & 0x1FFF0000) == 0x70000 )
      v6 = (unsigned __int16)v6;
    if ( v6
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids, v6);
    }
  }
  SetWindowStationUser(*(_QWORD *)(*(_QWORD *)(v2 + 16) + 96LL), &v27, 0, 0);
  v7 = IsHiberboot(LogoffFlags);
  LODWORD(v25) = v7;
  if ( !(unsigned int)CUser::ImpersonateUser(*(CUser **)(v2 + 32), 0) )
  {
    v9 = *(void **)(*(_QWORD *)(v2 + 32) + 472LL);
    if ( v9
      && WaitForSingleObject(v9, 0x1Eu) == 258
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids);
    }
    v10 = WNetClearConnections(0);
    if ( v10
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids, v10);
    }
    if ( (unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent() )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids);
      }
      WLEventWrite(&WLEvt_DwmpNotifyUserLogoff_Start);
      RecordBlackboxInfo(L"DwmpNotifyUserLogoff", 1, (struct _WLSM_GLOBAL_CONTEXT *)v2);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::GetImpl'::`2'::impl) )
      {
        CallWithHangTimeout::CallWithHangTimeout(v24, 0);
        DwmpNotifyUserLogoff();
        CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v24);
      }
      else
      {
        DwmpNotifyUserLogoff();
      }
      RecordBlackboxInfo(L"DwmpNotifyUserLogoff", 0, (struct _WLSM_GLOBAL_CONTEXT *)v2);
      WLEventWrite(&WLEvt_DwmpNotifyUserLogoff_Stop);
    }
    if ( (unsigned __int8)IsThemesOnLogoffPresent() )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids);
      }
      WLEventWrite(&WLEvt_ThemesOnLogoff_Start);
      ThemesOnLogoff();
      WLEventWrite(&WLEvt_ThemesOnLogoff_Stop);
    }
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids);
    }
    v26 = 0;
    NotifyConfig = CGlobalStore::GetNotifyConfig(*(CGlobalStore **)v2, 0, 0);
    v12 = InternalNotifyExecute(
            (__int64)NotifyConfig,
            3u,
            (__int64)&v26,
            (void (__fastcall *)(_QWORD, unsigned __int16 *))DisplayMessage_Callback,
            0,
            0);
    if ( v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids, v12);
      }
    }
    CUser::StopImpersonating(v13);
  }
  if ( (LogoffFlags & 2) != 0 )
  {
    v14 = 8;
    v15 = (LogoffFlags & 0x1000000) != 0 ? 1008 : 1205;
  }
  else if ( (LogoffFlags & 9) != 0 || v7 )
  {
    v15 = 1204;
    v14 = 7;
  }
  else
  {
    LOBYTE(v8) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly>::GetImpl'::`2'::impl,
      v8);
    v15 = CloudPCHelpers::IsBootToCloudModeRegistryCheck(v16) ? 7100 : 1003;
    v14 = 5;
  }
  WlDisplayStatusByResourceId(v15, v14, 16, *(_QWORD *)(v2 + 32));
  if ( (LogoffFlags & 0x4000000) != 0 )
  {
    if ( (unsigned __int8)IsConfigureUserArsoPresent() )
    {
      v17 = ConfigureUserArso(*(_QWORD *)(*(_QWORD *)(v2 + 32) + 160LL));
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids, v17);
      }
    }
  }
  if ( (LogoffFlags & 0xB) != 0 && (LogoffFlags & 0x20000) == 0 )
  {
    v18 = LogoffFlagsToShutdownFlags(LogoffFlags) | 0x23;
    if ( (LogoffFlags & 0x2000) != 0 )
      v18 |= 0x80000000;
    v20 = InternalInitiateShutdown(0, v18, 0x500FFu, 0, 0);
    if ( v20 || CallCheckForHiberbootRpc(0, v19) )
    {
      LogoffFlags &= 0xFFFFFFF4;
      CGlobalStore::SetLogoffFlags(*(CGlobalStore **)v2, LogoffFlags);
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids, v20);
      }
    }
    v7 = v25;
  }
  if ( (unsigned __int8)IsWinLogonExtPresent() && ((LogoffFlags & 0xB) == 0 || v7) )
  {
    v25 = 0;
    v25 = *(_QWORD *)(*(_QWORD *)(v2 + 32) + 128LL);
    NotifyInteractiveSessionLogoff(&v25);
  }
  if ( qword_1400D30D8 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids,
        *(unsigned int *)(*(_QWORD *)(v2 + 16) + 88LL));
    }
    WinSqmEndSession(qword_1400D30D0);
    qword_1400D30D0 = 0;
  }
  WLEventWriteWinSqmUserSessionChange(
    &WLEvt_WinSqmUserLogoff,
    *(_DWORD *)(*(_QWORD *)(v2 + 16) + 88LL),
    *(void **)(*(_QWORD *)(v2 + 32) + 160LL));
  v21 = *(void (__fastcall ****)(_QWORD, __int64))(v2 + 32);
  if ( v21 )
    (**v21)(v21, 1);
  *(_QWORD *)(v2 + 32) = 0;
  if ( (unsigned __int8)IsCamCleanupDisardedCandidateAccountsPresent() )
  {
    v22 = CamCleanupDisardedCandidateAccounts();
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids, v22);
    }
  }
  UpdatePerUserSystemParameters(0);
  return WlStateMachineSetSignal(0, 0);
}

```

## disassembly

```asm
0x140052c20  mov     [rsp+arg_18], rbx
0x140052c25  push    rsi
0x140052c26  push    rdi
0x140052c27  push    r12
0x140052c29  push    r13
0x140052c2b  push    r15
0x140052c2d  sub     rsp, 60h
0x140052c31  mov     rbx, rcx
0x140052c34  lea     r13, WPP_GLOBAL_Control
0x140052c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140052c42  cmp     rcx, r13
0x140052c45  jz      short loc_140052C70
0x140052c47  test    dword ptr [rcx+1Ch], 100h
0x140052c4e  jz      short loc_140052C70
0x140052c50  lea     rdi, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids
0x140052c57  cmp     byte ptr [rcx+19h], 4
0x140052c5b  jb      short loc_140052C77
0x140052c5d  mov     edx, 15h
0x140052c62  mov     r8, rdi
0x140052c65  mov     rcx, [rcx+10h]
0x140052c69  call    WPP_SF_
0x140052c6e  jmp     short loc_140052C77
0x140052c70  lea     rdi, WPP_68af0a08a65633b5f576d5b8c97140f4_Traceguids
0x140052c77  xor     esi, esi
0x140052c79  mov     [rsp+88h+arg_10], rsi
0x140052c81  mov     rbx, [rbx+8]
0x140052c85  mov     rcx, [rbx]; this
0x140052c88  call    ?GetLogoffFlags@CGlobalStore@@QEAAKXZ; CGlobalStore::GetLogoffFlags(void)
0x140052c8d  mov     r15d, eax
0x140052c90  mov     [rsp+88h+arg_8], esi
0x140052c97  xor     ecx, ecx; void *
0x140052c99  call    ?AsyncLogoffSupportSetUser@@YAXPEAX@Z; AsyncLogoffSupportSetUser(void *)
0x140052c9e  mov     rcx, [rbx+20h]; this
0x140052ca2  call    ?GenerateLogoffInitiatedAudit@CUser@@QEAAKXZ; CUser::GenerateLogoffInitiatedAudit(void)
0x140052ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x140052cae  mov     r12d, 2000h
0x140052cb4  cmp     rcx, r13
0x140052cb7  jz      short loc_140052CD4
0x140052cb9  test    [rcx+1Ch], r12d
0x140052cbd  jz      short loc_140052CD4
0x140052cbf  cmp     byte ptr [rcx+19h], 4
0x140052cc3  jb      short loc_140052CD4
0x140052cc5  lea     edx, [rsi+16h]
0x140052cc8  mov     r8, rdi
0x140052ccb  mov     rcx, [rcx+10h]
0x140052ccf  call    WPP_SF_
0x140052cd4  mov     rcx, [rbx+20h]; this
0x140052cd8  call    ?CloseHKeyCurrentUser@CUser@@QEAAXXZ; CUser::CloseHKeyCurrentUser(void)
0x140052cdd  mov     rcx, [rbx+10h]
0x140052ce1  mov     rcx, [rcx+60h]
0x140052ce5  call    cs:__imp_UnlockWindowStation
0x140052ceb  mov     rcx, [rbx+10h]
0x140052cef  mov     rcx, [rcx+60h]
0x140052cf3  call    cs:__imp_LockWindowStation
0x140052cf9  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140052cfc  call    ?WlAccessibilityOnLogoff@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@@Z; WlAccessibilityOnLogoff(_WLSM_GLOBAL_CONTEXT *)
0x140052d01  test    eax, eax
0x140052d03  jz      short loc_140052D39
0x140052d05  mov     rcx, cs:WPP_GLOBAL_Control
0x140052d0c  cmp     rcx, r13
0x140052d0f  jz      short loc_140052D39
0x140052d11  test    dword ptr [rcx+1Ch], 40000h
0x140052d18  jz      short loc_140052D39
0x140052d1a  mov     r13b, 2
0x140052d1d  cmp     [rcx+19h], r13b
0x140052d21  jb      short loc_140052D3C
0x140052d23  mov     edx, 17h
0x140052d28  mov     r9d, eax
0x140052d2b  mov     r8, rdi
0x140052d2e  mov     rcx, [rcx+10h]
0x140052d32  call    WPP_SF_d
0x140052d37  jmp     short loc_140052D3C
0x140052d39  mov     r13b, 2
0x140052d3c  call    WlSecureDesktopiShutdown
0x140052d41  test    eax, eax
0x140052d43  js      short loc_140052D7A
0x140052d45  mov     rcx, cs:WPP_GLOBAL_Control
0x140052d4c  lea     rax, WPP_GLOBAL_Control
0x140052d53  cmp     rcx, rax
0x140052d56  jz      short loc_140052DB0
0x140052d58  test    dword ptr [rcx+1Ch], 1000h
0x140052d5f  jz      short loc_140052DB0
0x140052d61  cmp     byte ptr [rcx+19h], 4
0x140052d65  jb      short loc_140052DB0
0x140052d67  mov     edx, 18h
0x140052d6c  mov     r8, rdi
0x140052d6f  mov     rcx, [rcx+10h]
0x140052d73  call    WPP_SF_
0x140052d78  jmp     short loc_140052DB0
0x140052d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140052d81  lea     rdx, WPP_GLOBAL_Control
0x140052d88  cmp     rcx, rdx
0x140052d8b  jz      short loc_140052DB0
0x140052d8d  test    dword ptr [rcx+1Ch], 1000h
0x140052d94  jz      short loc_140052DB0
0x140052d96  cmp     byte ptr [rcx+19h], 3
0x140052d9a  jb      short loc_140052DB0
0x140052d9c  mov     edx, 19h
0x140052da1  mov     r9d, eax
0x140052da4  mov     r8, rdi
0x140052da7  mov     rcx, [rcx+10h]
0x140052dab  call    WPP_SF_d
0x140052db0  call    IsUMgrLaunchShellInfrastructureHostPresent
0x140052db5  test    al, al
0x140052db7  jz      loc_140052E40
0x140052dbd  mov     r8, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140052dc0  mov     edx, 1; int
0x140052dc5  lea     rcx, aUmgrinformuser_1; "UMgrInformUserLogoff"
0x140052dcc  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140052dd1  mov     rcx, [rbx+20h]
0x140052dd5  mov     rcx, [rcx+88h]
0x140052ddc  call    cs:__imp_UMgrInformUserLogoff
0x140052de2  mov     esi, eax
0x140052de4  mov     r8, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140052de7  xor     edx, edx; int
0x140052de9  lea     rcx, aUmgrinformuser_1; "UMgrInformUserLogoff"
0x140052df0  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140052df5  mov     eax, esi
0x140052df7  and     eax, 1FFF0000h
0x140052dfc  cmp     eax, 70000h
0x140052e01  jnz     short loc_140052E06
0x140052e03  movzx   esi, si
0x140052e06  test    esi, esi
0x140052e08  jz      short loc_140052E40
0x140052e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140052e11  lea     rax, WPP_GLOBAL_Control
0x140052e18  cmp     rcx, rax
0x140052e1b  jz      short loc_140052E40
0x140052e1d  test    dword ptr [rcx+1Ch], 1000h
0x140052e24  jz      short loc_140052E40
0x140052e26  cmp     [rcx+19h], r13b
0x140052e2a  jb      short loc_140052E40
0x140052e2c  mov     edx, 1Ah
0x140052e31  mov     r9d, esi
0x140052e34  mov     r8, rdi
0x140052e37  mov     rcx, [rcx+10h]
0x140052e3b  call    WPP_SF_d
0x140052e40  mov     rcx, [rbx+10h]
0x140052e44  xor     r9d, r9d
0x140052e47  xor     r8d, r8d
0x140052e4a  lea     rdx, [rsp+88h+arg_10]
0x140052e52  mov     rcx, [rcx+60h]
0x140052e56  call    cs:__imp_SetWindowStationUser
0x140052e5c  mov     ecx, r15d; unsigned int
0x140052e5f  call    ?IsHiberboot@@YAHK@Z; IsHiberboot(ulong)
0x140052e64  mov     esi, eax
0x140052e66  mov     dword ptr [rsp+88h+arg_0], eax
0x140052e6d  xor     edx, edx; int
0x140052e6f  mov     rcx, [rbx+20h]; this
0x140052e73  call    ?ImpersonateUser@CUser@@QEAAKH@Z; CUser::ImpersonateUser(int)
0x140052e78  test    eax, eax
0x140052e7a  jnz     loc_1400530D0
0x140052e80  mov     rcx, [rbx+20h]
0x140052e84  mov     rcx, [rcx+1D8h]; hHandle
0x140052e8b  test    rcx, rcx
0x140052e8e  jz      short loc_140052ED4
0x140052e90  lea     edx, [rax+1Eh]; dwMilliseconds
0x140052e93  call    cs:__imp_WaitForSingleObject
0x140052e99  cmp     eax, 102h
0x140052e9e  jnz     short loc_140052ED4
0x140052ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x140052ea7  lea     rax, WPP_GLOBAL_Control
0x140052eae  cmp     rcx, rax
0x140052eb1  jz      short loc_140052ED4
0x140052eb3  test    [rcx+1Ch], r12d
0x140052eb7  jz      short loc_140052ED4
0x140052eb9  cmp     [rcx+19h], r13b
0x140052ebd  jb      short loc_140052ED4
0x140052ebf  mov     edx, 0B3h
0x140052ec4  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140052ecb  mov     rcx, [rcx+10h]
0x140052ecf  call    WPP_SF_
0x140052ed4  xor     ecx, ecx
0x140052ed6  call    cs:__imp_WNetClearConnections
0x140052edc  test    eax, eax
0x140052ede  jz      short loc_140052F16
0x140052ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x140052ee7  lea     rdx, WPP_GLOBAL_Control
0x140052eee  cmp     rcx, rdx
0x140052ef1  jz      short loc_140052F16
0x140052ef3  test    dword ptr [rcx+1Ch], 1000h
0x140052efa  jz      short loc_140052F16
0x140052efc  cmp     [rcx+19h], r13b
0x140052f00  jb      short loc_140052F16
0x140052f02  mov     edx, 1Bh
0x140052f07  mov     r9d, eax
0x140052f0a  mov     r8, rdi
0x140052f0d  mov     rcx, [rcx+10h]
0x140052f11  call    WPP_SF_d
0x140052f16  call    IsDwmpStartWinlogonMouseThreadPresent
0x140052f1b  test    al, al
0x140052f1d  jz      loc_140052FC4
0x140052f23  mov     rcx, cs:WPP_GLOBAL_Control
0x140052f2a  lea     rax, WPP_GLOBAL_Control
0x140052f31  cmp     rcx, rax
0x140052f34  jz      short loc_140052F53
0x140052f36  test    [rcx+1Ch], r12d
0x140052f3a  jz      short loc_140052F53
0x140052f3c  cmp     byte ptr [rcx+19h], 4
0x140052f40  jb      short loc_140052F53
0x140052f42  mov     edx, 1Ch
0x140052f47  mov     r8, rdi
0x140052f4a  mov     rcx, [rcx+10h]
0x140052f4e  call    WPP_SF_
0x140052f53  lea     rcx, WLEvt_DwmpNotifyUserLogoff_Start; struct _EVENT_DESCRIPTOR *
0x140052f5a  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140052f5f  mov     r8, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140052f62  mov     edx, 1; int
0x140052f67  lea     rcx, aDwmpnotifyuser_2; "DwmpNotifyUserLogoff"
0x140052f6e  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140052f73  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::GetImpl(void)'::`2'::impl
0x140052f7a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::__private_IsEnabled(void)
0x140052f7f  test    al, al
0x140052f81  jz      short loc_140052FA1
0x140052f83  xor     edx, edx
0x140052f85  lea     rcx, [rsp+88h+var_50]
0x140052f8a  call    ??0CallWithHangTimeout@@QEAA@W4TimeoutDuration@0@@Z; CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)
0x140052f8f  call    cs:__imp_DwmpNotifyUserLogoff
0x140052f95  lea     rcx, [rsp+88h+var_50]; this
0x140052f9a  call    ??1CallWithHangTimeout@@QEAA@XZ; CallWithHangTimeout::~CallWithHangTimeout(void)
0x140052f9f  jmp     short loc_140052FA7
0x140052fa1  call    cs:__imp_DwmpNotifyUserLogoff
0x140052fa7  mov     r8, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140052faa  xor     edx, edx; int
0x140052fac  lea     rcx, aDwmpnotifyuser_2; "DwmpNotifyUserLogoff"
0x140052fb3  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140052fb8  lea     rcx, WLEvt_DwmpNotifyUserLogoff_Stop; struct _EVENT_DESCRIPTOR *
0x140052fbf  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140052fc4  call    IsThemesOnLogoffPresent
0x140052fc9  test    al, al
0x140052fcb  jz      short loc_14005301B
0x140052fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140052fd4  lea     rax, WPP_GLOBAL_Control
0x140052fdb  cmp     rcx, rax
0x140052fde  jz      short loc_140052FFD
0x140052fe0  test    [rcx+1Ch], r12d
0x140052fe4  jz      short loc_140052FFD
0x140052fe6  cmp     byte ptr [rcx+19h], 4
0x140052fea  jb      short loc_140052FFD
0x140052fec  mov     edx, 1Dh
0x140052ff1  mov     r8, rdi
0x140052ff4  mov     rcx, [rcx+10h]
0x140052ff8  call    WPP_SF_
0x140052ffd  lea     rcx, WLEvt_ThemesOnLogoff_Start; struct _EVENT_DESCRIPTOR *
0x140053004  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140053009  call    cs:__imp_ThemesOnLogoff
0x14005300f  lea     rcx, WLEvt_ThemesOnLogoff_Stop; struct _EVENT_DESCRIPTOR *
0x140053016  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x14005301b  mov     rcx, cs:WPP_GLOBAL_Control
0x140053022  lea     rax, WPP_GLOBAL_Control
0x140053029  cmp     rcx, rax
0x14005302c  jz      short loc_14005304E
0x14005302e  test    dword ptr [rcx+1Ch], 100h
0x140053035  jz      short loc_14005304E
0x140053037  cmp     byte ptr [rcx+19h], 4
0x14005303b  jb      short loc_14005304E
0x14005303d  mov     edx, 1Eh
0x140053042  mov     r8, rdi
0x140053045  mov     rcx, [rcx+10h]
0x140053049  call    WPP_SF_
0x14005304e  mov     [rsp+88h+arg_8], 0
0x140053059  xor     r8d, r8d; unsigned __int16 *
0x14005305c  xor     edx, edx; int
0x14005305e  mov     rcx, [rbx]; this
0x140053061  call    ?GetNotifyConfig@CGlobalStore@@QEAAPEAXHPEBG@Z; CGlobalStore::GetNotifyConfig(int,ushort const *)
0x140053066  mov     rcx, rax
0x140053069  mov     [rsp+88h+var_60], 0
0x140053072  mov     qword ptr [rsp+88h+var_68], 0
0x14005307b  lea     r9, ?DisplayMessage_Callback@@YAXPEAXPEBG@Z; DisplayMessage_Callback(void *,ushort const *)
0x140053082  lea     r8, [rsp+88h+arg_8]
0x14005308a  mov     edx, 3
0x14005308f  call    ?InternalNotifyExecute@@YAKPEAXW4WLNOTIFICATION_ID@@PEAT_WLN_CLIENT_PARAMS@@P6AX0PEBG@Z0PEAG@Z; InternalNotifyExecute(void *,WLNOTIFICATION_ID,_WLN_CLIENT_PARAMS *,void (*)(void *,ushort const *),void *,ushort *)
0x140053094  test    eax, eax
0x140053096  jz      short loc_1400530CB
0x140053098  mov     rcx, cs:WPP_GLOBAL_Control
0x14005309f  lea     rdx, WPP_GLOBAL_Control
0x1400530a6  cmp     rcx, rdx
0x1400530a9  jz      short loc_1400530CB
0x1400530ab  test    [rcx+1Ch], r12d
0x1400530af  jz      short loc_1400530CB
0x1400530b1  cmp     [rcx+19h], r13b
0x1400530b5  jb      short loc_1400530CB
0x1400530b7  mov     edx, 1Fh
0x1400530bc  mov     r9d, eax
0x1400530bf  mov     r8, rdi
0x1400530c2  mov     rcx, [rcx+10h]
0x1400530c6  call    WPP_SF_d
0x1400530cb  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x1400530d0  test    r13b, r15b
0x1400530d3  jz      short loc_1400530F4
0x1400530d5  mov     edx, 8
0x1400530da  mov     eax, r15d
0x1400530dd  and     eax, 1000000h
0x1400530e2  neg     eax
0x1400530e4  sbb     ecx, ecx
0x1400530e6  and     ecx, 0FFFFFF3Bh
0x1400530ec  add     ecx, 4B5h
0x1400530f2  jmp     short loc_140053130
0x1400530f4  test    r15b, 9
0x1400530f8  jnz     short loc_140053126
  ... truncated ...
```
