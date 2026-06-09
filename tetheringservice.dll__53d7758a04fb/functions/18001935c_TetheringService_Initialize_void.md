# TetheringService::Initialize(void)

- ea: `0x18001935c`
- end: `0x180019b46`
- name: `?Initialize@TetheringService@@QEAAJXZ`
- size: `2026`
- prototype: `__int64 __fastcall(TetheringService *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000b888`

## callees

- `0x180001720`
- `0x180002590`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000cfd4`
- `0x18000f498`
- `0x180015e30`
- `0x18001935c`
- `0x18001a3ec`
- `0x18001a714`
- `0x18002b1f0`
- `0x18002bd20`
- `0x180031580`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019956`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019956`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800194c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019516`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001956c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800194c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019516`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001956c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800199e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019aa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800199e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019aa5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019966`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001957e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001963b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001957e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001963b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019739`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180019451`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180019451`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001993c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001993c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800195b7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800195b7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001962c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800196ba`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001972f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001962c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800196ba`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001972f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180019a19`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180019a6e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180019a19`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180019a6e`
- `ntdll!NtQueryWnfStateData` at `0x18001999e`
- `ntdll!NtQueryWnfStateData` at `0x18001999e`

## pseudocode

```c
__int64 __fastcall TetheringService::Initialize(TetheringService *this)
{
  int v2; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int LastError; // eax
  int v5; // ebx
  TetheringServiceTelemetry *v6; // rcx
  __int64 v7; // rdx
  HANDLE EventW; // rax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  HANDLE TimerQueue; // rax
  HANDLE v13; // rbx
  signed int v14; // eax
  signed int v15; // eax
  TetheringServiceTelemetry *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  void *v19; // rbp
  signed int v20; // eax
  void *v21; // rbx
  TetheringService *v22; // rcx
  signed int v23; // eax
  int AutoLoadSettingsInternal; // eax
  TetheringService *v25; // rcx
  unsigned int v26; // eax
  int v27; // ebx
  TetheringServiceTelemetry *v28; // rcx
  int v29; // ebp
  _DWORD *SettingValueGlobalInternal; // rax
  void *v31; // rsi
  ULONG v32; // ebp
  int v33; // eax
  TetheringServiceTelemetry *v34; // rcx
  __int64 v35; // rdx
  int v36; // eax
  unsigned int v37; // eax
  TetheringServiceTelemetry *v38; // rcx
  int v40; // [rsp+40h] [rbp-1068h] BYREF
  unsigned int v41; // [rsp+44h] [rbp-1064h] BYREF
  int v42; // [rsp+48h] [rbp-1060h] BYREF
  _BYTE v43[4096]; // [rsp+50h] [rbp-1058h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v40 = 0;
  v2 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180041008);
  g_lTraceLoggingRegistered = v2;
  if ( v2 < 0
    && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)v2);
  }
  *((_DWORD *)this + 452) = 3;
  *((_DWORD *)this + 467) = 1;
  *((_QWORD *)this + 227) = 0;
  *((_QWORD *)this + 228) = 0;
  *((_QWORD *)this + 229) = 0;
  *((_QWORD *)this + 230) = 0;
  *((_QWORD *)this + 231) = 0;
  *((_QWORD *)this + 232) = 0;
  *((_DWORD *)this + 466) = 0;
  *((_DWORD *)this + 468) = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 235) = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 16;
LABEL_14:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, (unsigned int)v5);
      goto LABEL_120;
    }
    goto LABEL_120;
  }
  *((_QWORD *)this + 228) = ThreadpoolCleanupGroup;
  *((_QWORD *)this + 229) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 194) = EventW;
  if ( EventW )
  {
    g_hWlanDisconnected = CreateEventW(0, 1, 0, 0);
    if ( !g_hWlanDisconnected )
    {
      v10 = GetLastError();
      v5 = v10;
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 18;
        goto LABEL_14;
      }
      goto LABEL_120;
    }
    g_hWlanPowerSet = CreateEventW(0, 1, 0, 0);
    if ( !g_hWlanPowerSet )
    {
      v11 = GetLastError();
      v5 = v11;
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 19;
        goto LABEL_14;
      }
      goto LABEL_120;
    }
    TimerQueue = CreateTimerQueue();
    *((_QWORD *)this + 195) = TimerQueue;
    v13 = TimerQueue;
    if ( !TimerQueue )
    {
      v14 = GetLastError();
      v5 = v14;
      if ( v14 > 0 )
        v5 = (unsigned __int16)v14 | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 20;
        goto LABEL_14;
      }
      goto LABEL_120;
    }
    if ( CreateTimerQueueTimer(
           (PHANDLE)this + 197,
           TimerQueue,
           TetheringService::PeerlesTimeoutCallback,
           this,
           0xFFFFFFFF,
           0xFFFFFFFF,
           0) )
    {
      *((_QWORD *)this + 198) = v13;
    }
    else
    {
      v15 = GetLastError();
      v5 = v15;
      if ( v15 > 0 )
        v5 = (unsigned __int16)v15 | 0x80070000;
      if ( v5 < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_121;
        }
        v17 = 21;
        goto LABEL_46;
      }
    }
    v19 = (void *)*((_QWORD *)this + 195);
    if ( CreateTimerQueueTimer(
           (PHANDLE)this + 200,
           v19,
           TetheringService::PubConDownTimeoutCallback,
           this,
           0xFFFFFFFF,
           0xFFFFFFFF,
           0) )
    {
      *((_QWORD *)this + 201) = v19;
    }
    else
    {
      v20 = GetLastError();
      v5 = v20;
      if ( v20 > 0 )
        v5 = (unsigned __int16)v20 | 0x80070000;
      if ( v5 < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_121;
        }
        v17 = 22;
LABEL_46:
        v18 = (unsigned int)v5;
LABEL_47:
        WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v18);
LABEL_121:
        TetheringService::CleanUp(this);
        *((_DWORD *)this + 56) = 1;
        goto LABEL_123;
      }
    }
    v21 = (void *)*((_QWORD *)this + 195);
    if ( CreateTimerQueueTimer(
           (PHANDLE)this + 203,
           v21,
           TetheringService::ServiceInactivityTimeoutCallback,
           this,
           0xFFFFFFFF,
           0xFFFFFFFF,
           0) )
    {
      *((_QWORD *)this + 204) = v21;
    }
    else
    {
      v23 = GetLastError();
      v5 = v23;
      if ( v23 > 0 )
        v5 = (unsigned __int16)v23 | 0x80070000;
      if ( v5 < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_121;
        }
        v17 = 23;
        v18 = (unsigned int)v5;
        goto LABEL_47;
      }
    }
    *((_BYTE *)this + 1890) = 1;
    AutoLoadSettingsInternal = TetheringService::MigrateSettingsNeeded(v22, &v40);
    v5 = AutoLoadSettingsInternal;
    if ( AutoLoadSettingsInternal < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_121;
      }
      v17 = 25;
      goto LABEL_69;
    }
    if ( v40 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 391, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      }
      v26 = TetheringService::MigratePrivateConnectionInformation(v25);
      v27 = v26;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 392, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v26);
        v28 = WPP_GLOBAL_Control;
      }
      if ( v27 == -2147024894 )
      {
        if ( v28 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)v28 + 2), 26, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      }
      else if ( v27 < 0 && v28 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v28 + 2), 27, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, (unsigned int)v27);
      }
    }
    AutoLoadSettingsInternal = TetheringSettingsLoadAutoLoadSettingsInternal();
    v5 = AutoLoadSettingsInternal;
    if ( AutoLoadSettingsInternal < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_121;
      }
      v17 = 28;
      goto LABEL_69;
    }
    AutoLoadSettingsInternal = EntitlementMgr::Initialize((TetheringService *)((char *)this + 568));
    v5 = AutoLoadSettingsInternal;
    if ( AutoLoadSettingsInternal < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_121;
      }
      v17 = 29;
      goto LABEL_69;
    }
    AutoLoadSettingsInternal = SharedAccessSvcMgr::Initialize((TetheringService *)((char *)this + 312));
    v5 = AutoLoadSettingsInternal;
    if ( AutoLoadSettingsInternal < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_121;
      }
      v17 = 31;
LABEL_69:
      v18 = (unsigned int)AutoLoadSettingsInternal;
      goto LABEL_47;
    }
    v29 = 5;
    SettingValueGlobalInternal = (_DWORD *)TetheringSettingsGetSettingValueGlobalInternal(8);
    v31 = SettingValueGlobalInternal;
    if ( SettingValueGlobalInternal )
      v29 = *SettingValueGlobalInternal;
    v32 = 60000 * v29;
    if ( ChangeTimerQueueTimer(*((HANDLE *)this + 204), *((HANDLE *)this + 203), v32, 0xFFFFFFFF) )
    {
      *((_DWORD *)this + 410) = v32;
      *((_BYTE *)this + 1644) = 1;
    }
    if ( v31 )
      free(v31);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
    v41 = 0;
    v42 = 4096;
    v33 = NtQueryWnfStateData(&WNF_SHR_DHCP_IPv4_LEASE_LIST, 0, 0, &v41, v43, &v42);
    if ( v33 && (v5 = v33 | 0x10000000, v33 < 0) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_109;
      }
      v35 = 32;
    }
    else
    {
      v36 = RtlSubscribeWnfStateChangeNotification(
              (char *)this + 1696,
              WNF_SHR_DHCP_IPv4_LEASE_LIST,
              v41,
              TetheringService::SharedAccessWnfCallback,
              0,
              0,
              0,
              0);
      if ( !v36 || (v5 = v36 | 0x10000000, v36 >= 0) )
      {
        v37 = RtlSubscribeWnfStateChangeNotification(
                (char *)this + 1704,
                WNF_ENTR_WIFI_POLICY_VALUE_CHANGED,
                0,
                TetheringService::MdmPolicyWnfCallback,
                0,
                0,
                0,
                0);
        if ( v37
          && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v37);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
        goto LABEL_120;
      }
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_109;
      }
      v35 = 33;
    }
    WPP_SF_d(*((_QWORD *)v34 + 2), v35, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, (unsigned int)v5);
LABEL_109:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
    goto LABEL_121;
  }
  v9 = GetLastError();
  v5 = v9;
  if ( v9 > 0 )
    v5 = (unsigned __int16)v9 | 0x80070000;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 17;
    goto LABEL_14;
  }
LABEL_120:
  if ( v5 < 0 )
    goto LABEL_121;
  *((_BYTE *)this + 1888) = 1;
LABEL_123:
  v38 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
        *((unsigned __int8 *)this + 1888));
      v38 = WPP_GLOBAL_Control;
    }
    if ( v38 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)v38 + 2), 36, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001935c  push    rbx
0x18001935e  push    rbp
0x18001935f  push    rsi
0x180019360  push    rdi
0x180019361  push    r12
0x180019363  push    r13
0x180019365  push    r14
0x180019367  push    r15
0x180019369  mov     eax, 1068h
0x18001936e  call    _alloca_probe
0x180019373  sub     rsp, rax
0x180019376  mov     rax, cs:__security_cookie
0x18001937d  xor     rax, rsp
0x180019380  mov     [rsp+10A8h+var_58], rax
0x180019388  mov     rdi, rcx
0x18001938b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019392  lea     r12, WPP_GLOBAL_Control
0x180019399  lea     r14, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800193a0  cmp     rcx, r12
0x1800193a3  jz      short loc_1800193BC
0x1800193a5  test    byte ptr [rcx+1Ch], 8
0x1800193a9  jz      short loc_1800193BC
0x1800193ab  mov     rcx, [rcx+10h]
0x1800193af  mov     edx, 0Eh
0x1800193b4  mov     r8, r14
0x1800193b7  call    WPP_SF_
0x1800193bc  xor     r15d, r15d
0x1800193bf  lea     rcx, dword_180041008; CallbackContext
0x1800193c6  mov     [rsp+10A8h+var_1068], r15d
0x1800193cb  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800193d0  mov     cs:?g_lTraceLoggingRegistered@@3JA, eax; long g_lTraceLoggingRegistered
0x1800193d6  test    eax, eax
0x1800193d8  jns     short loc_1800193FF
0x1800193da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193e1  cmp     rcx, r12
0x1800193e4  jz      short loc_1800193FF
0x1800193e6  test    byte ptr [rcx+1Ch], 2
0x1800193ea  jz      short loc_1800193FF
0x1800193ec  mov     rcx, [rcx+10h]
0x1800193f0  lea     edx, [r15+0Fh]
0x1800193f4  mov     r9d, eax
0x1800193f7  mov     r8, r14
0x1800193fa  call    WPP_SF_d
0x1800193ff  mov     r13d, 1
0x180019405  mov     dword ptr [rdi+710h], 3
0x18001940f  mov     [rdi+74Ch], r13d
0x180019416  mov     [rdi+718h], r15
0x18001941d  mov     [rdi+720h], r15
0x180019424  mov     [rdi+728h], r15
0x18001942b  mov     [rdi+730h], r15
0x180019432  mov     [rdi+738h], r15
0x180019439  mov     [rdi+740h], r15
0x180019440  mov     [rdi+748h], r15d
0x180019447  mov     dword ptr [rdi+750h], 48h ; 'H'
0x180019451  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180019457  mov     [rdi+758h], rax
0x18001945e  test    rax, rax
0x180019461  jnz     short loc_1800194AB
0x180019463  call    cs:__imp_GetLastError
0x180019469  mov     ebx, eax
0x18001946b  test    eax, eax
0x18001946d  jle     short loc_180019478
0x18001946f  movzx   ebx, ax
0x180019472  or      ebx, 80070000h
0x180019478  mov     rcx, cs:WPP_GLOBAL_Control
0x18001947f  cmp     rcx, r12
0x180019482  jz      loc_180019AAB
0x180019488  test    [rcx+1Ch], r13b
0x18001948c  jz      loc_180019AAB
0x180019492  mov     edx, 10h
0x180019497  mov     rcx, [rcx+10h]
0x18001949b  mov     r9d, ebx
0x18001949e  mov     r8, r14
0x1800194a1  call    WPP_SF_d
0x1800194a6  jmp     loc_180019AAB
0x1800194ab  xor     r9d, r9d; lpName
0x1800194ae  mov     [rdi+720h], rax
0x1800194b5  xor     r8d, r8d; bInitialState
0x1800194b8  mov     [rdi+728h], r15
0x1800194bf  xor     edx, edx; bManualReset
0x1800194c1  xor     ecx, ecx; lpEventAttributes
0x1800194c3  call    cs:__imp_CreateEventW
0x1800194c9  mov     [rdi+610h], rax
0x1800194d0  test    rax, rax
0x1800194d3  jnz     short loc_18001950B
0x1800194d5  call    cs:__imp_GetLastError
0x1800194db  mov     ebx, eax
0x1800194dd  test    eax, eax
0x1800194df  jle     short loc_1800194EA
0x1800194e1  movzx   ebx, ax
0x1800194e4  or      ebx, 80070000h
0x1800194ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194f1  cmp     rcx, r12
0x1800194f4  jz      loc_180019AAB
0x1800194fa  test    [rcx+1Ch], r13b
0x1800194fe  jz      loc_180019AAB
0x180019504  mov     edx, 11h
0x180019509  jmp     short loc_180019497
0x18001950b  xor     r9d, r9d; lpName
0x18001950e  xor     r8d, r8d; bInitialState
0x180019511  mov     edx, r13d; bManualReset
0x180019514  xor     ecx, ecx; lpEventAttributes
0x180019516  call    cs:__imp_CreateEventW
0x18001951c  mov     cs:?g_hWlanDisconnected@@3PEAXEA, rax; void * g_hWlanDisconnected
0x180019523  test    rax, rax
0x180019526  jnz     short loc_180019561
0x180019528  call    cs:__imp_GetLastError
0x18001952e  mov     ebx, eax
0x180019530  test    eax, eax
0x180019532  jle     short loc_18001953D
0x180019534  movzx   ebx, ax
0x180019537  or      ebx, 80070000h
0x18001953d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019544  cmp     rcx, r12
0x180019547  jz      loc_180019AAB
0x18001954d  test    [rcx+1Ch], r13b
0x180019551  jz      loc_180019AAB
0x180019557  mov     edx, 12h
0x18001955c  jmp     loc_180019497
0x180019561  xor     r9d, r9d; lpName
0x180019564  xor     r8d, r8d; bInitialState
0x180019567  mov     edx, r13d; bManualReset
0x18001956a  xor     ecx, ecx; lpEventAttributes
0x18001956c  call    cs:__imp_CreateEventW
0x180019572  mov     cs:?g_hWlanPowerSet@@3PEAXEA, rax; void * g_hWlanPowerSet
0x180019579  test    rax, rax
0x18001957c  jnz     short loc_1800195B7
0x18001957e  call    cs:__imp_GetLastError
0x180019584  mov     ebx, eax
0x180019586  test    eax, eax
0x180019588  jle     short loc_180019593
0x18001958a  movzx   ebx, ax
0x18001958d  or      ebx, 80070000h
0x180019593  mov     rcx, cs:WPP_GLOBAL_Control
0x18001959a  cmp     rcx, r12
0x18001959d  jz      loc_180019AAB
0x1800195a3  test    [rcx+1Ch], r13b
0x1800195a7  jz      loc_180019AAB
0x1800195ad  mov     edx, 13h
0x1800195b2  jmp     loc_180019497
0x1800195b7  call    cs:__imp_CreateTimerQueue
0x1800195bd  mov     [rdi+618h], rax
0x1800195c4  mov     rbx, rax
0x1800195c7  test    rax, rax
0x1800195ca  jnz     short loc_180019605
0x1800195cc  call    cs:__imp_GetLastError
0x1800195d2  mov     ebx, eax
0x1800195d4  test    eax, eax
0x1800195d6  jle     short loc_1800195E1
0x1800195d8  movzx   ebx, ax
0x1800195db  or      ebx, 80070000h
0x1800195e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195e8  cmp     rcx, r12
0x1800195eb  jz      loc_180019AAB
0x1800195f1  test    [rcx+1Ch], r13b
0x1800195f5  jz      loc_180019AAB
0x1800195fb  mov     edx, 14h
0x180019600  jmp     loc_180019497
0x180019605  or      eax, 0FFFFFFFFh
0x180019608  mov     [rsp+10A8h+Flags], r15d; Flags
0x18001960d  mov     [rsp+10A8h+Period], eax; Period
0x180019611  lea     rbp, [rdi+628h]
0x180019618  mov     rcx, rbp; phNewTimer
0x18001961b  mov     [rsp+10A8h+DueTime], eax; DueTime
0x18001961f  mov     r9, rdi; Parameter
0x180019622  lea     r8, ?PeerlesTimeoutCallback@TetheringService@@CAXPEAXE@Z; Callback
0x180019629  mov     rdx, rbx; TimerQueue
0x18001962c  call    cs:__imp_CreateTimerQueueTimer
0x180019632  mov     esi, 80070000h
0x180019637  test    eax, eax
0x180019639  jnz     short loc_180019683
0x18001963b  call    cs:__imp_GetLastError
0x180019641  mov     ebx, eax
0x180019643  test    eax, eax
0x180019645  jle     short loc_18001964C
0x180019647  movzx   ebx, ax
0x18001964a  or      ebx, esi
0x18001964c  test    ebx, ebx
0x18001964e  jns     short loc_180019687
0x180019650  mov     rcx, cs:WPP_GLOBAL_Control
0x180019657  cmp     rcx, r12
0x18001965a  jz      loc_180019AAF
0x180019660  test    [rcx+1Ch], r13b
0x180019664  jz      loc_180019AAF
0x18001966a  mov     edx, 15h
0x18001966f  mov     r9d, ebx
0x180019672  mov     r8, r14
0x180019675  mov     rcx, [rcx+10h]
0x180019679  call    WPP_SF_d
0x18001967e  jmp     loc_180019AAF
0x180019683  mov     [rbp+8], rbx
0x180019687  mov     rbp, [rdi+618h]
0x18001968e  lea     rbx, [rdi+640h]
0x180019695  mov     [rsp+10A8h+Flags], r15d; Flags
0x18001969a  lea     r8, ?PubConDownTimeoutCallback@TetheringService@@CAXPEAXE@Z; Callback
0x1800196a1  mov     rdx, rbp; TimerQueue
0x1800196a4  mov     [rsp+10A8h+Period], 0FFFFFFFFh; Period
0x1800196ac  mov     rcx, rbx; phNewTimer
0x1800196af  mov     [rsp+10A8h+DueTime], 0FFFFFFFFh; DueTime
0x1800196b7  mov     r9, rdi; Parameter
0x1800196ba  call    cs:__imp_CreateTimerQueueTimer
0x1800196c0  test    eax, eax
0x1800196c2  jnz     short loc_1800196FD
0x1800196c4  call    cs:__imp_GetLastError
0x1800196ca  mov     ebx, eax
0x1800196cc  test    eax, eax
0x1800196ce  jle     short loc_1800196D5
0x1800196d0  movzx   ebx, ax
0x1800196d3  or      ebx, esi
0x1800196d5  test    ebx, ebx
0x1800196d7  jns     short loc_180019701
0x1800196d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196e0  cmp     rcx, r12
0x1800196e3  jz      loc_180019AAF
0x1800196e9  test    [rcx+1Ch], r13b
0x1800196ed  jz      loc_180019AAF
0x1800196f3  mov     edx, 16h
0x1800196f8  jmp     loc_18001966F
0x1800196fd  mov     [rbx+8], rbp
0x180019701  mov     rbx, [rdi+618h]
0x180019708  lea     r14, [rdi+658h]
0x18001970f  or      eax, 0FFFFFFFFh
0x180019712  mov     [rsp+10A8h+Flags], r15d; Flags
0x180019717  mov     [rsp+10A8h+Period], eax; Period
0x18001971b  lea     r8, ?ServiceInactivityTimeoutCallback@TetheringService@@CAXPEAXE@Z; Callback
0x180019722  mov     rdx, rbx; TimerQueue
0x180019725  mov     [rsp+10A8h+DueTime], eax; DueTime
0x180019729  mov     rcx, r14; phNewTimer
0x18001972c  mov     r9, rdi; Parameter
0x18001972f  call    cs:__imp_CreateTimerQueueTimer
0x180019735  test    eax, eax
0x180019737  jnz     short loc_18001977C
0x180019739  call    cs:__imp_GetLastError
0x18001973f  mov     ebx, eax
0x180019741  test    eax, eax
0x180019743  jle     short loc_18001974A
0x180019745  movzx   ebx, ax
0x180019748  or      ebx, esi
0x18001974a  test    ebx, ebx
0x18001974c  jns     short loc_180019780
0x18001974e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019755  cmp     rcx, r12
0x180019758  jz      loc_180019AAF
0x18001975e  test    [rcx+1Ch], r13b
0x180019762  jz      loc_180019AAF
0x180019768  mov     edx, 17h
0x18001976d  mov     r9d, ebx
0x180019770  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180019777  jmp     loc_180019675
0x18001977c  mov     [r14+8], rbx
0x180019780  lea     rdx, [rsp+10A8h+var_1068]; int *
0x180019785  mov     [rdi+762h], r13b
0x18001978c  call    ?MigrateSettingsNeeded@TetheringService@@AEAAJPEAH@Z; TetheringService::MigrateSettingsNeeded(int *)
0x180019791  mov     ebx, eax
0x180019793  test    eax, eax
0x180019795  jns     short loc_1800197BB
0x180019797  mov     rcx, cs:WPP_GLOBAL_Control
0x18001979e  cmp     rcx, r12
0x1800197a1  jz      loc_180019AAF
0x1800197a7  test    [rcx+1Ch], r13b
0x1800197ab  jz      loc_180019AAF
0x1800197b1  mov     edx, 19h
0x1800197b6  mov     r9d, eax
0x1800197b9  jmp     short loc_180019770
0x1800197bb  cmp     [rsp+10A8h+var_1068], r15d
0x1800197c0  jz      loc_180019876
0x1800197c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197cd  cmp     rcx, r12
0x1800197d0  jz      short loc_1800197ED
0x1800197d2  test    byte ptr [rcx+1Ch], 8
0x1800197d6  jz      short loc_1800197ED
0x1800197d8  mov     rcx, [rcx+10h]
0x1800197dc  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800197e3  mov     edx, 187h
0x1800197e8  call    WPP_SF_
0x1800197ed  call    ?MigratePrivateConnectionInformation@TetheringService@@AEAAJXZ; TetheringService::MigratePrivateConnectionInformation(void)
0x1800197f2  mov     ebx, eax
0x1800197f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197fb  cmp     rcx, r12
0x1800197fe  jz      short loc_180019825
0x180019800  test    byte ptr [rcx+1Ch], 8
0x180019804  jz      short loc_180019825
0x180019806  mov     rcx, [rcx+10h]
0x18001980a  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180019811  mov     edx, 188h
0x180019816  mov     r9d, eax
0x180019819  call    WPP_SF_d
0x18001981e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019825  cmp     ebx, 80070002h
0x18001982b  jnz     short loc_18001984F
0x18001982d  cmp     rcx, r12
0x180019830  jz      short loc_180019876
0x180019832  test    byte ptr [rcx+1Ch], 4
0x180019836  jz      short loc_180019876
0x180019838  mov     rcx, [rcx+10h]
0x18001983c  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180019843  mov     edx, 1Ah
0x180019848  call    WPP_SF_
0x18001984d  jmp     short loc_180019876
0x18001984f  test    ebx, ebx
  ... truncated ...
```
