# TetheringService::StopSharing(ulong,TetheringService::StopReason)

- ea: `0x18001f740`
- end: `0x18001fe3d`
- name: `?StopSharing@TetheringService@@AEAAJKW4StopReason@1@@Z`
- size: `1789`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `29`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180015e30`
- `0x180019034`
- `0x18001aeb0`
- `0x18001b400`
- `0x18001c75c`
- `0x18001e4a4`
- `0x18001fe44`
- `0x180020030`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000d73c`
- `0x18000d8e4`
- `0x18000d9dc`
- `0x18000ee14`
- `0x180010660`
- `0x1800132c8`
- `0x180015cdc`
- `0x1800182e4`
- `0x18001b898`
- `0x18001c184`
- `0x18001d344`
- `0x18001f740`
- `0x1800209c4`
- `0x180020cb4`
- `0x180021580`
- `0x180021b88`
- `0x18002621c`
- `0x180026558`
- `0x180026930`
- `0x180027130`
- `0x1800272c0`
- `0x180027394`
- `0x180027550`
- `0x180029c10`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb50`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fc71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fc71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f9a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f9a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f817`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f959`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fd69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f817`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f959`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fd69`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001fb70`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001fb95`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001fbbe`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001fb70`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001fb95`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001fbbe`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001fa4c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001fa4c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fca8`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fca8`
- `WMICLNT!WmiNotificationRegistrationW` at `0x18001f9c4`
- `WMICLNT!WmiNotificationRegistrationW` at `0x18001f9c4`

## string_xrefs

