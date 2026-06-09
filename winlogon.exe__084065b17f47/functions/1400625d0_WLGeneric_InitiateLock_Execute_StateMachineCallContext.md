# WLGeneric_InitiateLock_Execute(_StateMachineCallContext *)

- ea: `0x1400625d0`
- end: `0x140062e14`
- name: `?WLGeneric_InitiateLock_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `2116`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `1`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140076e10`

## callees

- `0x140001178`
- `0x140004e80`
- `0x1400057f4`
- `0x1400060d0`
- `0x140006970`
- `0x140012164`
- `0x140012f6c`
- `0x1400133a0`
- `0x140014470`
- `0x1400160c4`
- `0x140016f30`
- `0x14001a618`
- `0x14002ba10`
- `0x14002d330`
- `0x1400333b0`
- `0x140037cf0`
- `0x140038300`
- `0x14003d7d8`
- `0x14003f84c`
- `0x14003fbcc`
- `0x1400403d8`
- `0x140041c34`
- `0x140041ef8`
- `0x140043db4`
- `0x140044800`
- `0x140044bbc`
- `0x14004d9f4`
- `0x14004df08`
- `0x14004e4ac`
- `0x14004e92c`
- `0x14004eb98`
- `0x14004effc`
- `0x140050554`
- `0x140050984`
- `0x140053720`
- `0x1400553b4`
- `0x14005b630`
- `0x14005d714`
- `0x140060cb0`
- `0x1400625d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140062630`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140062630`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140062ba4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140062ba4`
- `ext-ms-win-session-winlogon-notify-l1-1-0!NotifyInitiateLockExecute` at `0x140062718`
- `ext-ms-win-session-winlogon-notify-l1-1-0!NotifyInitiateLockExecute` at `0x140062718`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetLastInputInfo` at `0x140062654`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetLastInputInfo` at `0x140062654`

## pseudocode

