# WLGeneric_Welcome_Execute(_StateMachineCallContext *)

- ea: `0x1400858e0`
- end: `0x14008623a`
- name: `?WLGeneric_Welcome_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `2394`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `36`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400028cc`
- `0x140004f20`
- `0x1400057f4`
- `0x1400060d0`
- `0x140010330`
- `0x140010514`
- `0x140010de4`
- `0x140012164`
- `0x140012c24`
- `0x140014470`
- `0x1400160c4`
- `0x140016f30`
- `0x14002ba10`
- `0x1400333b0`
- `0x140034270`
- `0x140034700`
- `0x140037608`
- `0x140038454`
- `0x140041c34`
- `0x140044800`
- `0x14004eb98`
- `0x14004f830`
- `0x1400505c4`
- `0x140050984`
- `0x140053720`
- `0x140055ba4`
- `0x14005b630`
- `0x14005d714`
- `0x14007d084`
- `0x1400840e4`
- `0x1400841c0`
- `0x1400846a4`
- `0x140084730`
- `0x1400847bc`
- `0x1400858e0`
- `0x140089844`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140085c81`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140085c81`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140085d08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140085d08`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140085e2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140085e2f`
- `ntdll!RtlQueryResourcePolicy` at `0x140085d3f`
- `ntdll!RtlQueryResourcePolicy` at `0x140085d3f`
- `ext-ms-win-ntuser-private-l1-1-0!UpdatePerUserSystemParameters` at `0x140085b6d`
- `ext-ms-win-ntuser-private-l1-1-0!UpdatePerUserSystemParameters` at `0x140085ba3`
- `ext-ms-win-ntuser-private-l1-1-0!UpdatePerUserSystemParameters` at `0x140085b6d`
- `ext-ms-win-ntuser-private-l1-1-0!UpdatePerUserSystemParameters` at `0x140085ba3`
- `ext-ms-win-sysmain-pfapi-l1-1-0!PfRpcSyncPrefetchforBoot` at `0x140085d7e`
- `ext-ms-win-sysmain-pfapi-l1-1-0!PfRpcSyncPrefetchforBoot` at `0x140085d7e`

## string_xrefs

- `0x140085cfa`: `System\CurrentControlSet\Services\RdyBoost\Diagnostics`
- `0x140085cf3`: `ReadyBootTrainingCountSinceLastServicing`
- `0x14008615d`: `WluiDisplayWelcome_WaitForDismiss`
- `0x14008617b`: `WluiDisplayWelcome_WaitForDismiss`
- `0x140086095`: `WluiDisplayWelcome`
- `0x1400860f8`: `WluiDisplayWelcome`

## pseudocode