- `0x18001fa95`: `onecoreuap\net\tethering\service\tetheringservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TetheringService::StopSharing(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // r15d
  char v4; // r12
  TetheringServiceTelemetry *v6; // rdi
  char v7; // r13
  RTL_SRWLOCK *v8; // rbx
  TetheringServiceTelemetry *v9; // rcx
  int Session; // r14d
  void *v11; // rdx
  int SharedInterfaceIndices; // eax
  __int128 v13; // xmm0
  int v14; // eax
  unsigned int v15; // r9d
  unsigned int v16; // edi
  unsigned int v17; // r15d
  __int64 v18; // r8
  __int64 v19; // r9
  TetheringServiceTelemetry *v20; // rcx
  __int64 v21; // rax
  struct _GUID *v22; // rdx
  TetheringServiceTelemetry *v23; // rcx
  __int64 i; // rdi
  __int64 v25; // rcx
  TetheringServiceTelemetry *v26; // rcx
  char v28; // [rsp+30h] [rbp-D0h]
  char v29; // [rsp+31h] [rbp-CFh]
  unsigned int v30; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v31; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v32; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v33; // [rsp+40h] [rbp-C0h]
  TetheringSessionTelemetry *v34; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v36; // [rsp+58h] [rbp-A8h]
  __int64 v37; // [rsp+68h] [rbp-98h]
  _BYTE v38[72]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+C0h] [rbp-40h] BYREF
  int v41; // [rsp+C4h] [rbp-3Ch] BYREF
  _BYTE v42[216]; // [rsp+C8h] [rbp-38h] BYREF
  int v43; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v44; // [rsp+1A4h] [rbp+A4h]
  int v45; // [rsp+1B4h] [rbp+B4h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v3 = a3;
  v33 = a3;
  v4 = a2;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a2, a3, *(_DWORD *)(a1 + 224));
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  v29 = 0;
  v36 = 0;
  v37 = 0;
  memset_0(v38, 0, 0x50u);
  v8 = 0;
  v34 = 0;
  if ( v6 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
    WPP_SF_dd(*((_QWORD *)v6 + 2), 87, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 232));
  if ( *(_DWORD *)(a1 + 224) == 3 )
  {
    Session = 0;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
  }
  else
  {
    if ( *(_QWORD *)&g_pTetheringSessionId.Data1 )
    {
      Session = TetheringServiceTelemetry::GetSession(v9, *(struct _GUID **)&g_pTetheringSessionId.Data1, &v34);
      v8 = (RTL_SRWLOCK *)v34;
      if ( Session >= 0 )
      {
        if ( v34 )
        {
          if ( !TetheringSessionTelemetry::Initialized((RTL_SRWLOCK *)v34) )
            Session = -2147467259;
        }
        else
        {
          Session = -2147467261;
        }
      }
    }
    else
    {
      Session = -2147418113;
    }
    *(_DWORD *)(a1 + 224) = 5;
    if ( (v4 & 1) != 0 )
    {
      memset_0(&v41, 0, 0xD0u);
      v40 = 9;
      TetheringService::SendNotification((TetheringService *)a1, (struct _TETHERING_WNF_NOTIFICATION_MSG *)&v40);
    }
    if ( IsMobile() || *(_DWORD *)(a1 + 472) != 8 )
    {
      v28 = 0;
    }
    else
    {
      v28 = 1;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      }
      CSebHelper::PublishWnfEvent(a1 + 1288, 11);
    }
    if ( IsMobile() )
    {
      v29 = 1;
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1488));
      *(_QWORD *)&v36 = *(_QWORD *)(a1 + 1680);
      *(_QWORD *)(a1 + 1680) = 0;
      *((_QWORD *)&v36 + 1) = *(_QWORD *)(a1 + 1688);
      *(_QWORD *)(a1 + 1688) = 0;
      v37 = *(_QWORD *)(a1 + 1672);
      *(_QWORD *)(a1 + 1672) = 0;
      *(_WORD *)(a1 + 1664) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1488));
    }
    WmiNotificationRegistrationW(
      &GUID_NDIS_NOTIFY_ADAPTER_REMOVAL,
      0,
      TetheringService::NdisWmiEventNotificationHandler,
      a1);
    CNsiInterfaceMonitor::StopMonitor((CNsiInterfaceMonitor *)(a1 + 1712));
    if ( ((*(_DWORD *)(a1 + 476) - 1) & 0xFFFFFFF7) != 0 || (v7 = 1, (v4 & 4) == 0) )
    {
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      }
      BtPanHandler::Stop((BtPanHandler *)(a1 + 1184));
    }
    if ( *(_BYTE *)(a1 + 662) )
    {
      v11 = *(void **)(a1 + 576);
      if ( v11 )
      {
        DeleteTimerQueueTimer(*(HANDLE *)(a1 + 568), v11, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        *(_QWORD *)(a1 + 576) = 0;
      }
    }
    TetheringService::UnregisterEntitlementFailedCallback((TetheringService *)a1);
    v30 = 0;
    v31 = 0;
    SharedInterfaceIndices = InterfaceMgr::GetSharedInterfaceIndices((InterfaceMgr *)(a1 + 352), &v30, &v31);
    if ( SharedInterfaceIndices < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x478,
        (unsigned int)"onecoreuap\\net\\tethering\\service\\tetheringservice.cpp",
        (const char *)(unsigned int)SharedInterfaceIndices,
        4);
    InterfaceMgr::DisableSharedInterfaces((InterfaceMgr *)(a1 + 352));
    SharedAccessSvcMgr::Stop((SharedAccessSvcMgr *)(a1 + 312));
    v13 = *(_OWORD *)(a1 + 432);
    v14 = *(_DWORD *)(a1 + 448);
    v15 = *(_DWORD *)(a1 + 224);
    v43 = 25;
    v44 = v13;
    v45 = v14;
    NetworkingTriageScenario::MobileHotspot::TetheringStopped(
      (const struct NetworkingTriageScenario::MobileHotspot::RequiredFields *)&v43,
      v31,
      v30,
      v15,
      v3);
    v16 = 0;
    v32 = 0;
    Block = 0;
    if ( !(unsigned int)TetheringService::GetPeerList(
                          (struct _RTL_CRITICAL_SECTION *)a1,
                          &v32,
                          (struct _TETHERING_PEER_CONNECTION_DATA **)&Block,
                          0) )
    {
      v17 = v32;
      if ( v32 )
      {
        do
          TetheringService::RemovePeer((TetheringService *)a1, (unsigned __int8 (*)[6])((char *)Block + 226 * v16++));
        while ( v16 < v17 );
      }
      free(Block);
    }
    if ( ChangeTimerQueueTimer(*(HANDLE *)(a1 + 1584), *(HANDLE *)(a1 + 1576), 0xFFFFFFFF, 0xFFFFFFFF) )
      *(_BYTE *)(a1 + 1596) = 0;
    if ( ChangeTimerQueueTimer(*(HANDLE *)(a1 + 1608), *(HANDLE *)(a1 + 1600), 0xFFFFFFFF, 0xFFFFFFFF) )
      *(_BYTE *)(a1 + 1620) = 0;
    if ( ChangeTimerQueueTimer(*(HANDLE *)(a1 + 1632), *(HANDLE *)(a1 + 1624), *(_DWORD *)(a1 + 1640), 0xFFFFFFFF) )
      *(_BYTE *)(a1 + 1644) = 1;
    if ( v7 && (v4 & 2) == 0 )
      TetheringService::SetWiFiPowerState((TetheringService *)a1, 0, v18, v19);
    *(_DWORD *)(a1 + 224) = 3;
    memset_0((void *)(a1 + 8), 0, 0xD4u);
    *(_BYTE *)(a1 + 220) = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1752));
    if ( *(_BYTE *)(a1 + 1792) )
    {
      CPowerHandler::PreventSleepInternal((const struct _WNF_STATE_NAME *)(a1 + 1752), 0);
      *(_BYTE *)(a1 + 1792) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1752));
    if ( Session < 0 )
    {
      v3 = v33;
    }
    else
    {
      if ( !v8 )
        ATL::AtlThrowImpl(-2147467259);
      TetheringServiceTelemetry::AcquireSessionData(v20, v8, (struct TetheringServiceTelemetry::SESSION_DATA *)v38);
      v21 = v39;
      v3 = v33;
      *(_DWORD *)(v39 + 36) = v33;
      *(_DWORD *)(v21 + 32) = 0;
      ReleaseSRWLockExclusive(v8 + 2);
      TetheringServiceTelemetry::StopSession(v23, v22);
    }
    v7 = v28;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 232));
  if ( v29 )
  {
    for ( i = 0; i != 3; ++i )
    {
      v25 = *((_QWORD *)&v36 + i);
      if ( v25 )
        RtlUnsubscribeWnfNotificationWaitForCompletion(v25);
    }
  }
  if ( (v4 & 1) != 0 )
  {
    memset_0(v42, 0, 0xCCu);
    v40 = 2;
    if ( v3 == 10 )
      v41 = *(_DWORD *)(a1 + 1648);
    else
      v41 = 0;
    TetheringService::SendNotification((TetheringService *)a1, (struct _TETHERING_WNF_NOTIFICATION_MSG *)&v40);
  }
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
    CSebHelper::PublishWnfEvent(a1 + 1288, 11);
  }
  if ( v3 != 10 )
    *(_DWORD *)(a1 + 1648) = 0;
  if ( *(_DWORD *)(a1 + 1656) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 272));
    if ( (unsigned int)TetheringService::ChangeConnectionType((TetheringService *)a1, 4u, 1) )
      *(_DWORD *)(a1 + 1656) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 272));
  }
  if ( Session >= 0 )
    goto LABEL_85;
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_89;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      92,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)Session);
LABEL_85:
    v26 = WPP_GLOBAL_Control;
  }
  if ( v26 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v26 + 2), 93, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, 0);
LABEL_89:
  if ( v8 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v8->Ptr + 2))(v8);
  return 0;
}

```