```c
__int64 __fastcall WLGeneric_InitiateLock_Execute(struct _StateMachineCallContext *a1)
{
  char v1; // r15
  unsigned int v2; // r12d
  __int64 v3; // rbx
  unsigned int v4; // r13d
  ULONGLONG TickCount64; // rdi
  __int64 v6; // r9
  void *v7; // rdx
  unsigned int v8; // r8d
  unsigned __int8 v9; // r9
  __int64 v10; // r9
  __int64 v11; // r9
  CUser *v12; // rcx
  int v13; // r15d
  __int64 v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // r9
  void *NotifyConfig; // rax
  unsigned int v18; // eax
  CUser *v19; // rcx
  CUser *v20; // rcx
  __int64 v21; // r9
  struct _RPC_ASYNC_STATE *v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // esi
  int CloudPCMode; // edi
  unsigned __int16 *v27; // rdx
  const unsigned __int16 *v28; // r8
  int v29; // r9d
  const BYTE *v30; // rax
  BOOL v31; // ecx
  char v33; // [rsp+80h] [rbp-2B8h] BYREF
  char v34; // [rsp+81h] [rbp-2B7h] BYREF
  char v35[2]; // [rsp+82h] [rbp-2B6h] BYREF
  int v36; // [rsp+84h] [rbp-2B4h]
  PRPC_ASYNC_STATE pAsync; // [rsp+88h] [rbp-2B0h] BYREF
  int v38; // [rsp+90h] [rbp-2A8h]
  BOOL v39; // [rsp+94h] [rbp-2A4h] BYREF
  int v40; // [rsp+98h] [rbp-2A0h] BYREF
  int v41; // [rsp+9Ch] [rbp-29Ch] BYREF
  unsigned int v42; // [rsp+A0h] [rbp-298h] BYREF
  int v43; // [rsp+A4h] [rbp-294h] BYREF
  struct tagLASTINPUTINFO plii; // [rsp+A8h] [rbp-290h] BYREF
  ULONGLONG v45; // [rsp+B0h] [rbp-288h]
  const BYTE *v46; // [rsp+B8h] [rbp-280h] BYREF
  ULONGLONG v47; // [rsp+C0h] [rbp-278h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-270h] BYREF
  _OWORD v49[2]; // [rsp+D0h] [rbp-268h] BYREF
  _BYTE pvData[528]; // [rsp+F0h] [rbp-248h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = *((_QWORD *)a1 + 1);
  pAsync = (PRPC_ASYNC_STATE)*((_QWORD *)a1 + 5);
  v4 = *((_DWORD *)a1 + 12);
  v38 = *((_DWORD *)a1 + 13);
  v36 = 0;
  v45 = 0;
  TickCount64 = GetTickCount64();
  plii.dwTime = 0;
  plii.cbSize = 8;
  if ( GetLastInputInfo(&plii) )
    v45 = TickCount64 - plii.dwTime;
  if ( !v4 )
    v4 = 2;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v6);
  }
  if ( (*(_DWORD *)(*(_QWORD *)(v3 + 16) + 376LL)
     || !(unsigned int)CUser::IsLockWorkstationDisabled(*(CUser **)(v3 + 32)))
    && *(_DWORD *)(*(_QWORD *)(v3 + 16) + 148LL) != 3
    && (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl)
     || *(_DWORD *)(*(_QWORD *)(v3 + 16) + 148LL) != 4) )
  {
    if ( (unsigned __int8)IsNotifyInitiateLockExecutePresent() )
      NotifyInitiateLockExecute();
    if ( ShouldDisconnectOnLock((struct _WLSM_GLOBAL_CONTEXT *)v3)
      && WinStationDisconnectWrapper((struct _WLSM_GLOBAL_CONTEXT *)v3, v7, v8, v9) )
    {
      WlAccessibilitySwitchDesktop(v3, 2, 0, 0);
      RecordBlackboxInfo(L"WluiReleaseUI", 1, (struct _WLSM_GLOBAL_CONTEXT *)v3);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
      {
        CallWithHangTimeout::CallWithHangTimeout(v49, 0);
        WluiReleaseUI();
        CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v49);
      }
      else
      {
        WluiReleaseUI();
      }
      RecordBlackboxInfo(L"WluiReleaseUI", 0, (struct _WLSM_GLOBAL_CONTEXT *)v3);
      v2 = 1;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v10);
      }
      v36 = 1;
      CSession::ResetAutoLock(*(_QWORD *)(v3 + 16), 3, 0xFFFFFFFFLL);
LABEL_26:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_76;
    }
    if ( g_fIgnoreLockEvent )
      g_fIgnoreLockEvent = 0;
    else
      WLEventWrite(&WLDiagEvt_Lock_Start);
    CSession::SetSessionLocked(*(CSession **)(v3 + 16), 1);
    CSession::CaptureInputDesktopForLockScreen(*(CSession **)(v3 + 16));
    RecordBlackboxInfo(L"WluiInformLogonUI", 1, (struct _WLSM_GLOBAL_CONTEXT *)v3);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
    {
      CallWithHangTimeout::CallWithHangTimeout(v49, 0);
      v13 = WluiInformLogonUI(7, 2);
      CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v49);
    }
    else
    {
      v13 = WluiInformLogonUI(7, 2);
    }
    RecordBlackboxInfo(L"WluiInformLogonUI", 0, (struct _WLSM_GLOBAL_CONTEXT *)v3);
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v4, v13);
    }
    if ( (*(_DWORD *)(*(_QWORD *)(v3 + 16) + 144LL) != 2
       || !(unsigned int)IsSASRequired((struct _WLSM_GLOBAL_CONTEXT *)v3)
       && (unsigned int)IsLockScreenDisabled((struct _WLSM_GLOBAL_CONTEXT *)v3, 1)
       || (unsigned int)CSession::GetLockScreenDesktop(v14, v3) != 2)
      && !*(_DWORD *)(*(_QWORD *)(v3 + 16) + 376LL) )
    {
      WlDisplayStatusByResourceId(1006, 2u, 0x10u, *(_QWORD *)(v3 + 32));
    }
    NotifyUserPresenceOnDesktopForDMAProtection(0, (struct _WLSM_GLOBAL_CONTEXT *)v3);
    WlAccessibilitySwitchDesktop(v3, 0, 0, 0);
    v15 = CUser::ImpersonateUser(*(CUser **)(v3 + 32), 0);
    if ( v15 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v15);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v16);
      }
      NotifyConfig = CGlobalStore::GetNotifyConfig(*(CGlobalStore **)v3, 0, 0);
      v18 = InternalNotifyExecute((__int64)NotifyConfig, 4u, 0, 0, 0, 0);
      if ( v18 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v18);
        }
      }
      CUser::StopImpersonating(v19);
    }
    v20 = WPP_GLOBAL_Control;
LABEL_59:
    if ( v20 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v20 + 7) & 0x4000) != 0 && *((_BYTE *)v20 + 25) >= 5u )
      WPP_SF_(*((_QWORD *)v20 + 2), 41, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v16);
    CUser::StopUserPresencePolling(*(CUser **)(v3 + 32), 0);
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v21);
    }
    NotifyPowerMgmt(1u);
    v1 = 0;
    goto LABEL_26;
  }
  WlAccessibilitySwitchDesktop(v3, 2, 0, 0);
  RecordBlackboxInfo(L"WluiReleaseUI", 1, (struct _WLSM_GLOBAL_CONTEXT *)v3);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
  {
    CallWithHangTimeout::CallWithHangTimeout(v49, 0);
    WluiReleaseUI();
    CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v49);
  }
  else
  {
    WluiReleaseUI();
  }
  RecordBlackboxInfo(L"WluiReleaseUI", 0, (struct _WLSM_GLOBAL_CONTEXT *)v3);
  v2 = 1;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v11);
    v12 = WPP_GLOBAL_Control;
  }
  v1 = 1;
LABEL_76:
  v22 = pAsync;
  if ( pAsync )
  {
    if ( v12 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x40) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v12 + 2), 43, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v11);
      v22 = pAsync;
    }
    v23 = RpcAsyncCompleteCall(v22, 0);
    if ( v23
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v23);
    }
  }
  if ( !v2 )
  {
    v24 = ReportAuditingLog((struct _WLSM_GLOBAL_CONTEXT *)v3, 0x12C0u);
    if ( v24 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v24);
      }
    }
  }
  v25 = WlStateMachineSetSignal(v2, 0);
  CloudPCMode = CloudPCHelpers::GetCloudPCMode();
  CloudPCHelpers::GetCorrelationId(pvData, v27, v28);
  v49[0] = 0;
  WLGetTSActivityId(v49);
  if ( (unsigned int)dword_1400CF778 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
  {
    v30 = pvData;
    if ( CloudPCMode != 1 )
      v30 = &pPassword;
    v46 = v30;
    v31 = CloudPCMode == 1 && GetSharedModeType() == 1;
    v39 = v31;
    v40 = CloudPCMode;
    v47 = v45;
    v41 = v38;
    v42 = v4;
    v33 = v36;
    v34 = v1;
    v43 = *(_DWORD *)(*(_QWORD *)(v3 + 16) + 88LL);
    v35[0] = v2 ^ 1;
    LODWORD(pAsync) = v25;
    v48 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v43,
      (unsigned int)&dword_1400BB33C,
      (unsigned int)v49,
      v29,
      (__int64)&v48,
      (__int64)&pAsync,
      (__int64)v35,
      (__int64)&v43,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v47,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v46);
  }
  return v25;
}

```

