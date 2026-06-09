# UbpmInitializeMaintenance

- ea: `0x18002e220`
- end: `0x18002e75e`
- name: `UbpmInitializeMaintenance`
- size: `1342`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a0cc`

## callees

- `0x18000a6e0`
- `0x180016d80`
- `0x18001f16c`
- `0x180024600`
- `0x180027eb4`
- `0x1800284d0`
- `0x1800295cc`
- `0x18002978c`
- `0x18002a520`
- `0x18002b640`
- `0x18002e220`
- `0x18002f544`
- `0x180030e18`
- `0x180036604`
- `0x1800368b4`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002e338`
- `ntdll!RtlNtStatusToDosError` at `0x18002e338`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e2f8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e3c1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e64b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e2f8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e3c1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e64b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002e458`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002e458`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002e616`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002e616`
- `EventAggregation!EACreateAggregateEvent` at `0x18002e57a`
- `EventAggregation!EACreateAggregateEvent` at `0x18002e5d5`
- `EventAggregation!EACreateAggregateEvent` at `0x18002e57a`
- `EventAggregation!EACreateAggregateEvent` at `0x18002e5d5`
- `UMPDC!SleepstudyHelperCreateLibrary` at `0x18002e32e`
- `UMPDC!SleepstudyHelperCreateLibrary` at `0x18002e32e`
- `TimeBrokerClient!TbCreateCEvent` at `0x18002e519`
- `TimeBrokerClient!TbCreateCEvent` at `0x18002e519`

## pseudocode