```c
__int64 __fastcall WLGeneric_Welcome_Execute(struct _StateMachineCallContext *a1)
{
  __int64 v1; // rsi
  int v2; // r12d
  unsigned __int8 v3; // dl
  CUser *v4; // rcx
  _DWORD *v5; // rax
  int v6; // edx
  unsigned __int8 v7; // dl
  unsigned int v8; // r15d
  ULONG v9; // edx
  unsigned __int128 v10; // rax
  char v11; // cl
  unsigned __int64 v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // r15
  __int64 v15; // r15
  char v16; // r8
  int v17; // ecx
  int v18; // r9d
  __int64 v19; // rcx
  int v20; // edi
  CUser *v21; // rcx
  __int64 v22; // rdx
  int v23; // r15d
  unsigned int v24; // edi
  __int64 v25; // rdx
  __int64 v26; // rdx
  unsigned int v27; // edi
  unsigned int v28; // edi
  char pvData[8]; // [rsp+40h] [rbp-98h] BYREF
  ULONGLONG TickCount64; // [rsp+48h] [rbp-90h] BYREF
  int v32; // [rsp+50h] [rbp-88h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-84h] BYREF
  __int64 v34; // [rsp+58h] [rbp-80h] BYREF
  struct _StateMachineCallContext *v35; // [rsp+60h] [rbp-78h]
  struct _GUID v36; // [rsp+68h] [rbp-70h] BYREF
  _OWORD v37[2]; // [rsp+78h] [rbp-60h] BYREF

  v35 = a1;
  v1 = *((_QWORD *)a1 + 1);
  v2 = 0;
  WLEventWrite(&WLEvt_DisplayWelcomeScreen_Start);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *(_DWORD **)(v1 + 16);
  if ( v5[60] )
  {
    if ( v4 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 4u )
      WPP_SF_(*((_QWORD *)v4 + 2), 32, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
    RecordBlackboxInfo(L"WaitForLsmSyncEventOnSpecialHiberbootSession", 1, (struct _WLSM_GLOBAL_CONTEXT *)v1);
    CSession::WaitForLsmSyncEvent(*(CSession **)(v1 + 16));
    RecordBlackboxInfo(L"WaitForLsmSyncEventOnSpecialHiberbootSession", 0, (struct _WLSM_GLOBAL_CONTEXT *)v1);
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
    }
  }
  else if ( v5[62] )
  {
    if ( v5[64] )
    {
      if ( v4 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 4u )
        WPP_SF_(*((_QWORD *)v4 + 2), 34, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
      *(_DWORD *)(*(_QWORD *)(v1 + 16) + 248LL) = 0;
      GetSwitchUserCredentials((struct _WLSM_GLOBAL_CONTEXT *)v1, 0);
      WinlogonProvider::UserSwitchReturnedToWelcomeLockscreen();
    }
    else
    {
      if ( v4 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 4u )
        WPP_SF_(*((_QWORD *)v4 + 2), 35, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
      RecordBlackboxInfo(L"UserSwitchRecievedLsmEvent", 1, (struct _WLSM_GLOBAL_CONTEXT *)v1);
      CSession::WaitForLsmSyncEvent(*(CSession **)(v1 + 16));
      RecordBlackboxInfo(L"UserSwitchRecievedLsmEvent", 0, (struct _WLSM_GLOBAL_CONTEXT *)v1);
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
      }
      *(_DWORD *)(*(_QWORD *)(v1 + 16) + 256LL) = 1;
      WinlogonProvider::UserSwitchRecievedLsmEvent();
    }
  }
  if ( CallCheckForHiberbootRpc(0, v3) )
  {
    CSession::SwitchDesktop(*(_QWORD *)(v1 + 16), 2, 0, 0, 0);
    SuspendComputer(1, v6, 1, 0);
    *(_DWORD *)(*(_QWORD *)(v1 + 16) + 240LL) = 0;
    if ( (unsigned __int8)IsLoadLocalFontsPresent() )
    {
      WLEventWrite(&WLEvt_UpdatePerUserSystemParameters_Start, 0);
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
      }
      if ( !(unsigned int)UpdatePerUserSystemParameters(16)
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
      }
      if ( !(unsigned int)UpdatePerUserSystemParameters(0)
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
      }
      WLEventWrite(&WLEvt_UpdatePerUserSystemParameters_Stop, 0);
    }
    v2 = 1;
    CallCheckForHiberbootRpc(1u, v7);
    *(_DWORD *)(*(_QWORD *)(v1 + 16) + 224LL) = 0;
    v8 = WinLogonBootShell(1);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids, v8);
      }
      v9 = 43;
      if ( v8 != 641 )
        v9 = 39;
      InternalInitiateShutdown(0, v9, 0x80020000, 0, 1);
    }
    RegDeleteKeyExW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\AutoLogonChecked",
      0,
      0);
  }
  if ( *(_DWORD *)(*(_QWORD *)(v1 + 16) + 172LL) && (g_Diagnostics_Status & 1) == 0 )
  {
    v36.Data1 = 1729382729;
    *(_DWORD *)&v36.Data2 = 1213813042;
    *(_DWORD *)v36.Data4 = 933705344;
    *(_DWORD *)&v36.Data4[4] = -668649292;
    *(_DWORD *)pvData = 0;
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\RdyBoost\\Diagnostics",
           L"ReadyBootTrainingCountSinceLastServicing",
           0x18u,
           0,
           pvData,
           &pcbData) )
    {
      *(_DWORD *)pvData = 0;
    }
    LOBYTE(v12) = 0;
    if ( *(_DWORD *)pvData
      && (LODWORD(TickCount64) = 0, (int)RtlQueryResourcePolicy(2, 0, &TickCount64, 4) >= 0)
      && (_DWORD)TickCount64 == 10 )
    {
      v13 = MEMORY[0x7FFE03B0];
      v14 = MEMORY[0x7FFE0008];
      while ( v13 != MEMORY[0x7FFE03B0] )
      {
        _mm_pause();
        v13 = MEMORY[0x7FFE03B0];
        v14 = MEMORY[0x7FFE0008];
      }
      v15 = v14 - v13;
      v16 = PfRpcSyncPrefetchforBoot();
      v11 = MEMORY[0x7FFE03B0];
      v10 = (unsigned __int64)(MEMORY[0x7FFE0008] - MEMORY[0x7FFE03B0] - v15) * (unsigned __int128)0x346DC5D63886594BuLL;
      v12 = (MEMORY[0x7FFE0008] - MEMORY[0x7FFE03B0] - v15) / 0x2710uLL;
    }
    else
    {
      v16 = 50;
    }
    WLEventWriteStartStopScenario(
      v11,
      *((const struct _EVENT_DESCRIPTOR **)&v10 + 1),
      &v36,
      *(_DWORD *)(*(_QWORD *)(v1 + 16) + 88LL),
      pvData[0],
      v16,
      v12);
    v37[0] = 0;
    WLGetTSActivityId(v37);
    if ( (unsigned int)dword_1400CF778 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
    {
      TickCount64 = GetTickCount64();
      v34 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v17,
        (unsigned int)qword_1400BD660,
        (unsigned int)v37,
        v18,
        (__int64)&v34,
        (__int64)&TickCount64);
    }
    g_Diagnostics_Status |= 1u;
  }
  if ( v2 )
  {
    RecordBlackboxInfo(L"WluiInformLogonUI", 1, (struct _WLSM_GLOBAL_CONTEXT *)v1);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
    {
      CallWithHangTimeout::CallWithHangTimeout(v37, 0);
      WluiInformLogonUI(2, 1);
      CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v37);
    }
    else
    {
      WluiInformLogonUI(2, 1);
    }
    RecordBlackboxInfo(L"WluiInformLogonUI", 0, (struct _WLSM_GLOBAL_CONTEXT *)v1);
  }
  RecordBlackboxInfo(L"WluiReleaseContext", 1, (struct _WLSM_GLOBAL_CONTEXT *)v1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
  {
    CallWithHangTimeout::CallWithHangTimeout(v37, 0);
    WluiReleaseContext();
    CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v37);
  }
  else
  {
    WluiReleaseContext();
  }
  RecordBlackboxInfo(L"WluiReleaseContext", 0, (struct _WLSM_GLOBAL_CONTEXT *)v1);
  CGlobalStore::FreeCredentials(*(CGlobalStore **)v1);
  v32 = 0;
  v19 = *(_QWORD *)(v1 + 16);
  v20 = *(_DWORD *)(v19 + 312) != 0 ? 4 : 0;
  LODWORD(TickCount64) = v20;
  if ( g_dwCreateSessionRet == 1641 )
  {
    WlDisplayStatusByResourceId(1205, 7, 16, 0);
    return 0;
  }
  *(_DWORD *)(v19 + 228) = *((_DWORD *)v35 + 16) == 24;
  if ( *(_DWORD *)(*(_QWORD *)(v1 + 16) + 248LL) )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_124;
    }
    v22 = 41;
LABEL_87:
    WPP_SF_(*((_QWORD *)v21 + 2), v22, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
LABEL_124:
    *(_DWORD *)pvData = WlStateMachineSetSignal(0x29u, 0);
    return 0;
  }
  if ( (unsigned int)CandidateAccountManagerPolicy::IsAutoAadConnectEnabled() && dword_1400D1898 )
  {
    dword_1400D1898 = 0;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_124;
    }
    v22 = 42;
    goto LABEL_87;
  }
  v23 = IsSASRequired((struct _WLSM_GLOBAL_CONTEXT *)v1);
  if ( v23 )
  {
    v20 |= 1u;
    LODWORD(TickCount64) = v20;
  }
  v24 = v20 | 0x10;
  LODWORD(TickCount64) = v24;
  if ( g_fLaunchedFirstLogonAnimation )
    goto LABEL_124;
  if ( v23 || !(unsigned int)IsLockScreenDisabled((struct _WLSM_GLOBAL_CONTEXT *)v1, 0) )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
    }
    RecordBlackboxInfo(L"WluiDisplayWelcome", 1, (struct _WLSM_GLOBAL_CONTEXT *)v1);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
    {
      CallWithHangTimeout::CallWithHangTimeout(v37, 0);
      v27 = WluiDisplayWelcome(v24, v26, &v32);
      *(_DWORD *)pvData = v27;
      CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v37);
    }
    else
    {
      v27 = WluiDisplayWelcome(v24, v25, &v32);
      *(_DWORD *)pvData = v27;
    }
    RecordBlackboxInfo(L"WluiDisplayWelcome", 0, (struct _WLSM_GLOBAL_CONTEXT *)v1);
    pcbData = 0;
    WinlogonProvider::WluiDisplayWelcome<enum LockScreenType,enum _WLUI_REQUEST_FLAGS &,unsigned long &>(
      &pcbData,
      &TickCount64,
      pvData);
    if ( v27 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids, v27);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
      }
      RecordBlackboxInfo(L"WluiDisplayWelcome_WaitForDismiss", 1, (struct _WLSM_GLOBAL_CONTEXT *)v1);
      v28 = WluiWaitForLockScreenDismiss(0);
      *(_DWORD *)pvData = v28;
      RecordBlackboxInfo(L"WluiDisplayWelcome_WaitForDismiss", 0, (struct _WLSM_GLOBAL_CONTEXT *)v1);
      if ( v28
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids, v28);
      }
      WinlogonProvider::WluiDisplayWelcome_WaitForDismiss<unsigned long &>(pvData);
    }
  }
  if ( g_fLaunchedFirstLogonAnimation || !v23 || v32 )
    goto LABEL_124;
  return 0;
}

```