## disassembly

```asm
0x1400625d0  mov     [rsp+arg_8], rbx
0x1400625d5  mov     [rsp+arg_10], rsi
0x1400625da  push    rdi
0x1400625db  push    r12
0x1400625dd  push    r13
0x1400625df  push    r14
0x1400625e1  push    r15
0x1400625e3  sub     rsp, 310h
0x1400625ea  mov     rax, cs:__security_cookie
0x1400625f1  xor     rax, rsp
0x1400625f4  mov     [rsp+338h+var_38], rax
0x1400625fc  xor     r15d, r15d
0x1400625ff  mov     r12d, r15d
0x140062602  mov     rbx, [rcx+8]
0x140062606  mov     rax, [rcx+28h]
0x14006260a  mov     [rsp+338h+pAsync], rax
0x140062612  mov     r13d, [rcx+30h]
0x140062616  mov     eax, [rcx+34h]
0x140062619  mov     [rsp+338h+var_2A8], eax
0x140062620  mov     [rsp+338h+var_2B4], r15d
0x140062628  mov     [rsp+338h+var_288], r15
0x140062630  call    cs:__imp_GetTickCount64
0x140062636  mov     rdi, rax
0x140062639  mov     qword ptr [rsp+338h+plii.cbSize], r15
0x140062641  mov     [rsp+338h+plii.cbSize], 8
0x14006264c  lea     rcx, [rsp+338h+plii]; plii
0x140062654  call    cs:__imp_GetLastInputInfo
0x14006265a  test    eax, eax
0x14006265c  jz      short loc_140062670
0x14006265e  mov     ecx, [rsp+338h+plii.dwTime]
0x140062665  sub     rdi, rcx
0x140062668  mov     [rsp+338h+var_288], rdi
0x140062670  mov     r14d, 2
0x140062676  test    r13d, r13d
0x140062679  cmovz   r13d, r14d
0x14006267d  lea     rdi, WPP_GLOBAL_Control
0x140062684  mov     rcx, cs:WPP_GLOBAL_Control
0x14006268b  cmp     rcx, rdi
0x14006268e  jz      short loc_1400626B8
0x140062690  test    dword ptr [rcx+1Ch], 100h
0x140062697  jz      short loc_1400626B8
0x140062699  lea     rsi, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x1400626a0  cmp     byte ptr [rcx+19h], 4
0x1400626a4  jb      short loc_1400626BF
0x1400626a6  lea     edx, [r14+20h]
0x1400626aa  mov     r8, rsi
0x1400626ad  mov     rcx, [rcx+10h]
0x1400626b1  call    WPP_SF_
0x1400626b6  jmp     short loc_1400626BF
0x1400626b8  lea     rsi, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x1400626bf  mov     rax, [rbx+10h]
0x1400626c3  cmp     [rax+178h], r15d
0x1400626ca  jnz     short loc_1400626DD
0x1400626cc  mov     rcx, [rbx+20h]; this
0x1400626d0  call    ?IsLockWorkstationDisabled@CUser@@QEAAHXZ; CUser::IsLockWorkstationDisabled(void)
0x1400626d5  test    eax, eax
0x1400626d7  jnz     loc_140062AB5
0x1400626dd  mov     rax, [rbx+10h]
0x1400626e1  cmp     dword ptr [rax+94h], 3
0x1400626e8  jz      loc_140062AB5
0x1400626ee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x1400626f5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x1400626fa  test    al, al
0x1400626fc  jz      short loc_14006270F
0x1400626fe  mov     rax, [rbx+10h]
0x140062702  cmp     dword ptr [rax+94h], 4
0x140062709  jz      loc_140062AB5
0x14006270f  call    IsNotifyInitiateLockExecutePresent
0x140062714  test    al, al
0x140062716  jz      short loc_14006271E
0x140062718  call    cs:__imp_NotifyInitiateLockExecute
0x14006271e  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140062721  call    ?ShouldDisconnectOnLock@@YA_NPEAU_WLSM_GLOBAL_CONTEXT@@@Z; ShouldDisconnectOnLock(_WLSM_GLOBAL_CONTEXT *)
0x140062726  test    al, al
0x140062728  jz      loc_140062806
0x14006272e  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140062731  call    ?WinStationDisconnectWrapper@@YAEPEAU_WLSM_GLOBAL_CONTEXT@@PEAXKE@Z; WinStationDisconnectWrapper(_WLSM_GLOBAL_CONTEXT *,void *,ulong,uchar)
0x140062736  test    al, al
0x140062738  jz      loc_140062806
0x14006273e  xor     r9d, r9d
0x140062741  xor     r8d, r8d
0x140062744  mov     edx, r14d
0x140062747  mov     rcx, rbx
0x14006274a  call    ?WlAccessibilitySwitchDesktop@@YAXPEAU_WLSM_GLOBAL_CONTEXT@@W4_DESKTOPID@@KK@Z; WlAccessibilitySwitchDesktop(_WLSM_GLOBAL_CONTEXT *,_DESKTOPID,ulong,ulong)
0x14006274f  mov     r8, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140062752  mov     r14d, 1
0x140062758  mov     edx, r14d; int
0x14006275b  lea     rcx, aWluireleaseui; "WluiReleaseUI"
0x140062762  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140062767  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl(void)'::`2'::impl
0x14006276e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(void)
0x140062773  test    al, al
0x140062775  jz      short loc_14006279A
0x140062777  xor     edx, edx
0x140062779  lea     rcx, [rsp+338h+var_268]
0x140062781  call    ??0CallWithHangTimeout@@QEAA@W4TimeoutDuration@0@@Z; CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)
0x140062786  call    WluiReleaseUI
0x14006278b  lea     rcx, [rsp+338h+var_268]; this
0x140062793  call    ??1CallWithHangTimeout@@QEAA@XZ; CallWithHangTimeout::~CallWithHangTimeout(void)
0x140062798  jmp     short loc_14006279F
0x14006279a  call    WluiReleaseUI
0x14006279f  mov     r8, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x1400627a2  xor     edx, edx; int
0x1400627a4  lea     rcx, aWluireleaseui; "WluiReleaseUI"
0x1400627ab  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x1400627b0  mov     r12d, r14d
0x1400627b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400627ba  cmp     rcx, rdi
0x1400627bd  mov     edi, 4000h
0x1400627c2  jz      short loc_1400627E0
0x1400627c4  test    [rcx+1Ch], edi
0x1400627c7  jz      short loc_1400627E0
0x1400627c9  cmp     byte ptr [rcx+19h], 2
0x1400627cd  jb      short loc_1400627E0
0x1400627cf  mov     edx, 24h ; '$'
0x1400627d4  mov     r8, rsi
0x1400627d7  mov     rcx, [rcx+10h]
0x1400627db  call    WPP_SF_
0x1400627e0  mov     [rsp+338h+var_2B4], r14d
0x1400627e8  or      r8d, 0FFFFFFFFh
0x1400627ec  mov     edx, 3
0x1400627f1  mov     rcx, [rbx+10h]
0x1400627f5  call    ?ResetAutoLock@CSession@@QEAAXW4AutoLockStopReason@1@K@Z; CSession::ResetAutoLock(CSession::AutoLockStopReason,ulong)
0x1400627fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140062801  jmp     loc_140062B61
0x140062806  cmp     cs:?g_fIgnoreLockEvent@@3EA, r15b; uchar g_fIgnoreLockEvent
0x14006280d  jnz     short loc_14006281D
0x14006280f  lea     rcx, WLDiagEvt_Lock_Start; struct _EVENT_DESCRIPTOR *
0x140062816  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x14006281b  jmp     short loc_140062824
0x14006281d  mov     cs:?g_fIgnoreLockEvent@@3EA, r15b; uchar g_fIgnoreLockEvent
0x140062824  mov     r14d, 1
0x14006282a  mov     edx, r14d; int
0x14006282d  mov     rcx, [rbx+10h]; this
0x140062831  call    ?SetSessionLocked@CSession@@QEAAXH@Z; CSession::SetSessionLocked(int)
0x140062836  mov     rcx, [rbx+10h]; this
0x14006283a  call    ?CaptureInputDesktopForLockScreen@CSession@@QEAAXXZ; CSession::CaptureInputDesktopForLockScreen(void)
0x14006283f  mov     r8, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140062842  mov     edx, r14d; int
0x140062845  lea     rcx, aWluiinformlogo; "WluiInformLogonUI"
0x14006284c  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140062851  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl(void)'::`2'::impl
0x140062858  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(void)
0x14006285d  test    al, al
0x14006285f  jz      short loc_140062891
0x140062861  xor     edx, edx
0x140062863  lea     rcx, [rsp+338h+var_268]
0x14006286b  call    ??0CallWithHangTimeout@@QEAA@W4TimeoutDuration@0@@Z; CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)
0x140062870  mov     r8d, r13d
0x140062873  lea     edx, [r14+1]
0x140062877  lea     ecx, [rdx+5]
0x14006287a  call    WluiInformLogonUI
0x14006287f  mov     r15d, eax
0x140062882  lea     rcx, [rsp+338h+var_268]; this
0x14006288a  call    ??1CallWithHangTimeout@@QEAA@XZ; CallWithHangTimeout::~CallWithHangTimeout(void)
0x14006288f  jmp     short loc_1400628A4
0x140062891  mov     r8d, r13d
0x140062894  mov     edx, 2
0x140062899  lea     ecx, [rdx+5]
0x14006289c  call    WluiInformLogonUI
0x1400628a1  mov     r15d, eax
0x1400628a4  mov     r8, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x1400628a7  xor     edx, edx; int
0x1400628a9  lea     rcx, aWluiinformlogo; "WluiInformLogonUI"
0x1400628b0  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x1400628b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400628bc  cmp     rcx, rdi
0x1400628bf  mov     edi, 4000h
0x1400628c4  jz      short loc_1400628EA
0x1400628c6  test    [rcx+1Ch], edi
0x1400628c9  jz      short loc_1400628EA
0x1400628cb  cmp     byte ptr [rcx+19h], 5
0x1400628cf  jb      short loc_1400628EA
0x1400628d1  mov     edx, 25h ; '%'
0x1400628d6  mov     dword ptr [rsp+338h+var_318], r15d
0x1400628db  mov     r9d, r13d
0x1400628de  mov     r8, rsi
0x1400628e1  mov     rcx, [rcx+10h]
0x1400628e5  call    WPP_SF_DD
0x1400628ea  mov     rax, [rbx+10h]
0x1400628ee  mov     r15d, 2
0x1400628f4  cmp     [rax+90h], r15d
0x1400628fb  jnz     short loc_140062925
0x1400628fd  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140062900  call    ?IsSASRequired@@YAHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; IsSASRequired(_WLSM_GLOBAL_CONTEXT *)
0x140062905  test    eax, eax
0x140062907  jnz     short loc_140062918
0x140062909  mov     edx, r14d; int
0x14006290c  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x14006290f  call    ?IsLockScreenDisabled@@YAHPEAU_WLSM_GLOBAL_CONTEXT@@H@Z; IsLockScreenDisabled(_WLSM_GLOBAL_CONTEXT *,int)
0x140062914  test    eax, eax
0x140062916  jnz     short loc_140062925
0x140062918  mov     rdx, rbx
0x14006291b  call    ?GetLockScreenDesktop@CSession@@QEAA?AW4_DESKTOPID@@PEAU_WLSM_GLOBAL_CONTEXT@@@Z; CSession::GetLockScreenDesktop(_WLSM_GLOBAL_CONTEXT *)
0x140062920  cmp     eax, r15d
0x140062923  jz      short loc_140062949
0x140062925  mov     rax, [rbx+10h]
0x140062929  cmp     dword ptr [rax+178h], 0
0x140062930  jnz     short loc_140062949
0x140062932  mov     r9, [rbx+20h]
0x140062936  mov     r8d, 10h
0x14006293c  mov     edx, r15d
0x14006293f  mov     ecx, 3EEh
0x140062944  call    ?WlDisplayStatusByResourceId@@YAKIW4_WLUI_STATE@@KPEAVCUser@@@Z; WlDisplayStatusByResourceId(uint,_WLUI_STATE,ulong,CUser *)
0x140062949  mov     rdx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x14006294c  xor     ecx, ecx; int
0x14006294e  call    ?NotifyUserPresenceOnDesktopForDMAProtection@@YAXHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; NotifyUserPresenceOnDesktopForDMAProtection(int,_WLSM_GLOBAL_CONTEXT *)
0x140062953  xor     r9d, r9d
0x140062956  xor     r8d, r8d
0x140062959  xor     edx, edx
0x14006295b  mov     rcx, rbx
0x14006295e  call    ?WlAccessibilitySwitchDesktop@@YAXPEAU_WLSM_GLOBAL_CONTEXT@@W4_DESKTOPID@@KK@Z; WlAccessibilitySwitchDesktop(_WLSM_GLOBAL_CONTEXT *,_DESKTOPID,ulong,ulong)
0x140062963  xor     edx, edx; int
0x140062965  mov     rcx, [rbx+20h]; this
0x140062969  call    ?ImpersonateUser@CUser@@QEAAKH@Z; CUser::ImpersonateUser(int)
0x14006296e  test    eax, eax
0x140062970  jnz     loc_140062A0A
0x140062976  mov     rcx, cs:WPP_GLOBAL_Control
0x14006297d  lea     r15, WPP_GLOBAL_Control
0x140062984  cmp     rcx, r15
0x140062987  jz      short loc_1400629A3
0x140062989  test    [rcx+1Ch], edi
0x14006298c  jz      short loc_1400629A3
0x14006298e  cmp     byte ptr [rcx+19h], 4
0x140062992  jb      short loc_1400629A3
0x140062994  lea     edx, [rax+26h]
0x140062997  mov     r8, rsi
0x14006299a  mov     rcx, [rcx+10h]
0x14006299e  call    WPP_SF_
0x1400629a3  xor     r8d, r8d; unsigned __int16 *
0x1400629a6  xor     edx, edx; int
0x1400629a8  mov     rcx, [rbx]; this
0x1400629ab  call    ?GetNotifyConfig@CGlobalStore@@QEAAPEAXHPEBG@Z; CGlobalStore::GetNotifyConfig(int,ushort const *)
0x1400629b0  mov     [rsp+338h+var_310], 0
0x1400629b9  mov     [rsp+338h+var_318], 0
0x1400629c2  xor     r9d, r9d
0x1400629c5  xor     r8d, r8d
0x1400629c8  lea     edx, [r9+4]
0x1400629cc  mov     rcx, rax
0x1400629cf  call    ?InternalNotifyExecute@@YAKPEAXW4WLNOTIFICATION_ID@@PEAT_WLN_CLIENT_PARAMS@@P6AX0PEBG@Z0PEAG@Z; InternalNotifyExecute(void *,WLNOTIFICATION_ID,_WLN_CLIENT_PARAMS *,void (*)(void *,ushort const *),void *,ushort *)
0x1400629d4  test    eax, eax
0x1400629d6  jz      short loc_140062A03
0x1400629d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400629df  cmp     rcx, r15
0x1400629e2  jz      short loc_140062A03
0x1400629e4  test    [rcx+1Ch], edi
0x1400629e7  jz      short loc_140062A03
0x1400629e9  cmp     byte ptr [rcx+19h], 2
0x1400629ed  jb      short loc_140062A03
0x1400629ef  mov     edx, 27h ; '''
0x1400629f4  mov     r9d, eax
0x1400629f7  mov     r8, rsi
0x1400629fa  mov     rcx, [rcx+10h]
0x1400629fe  call    WPP_SF_d
0x140062a03  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x140062a08  jmp     short loc_140062A3C
0x140062a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140062a11  lea     rdx, WPP_GLOBAL_Control
0x140062a18  cmp     rcx, rdx
0x140062a1b  jz      short loc_140062A43
0x140062a1d  test    [rcx+1Ch], edi
0x140062a20  jz      short loc_140062A43
0x140062a22  cmp     [rcx+19h], r15b
0x140062a26  jb      short loc_140062A43
0x140062a28  mov     edx, 28h ; '('
0x140062a2d  mov     r9d, eax
0x140062a30  mov     r8, rsi
0x140062a33  mov     rcx, [rcx+10h]
0x140062a37  call    WPP_SF_d
0x140062a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140062a43  lea     rax, WPP_GLOBAL_Control
0x140062a4a  cmp     rcx, rax
0x140062a4d  jz      short loc_140062A6B
0x140062a4f  test    [rcx+1Ch], edi
0x140062a52  jz      short loc_140062A6B
0x140062a54  cmp     byte ptr [rcx+19h], 5
0x140062a58  jb      short loc_140062A6B
0x140062a5a  mov     edx, 29h ; ')'
0x140062a5f  mov     r8, rsi
0x140062a62  mov     rcx, [rcx+10h]
0x140062a66  call    WPP_SF_
0x140062a6b  xor     edx, edx; bool
0x140062a6d  mov     rcx, [rbx+20h]; this
0x140062a71  call    ?StopUserPresencePolling@CUser@@QEAAX_N@Z; CUser::StopUserPresencePolling(bool)
0x140062a76  mov     rcx, cs:WPP_GLOBAL_Control
0x140062a7d  lea     rax, WPP_GLOBAL_Control
0x140062a84  cmp     rcx, rax
0x140062a87  jz      short loc_140062AA5
0x140062a89  test    [rcx+1Ch], edi
0x140062a8c  jz      short loc_140062AA5
0x140062a8e  cmp     byte ptr [rcx+19h], 4
0x140062a92  jb      short loc_140062AA5
0x140062a94  mov     edx, 2Ah ; '*'
0x140062a99  mov     r8, rsi
0x140062a9c  mov     rcx, [rcx+10h]
0x140062aa0  call    WPP_SF_
0x140062aa5  mov     cl, r14b; unsigned __int8
0x140062aa8  call    ?NotifyPowerMgmt@@YAXE@Z; NotifyPowerMgmt(uchar)
0x140062aad  xor     r15b, r15b
0x140062ab0  jmp     loc_1400627FA
  ... truncated ...
```