```c
__int64 UbpmInitializeMaintenance()
{
  NTSTATUS v0; // esi
  int v1; // r14d
  unsigned int MaintenanceSettings; // ebx
  int v3; // edi
  __int64 v4; // rcx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  NTSTATUS v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-CCh] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME v17; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v18[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME v19; // [rsp+80h] [rbp-80h] BYREF
  __m256i v20; // [rsp+90h] [rbp-70h]
  __int128 v21; // [rsp+B0h] [rbp-50h]
  __int128 v22; // [rsp+C0h] [rbp-40h]
  __int128 v23; // [rsp+D0h] [rbp-30h]
  __int128 v24; // [rsp+E0h] [rbp-20h]
  __int128 v25; // [rsp+F0h] [rbp-10h]
  __int128 v26; // [rsp+100h] [rbp+0h]
  __int128 v27; // [rsp+110h] [rbp+10h]
  __int128 v28; // [rsp+120h] [rbp+20h]
  __int128 v29; // [rsp+130h] [rbp+30h]
  __int128 v30; // [rsp+140h] [rbp+40h]
  __int128 v31; // [rsp+150h] [rbp+50h]
  __int128 v32; // [rsp+160h] [rbp+60h]
  __int64 v33; // [rsp+170h] [rbp+70h]
  __int128 v34; // [rsp+180h] [rbp+80h] BYREF
  __int128 v35; // [rsp+190h] [rbp+90h]
  __int128 v36; // [rsp+1A0h] [rbp+A0h]
  __int64 v37; // [rsp+1B0h] [rbp+B0h]
  SYSTEMTIME Time; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1D0h] [rbp+D0h] BYREF
  __m256i v40; // [rsp+1E0h] [rbp+E0h]
  __int128 v41; // [rsp+200h] [rbp+100h]
  __int128 v42; // [rsp+210h] [rbp+110h]
  __int128 v43; // [rsp+220h] [rbp+120h]
  __int128 v44; // [rsp+230h] [rbp+130h]
  _OWORD v45[8]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v46; // [rsp+2C0h] [rbp+1C0h]
  char v47[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  SYSTEMTIME *p_Time; // [rsp+2F0h] [rbp+1F0h]
  __int64 v49; // [rsp+2F8h] [rbp+1F8h]
  unsigned int *v50; // [rsp+300h] [rbp+200h]
  __int64 v51; // [rsp+308h] [rbp+208h]
  int *v52; // [rsp+310h] [rbp+210h]
  __int64 v53; // [rsp+318h] [rbp+218h]
  NTSTATUS *v54; // [rsp+320h] [rbp+220h]
  __int64 v55; // [rsp+328h] [rbp+228h]

  memset_0(&SystemTime, 0, 0xF8u);
  v16 = 0;
  *(_QWORD *)&Time.wYear = 0;
  v14 = 0;
  memset(v18, 0, 28);
  v37 = 0;
  v0 = 0;
  v1 = 0;
  v17 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  UbpmpInitializeMaintenanceParameters(&v17);
  MaintenanceSettings = UbpmpReadMaintenanceSettings(
                          (struct _UBPM_MAINTENANCE_PARAMETERS *)&v17,
                          (const unsigned __int16 **)&Time);
  if ( MaintenanceSettings )
  {
    v3 = 10;
    goto LABEL_29;
  }
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenancePilotLock);
  byte_18004CB32 = BYTE8(v18[1]);
  dword_18004CF00 = 0;
  RtlReleaseSRWLockExclusive(&g_MaintenancePilotLock);
  MaintenanceSettings = UbpmMaintenanceInitializeTaskTriggers();
  if ( MaintenanceSettings )
  {
    v3 = 20;
    goto LABEL_29;
  }
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenanceLaunchLock);
  UbpmpRegisterPdcClient();
  v0 = SleepstudyHelperCreateLibrary(1936944500, &v16);
  RtlNtStatusToDosError(v0);
  if ( v0 == -1073741637 )
  {
    v1 = 10;
  }
  else if ( v0 >= 0 )
  {
    qword_18004CB48 = v16;
    v16 = 0;
  }
  else
  {
    v1 = 20;
    if ( (unsigned int)dword_18004C0F0 > 2 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL) )
    {
      v15 = 20;
      v13 = v0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v5,
        (unsigned int)byte_180043DCD,
        v6,
        v7,
        (__int64)&v13,
        (__int64)&v15);
    }
  }
  dword_18004CEE8 = 0;
  RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
  if ( g_CrmRegistrationHandle )
  {
    MaintenanceSettings = UbpmpInitializeCrmMaintenanceLevels();
    if ( MaintenanceSettings )
    {
      v3 = 30;
      goto LABEL_29;
    }
  }
  else
  {
    MaintenanceSettings = UbpmpInitializeLegacyMaintenanceLevels();
    if ( MaintenanceSettings )
    {
      v3 = 40;
      goto LABEL_29;
    }
  }
  memset_0(&SystemTime, 0, 0xF8u);
  *(_DWORD *)&SystemTime.wYear = 2;
  DWORD2(v43) = 0;
  StringCbCopyW((unsigned __int16 *)v45 + 2, 0x80u, L"TsMaintPeriodRetrigger");
  *(__int64 *)((char *)&v40.m256i_i64[1] + 4) = 60;
  v40.m256i_i32[2] = 120;
  v3 = 60;
  GetSystemTime((LPSYSTEMTIME)&SystemTime.wHour);
  v19 = SystemTime;
  v33 = v46;
  v20 = v40;
  v22 = v42;
  v21 = v41;
  v24 = v44;
  v23 = v43;
  v26 = v45[1];
  v25 = v45[0];
  v28 = v45[3];
  v27 = v45[2];
  v30 = v45[5];
  v29 = v45[4];
  v32 = v45[7];
  v31 = v45[6];
  MaintenanceSettings = TbCreateCEvent(&v19, &qword_18004CB20);
  if ( MaintenanceSettings )
  {
    v3 = 50;
  }
  else
  {
    v37 = 0;
    v34 = (unsigned __int64)qword_18004CB20;
    *((_QWORD *)&v36 + 1) = 0;
    *(_QWORD *)&v36 = &UbpmpMaintenanceTelemetryCallback;
    v35 = 0;
    MaintenanceSettings = EACreateAggregateEvent(&v34, &qword_18004CB18);
    if ( !MaintenanceSettings )
    {
      v37 = 0;
      v34 = (unsigned __int64)qword_18004CB20;
      *((_QWORD *)&v36 + 1) = 0;
      *(_QWORD *)&v36 = &UbpmpMaintenanceEvalAllTriggersCallback;
      v35 = 0;
      MaintenanceSettings = EACreateAggregateEvent(&v34, &qword_18004CB28);
      if ( MaintenanceSettings )
      {
        v3 = 70;
      }
      else
      {
        if ( !UbpmpMaintenanceStateReported(&v14) && v14 - 2 <= 2 )
        {
          Time = 0;
          GetLocalTime(&Time);
          UbpmpReportMaintenanceState(&Time, 0);
        }
        UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenancePilotLock);
        byte_18004CB30 = 1;
        dword_18004CF00 = 0;
        RtlReleaseSRWLockExclusive(&g_MaintenancePilotLock);
        if ( (unsigned int)dword_18004C0F0 > 4 && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL) )
        {
          v13 = v1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v9,
            (unsigned int)&word_180043D96,
            v10,
            v11,
            (__int64)&v13);
        }
        v3 = 0;
        MaintenanceSettings = 0;
      }
    }
  }
LABEL_29:
  if ( (unsigned int)dword_18004C0F0 > 4 )
  {
    v54 = &v13;
    v52 = &v15;
    v50 = &v14;
    *(_DWORD *)&Time.wYear = MaintenanceSettings;
    p_Time = &Time;
    v55 = 4;
    v53 = 4;
    v51 = 4;
    v49 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18004C0F0, byte_18004418B, 0, 0, 6, v47, __PAIR64__(v3, v1), v0);
  }
  return MaintenanceSettings;
}

```

