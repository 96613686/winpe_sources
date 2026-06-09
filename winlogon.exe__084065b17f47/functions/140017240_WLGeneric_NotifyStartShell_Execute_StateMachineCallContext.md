# WLGeneric_NotifyStartShell_Execute(_StateMachineCallContext *)

- ea: `0x140017240`
- end: `0x1400176f1`
- name: `?WLGeneric_NotifyStartShell_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `1201`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400057f4`
- `0x140006970`
- `0x140014370`
- `0x140016f60`
- `0x140017240`
- `0x1400176f8`
- `0x1400180f0`
- `0x1400333b0`
- `0x14003ceb8`
- `0x1400403d8`
- `0x140041c34`
- `0x14004df08`
- `0x14004f03c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001759a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001759a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001761e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001761e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14001733d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14001738f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14001733d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14001738f`
- `ntdll!RtlLeaveCriticalSection` at `0x140017431`
- `ntdll!RtlLeaveCriticalSection` at `0x140017431`
- `ntdll!RtlEnterCriticalSection` at `0x140017427`
- `ntdll!RtlEnterCriticalSection` at `0x140017427`
- `ntdll!NtClose` at `0x1400173b1`
- `ntdll!NtClose` at `0x1400173b1`

## pseudocode

```c
__int64 __fastcall WLGeneric_NotifyStartShell_Execute(
        struct _StateMachineCallContext *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  CSession **v5; // rbx
  int v6; // esi
  CSession *v7; // rcx
  unsigned int v8; // r14d
  int v9; // r15d
  unsigned int v10; // eax
  unsigned int MachinePolicy; // eax
  DWORD v12; // edi
  void *v13; // r14
  CUser *v14; // rcx
  __int64 v15; // r9
  DWORD v16; // eax
  CUser *v17; // r10
  CSession *v18; // rdi
  unsigned int v19; // eax
  __int64 v20; // r9
  CUser *v21; // rcx
  __int64 v22; // rdx
  DWORD LastError; // eax
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, a4);
  }
  v5 = (CSession **)*((_QWORD *)a1 + 1);
  v6 = 0;
  v7 = v5[2];
  v8 = *((_DWORD *)v7 + 94);
  v9 = *((_DWORD *)v7 + 98);
  CSession::PerformDelayedSwitchToApplicationDesktop(v7, v5, v8 != 0);
  if ( v8 )
  {
    switch ( v9 )
    {
      case 1:
        WLEventWrite(&WLEvt_AutomaticRestartSignOn_Info);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_3;
        }
        v22 = 198;
        break;
      case 2:
        WLEventWrite(&WLEvt_PinResetLogon_Info);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_3;
        }
        v22 = 199;
        break;
      case 4:
        WLEventWrite(&WLEvt_AssignedAccessLogon_Info);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_3;
        }
        v22 = 200;
        break;
      default:
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v8, v9);
        }
        goto LABEL_3;
    }
    WPP_SF_(*((_QWORD *)v21 + 2), v22, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v20);
  }
LABEL_3:
  v10 = WlAccessibilityOnLogon(v5, v8 != 0);
  if ( v10
    && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v10);
  }
  MachinePolicy = CMachine::GetMachinePolicy(v5[1], L"NetworkConnectionsTimeout", 3u);
  CUser::RestoreNetworkConnections(v5[4], MachinePolicy);
  v12 = 0;
  v13 = (void *)*((_QWORD *)v5[4] + 17);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
  {
    if ( !ImpersonateLoggedOnUser(v13) )
    {
      LastError = GetLastError();
      v12 = LastError;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_16;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, LastError);
    }
    v17 = WPP_GLOBAL_Control;
LABEL_16:
    v14 = 0;
    goto LABEL_18;
  }
  if ( ImpersonateLoggedOnUser(v13) )
  {
LABEL_17:
    v17 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v16 = GetLastError();
  v12 = v16;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v16);
    goto LABEL_17;
  }
LABEL_18:
  if ( v12 )
  {
    if ( v17 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x1000) != 0 && *((_BYTE *)v17 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v17 + 2), 203, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v12);
  }
  else
  {
    v6 = 1;
    if ( v17 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x1000) != 0 && *((_BYTE *)v17 + 25) >= 2u )
      WPP_SF_(*((_QWORD *)v17 + 2), 204, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v15);
    v18 = *v5;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)*v5 + 16));
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v18 + 16));
    if ( !*((_QWORD *)v18 + 24) )
      SetLastError(0);
    v19 = InternalNotifyExecute(*((_QWORD *)v18 + 24), 0xCu, 0, 0, 0, 0);
    if ( v19 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v19);
      }
    }
  }
  if ( v6 )
    CUser::StopImpersonating(v14);
  result = 13;
  if ( qword_1400D30C8 )
    return SignalManagerSetSignal(*(PRTL_CRITICAL_SECTION *)qword_1400D30C8);
  return result;
}

```