## disassembly

```asm
0x18001f740  mov     [rsp-8+arg_10], rbx
0x18001f745  push    rbp
0x18001f746  push    rsi
0x18001f747  push    rdi
0x18001f748  push    r12
0x18001f74a  push    r13
0x18001f74c  push    r14
0x18001f74e  push    r15
0x18001f750  lea     rbp, [rsp-0C0h]
0x18001f758  sub     rsp, 1C0h
0x18001f75f  mov     rax, cs:__security_cookie
0x18001f766  xor     rax, rsp
0x18001f769  mov     [rbp+0F0h+var_38], rax
0x18001f770  mov     r15d, r8d
0x18001f773  mov     [rsp+1F0h+var_1B0], r8d
0x18001f778  mov     r12d, edx
0x18001f77b  mov     rsi, rcx
0x18001f77e  lea     r14, WPP_GLOBAL_Control
0x18001f785  mov     rdi, cs:WPP_GLOBAL_Control
0x18001f78c  cmp     rdi, r14
0x18001f78f  jz      short loc_18001F7B9
0x18001f791  test    byte ptr [rdi+1Ch], 8
0x18001f795  jz      short loc_18001F7B9
0x18001f797  mov     rcx, [rdi+10h]
0x18001f79b  mov     eax, [rsi+0E0h]
0x18001f7a1  mov     [rsp+1F0h+var_1C8], eax
0x18001f7a5  mov     [rsp+1F0h+var_1D0], r8d
0x18001f7aa  mov     r9d, edx
0x18001f7ad  call    WPP_SF_ddd
0x18001f7b2  mov     rdi, cs:WPP_GLOBAL_Control
0x18001f7b9  xor     r13d, r13d
0x18001f7bc  mov     [rsp+1F0h+var_1BF], r13b
0x18001f7c1  xorps   xmm0, xmm0
0x18001f7c4  xor     eax, eax
0x18001f7c6  movups  [rsp+1F0h+var_198], xmm0
0x18001f7cb  mov     [rsp+1F0h+var_188], rax
0x18001f7d0  xor     edx, edx; Val
0x18001f7d2  lea     r8d, [r13+50h]; Size
0x18001f7d6  lea     rcx, [rsp+1F0h+var_180]; void *
0x18001f7db  call    memset_0
0x18001f7e0  nop
0x18001f7e1  mov     ebx, r13d
0x18001f7e4  mov     [rsp+1F0h+var_1A8], rbx
0x18001f7e9  cmp     rdi, r14
0x18001f7ec  jz      short loc_18001F810
0x18001f7ee  test    byte ptr [rdi+1Ch], 4
0x18001f7f2  jz      short loc_18001F810
0x18001f7f4  lea     edx, [r13+57h]
0x18001f7f8  mov     [rsp+1F0h+var_1D0], r15d
0x18001f7fd  mov     r9d, r12d
0x18001f800  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001f807  mov     rcx, [rdi+10h]
0x18001f80b  call    WPP_SF_dd
0x18001f810  lea     rcx, [rsi+0E8h]; lpCriticalSection
0x18001f817  call    cs:__imp_EnterCriticalSection
0x18001f81d  mov     eax, [rsi+0E0h]
0x18001f823  cmp     eax, 3
0x18001f826  jnz     short loc_18001F866
0x18001f828  mov     r14d, r13d
0x18001f82b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f832  lea     rax, WPP_GLOBAL_Control
0x18001f839  cmp     rcx, rax
0x18001f83c  jz      loc_18001FC88
0x18001f842  test    byte ptr [rcx+1Ch], 4
0x18001f846  jz      loc_18001FC88
0x18001f84c  mov     edx, 58h ; 'X'
0x18001f851  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001f858  mov     rcx, [rcx+10h]
0x18001f85c  call    WPP_SF_
0x18001f861  jmp     loc_18001FC88
0x18001f866  mov     edi, 80004005h
0x18001f86b  mov     rdx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data1; struct _GUID *
0x18001f872  test    rdx, rdx
0x18001f875  jnz     short loc_18001F87F
0x18001f877  mov     r14d, 8000FFFFh
0x18001f87d  jmp     short loc_18001F8B0
0x18001f87f  lea     r8, [rsp+1F0h+var_1A8]; struct TetheringSessionTelemetry **
0x18001f884  call    ?GetSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@PEAPEAVTetheringSessionTelemetry@@@Z; TetheringServiceTelemetry::GetSession(_GUID *,TetheringSessionTelemetry * *)
0x18001f889  mov     r14d, eax
0x18001f88c  mov     rbx, [rsp+1F0h+var_1A8]
0x18001f891  test    eax, eax
0x18001f893  js      short loc_18001F8B0
0x18001f895  test    rbx, rbx
0x18001f898  jnz     short loc_18001F8A2
0x18001f89a  mov     r14d, 80004003h
0x18001f8a0  jmp     short loc_18001F8B0
0x18001f8a2  mov     rcx, rbx; this
0x18001f8a5  call    ?Initialized@TetheringSessionTelemetry@@QEAAHXZ; TetheringSessionTelemetry::Initialized(void)
0x18001f8aa  test    eax, eax
0x18001f8ac  cmovz   r14d, edi
0x18001f8b0  mov     dword ptr [rsi+0E0h], 5
0x18001f8ba  test    r12b, 1
0x18001f8be  jz      short loc_18001F8E4
0x18001f8c0  xor     edx, edx; Val
0x18001f8c2  mov     r8d, 0D0h; Size
0x18001f8c8  lea     rcx, [rbp+0F0h+var_12C]; void *
0x18001f8cc  call    memset_0
0x18001f8d1  mov     [rbp+0F0h+var_130], 9
0x18001f8d8  lea     rdx, [rbp+0F0h+var_130]; struct _TETHERING_WNF_NOTIFICATION_MSG *
0x18001f8dc  mov     rcx, rsi; this
0x18001f8df  call    ?SendNotification@TetheringService@@AEAAXPEAU_TETHERING_WNF_NOTIFICATION_MSG@@@Z; TetheringService::SendNotification(_TETHERING_WNF_NOTIFICATION_MSG *)
0x18001f8e4  call    ?IsMobile@@YA_NXZ; IsMobile(void)
0x18001f8e9  test    al, al
0x18001f8eb  jnz     short loc_18001F93C
0x18001f8ed  cmp     dword ptr [rsi+1D8h], 8
0x18001f8f4  jnz     short loc_18001F93C
0x18001f8f6  mov     [rsp+1F0h+var_1C0], 1
0x18001f8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f902  lea     rax, WPP_GLOBAL_Control
0x18001f909  cmp     rcx, rax
0x18001f90c  jz      short loc_18001F929
0x18001f90e  test    byte ptr [rcx+1Ch], 4
0x18001f912  jz      short loc_18001F929
0x18001f914  mov     edx, 59h ; 'Y'
0x18001f919  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001f920  mov     rcx, [rcx+10h]
0x18001f924  call    WPP_SF_
0x18001f929  lea     rcx, [rsi+508h]
0x18001f930  mov     edx, 0Bh
0x18001f935  call    ?PublishWnfEvent@CSebHelper@@SAJAEBU_GUID@@W4NotificationMessageType@@I@Z; CSebHelper::PublishWnfEvent(_GUID const &,NotificationMessageType,uint)
0x18001f93a  jmp     short loc_18001F941
0x18001f93c  mov     [rsp+1F0h+var_1C0], r13b
0x18001f941  call    ?IsMobile@@YA_NXZ; IsMobile(void)
0x18001f946  test    al, al
0x18001f948  jz      short loc_18001F9A9
0x18001f94a  mov     [rsp+1F0h+var_1BF], 1
0x18001f94f  lea     rdi, [rsi+5D0h]
0x18001f956  mov     rcx, rdi; lpCriticalSection
0x18001f959  call    cs:__imp_EnterCriticalSection
0x18001f95f  mov     rax, [rsi+690h]
0x18001f966  mov     qword ptr [rsp+1F0h+var_198], rax
0x18001f96b  mov     [rsi+690h], r13
0x18001f972  mov     rax, [rsi+698h]
0x18001f979  mov     qword ptr [rsp+1F0h+var_198+8], rax
0x18001f97e  mov     [rsi+698h], r13
0x18001f985  mov     rax, [rsi+688h]
0x18001f98c  mov     [rsp+1F0h+var_188], rax
0x18001f991  mov     [rsi+688h], r13
0x18001f998  mov     [rsi+680h], r13w
0x18001f9a0  mov     rcx, rdi; lpCriticalSection
0x18001f9a3  call    cs:__imp_LeaveCriticalSection
0x18001f9a9  mov     [rsp+1F0h+var_1D0], 4; int
0x18001f9b1  mov     r9, rsi
0x18001f9b4  lea     r8, ?NdisWmiEventNotificationHandler@TetheringService@@CAXPEAU_WNODE_HEADER@@_K@Z; TetheringService::NdisWmiEventNotificationHandler(_WNODE_HEADER *,unsigned __int64)
0x18001f9bb  xor     edx, edx
0x18001f9bd  lea     rcx, GUID_NDIS_NOTIFY_ADAPTER_REMOVAL
0x18001f9c4  call    cs:__imp_WmiNotificationRegistrationW
0x18001f9ca  lea     rcx, [rsi+6B0h]; this
0x18001f9d1  call    ?StopMonitor@CNsiInterfaceMonitor@@QEAAXXZ; CNsiInterfaceMonitor::StopMonitor(void)
0x18001f9d6  lea     rdi, [rsi+160h]
0x18001f9dd  mov     eax, [rdi+7Ch]
0x18001f9e0  dec     eax
0x18001f9e2  test    eax, 0FFFFFFF7h
0x18001f9e7  jnz     short loc_18001F9F2
0x18001f9e9  mov     r13b, 1
0x18001f9ec  test    r12b, 4
0x18001f9f0  jnz     short loc_18001FA2C
0x18001f9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9f9  lea     rax, WPP_GLOBAL_Control
0x18001fa00  cmp     rcx, rax
0x18001fa03  jz      short loc_18001FA20
0x18001fa05  test    byte ptr [rcx+1Ch], 4
0x18001fa09  jz      short loc_18001FA20
0x18001fa0b  mov     edx, 5Ah ; 'Z'
0x18001fa10  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001fa17  mov     rcx, [rcx+10h]
0x18001fa1b  call    WPP_SF_
0x18001fa20  lea     rcx, [rsi+4A0h]; this
0x18001fa27  call    ?Stop@BtPanHandler@@QEAAJXZ; BtPanHandler::Stop(void)
0x18001fa2c  cmp     byte ptr [rsi+296h], 0
0x18001fa33  jz      short loc_18001FA5D
0x18001fa35  mov     rdx, [rsi+240h]; Timer
0x18001fa3c  test    rdx, rdx
0x18001fa3f  jz      short loc_18001FA5D
0x18001fa41  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001fa45  mov     rcx, [rsi+238h]; TimerQueue
0x18001fa4c  call    cs:__imp_DeleteTimerQueueTimer
0x18001fa52  mov     qword ptr [rsi+240h], 0
0x18001fa5d  mov     rcx, rsi; this
0x18001fa60  call    ?UnregisterEntitlementFailedCallback@TetheringService@@AEAAXXZ; TetheringService::UnregisterEntitlementFailedCallback(void)
0x18001fa65  mov     [rsp+1F0h+var_1BC], 0
0x18001fa6d  mov     [rsp+1F0h+var_1B8], 0
0x18001fa75  lea     r8, [rsp+1F0h+var_1B8]; unsigned int *
0x18001fa7a  lea     rdx, [rsp+1F0h+var_1BC]; unsigned int *
0x18001fa7f  mov     rcx, rdi; this
0x18001fa82  call    ?GetSharedInterfaceIndices@InterfaceMgr@@QEAAJPEAK0@Z; InterfaceMgr::GetSharedInterfaceIndices(ulong *,ulong *)
0x18001fa87  mov     rcx, [rbp+0F8h]; this
0x18001fa8e  test    eax, eax
0x18001fa90  jns     short loc_18001FAA6
0x18001fa92  mov     r9d, eax; char *
0x18001fa95  lea     r8, aOnecoreuapNetT_2; "onecoreuap\\net\\tethering\\service\\te"...
0x18001fa9c  mov     edx, 478h; void *
0x18001faa1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001faa6  mov     rcx, rdi; this
0x18001faa9  call    ?DisableSharedInterfaces@InterfaceMgr@@QEAAJXZ; InterfaceMgr::DisableSharedInterfaces(void)
0x18001faae  lea     rcx, [rsi+138h]; this
0x18001fab5  call    ?Stop@SharedAccessSvcMgr@@QEAAJXZ; SharedAccessSvcMgr::Stop(void)
0x18001faba  movups  xmm0, xmmword ptr [rsi+1B0h]
0x18001fac1  mov     eax, [rsi+1C0h]
0x18001fac7  mov     r9d, [rsi+0E0h]; unsigned int
0x18001face  mov     [rbp+0F0h+var_50], 19h
0x18001fad8  movdqu  [rbp+0F0h+var_4C], xmm0
0x18001fae0  mov     [rbp+0F0h+var_3C], eax
0x18001fae6  mov     [rsp+1F0h+var_1D0], r15d; unsigned int
0x18001faeb  mov     r8d, [rsp+1F0h+var_1BC]; unsigned int
0x18001faf0  mov     edx, [rsp+1F0h+var_1B8]; unsigned int
0x18001faf4  lea     rcx, [rbp+0F0h+var_50]; struct NetworkingTriageScenario::MobileHotspot::RequiredFields *
0x18001fafb  call    ?TetheringStopped@MobileHotspot@NetworkingTriageScenario@@SAXAEBURequiredFields@12@KKKK@Z; NetworkingTriageScenario::MobileHotspot::TetheringStopped(NetworkingTriageScenario::MobileHotspot::RequiredFields const &,ulong,ulong,ulong,ulong)
0x18001fb00  xor     edi, edi
0x18001fb02  mov     [rsp+1F0h+var_1B4], edi
0x18001fb06  mov     [rsp+1F0h+Block], rdi
0x18001fb0b  xor     r9d, r9d; int
0x18001fb0e  lea     r8, [rsp+1F0h+Block]; struct _TETHERING_PEER_CONNECTION_DATA **
0x18001fb13  lea     rdx, [rsp+1F0h+var_1B4]; unsigned int *
0x18001fb18  mov     rcx, rsi; this
0x18001fb1b  call    ?GetPeerList@TetheringService@@QEAAJPEAKPEAPEAU_TETHERING_PEER_CONNECTION_DATA@@H@Z; TetheringService::GetPeerList(ulong *,_TETHERING_PEER_CONNECTION_DATA * *,int)
0x18001fb20  test    eax, eax
0x18001fb22  jnz     short loc_18001FB58
0x18001fb24  mov     r15d, [rsp+1F0h+var_1B4]
0x18001fb29  test    r15d, r15d
0x18001fb2c  jz      short loc_18001FB4B
0x18001fb2e  mov     eax, edi
0x18001fb30  imul    rdx, rax, 0E2h
0x18001fb37  add     rdx, [rsp+1F0h+Block]; unsigned __int8 (*)[6]
0x18001fb3c  mov     rcx, rsi; this
0x18001fb3f  call    ?RemovePeer@TetheringService@@QEAAXPEAY05E@Z; TetheringService::RemovePeer(uchar (*)[6])
0x18001fb44  inc     edi
0x18001fb46  cmp     edi, r15d
0x18001fb49  jb      short loc_18001FB2E
0x18001fb4b  mov     rcx, [rsp+1F0h+Block]; Block
0x18001fb50  call    cs:__imp_free
0x18001fb56  xor     edi, edi
0x18001fb58  or      r15d, 0FFFFFFFFh
0x18001fb5c  mov     r9d, r15d; Period
0x18001fb5f  mov     r8d, r15d; DueTime
0x18001fb62  mov     rdx, [rsi+628h]; Timer
0x18001fb69  mov     rcx, [rsi+630h]; TimerQueue
0x18001fb70  call    cs:__imp_ChangeTimerQueueTimer
0x18001fb76  test    eax, eax
0x18001fb78  jz      short loc_18001FB81
0x18001fb7a  mov     [rsi+63Ch], dil
0x18001fb81  mov     r9d, r15d; Period
0x18001fb84  mov     r8d, r15d; DueTime
0x18001fb87  mov     rdx, [rsi+640h]; Timer
0x18001fb8e  mov     rcx, [rsi+648h]; TimerQueue
0x18001fb95  call    cs:__imp_ChangeTimerQueueTimer
0x18001fb9b  test    eax, eax
0x18001fb9d  jz      short loc_18001FBA6
0x18001fb9f  mov     [rsi+654h], dil
0x18001fba6  mov     r9d, r15d; Period
0x18001fba9  mov     r8d, [rsi+668h]; DueTime
0x18001fbb0  mov     rdx, [rsi+658h]; Timer
0x18001fbb7  mov     rcx, [rsi+660h]; TimerQueue
0x18001fbbe  call    cs:__imp_ChangeTimerQueueTimer
0x18001fbc4  test    eax, eax
0x18001fbc6  jz      short loc_18001FBCF
0x18001fbc8  mov     byte ptr [rsi+66Ch], 1
0x18001fbcf  test    r13b, r13b
0x18001fbd2  jz      short loc_18001FBE4
0x18001fbd4  test    r12b, 2
0x18001fbd8  jnz     short loc_18001FBE4
0x18001fbda  xor     edx, edx; bool
0x18001fbdc  mov     rcx, rsi; this
0x18001fbdf  call    ?SetWiFiPowerState@TetheringService@@AEAAJ_N@Z; TetheringService::SetWiFiPowerState(bool)
0x18001fbe4  mov     dword ptr [rsi+0E0h], 3
0x18001fbee  lea     rcx, [rsi+8]; void *
0x18001fbf2  xor     edx, edx; Val
0x18001fbf4  mov     r8d, 0D4h; Size
0x18001fbfa  call    memset_0
0x18001fbff  mov     [rsi+0DCh], dil
0x18001fc06  lea     rdi, [rsi+6D8h]
0x18001fc0d  mov     rcx, rdi; lpCriticalSection
0x18001fc10  call    cs:__imp_EnterCriticalSection
0x18001fc16  mov     r15d, r14d
0x18001fc19  shr     r15d, 1Fh
0x18001fc1d  xor     r15b, 1
0x18001fc21  cmp     byte ptr [rdi+28h], 0
0x18001fc25  jz      short loc_18001FC35
0x18001fc27  xor     edx, edx; bool
0x18001fc29  mov     rcx, rdi; this
0x18001fc2c  call    ?PreventSleepInternal@CPowerHandler@@AEAAJ_N@Z; CPowerHandler::PreventSleepInternal(bool)
0x18001fc31  mov     byte ptr [rdi+28h], 0
0x18001fc35  mov     rcx, rdi; lpCriticalSection
0x18001fc38  call    cs:__imp_LeaveCriticalSection
0x18001fc3e  test    r15b, r15b
0x18001fc41  jz      short loc_18001FC7E
0x18001fc43  test    rbx, rbx
0x18001fc46  jz      loc_18001FE32
0x18001fc4c  lea     r8, [rsp+1F0h+var_180]; struct TetheringServiceTelemetry::SESSION_DATA *
0x18001fc51  mov     rdx, rbx; struct TetheringSessionTelemetry *
0x18001fc54  call    ?AcquireSessionData@TetheringServiceTelemetry@@QEAAXAEAVTetheringSessionTelemetry@@AEAUSESSION_DATA@1@@Z; TetheringServiceTelemetry::AcquireSessionData(TetheringSessionTelemetry &,TetheringServiceTelemetry::SESSION_DATA &)
0x18001fc59  mov     rax, [rbp+0F0h+var_138]
0x18001fc5d  mov     r15d, [rsp+1F0h+var_1B0]
0x18001fc62  mov     [rax+24h], r15d
0x18001fc66  mov     dword ptr [rax+20h], 0
0x18001fc6d  lea     rcx, [rbx+10h]; SRWLock
0x18001fc71  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fc77  call    ?StopSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@@Z; TetheringServiceTelemetry::StopSession(_GUID *)
0x18001fc7c  jmp     short loc_18001FC83
0x18001fc7e  mov     r15d, [rsp+1F0h+var_1B0]
  ... truncated ...
```