## disassembly

```asm
0x1400858e0  push    rbx
0x1400858e2  push    rsi
0x1400858e3  push    rdi
0x1400858e4  push    r12
0x1400858e6  push    r14
0x1400858e8  push    r15
0x1400858ea  sub     rsp, 0A8h
0x1400858f1  mov     rax, cs:__security_cookie
0x1400858f8  xor     rax, rsp
0x1400858fb  mov     [rsp+0D8h+var_40], rax
0x140085903  mov     [rsp+0D8h+var_78], rcx
0x140085908  mov     rsi, [rcx+8]
0x14008590c  xor     r15d, r15d
0x14008590f  mov     r12d, r15d
0x140085912  lea     rcx, WLEvt_DisplayWelcomeScreen_Start; struct _EVENT_DESCRIPTOR *
0x140085919  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x14008591e  lea     rdi, WPP_GLOBAL_Control
0x140085925  mov     rcx, cs:WPP_GLOBAL_Control
0x14008592c  cmp     rcx, rdi
0x14008592f  jz      short loc_140085960
0x140085931  test    dword ptr [rcx+1Ch], 100h
0x140085938  jz      short loc_140085960
0x14008593a  lea     r14, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids
0x140085941  cmp     byte ptr [rcx+19h], 4
0x140085945  jb      short loc_140085967
0x140085947  lea     edx, [r15+1Fh]
0x14008594b  mov     r8, r14
0x14008594e  mov     rcx, [rcx+10h]
0x140085952  call    WPP_SF_
0x140085957  mov     rcx, cs:WPP_GLOBAL_Control
0x14008595e  jmp     short loc_140085967
0x140085960  lea     r14, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids
0x140085967  mov     rax, [rsi+10h]
0x14008596b  cmp     [rax+0F0h], r15d
0x140085972  jz      loc_140085A00
0x140085978  mov     ebx, 1
0x14008597d  cmp     rcx, rdi
0x140085980  jz      short loc_14008599C
0x140085982  test    [rcx+1Ch], bl
0x140085985  jz      short loc_14008599C
0x140085987  cmp     byte ptr [rcx+19h], 4
0x14008598b  jb      short loc_14008599C
0x14008598d  lea     edx, [rbx+1Fh]
0x140085990  mov     r8, r14
0x140085993  mov     rcx, [rcx+10h]
0x140085997  call    WPP_SF_
0x14008599c  mov     r8, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x14008599f  mov     edx, ebx; int
0x1400859a1  lea     rcx, aWaitforlsmsync; "WaitForLsmSyncEventOnSpecialHiberbootSe"...
0x1400859a8  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x1400859ad  mov     rcx, [rsi+10h]; this
0x1400859b1  call    ?WaitForLsmSyncEvent@CSession@@QEAAXXZ; CSession::WaitForLsmSyncEvent(void)
0x1400859b6  mov     r8, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x1400859b9  xor     edx, edx; int
0x1400859bb  lea     rcx, aWaitforlsmsync; "WaitForLsmSyncEventOnSpecialHiberbootSe"...
0x1400859c2  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x1400859c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400859ce  cmp     rcx, rdi
0x1400859d1  jz      loc_140085AE6
0x1400859d7  test    [rcx+1Ch], bl
0x1400859da  jz      loc_140085AE6
0x1400859e0  cmp     byte ptr [rcx+19h], 4
0x1400859e4  jb      loc_140085AE6
0x1400859ea  mov     edx, 21h ; '!'
0x1400859ef  mov     r8, r14
0x1400859f2  mov     rcx, [rcx+10h]
0x1400859f6  call    WPP_SF_
0x1400859fb  jmp     loc_140085AE6
0x140085a00  cmp     [rax+0F8h], r15d
0x140085a07  jz      loc_140085AE1
0x140085a0d  cmp     [rax+100h], r15d
0x140085a14  jz      short loc_140085A59
0x140085a16  mov     ebx, 1
0x140085a1b  cmp     rcx, rdi
0x140085a1e  jz      short loc_140085A3A
0x140085a20  test    [rcx+1Ch], bl
0x140085a23  jz      short loc_140085A3A
0x140085a25  cmp     byte ptr [rcx+19h], 4
0x140085a29  jb      short loc_140085A3A
0x140085a2b  lea     edx, [rbx+21h]
0x140085a2e  mov     r8, r14
0x140085a31  mov     rcx, [rcx+10h]
0x140085a35  call    WPP_SF_
0x140085a3a  mov     rax, [rsi+10h]
0x140085a3e  mov     [rax+0F8h], r15d
0x140085a45  xor     edx, edx; struct _CRED_PROV_CREDENTIAL *
0x140085a47  mov     rcx, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x140085a4a  call    ?GetSwitchUserCredentials@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@PEAU_CRED_PROV_CREDENTIAL@@@Z; GetSwitchUserCredentials(_WLSM_GLOBAL_CONTEXT *,_CRED_PROV_CREDENTIAL *)
0x140085a4f  call    ?UserSwitchReturnedToWelcomeLockscreen@WinlogonProvider@@SAXXZ; WinlogonProvider::UserSwitchReturnedToWelcomeLockscreen(void)
0x140085a54  jmp     loc_140085AE6
0x140085a59  mov     ebx, 1
0x140085a5e  cmp     rcx, rdi
0x140085a61  jz      short loc_140085A7D
0x140085a63  test    [rcx+1Ch], bl
0x140085a66  jz      short loc_140085A7D
0x140085a68  cmp     byte ptr [rcx+19h], 4
0x140085a6c  jb      short loc_140085A7D
0x140085a6e  lea     edx, [rbx+22h]
0x140085a71  mov     r8, r14
0x140085a74  mov     rcx, [rcx+10h]
0x140085a78  call    WPP_SF_
0x140085a7d  mov     r8, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x140085a80  mov     edx, ebx; int
0x140085a82  lea     rcx, aUserswitchreci; "UserSwitchRecievedLsmEvent"
0x140085a89  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140085a8e  mov     rcx, [rsi+10h]; this
0x140085a92  call    ?WaitForLsmSyncEvent@CSession@@QEAAXXZ; CSession::WaitForLsmSyncEvent(void)
0x140085a97  mov     r8, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x140085a9a  xor     edx, edx; int
0x140085a9c  lea     rcx, aUserswitchreci; "UserSwitchRecievedLsmEvent"
0x140085aa3  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140085aa8  mov     rcx, cs:WPP_GLOBAL_Control
0x140085aaf  cmp     rcx, rdi
0x140085ab2  jz      short loc_140085AD0
0x140085ab4  test    [rcx+1Ch], bl
0x140085ab7  jz      short loc_140085AD0
0x140085ab9  cmp     byte ptr [rcx+19h], 4
0x140085abd  jb      short loc_140085AD0
0x140085abf  mov     edx, 24h ; '$'
0x140085ac4  mov     r8, r14
0x140085ac7  mov     rcx, [rcx+10h]
0x140085acb  call    WPP_SF_
0x140085ad0  mov     rax, [rsi+10h]
0x140085ad4  mov     [rax+100h], ebx
0x140085ada  call    ?UserSwitchRecievedLsmEvent@WinlogonProvider@@SAXXZ; WinlogonProvider::UserSwitchRecievedLsmEvent(void)
0x140085adf  jmp     short loc_140085AE6
0x140085ae1  mov     ebx, 1
0x140085ae6  xor     ecx, ecx; unsigned __int8
0x140085ae8  call    ?CallCheckForHiberbootRpc@@YAHEE@Z; CallCheckForHiberbootRpc(uchar,uchar)
0x140085aed  test    eax, eax
0x140085aef  jz      loc_140085C8A
0x140085af5  mov     dword ptr [rsp+0D8h+pdwType], r15d
0x140085afa  xor     r9d, r9d
0x140085afd  xor     r8d, r8d
0x140085b00  lea     edx, [r9+2]
0x140085b04  mov     rcx, [rsi+10h]
0x140085b08  call    ?SwitchDesktop@CSession@@QEAAXW4_DESKTOPID@@PEAHKK@Z; CSession::SwitchDesktop(_DESKTOPID,int *,ulong,ulong)
0x140085b0d  xor     r9d, r9d; int
0x140085b10  mov     r8d, ebx; int
0x140085b13  mov     ecx, ebx; int
0x140085b15  call    ?SuspendComputer@@YAKHHHH@Z; SuspendComputer(int,int,int,int)
0x140085b1a  mov     rax, [rsi+10h]
0x140085b1e  mov     [rax+0F0h], r15d
0x140085b25  call    IsLoadLocalFontsPresent
0x140085b2a  test    al, al
0x140085b2c  jz      loc_140085BF0
0x140085b32  xor     edx, edx; unsigned int
0x140085b34  lea     rcx, WLEvt_UpdatePerUserSystemParameters_Start; struct _EVENT_DESCRIPTOR *
0x140085b3b  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@K@Z; WLEventWrite(_EVENT_DESCRIPTOR const &,ulong)
0x140085b40  mov     rcx, cs:WPP_GLOBAL_Control
0x140085b47  cmp     rcx, rdi
0x140085b4a  jz      short loc_140085B68
0x140085b4c  test    [rcx+1Ch], bl
0x140085b4f  jz      short loc_140085B68
0x140085b51  cmp     byte ptr [rcx+19h], 4
0x140085b55  jb      short loc_140085B68
0x140085b57  mov     edx, 25h ; '%'
0x140085b5c  mov     r8, r14
0x140085b5f  mov     rcx, [rcx+10h]
0x140085b63  call    WPP_SF_
0x140085b68  mov     ecx, 10h
0x140085b6d  call    cs:__imp_UpdatePerUserSystemParameters
0x140085b73  test    eax, eax
0x140085b75  jnz     short loc_140085BA1
0x140085b77  mov     rcx, cs:WPP_GLOBAL_Control
0x140085b7e  cmp     rcx, rdi
0x140085b81  jz      short loc_140085BA1
0x140085b83  test    dword ptr [rcx+1Ch], 1000h
0x140085b8a  jz      short loc_140085BA1
0x140085b8c  cmp     byte ptr [rcx+19h], 2
0x140085b90  jb      short loc_140085BA1
0x140085b92  lea     edx, [rax+26h]
0x140085b95  mov     r8, r14
0x140085b98  mov     rcx, [rcx+10h]
0x140085b9c  call    WPP_SF_
0x140085ba1  xor     ecx, ecx
0x140085ba3  call    cs:__imp_UpdatePerUserSystemParameters
0x140085ba9  test    eax, eax
0x140085bab  jnz     short loc_140085BDB
0x140085bad  mov     rcx, cs:WPP_GLOBAL_Control
0x140085bb4  cmp     rcx, rdi
0x140085bb7  jz      short loc_140085BDB
0x140085bb9  test    dword ptr [rcx+1Ch], 1000h
0x140085bc0  jz      short loc_140085BDB
0x140085bc2  cmp     byte ptr [rcx+19h], 2
0x140085bc6  jb      short loc_140085BDB
0x140085bc8  lea     edi, [rax+27h]
0x140085bcb  mov     edx, edi
0x140085bcd  mov     r8, r14
0x140085bd0  mov     rcx, [rcx+10h]
0x140085bd4  call    WPP_SF_
0x140085bd9  jmp     short loc_140085BE0
0x140085bdb  mov     edi, 27h ; '''
0x140085be0  xor     edx, edx; unsigned int
0x140085be2  lea     rcx, WLEvt_UpdatePerUserSystemParameters_Stop; struct _EVENT_DESCRIPTOR *
0x140085be9  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@K@Z; WLEventWrite(_EVENT_DESCRIPTOR const &,ulong)
0x140085bee  jmp     short loc_140085BF5
0x140085bf0  mov     edi, 27h ; '''
0x140085bf5  mov     r12d, ebx
0x140085bf8  mov     cl, bl; unsigned __int8
0x140085bfa  call    ?CallCheckForHiberbootRpc@@YAHEE@Z; CallCheckForHiberbootRpc(uchar,uchar)
0x140085bff  mov     rax, [rsi+10h]
0x140085c03  mov     [rax+0E0h], r15d
0x140085c0a  mov     ecx, ebx; int
0x140085c0c  call    ?WinLogonBootShell@@YAKH@Z; WinLogonBootShell(int)
0x140085c11  mov     r15d, eax
0x140085c14  test    eax, eax
0x140085c16  jz      short loc_140085C6D
0x140085c18  mov     rcx, cs:WPP_GLOBAL_Control
0x140085c1f  lea     rax, WPP_GLOBAL_Control
0x140085c26  cmp     rcx, rax
0x140085c29  jz      short loc_140085C4A
0x140085c2b  test    [rcx+1Ch], bl
0x140085c2e  jz      short loc_140085C4A
0x140085c30  cmp     byte ptr [rcx+19h], 4
0x140085c34  jb      short loc_140085C4A
0x140085c36  mov     edx, 28h ; '('
0x140085c3b  mov     r9d, r15d
0x140085c3e  mov     r8, r14
0x140085c41  mov     rcx, [rcx+10h]
0x140085c45  call    WPP_SF_d
0x140085c4a  mov     edx, 2Bh ; '+'
0x140085c4f  cmp     r15d, 281h
0x140085c56  cmovnz  edx, edi; unsigned int
0x140085c59  mov     dword ptr [rsp+0D8h+pdwType], ebx; int
0x140085c5d  xor     r9d, r9d; unsigned __int16 *
0x140085c60  xor     ecx, ecx; unsigned __int8
0x140085c62  mov     r8d, 80020000h; unsigned int
0x140085c68  call    ?InternalInitiateShutdown@@YAKEKKPEAGH@Z; InternalInitiateShutdown(uchar,ulong,ulong,ushort *,int)
0x140085c6d  xor     r9d, r9d; Reserved
0x140085c70  xor     r8d, r8d; samDesired
0x140085c73  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Windows NT\\Curren"...
0x140085c7a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140085c81  call    cs:__imp_RegDeleteKeyExW
0x140085c87  xor     r15d, r15d
0x140085c8a  mov     rax, [rsi+10h]
0x140085c8e  cmp     [rax+0ACh], r15d
0x140085c95  jz      loc_140085E6E
0x140085c9b  test    cs:?g_Diagnostics_Status@@3UDiagnostics_Status@@A, bl; Diagnostics_Status g_Diagnostics_Status
0x140085ca1  jnz     loc_140085E6E
0x140085ca7  mov     [rsp+0D8h+var_70.Data1], 67144949h
0x140085caf  mov     dword ptr [rsp+0D8h+var_70.Data2], 48595132h
0x140085cb7  mov     dword ptr [rsp+0D8h+var_70.Data4], 37A73680h
0x140085cbf  mov     dword ptr [rsp+0D8h+var_70.Data4+4], 0D82538B4h
0x140085cc7  mov     dword ptr [rsp+0D8h+var_98], r15d
0x140085ccc  mov     [rsp+0D8h+var_84], 4
0x140085cd4  lea     rax, [rsp+0D8h+var_84]
0x140085cd9  mov     [rsp+0D8h+pcbData], rax; pcbData
0x140085cde  lea     rax, [rsp+0D8h+var_98]
0x140085ce3  mov     [rsp+0D8h+pvData], rax; pvData
0x140085ce8  mov     [rsp+0D8h+pdwType], r15; pdwType
0x140085ced  mov     r9d, 18h; dwFlags
0x140085cf3  lea     r8, aReadyboottrain; "ReadyBootTrainingCountSinceLastServicin"...
0x140085cfa  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\Rd"...
0x140085d01  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140085d08  call    cs:__imp_RegGetValueW
0x140085d0e  test    r15b, r15b
0x140085d11  jnz     short loc_140085D1C
0x140085d13  test    eax, eax
0x140085d15  jz      short loc_140085D1C
0x140085d17  mov     dword ptr [rsp+0D8h+var_98], r15d
0x140085d1c  mov     rdi, r15
0x140085d1f  cmp     dword ptr [rsp+0D8h+var_98], r15d
0x140085d24  jz      loc_140085DCF
0x140085d2a  mov     dword ptr [rsp+0D8h+var_90], r15d
0x140085d2f  mov     r9d, 4
0x140085d35  lea     r8, [rsp+0D8h+var_90]
0x140085d3a  xor     edx, edx
0x140085d3c  lea     ecx, [rdx+2]
0x140085d3f  call    cs:__imp_RtlQueryResourcePolicy
0x140085d45  test    eax, eax
0x140085d47  js      loc_140085DCF
0x140085d4d  cmp     dword ptr [rsp+0D8h+var_90], 0Ah
0x140085d52  jnz     short loc_140085DCF
0x140085d54  mov     edx, 7FFE03B0h
0x140085d59  mov     rcx, [rdx]
0x140085d5c  mov     r15, ds:7FFE0008h
0x140085d64  mov     edi, 7FFE0008h
0x140085d69  mov     rax, [rdx]
0x140085d6c  cmp     rcx, rax
0x140085d6f  jz      short loc_140085D7B
0x140085d71  pause
0x140085d73  mov     rcx, [rdx]
0x140085d76  mov     r15, [rdi]
0x140085d79  jmp     short loc_140085D69
0x140085d7b  sub     r15, rcx
0x140085d7e  call    cs:__imp_PfRpcSyncPrefetchforBoot
0x140085d84  mov     r8d, eax
0x140085d87  mov     r10d, 7FFE03B0h
0x140085d8d  mov     r9, [r10]
0x140085d90  mov     rdx, ds:7FFE0008h
0x140085d98  mov     rcx, [r10]
0x140085d9b  cmp     r9, rcx
0x140085d9e  jz      short loc_140085DB0
0x140085da0  pause
0x140085da2  mov     r9, [r10]
0x140085da5  mov     rdx, [rdi]
0x140085da8  mov     rax, [r10]
0x140085dab  cmp     r9, rax
0x140085dae  jnz     short loc_140085DA0
  ... truncated ...
```