## disassembly

```asm
0x140017240  mov     [rsp+arg_8], rbx
0x140017245  mov     [rsp+arg_10], rsi
0x14001724a  push    rdi
0x14001724b  push    r12
0x14001724d  push    r13
0x14001724f  push    r14
0x140017251  push    r15
0x140017253  sub     rsp, 50h
0x140017257  mov     rbx, rcx
0x14001725a  lea     r13, WPP_GLOBAL_Control
0x140017261  mov     rcx, cs:WPP_GLOBAL_Control
0x140017268  cmp     rcx, r13
0x14001726b  jnz     loc_1400176C0
0x140017271  mov     rbx, [rbx+8]
0x140017275  xor     r12d, r12d
0x140017278  mov     esi, r12d
0x14001727b  mov     [rsp+78h+var_44], r12d
0x140017280  mov     rcx, [rbx+10h]; this
0x140017284  mov     r14d, [rcx+178h]
0x14001728b  mov     r15d, [rcx+188h]
0x140017292  mov     edi, r12d
0x140017295  test    r14d, r14d
0x140017298  setnz   dil
0x14001729c  mov     r8d, edi; int
0x14001729f  mov     rdx, rbx; void *
0x1400172a2  call    ?PerformDelayedSwitchToApplicationDesktop@CSession@@QEAAXPEAXH@Z; CSession::PerformDelayedSwitchToApplicationDesktop(void *,int)
0x1400172a7  test    r14d, r14d
0x1400172aa  jnz     loc_140017476
0x1400172b0  mov     edx, edi; int
0x1400172b2  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x1400172b5  call    ?WlAccessibilityOnLogon@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@H@Z; WlAccessibilityOnLogon(_WLSM_GLOBAL_CONTEXT *,int)
0x1400172ba  test    eax, eax
0x1400172bc  jz      short loc_1400172F1
0x1400172be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400172c5  cmp     rcx, r13
0x1400172c8  jz      short loc_1400172F1
0x1400172ca  test    dword ptr [rcx+1Ch], 40000h
0x1400172d1  jz      short loc_1400172F1
0x1400172d3  cmp     byte ptr [rcx+19h], 2
0x1400172d7  jb      short loc_1400172F1
0x1400172d9  mov     edx, 0CAh
0x1400172de  mov     r9d, eax
0x1400172e1  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x1400172e8  mov     rcx, [rcx+10h]
0x1400172ec  call    WPP_SF_d
0x1400172f1  mov     r8d, 3; unsigned int
0x1400172f7  lea     rdx, aNetworkconnect; "NetworkConnectionsTimeout"
0x1400172fe  mov     rcx, [rbx+8]; this
0x140017302  call    ?GetMachinePolicy@CMachine@@QEAAKPEBGK@Z; CMachine::GetMachinePolicy(ushort const *,ulong)
0x140017307  mov     edx, eax; unsigned int
0x140017309  mov     rcx, [rbx+20h]; this
0x14001730d  call    ?RestoreNetworkConnections@CUser@@QEAAXK@Z; CUser::RestoreNetworkConnections(ulong)
0x140017312  mov     rax, [rbx+20h]
0x140017316  mov     edi, r12d
0x140017319  mov     [rsp+78h+var_48], r12d
0x14001731e  mov     r14, [rax+88h]
0x140017325  mov     [rsp+78h+var_38], r14
0x14001732a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x140017331  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x140017336  mov     rcx, r14; hToken
0x140017339  test    al, al
0x14001733b  jnz     short loc_140017387
0x14001733d  call    cs:__imp_ImpersonateLoggedOnUser
0x140017343  test    eax, eax
0x140017345  jnz     short loc_1400173BF
0x140017347  call    cs:__imp_GetLastError
0x14001734d  mov     edi, eax
0x14001734f  mov     [rsp+78h+var_48], eax
0x140017353  mov     r10, cs:WPP_GLOBAL_Control
0x14001735a  cmp     r10, r13
0x14001735d  jz      short loc_1400173C6
0x14001735f  test    byte ptr [r10+1Ch], 20h
0x140017364  jz      short loc_1400173C6
0x140017366  cmp     byte ptr [r10+19h], 2
0x14001736b  jb      short loc_1400173C6
0x14001736d  mov     edx, 1Bh
0x140017372  mov     r9d, eax
0x140017375  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14001737c  mov     rcx, [r10+10h]
0x140017380  call    WPP_SF_d
0x140017385  jmp     short loc_1400173BF
0x140017387  mov     [rsp+78h+Handle], r12
0x14001738f  call    cs:__imp_ImpersonateLoggedOnUser
0x140017395  test    eax, eax
0x140017397  jz      loc_14001759A
0x14001739d  mov     r10, cs:WPP_GLOBAL_Control
0x1400173a4  mov     rcx, [rsp+78h+Handle]; Handle
0x1400173ac  test    rcx, rcx
0x1400173af  jz      short loc_1400173C6
0x1400173b1  call    cs:__imp_NtClose
0x1400173b7  mov     [rsp+78h+Handle], r12
0x1400173bf  mov     r10, cs:WPP_GLOBAL_Control
0x1400173c6  test    edi, edi
0x1400173c8  jz      short loc_140017409
0x1400173ca  cmp     r10, r13
0x1400173cd  jz      loc_14001766D
0x1400173d3  test    dword ptr [r10+1Ch], 1000h
0x1400173db  jz      loc_14001766D
0x1400173e1  cmp     byte ptr [r10+19h], 2
0x1400173e6  jb      loc_14001766D
0x1400173ec  mov     edx, 0CBh
0x1400173f1  mov     r9d, edi
0x1400173f4  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x1400173fb  mov     rcx, [r10+10h]
0x1400173ff  call    WPP_SF_d
0x140017404  jmp     loc_14001766D
0x140017409  mov     esi, 1
0x14001740e  mov     [rsp+78h+var_44], esi
0x140017412  cmp     r10, r13
0x140017415  jnz     loc_1400175E9
0x14001741b  mov     rdi, [rbx]
0x14001741e  mov     [rsp+78h+var_40], r12d
0x140017423  lea     rcx, [rdi+10h]; CriticalSection
0x140017427  call    cs:__imp_RtlEnterCriticalSection
0x14001742d  lea     rcx, [rdi+10h]; CriticalSection
0x140017431  call    cs:__imp_RtlLeaveCriticalSection
0x140017437  cmp     qword ptr [rdi+0C0h], 0
0x14001743f  jz      loc_14001761C
0x140017445  mov     [rsp+78h+var_50], r12
0x14001744a  mov     [rsp+78h+var_58], r12
0x14001744f  xor     r9d, r9d
0x140017452  xor     r8d, r8d
0x140017455  mov     edx, 0Ch
0x14001745a  mov     rcx, [rdi+0C0h]
0x140017461  call    ?InternalNotifyExecute@@YAKPEAXW4WLNOTIFICATION_ID@@PEAT_WLN_CLIENT_PARAMS@@P6AX0PEBG@Z0PEAG@Z; InternalNotifyExecute(void *,WLNOTIFICATION_ID,_WLN_CLIENT_PARAMS *,void (*)(void *,ushort const *),void *,ushort *)
0x140017466  test    eax, eax
0x140017468  jnz     loc_140017629
0x14001746e  mov     edi, r12d
0x140017471  jmp     loc_14001766D
0x140017476  mov     ecx, r15d
0x140017479  sub     ecx, 1
0x14001747c  jz      loc_14001754D
0x140017482  sub     ecx, 1
0x140017485  jz      loc_140017513
0x14001748b  cmp     ecx, 2
0x14001748e  jz      short loc_1400174D9
0x140017490  mov     rcx, cs:WPP_GLOBAL_Control
0x140017497  cmp     rcx, r13
0x14001749a  jz      loc_1400172B0
0x1400174a0  test    dword ptr [rcx+1Ch], 1000h
0x1400174a7  jz      loc_1400172B0
0x1400174ad  cmp     byte ptr [rcx+19h], 2
0x1400174b1  jb      loc_1400172B0
0x1400174b7  mov     edx, 0C9h
0x1400174bc  mov     dword ptr [rsp+78h+var_58], r15d
0x1400174c1  mov     r9d, r14d
0x1400174c4  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x1400174cb  mov     rcx, [rcx+10h]
0x1400174cf  call    WPP_SF_DD
0x1400174d4  jmp     loc_1400172B0
0x1400174d9  lea     rcx, WLEvt_AssignedAccessLogon_Info; struct _EVENT_DESCRIPTOR *
0x1400174e0  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x1400174e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400174ec  cmp     rcx, r13
0x1400174ef  jz      loc_1400172B0
0x1400174f5  test    dword ptr [rcx+1Ch], 1000h
0x1400174fc  jz      loc_1400172B0
0x140017502  cmp     byte ptr [rcx+19h], 4
0x140017506  jb      loc_1400172B0
0x14001750c  mov     edx, 0C8h
0x140017511  jmp     short loc_140017585
0x140017513  lea     rcx, WLEvt_PinResetLogon_Info; struct _EVENT_DESCRIPTOR *
0x14001751a  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x14001751f  mov     rcx, cs:WPP_GLOBAL_Control
0x140017526  cmp     rcx, r13
0x140017529  jz      loc_1400172B0
0x14001752f  test    dword ptr [rcx+1Ch], 1000h
0x140017536  jz      loc_1400172B0
0x14001753c  cmp     byte ptr [rcx+19h], 4
0x140017540  jb      loc_1400172B0
0x140017546  mov     edx, 0C7h
0x14001754b  jmp     short loc_140017585
0x14001754d  lea     rcx, WLEvt_AutomaticRestartSignOn_Info; struct _EVENT_DESCRIPTOR *
0x140017554  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140017559  mov     rcx, cs:WPP_GLOBAL_Control
0x140017560  cmp     rcx, r13
0x140017563  jz      loc_1400172B0
0x140017569  test    dword ptr [rcx+1Ch], 1000h
0x140017570  jz      loc_1400172B0
0x140017576  cmp     byte ptr [rcx+19h], 4
0x14001757a  jb      loc_1400172B0
0x140017580  mov     edx, 0C6h
0x140017585  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x14001758c  mov     rcx, [rcx+10h]
0x140017590  call    WPP_SF_
0x140017595  jmp     loc_1400172B0
0x14001759a  call    cs:__imp_GetLastError
0x1400175a0  mov     edi, eax
0x1400175a2  mov     [rsp+78h+var_48], eax
0x1400175a6  mov     r10, cs:WPP_GLOBAL_Control
0x1400175ad  cmp     r10, r13
0x1400175b0  jz      loc_1400173A4
0x1400175b6  test    byte ptr [r10+1Ch], 20h
0x1400175bb  jz      loc_1400173A4
0x1400175c1  cmp     byte ptr [r10+19h], 2
0x1400175c6  jb      loc_1400173A4
0x1400175cc  mov     edx, 19h
0x1400175d1  mov     r9d, eax
0x1400175d4  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x1400175db  mov     rcx, [r10+10h]
0x1400175df  call    WPP_SF_d
0x1400175e4  jmp     loc_14001739D
0x1400175e9  test    dword ptr [r10+1Ch], 1000h
0x1400175f1  jz      loc_14001741B
0x1400175f7  cmp     byte ptr [r10+19h], 2
0x1400175fc  jb      loc_14001741B
0x140017602  mov     edx, 0CCh
0x140017607  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x14001760e  mov     rcx, [r10+10h]
0x140017612  call    WPP_SF_
0x140017617  jmp     loc_14001741B
0x14001761c  xor     ecx, ecx; dwErrCode
0x14001761e  call    cs:__imp_SetLastError
0x140017624  jmp     loc_140017445
0x140017629  mov     rcx, cs:WPP_GLOBAL_Control
0x140017630  cmp     rcx, r13
0x140017633  jz      loc_14001746E
0x140017639  test    dword ptr [rcx+1Ch], 1000h
0x140017640  jz      loc_14001746E
0x140017646  cmp     byte ptr [rcx+19h], 3
0x14001764a  jb      loc_14001746E
0x140017650  mov     edx, 0CDh
0x140017655  mov     r9d, eax
0x140017658  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x14001765f  mov     rcx, [rcx+10h]
0x140017663  call    WPP_SF_d
0x140017668  jmp     loc_14001746E
0x14001766d  test    esi, esi
0x14001766f  jnz     short loc_1400176B9
0x140017671  mov     edx, r12d
0x140017674  test    edi, edi
0x140017676  setnz   dl
0x140017679  mov     eax, 0Dh
0x14001767e  mov     rcx, cs:qword_1400D30C8
0x140017685  test    rcx, rcx
0x140017688  jz      short loc_14001769F
0x14001768a  mov     eax, edx
0x14001768c  mov     r8, [rcx+20h]
0x140017690  xor     r9d, r9d
0x140017693  mov     r8, [r8+rax*8]
0x140017697  mov     rcx, [rcx]; CriticalSection
0x14001769a  call    SignalManagerSetSignal
0x14001769f  lea     r11, [rsp+78h+var_28]
0x1400176a4  mov     rbx, [r11+38h]
0x1400176a8  mov     rsi, [r11+40h]
0x1400176ac  mov     rsp, r11
0x1400176af  pop     r15
0x1400176b1  pop     r14
0x1400176b3  pop     r13
0x1400176b5  pop     r12
0x1400176b7  pop     rdi
0x1400176b8  retn
0x1400176b9  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x1400176be  jmp     short loc_140017671
0x1400176c0  test    dword ptr [rcx+1Ch], 100h
0x1400176c7  jz      loc_140017271
0x1400176cd  cmp     byte ptr [rcx+19h], 4
0x1400176d1  jb      loc_140017271
0x1400176d7  mov     edx, 0C5h
0x1400176dc  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x1400176e3  mov     rcx, [rcx+10h]
0x1400176e7  call    WPP_SF_
0x1400176ec  jmp     loc_140017271
0x14009d860  push    rbp
0x14009d862  sub     rsp, 30h
0x14009d866  mov     rbp, rdx
0x14009d869  cmp     dword ptr [rbp+34h], 0
0x14009d86d  jz      short loc_14009D875
0x14009d86f  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x14009d874  nop
0x14009d875  add     rsp, 30h
0x14009d879  pop     rbp
0x14009d87a  retn
```