## disassembly

```asm
0x18002e220  push    rbp
0x18002e222  push    rbx
0x18002e223  push    rsi
0x18002e224  push    rdi
0x18002e225  push    r14
0x18002e227  push    r15
0x18002e229  lea     rbp, [rsp-248h]
0x18002e231  sub     rsp, 348h
0x18002e238  mov     rax, cs:__security_cookie
0x18002e23f  xor     rax, rsp
0x18002e242  mov     [rbp+270h+var_40], rax
0x18002e249  xor     edx, edx; Val
0x18002e24b  lea     rcx, [rbp+270h+SystemTime]; void *
0x18002e252  mov     r8d, 0F8h; Size
0x18002e258  call    memset_0
0x18002e25d  xor     r15d, r15d
0x18002e260  lea     rcx, [rsp+370h+var_328]; struct _SYSTEMTIME *
0x18002e265  xorps   xmm0, xmm0
0x18002e268  mov     [rsp+370h+var_330], r15
0x18002e26d  xorps   xmm1, xmm1
0x18002e270  mov     qword ptr [rbp+270h+Time.wYear], r15
0x18002e277  xor     eax, eax
0x18002e279  mov     dword ptr [rsp+370h+var_340+4], r15d
0x18002e27e  movups  [rsp+370h+var_318], xmm0
0x18002e283  mov     [rbp+270h+var_1C0], rax
0x18002e28a  mov     esi, r15d
0x18002e28d  movups  [rsp+370h+var_318+0Ch], xmm0
0x18002e292  mov     r14d, r15d
0x18002e295  movups  xmmword ptr [rsp+370h+var_328.wYear], xmm0
0x18002e29a  movups  [rbp+270h+var_1F0], xmm1
0x18002e2a1  movups  [rbp+270h+var_1E0], xmm1
0x18002e2a8  movups  [rbp+270h+var_1D0], xmm1
0x18002e2af  call    ?UbpmpInitializeMaintenanceParameters@@YAXPEAU_UBPM_MAINTENANCE_PARAMETERS@@@Z; UbpmpInitializeMaintenanceParameters(_UBPM_MAINTENANCE_PARAMETERS *)
0x18002e2b4  lea     rdx, [rbp+270h+Time]; unsigned __int16 **
0x18002e2bb  lea     rcx, [rsp+370h+var_328]; struct _UBPM_MAINTENANCE_PARAMETERS *
0x18002e2c0  call    ?UbpmpReadMaintenanceSettings@@YAKPEAU_UBPM_MAINTENANCE_PARAMETERS@@PEAPEBG@Z; UbpmpReadMaintenanceSettings(_UBPM_MAINTENANCE_PARAMETERS *,ushort const * *)
0x18002e2c5  mov     ebx, eax
0x18002e2c7  test    eax, eax
0x18002e2c9  jz      short loc_18002E2D4
0x18002e2cb  lea     edi, [r15+0Ah]
0x18002e2cf  jmp     loc_18002E690
0x18002e2d4  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x18002e2db  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002e2e0  mov     al, [rsp+370h+var_300]
0x18002e2e4  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_MaintenancePilotLock
0x18002e2eb  mov     cs:byte_18004CB32, al
0x18002e2f1  mov     cs:dword_18004CF00, r15d
0x18002e2f8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002e2fe  call    UbpmMaintenanceInitializeTaskTriggers
0x18002e303  mov     ebx, eax
0x18002e305  test    eax, eax
0x18002e307  jz      short loc_18002E313
0x18002e309  mov     edi, 14h
0x18002e30e  jmp     loc_18002E690
0x18002e313  lea     rcx, g_MaintenanceLaunchLock; struct _UBPM_SRWLOCK *
0x18002e31a  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002e31f  call    ?UbpmpRegisterPdcClient@@YAXXZ; UbpmpRegisterPdcClient(void)
0x18002e324  lea     rdx, [rsp+370h+var_330]
0x18002e329  mov     ecx, 73736D74h
0x18002e32e  call    cs:__imp_SleepstudyHelperCreateLibrary
0x18002e334  mov     ecx, eax; Status
0x18002e336  mov     esi, eax
0x18002e338  call    cs:__imp_RtlNtStatusToDosError
0x18002e33e  cmp     esi, 0C00000BBh
0x18002e344  jnz     short loc_18002E34E
0x18002e346  mov     r14d, 0Ah
0x18002e34c  jmp     short loc_18002E3B3
0x18002e34e  test    esi, esi
0x18002e350  jns     short loc_18002E3A2
0x18002e352  mov     eax, cs:dword_18004C0F0
0x18002e358  mov     edi, 14h
0x18002e35d  mov     r14d, edi
0x18002e360  cmp     eax, 2
0x18002e363  jbe     short loc_18002E3B3
0x18002e365  mov     rdx, 200000000000h
0x18002e36f  call    _tlgKeywordOn
0x18002e374  test    al, al
0x18002e376  jz      short loc_18002E3B3
0x18002e378  lea     rax, [rsp+370h+var_338]
0x18002e37d  mov     [rsp+370h+var_338], edi
0x18002e381  mov     [rsp+370h+var_348], rax
0x18002e386  lea     rdx, byte_180043DCD
0x18002e38d  lea     rax, [rsp+370h+var_340]
0x18002e392  mov     dword ptr [rsp+370h+var_340], esi
0x18002e396  mov     [rsp+370h+var_350], rax
0x18002e39b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002e3a0  jmp     short loc_18002E3B3
0x18002e3a2  mov     rax, [rsp+370h+var_330]
0x18002e3a7  mov     cs:qword_18004CB48, rax
0x18002e3ae  mov     [rsp+370h+var_330], r15
0x18002e3b3  lea     rcx, g_MaintenanceLaunchLock
0x18002e3ba  mov     cs:dword_18004CEE8, r15d
0x18002e3c1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002e3c7  cmp     cs:g_CrmRegistrationHandle, r15
0x18002e3ce  jz      short loc_18002E3E5
0x18002e3d0  call    ?UbpmpInitializeCrmMaintenanceLevels@@YAKXZ; UbpmpInitializeCrmMaintenanceLevels(void)
0x18002e3d5  mov     ebx, eax
0x18002e3d7  test    eax, eax
0x18002e3d9  jz      short loc_18002E3FA
0x18002e3db  mov     edi, 1Eh
0x18002e3e0  jmp     loc_18002E690
0x18002e3e5  call    ?UbpmpInitializeLegacyMaintenanceLevels@@YAKXZ; UbpmpInitializeLegacyMaintenanceLevels(void)
0x18002e3ea  mov     ebx, eax
0x18002e3ec  test    eax, eax
0x18002e3ee  jz      short loc_18002E3FA
0x18002e3f0  mov     edi, 28h ; '('
0x18002e3f5  jmp     loc_18002E690
0x18002e3fa  xor     edx, edx; Val
0x18002e3fc  lea     rcx, [rbp+270h+SystemTime]; void *
0x18002e403  mov     r8d, 0F8h; Size
0x18002e409  call    memset_0
0x18002e40e  lea     r8, aTsmaintperiodr; "TsMaintPeriodRetrigger"
0x18002e415  mov     dword ptr [rbp+270h+SystemTime.wYear], 2
0x18002e41f  mov     edx, 80h; unsigned __int64
0x18002e424  mov     [rbp+270h+var_148], r15d
0x18002e42b  lea     rcx, [rbp+270h+var_12C]; unsigned __int16 *
0x18002e432  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e437  lea     rcx, [rbp+270h+SystemTime.wHour]; lpSystemTime
0x18002e43e  mov     qword ptr [rbp+270h+var_184], 3Ch ; '<'
0x18002e449  mov     [rbp+270h+var_188], 78h ; 'x'
0x18002e453  mov     edi, 3Ch ; '<'
0x18002e458  call    cs:__imp_GetSystemTime
0x18002e45e  movaps  xmm0, xmmword ptr [rbp+270h+SystemTime.wYear]
0x18002e465  lea     rdx, qword_18004CB20
0x18002e46c  movaps  xmm1, xmmword ptr [rbp+0E0h]
0x18002e473  lea     rcx, [rbp+270h+var_2F0]
0x18002e477  mov     rax, [rbp+270h+var_B0]
0x18002e47e  movups  [rbp+270h+var_2F0], xmm0
0x18002e482  mov     [rbp+270h+var_200], rax
0x18002e486  movaps  xmm0, [rbp+270h+var_184+4]
0x18002e48d  movups  [rbp+270h+var_2D0], xmm0
0x18002e491  movaps  xmm0, [rbp+270h+var_160]
0x18002e498  movups  [rbp+270h+var_2E0], xmm1
0x18002e49c  movaps  xmm1, [rbp+270h+var_170]
0x18002e4a3  movups  [rbp+270h+var_2B0], xmm0
0x18002e4a7  movaps  xmm0, [rbp+270h+var_140]
0x18002e4ae  movups  [rbp+270h+var_2C0], xmm1
0x18002e4b2  movaps  xmm1, xmmword ptr [rbp+120h]
0x18002e4b9  movups  [rbp+270h+var_290], xmm0
0x18002e4bd  movaps  xmm0, [rbp+270h+var_120]
0x18002e4c4  movups  [rbp+270h+var_2A0], xmm1
0x18002e4c8  movaps  xmm1, xmmword ptr [rbp+140h]
0x18002e4cf  movups  [rbp+270h+var_270], xmm0
0x18002e4d3  movaps  xmm0, [rbp+270h+var_100]
0x18002e4da  movups  [rbp+270h+var_280], xmm1
0x18002e4de  movaps  xmm1, [rbp+270h+var_110]
0x18002e4e5  movups  [rbp+270h+var_250], xmm0
0x18002e4e9  movaps  xmm0, [rbp+270h+var_E0]
0x18002e4f0  movups  [rbp+270h+var_260], xmm1
0x18002e4f4  movaps  xmm1, [rbp+270h+var_F0]
0x18002e4fb  movups  [rbp+270h+var_230], xmm0
0x18002e4ff  movaps  xmm0, [rbp+270h+var_C0]
0x18002e506  movups  [rbp+270h+var_240], xmm1
0x18002e50a  movaps  xmm1, [rbp+270h+var_D0]
0x18002e511  movups  [rbp+270h+var_210], xmm0
0x18002e515  movups  [rbp+270h+var_220], xmm1
0x18002e519  call    cs:__imp_TbCreateCEvent
0x18002e51f  mov     ebx, eax
0x18002e521  test    eax, eax
0x18002e523  jz      short loc_18002E52F
0x18002e525  mov     edi, 32h ; '2'
0x18002e52a  jmp     loc_18002E690
0x18002e52f  xor     eax, eax
0x18002e531  lea     rdx, qword_18004CB18
0x18002e538  xorps   xmm0, xmm0
0x18002e53b  mov     [rbp+270h+var_1C0], rax
0x18002e542  mov     rax, cs:qword_18004CB20
0x18002e549  lea     rcx, [rbp+270h+var_1F0]
0x18002e550  movups  [rbp+270h+var_1F0], xmm0
0x18002e557  mov     qword ptr [rbp+270h+var_1F0], rax
0x18002e55e  lea     rax, ?UbpmpMaintenanceTelemetryCallback@@YAXPEAXU_CBROKERED_EVENT_ID@@00K@Z; UbpmpMaintenanceTelemetryCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)
0x18002e565  movups  [rbp+270h+var_1D0], xmm0
0x18002e56c  mov     qword ptr [rbp+270h+var_1D0], rax
0x18002e573  movups  [rbp+270h+var_1E0], xmm0
0x18002e57a  call    cs:__imp_EACreateAggregateEvent
0x18002e580  mov     ebx, eax
0x18002e582  test    eax, eax
0x18002e584  jnz     loc_18002E690
0x18002e58a  xor     eax, eax
0x18002e58c  lea     rdx, qword_18004CB28
0x18002e593  xorps   xmm0, xmm0
0x18002e596  mov     [rbp+270h+var_1C0], rax
0x18002e59d  mov     rax, cs:qword_18004CB20
0x18002e5a4  lea     rcx, [rbp+270h+var_1F0]
0x18002e5ab  movups  [rbp+270h+var_1F0], xmm0
0x18002e5b2  mov     qword ptr [rbp+270h+var_1F0], rax
0x18002e5b9  lea     rax, ?UbpmpMaintenanceEvalAllTriggersCallback@@YAXPEAXU_CBROKERED_EVENT_ID@@00K@Z; UbpmpMaintenanceEvalAllTriggersCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)
0x18002e5c0  movups  [rbp+270h+var_1D0], xmm0
0x18002e5c7  mov     qword ptr [rbp+270h+var_1D0], rax
0x18002e5ce  movups  [rbp+270h+var_1E0], xmm0
0x18002e5d5  call    cs:__imp_EACreateAggregateEvent
0x18002e5db  mov     ebx, eax
0x18002e5dd  test    eax, eax
0x18002e5df  jz      short loc_18002E5EB
0x18002e5e1  mov     edi, 46h ; 'F'
0x18002e5e6  jmp     loc_18002E690
0x18002e5eb  lea     rcx, [rsp+370h+var_340+4]; unsigned int *
0x18002e5f0  call    ?UbpmpMaintenanceStateReported@@YAKPEAK@Z; UbpmpMaintenanceStateReported(ulong *)
0x18002e5f5  test    eax, eax
0x18002e5f7  jnz     short loc_18002E62A
0x18002e5f9  mov     eax, dword ptr [rsp+370h+var_340+4]
0x18002e5fd  add     eax, 0FFFFFFFEh
0x18002e600  cmp     eax, 2
0x18002e603  ja      short loc_18002E62A
0x18002e605  xorps   xmm0, xmm0
0x18002e608  lea     rcx, [rbp+270h+Time]; lpSystemTime
0x18002e60f  movups  xmmword ptr [rbp+270h+Time.wYear], xmm0
0x18002e616  call    cs:__imp_GetLocalTime
0x18002e61c  xor     edx, edx; unsigned int
0x18002e61e  lea     rcx, [rbp+270h+Time]; lpTime
0x18002e625  call    ?UbpmpReportMaintenanceState@@YAXPEAU_SYSTEMTIME@@K@Z; UbpmpReportMaintenanceState(_SYSTEMTIME *,ulong)
0x18002e62a  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x18002e631  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002e636  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_MaintenancePilotLock
0x18002e63d  mov     cs:byte_18004CB30, 1
0x18002e644  mov     cs:dword_18004CF00, r15d
0x18002e64b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002e651  mov     eax, cs:dword_18004C0F0
0x18002e657  cmp     eax, 4
0x18002e65a  jbe     short loc_18002E68A
0x18002e65c  mov     rdx, 400000000000h
0x18002e666  call    _tlgKeywordOn
0x18002e66b  test    al, al
0x18002e66d  jz      short loc_18002E68A
0x18002e66f  lea     rax, [rsp+370h+var_340]
0x18002e674  mov     dword ptr [rsp+370h+var_340], r14d
0x18002e679  lea     rdx, word_180043D96
0x18002e680  mov     [rsp+370h+var_350], rax
0x18002e685  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002e68a  mov     edi, r15d
0x18002e68d  mov     ebx, r15d
0x18002e690  mov     eax, cs:dword_18004C0F0
0x18002e696  cmp     eax, 4
0x18002e699  jbe     loc_18002E73D
0x18002e69f  lea     rax, [rsp+370h+var_340]
0x18002e6a4  mov     dword ptr [rsp+370h+var_340], r14d
0x18002e6a9  mov     [rbp+270h+var_50], rax
0x18002e6b0  lea     rdx, byte_18004418B
0x18002e6b7  lea     rax, [rsp+370h+var_338]
0x18002e6bc  mov     [rsp+370h+var_338], esi
0x18002e6c0  mov     [rbp+270h+var_60], rax
0x18002e6c7  lea     rcx, dword_18004C0F0
0x18002e6ce  lea     rax, [rsp+370h+var_340+4]
0x18002e6d3  mov     dword ptr [rsp+370h+var_340+4], edi
0x18002e6d7  mov     [rbp+270h+var_70], rax
0x18002e6de  xor     r9d, r9d
0x18002e6e1  lea     rax, [rbp+270h+Time]
0x18002e6e8  mov     dword ptr [rbp+270h+Time.wYear], ebx
0x18002e6ee  mov     [rbp+270h+var_80], rax
0x18002e6f5  xor     r8d, r8d
0x18002e6f8  lea     rax, [rbp+270h+var_A0]
0x18002e6ff  mov     [rbp+270h+var_48], 4
0x18002e70a  mov     [rsp+370h+var_348], rax
0x18002e70f  mov     dword ptr [rsp+370h+var_350], 6
0x18002e717  mov     [rbp+270h+var_58], 4
0x18002e722  mov     [rbp+270h+var_68], 4
0x18002e72d  mov     [rbp+270h+var_78], 4
0x18002e738  call    _tlgWriteTransfer_EventWriteTransfer
0x18002e73d  mov     eax, ebx
0x18002e73f  mov     rcx, [rbp+270h+var_40]
0x18002e746  xor     rcx, rsp; StackCookie
0x18002e749  call    __security_check_cookie
0x18002e74e  add     rsp, 348h
0x18002e755  pop     r15
0x18002e757  pop     r14
0x18002e759  pop     rdi
0x18002e75a  pop     rsi
0x18002e75b  pop     rbx
0x18002e75c  pop     rbp
0x18002e75d  retn
```
