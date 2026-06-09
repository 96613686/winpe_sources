# s_UbpmRpcTaskHostReportTaskStatus

- ea: `0x18000c650`
- end: `0x18000d1ee`
- name: `s_UbpmRpcTaskHostReportTaskStatus`
- size: `2974`
- prototype: `__int64 __fastcall(unsigned int *, __int64, UUID *, int, void *, int)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callees

- `0x180004240`
- `0x1800046c0`
- `0x180004a30`
- `0x180004c6c`
- `0x180005ed0`
- `0x180007460`
- `0x180007480`
- `0x180009750`
- `0x18000ad3c`
- `0x18000ada4`
- `0x18000ae00`
- `0x18000ae40`
- `0x18000c650`
- `0x18000d200`
- `0x18000d578`
- `0x18001e9f4`
- `0x18001eb04`
- `0x18001f600`
- `0x180020144`
- `0x180030cec`
- `0x1800354e0`
- `0x18003ca54`
- `0x18003ccdc`
- `0x18003ce20`
- `0x18003ce90`
- `0x18003cf14`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000c91f`
- `ntdll!RtlFreeHeap` at `0x18000c940`
- `ntdll!RtlFreeHeap` at `0x18000c961`
- `ntdll!RtlFreeHeap` at `0x18000c97f`
- `ntdll!RtlFreeHeap` at `0x18000c99d`
- `ntdll!RtlFreeHeap` at `0x18000c9b5`
- `ntdll!RtlFreeHeap` at `0x18000cb8d`
- `ntdll!RtlFreeHeap` at `0x18000cd0e`
- `ntdll!RtlFreeHeap` at `0x18000cd2c`
- `ntdll!RtlFreeHeap` at `0x18000cd44`
- `ntdll!RtlFreeHeap` at `0x18000c91f`
- `ntdll!RtlFreeHeap` at `0x18000c940`
- `ntdll!RtlFreeHeap` at `0x18000c961`
- `ntdll!RtlFreeHeap` at `0x18000c97f`
- `ntdll!RtlFreeHeap` at `0x18000c99d`
- `ntdll!RtlFreeHeap` at `0x18000c9b5`
- `ntdll!RtlFreeHeap` at `0x18000cb8d`
- `ntdll!RtlFreeHeap` at `0x18000cd0e`
- `ntdll!RtlFreeHeap` at `0x18000cd2c`
- `ntdll!RtlFreeHeap` at `0x18000cd44`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000c715`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000cfe8`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000d03b`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000c715`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000cfe8`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000d03b`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000c6ee`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000c6ee`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c720`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c736`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000cb00`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ce78`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c720`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c736`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000cb00`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ce78`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c9c6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c9d6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cb49`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cc98`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cea9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d000`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d010`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d0e2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d0f0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c9c6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c9d6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cb49`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cc98`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cea9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d000`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d010`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d0e2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d0f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ca12`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ca4b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cae1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cb5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ca12`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ca4b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cae1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cb5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c726`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c73c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c726`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c73c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce7e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ca27`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ca5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000caf6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000cb70`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ca27`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ca5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000caf6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000cb70`
- `RPCRT4!UuidEqual` at `0x18000c796`
- `RPCRT4!UuidEqual` at `0x18000c796`

## string_xrefs

- `0x18000ce08`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18000ce5d`: `ReportTaskEvent(0x%x) --> ret=%d`

## pseudocode

```c
__int64 __fastcall s_UbpmRpcTaskHostReportTaskStatus(unsigned int *a1, __int64 a2, UUID *a3, int a4, void *a5, int a6)
{
  char *v9; // rdi
  unsigned int *i; // rax
  unsigned int *v12; // r13
  __int64 v13; // r8
  int v14; // ebx
  int v15; // r9d
  unsigned __int16 v16; // r15
  unsigned __int16 *v17; // rdx
  unsigned __int16 *v18; // r9
  __int64 v19; // r8
  __int64 v20; // r11
  __int64 v21; // rcx
  __int64 v22; // r10
  unsigned __int16 *v23; // rcx
  unsigned __int16 *v24; // rcx
  unsigned __int16 *v25; // rdx
  unsigned __int16 *v26; // rcx
  __int16 v27; // ax
  __int16 v28; // ax
  unsigned int *v29; // rdx
  __int64 v30; // rax
  unsigned int **v31; // rcx
  void *v32; // r8
  void *v33; // r8
  void *v34; // r8
  void *v35; // r8
  void *v36; // r8
  DWORD v37; // ebx
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  DWORD v41; // ebx
  unsigned int v42; // esi
  PVOID v43; // r15
  int v44; // r13d
  DWORD v45; // ebx
  signed __int64 v46; // r13
  DWORD v47; // ebx
  char *v49; // rcx
  char *v50; // rax
  char **v51; // rdx
  void *v52; // r8
  void *v53; // r8
  int v54; // eax
  __int64 v55; // r8
  bool v56; // cc
  const unsigned __int16 *v57; // r9
  int v58; // eax
  __int64 v59; // r8
  __int64 v60; // rcx
  unsigned int v61; // eax
  __int64 v62; // r8
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r8
  void *v66; // [rsp+28h] [rbp-D8h]
  const struct _GUID *pSid; // [rsp+30h] [rbp-D0h]
  void *v68; // [rsp+38h] [rbp-C8h]
  const struct _GUID *v69; // [rsp+40h] [rbp-C0h]
  size_t Size; // [rsp+48h] [rbp-B8h]
  int v71; // [rsp+80h] [rbp-80h]
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v73; // [rsp+90h] [rbp-70h]
  RPC_STATUS v74; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int *v75; // [rsp+98h] [rbp-68h]
  PVOID v76; // [rsp+A0h] [rbp-60h]
  unsigned int *v77; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID v78; // [rsp+B0h] [rbp-50h] BYREF
  UUID Uuid2; // [rsp+C0h] [rbp-40h] BYREF
  __int128 TlsValue; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v81; // [rsp+E0h] [rbp-20h]
  __int128 v82; // [rsp+F0h] [rbp-10h]
  __int128 v83; // [rsp+100h] [rbp+0h]
  __int128 v84; // [rsp+110h] [rbp+10h]
  __int128 v85; // [rsp+120h] [rbp+20h]
  __int128 v86; // [rsp+130h] [rbp+30h]
  __int128 v87; // [rsp+140h] [rbp+40h]
  __int64 v88; // [rsp+150h] [rbp+50h]
  unsigned __int16 v89[256]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v90[256]; // [rsp+360h] [rbp+260h] BYREF

  v77 = a1;
  v76 = 0;
  v9 = 0;
  memset_0(v89, 0, sizeof(v89));
  memset_0(v90, 0, sizeof(v90));
  P = 0;
  v74 = 0;
  Uuid2 = 0;
  v78 = 0;
  if ( a4 != 1 || !a2 )
    return 87;
  RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
  if ( *a1 != 1665679957 )
  {
    RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
    return 5;
  }
  if ( (a1[26] & 4) != 0 )
  {
    RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
    v42 = 1067;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, a1[8], 1067);
    return v42;
  }
  RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
  RtlAcquireSRWLockExclusive(a1 + 20);
  a1[22] = GetCurrentThreadId();
  RtlAcquireSRWLockExclusive(a1 + 16);
  a1[18] = GetCurrentThreadId();
  v73 = a1[8];
  for ( i = (unsigned int *)*((_QWORD *)a1 + 25); ; i = *(unsigned int **)i )
  {
    v75 = i;
    if ( i == a1 + 50 )
    {
      a1[18] = 0;
      RtlReleaseSRWLockExclusive(a1 + 16);
      a1[22] = 0;
      RtlReleaseSRWLockExclusive(a1 + 20);
      v42 = 87;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_qddi(*((_QWORD *)WPP_GLOBAL_Control + 2), v63, v64, a1, a1[8], *((unsigned __int16 *)a1 + 98), a2);
      v43 = P;
      goto LABEL_57;
    }
    v12 = i - 4;
    if ( i[10] == a6 )
    {
      if ( *((_QWORD *)v12 + 12) )
        break;
    }
LABEL_122:
    ;
  }
  if ( !UuidEqual((UUID *)v12 + 2, a3, &v74) )
  {
    i = v75;
    goto LABEL_122;
  }
  if ( (v12[26] & 1) != 0 )
  {
    a1[18] = 0;
    RtlReleaseSRWLockExclusive(a1 + 16);
    a1[22] = 0;
    RtlReleaseSRWLockExclusive(a1 + 20);
    v42 = 4320;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qqidd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v65, a1, v12, a2, a1[8], *((unsigned __int16 *)a1 + 98));
    return v42;
  }
  v14 = 0;
  v71 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v69 = (const struct _GUID *)*((_QWORD *)v12 + 16);
    LODWORD(v68) = *((unsigned __int16 *)a1 + 98);
    WPP_SF_qqiddi(*((_QWORD *)WPP_GLOBAL_Control + 2), *((unsigned __int16 *)a1 + 98), v13, a1, v12, a2, a1[8]);
  }
  Uuid2 = *(UUID *)(v12 + 15);
  *((_BYTE *)v12 + 104) |= 1u;
  v15 = v12[31];
  v78 = *(struct _GUID *)(v12 + 27);
  v16 = *((_WORD *)v12 + 53);
  if ( v16 )
  {
    LODWORD(Size) = v12[37];
    UbpmRunNextSerializedAction(
      (int)&Uuid2,
      v16,
      (int)&v78,
      v15,
      *((_QWORD *)v12 + 16),
      a1[48],
      *((PSID *)a1 + 23),
      *((_QWORD *)v12 + 17),
      v12[36],
      Size,
      *((void **)v12 + 19),
      *((_BYTE *)v12 + 160),
      *((unsigned __int16 ***)v12 + 21),
      v12[44],
      *((_BYTE *)v12 + 180),
      *((unsigned __int16 ***)v12 + 23));
  }
  v17 = (unsigned __int16 *)*((_QWORD *)v12 + 10);
  v18 = v89;
  v19 = 2147483646;
  v20 = 256;
  v21 = 2147483646;
  v22 = 256;
  do
  {
    if ( !v21 )
      break;
    if ( !*v17 )
      break;
    *v18++ = *v17++;
    --v21;
    --v22;
  }
  while ( v22 );
  v23 = v18 - 1;
  if ( v22 )
    v23 = v18;
  *v23 = 0;
  v24 = (unsigned __int16 *)*((_QWORD *)v12 + 11);
  if ( v24 )
  {
    v25 = v90;
    do
    {
      if ( !v19 )
        break;
      if ( !*v24 )
        break;
      *v25++ = *v24++;
      --v19;
      --v20;
    }
    while ( v20 );
    v26 = v25 - 1;
    if ( v20 )
      v26 = v25;
    *v26 = 0;
  }
  if ( v16 <= 1u )
  {
    LODWORD(v60) = (_DWORD)::pSid;
    if ( *((_QWORD *)a1 + 23) )
      v60 = *((_QWORD *)a1 + 23);
    UbpmUtilsGetAccountNamesFromSid(v60, 1, 0, 0, (__int64)&P);
  }
  v27 = *((_WORD *)a1 + 98);
  if ( !v27 || (v28 = v27 - 1, (*((_WORD *)a1 + 98) = v28) == 0) )
  {
    if ( *((unsigned int **)a1 + 27) == a1 + 54 )
      v14 = 1;
    v71 = v14;
  }
  if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v12 + 1, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
  {
    v29 = v75;
    v30 = *(_QWORD *)v75;
    if ( *(unsigned int **)(*(_QWORD *)v75 + 8LL) == v75 )
    {
      v31 = (unsigned int **)*((_QWORD *)v75 + 1);
      if ( *v31 == v75 )
      {
        *v31 = (unsigned int *)v30;
        *(_QWORD *)(v30 + 8) = v31;
        *((_QWORD *)v29 + 1) = v29;
        *(_QWORD *)v29 = v29;
        UbpmUtilsSystemPowerOff(*((HANDLE *)v12 + 24));
        v32 = (void *)*((_QWORD *)v12 + 21);
        if ( v32 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v32);
        v33 = (void *)*((_QWORD *)v12 + 23);
        if ( v33 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
        v34 = (void *)*((_QWORD *)v12 + 19);
        if ( v34 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v34);
        v35 = (void *)*((_QWORD *)v12 + 10);
        if ( v35 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v35);
        v36 = (void *)*((_QWORD *)v12 + 11);
        if ( v36 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v36);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
        v12 = 0;
        goto LABEL_45;
      }
    }
LABEL_92:
    __fastfail(3u);
  }
LABEL_45:
  a1[18] = 0;
  RtlReleaseSRWLockExclusive(a1 + 16);
  a1[22] = 0;
  RtlReleaseSRWLockExclusive(a1 + 20);
  v37 = UbpmpLockTrackerId;
  v88 = 0;
  TlsValue = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  if ( UbpmpLockTrackerId != -1 )
  {
    if ( TlsGetValue(UbpmpLockTrackerId) )
      __int2c();
    TlsSetValue(v37, &TlsValue);
  }
  v38 = UbpmpOpenTriggerConsumer(&Uuid2, 0);
  v41 = UbpmpLockTrackerId;
  v42 = v38;
  if ( UbpmpLockTrackerId != -1 )
  {
    if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
      __int2c();
    TlsSetValue(v41, 0);
  }
  v9 = (char *)v76;
  if ( v42 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qqdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, v40, a1, v12, a1[8], *((unsigned __int16 *)a1 + 98));
    v43 = P;
    v42 = 0;
    v44 = v71;
  }
  else
  {
    UbpmpExecutionTimeLimitCallback(v76, 0, 0);
    if ( (int)a5 < 0 )
    {
      ReportTaskEvent(g_hTaskEventManager, &ACTION_FAILURE, v89, &v78, v90, (unsigned int)a5, v73);
      v56 = v16 <= 1u;
      v43 = P;
      if ( v56 )
        ReportTaskEvent(g_hTaskEventManager, &JOB_FAILURE, v89, &v78, (const unsigned __int16 *)P, (unsigned int)a5);
      UbpmScheduleRestartOnFailure(v9, 0);
    }
    else
    {
      v54 = EventManager::EvtReport(g_hTaskEventManager, &ACTION_SUCCESS, v89, &v78, v90, (char)a5, v73, v68, v69);
      v55 = (unsigned __int16)v54;
      if ( v54 >= 0 )
        v55 = 0;
      TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", &ACTION_SUCCESS, v55);
      v56 = v16 <= 1u;
      v43 = P;
      if ( v56 )
      {
        v57 = L"(NONE)";
        if ( P )
          v57 = (const unsigned __int16 *)P;
        v58 = EventManager::EvtReport(g_hTaskEventManager, &JOB_SUCCESS, v89, v57, &v78, v66, pSid);
        v59 = (unsigned __int16)v58;
        if ( v58 >= 0 )
          v59 = 0;
        TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", &JOB_SUCCESS, v59);
      }
    }
    v44 = v71;
    RtlAcquireSRWLockExclusive(v9 + 208);
    *((_DWORD *)v9 + 54) = GetCurrentThreadId();
    UbpmpTriggerConsumerReportResult(v9, (unsigned int)a5, 0);
    *((_DWORD *)v9 + 54) = 0;
    RtlReleaseSRWLockExclusive(v9 + 208);
  }
  if ( v44 == 1 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)a1 + 12);
    v61 = UbpmUtilsSubmitThreadPoolWork((void (*)(void *, unsigned __int8, void *))UbpmpStopHostCallback, a1, 1, 0, 0);
    if ( v61 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v62, a1[8], a1, v61);
      UbpmpDecrementRefAndDelete(&v77, 1);
    }
  }
LABEL_57:
  if ( v9 )
  {
    v45 = UbpmpLockTrackerId;
    v88 = 0;
    TlsValue = 0;
    v81 = 0;
    v82 = 0;
    v83 = 0;
    v84 = 0;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    if ( UbpmpLockTrackerId != -1 )
    {
      if ( TlsGetValue(UbpmpLockTrackerId) )
        __int2c();
      TlsSetValue(v45, &TlsValue);
    }
    RtlAcquireSRWLockExclusive(v9 + 48);
    *((_DWORD *)v9 + 14) = GetCurrentThreadId();
    v46 = _InterlockedDecrement64((volatile signed __int64 *)v9 + 8);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_Siq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*((_QWORD *)v9 + 3) + 8LL),
        v46,
        (char)v9);
    if ( v46 || !(unsigned __int8)UbpmConsumerIsUnregistered(v9) )
    {
      *((_DWORD *)v9 + 14) = 0;
      RtlReleaseSRWLockExclusive(v9 + 48);
    }
    else
    {
      v9[104] = 1;
      *((_DWORD *)v9 + 14) = 0;
      RtlReleaseSRWLockExclusive(v9 + 48);
      UbpmpAcquireListLockExclusive();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          123,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(*((_QWORD *)v9 + 3) + 8LL),
          g_cTotalConsumers);
      v49 = (char *)*((_QWORD *)v9 + 1);
      v50 = v9 + 8;
      if ( v49 != v9 + 8 )
      {
        if ( *((char **)v49 + 1) != v50 )
          goto LABEL_92;
        v51 = (char **)*((_QWORD *)v9 + 2);
        if ( *v51 != v50 )
          goto LABEL_92;
        --g_cTotalConsumers;
        *v51 = v49;
        *((_QWORD *)v49 + 1) = v51;
        *((_QWORD *)v9 + 2) = v9 + 8;
        *(_QWORD *)v50 = v50;
      }
      UbpmpReleaseListLockExclusive();
      v52 = (void *)*((_QWORD *)v9 + 4);
      if ( v52 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v52);
      v53 = (void *)*((_QWORD *)v9 + 3);
      if ( v53 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v53);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    }
    v47 = UbpmpLockTrackerId;
    if ( UbpmpLockTrackerId != -1 )
    {
      if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
        __int2c();
      TlsSetValue(v47, 0);
    }
  }
  if ( v43 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v43);
  return v42;
}

```

## disassembly

```asm
0x18000c650  push    rbp
0x18000c652  push    rbx
0x18000c653  push    rsi
0x18000c654  push    rdi
0x18000c655  push    r12
0x18000c657  push    r14
0x18000c659  push    r15
0x18000c65b  lea     rbp, [rsp-470h]
0x18000c663  sub     rsp, 570h
0x18000c66a  mov     rax, cs:__security_cookie
0x18000c671  xor     rax, rsp
0x18000c674  mov     [rbp+4A0h+var_40], rax
0x18000c67b  mov     r15, r8
0x18000c67e  mov     [rbp+4A0h+var_4F8], rcx
0x18000c682  mov     r14, rdx
0x18000c685  mov     r12, rcx
0x18000c688  xor     esi, esi
0x18000c68a  lea     rcx, [rbp+4A0h+var_440]; void *
0x18000c68e  xor     edx, edx; Val
0x18000c690  mov     [rbp+4A0h+var_500], rsi
0x18000c694  mov     r8d, 200h; Size
0x18000c69a  mov     edi, esi
0x18000c69c  mov     ebx, r9d
0x18000c69f  call    memset_0
0x18000c6a4  xor     edx, edx; Val
0x18000c6a6  lea     rcx, [rbp+4A0h+var_240]; void *
0x18000c6ad  mov     r8d, 200h; Size
0x18000c6b3  call    memset_0
0x18000c6b8  mov     [rbp+4A0h+P], rsi
0x18000c6bc  xorps   xmm0, xmm0
0x18000c6bf  mov     dword ptr [rbp+4A0h+var_510+4], esi
0x18000c6c2  xorps   xmm1, xmm1
0x18000c6c5  movups  xmmword ptr [rbp+4A0h+Uuid2.Data1], xmm0
0x18000c6c9  movups  xmmword ptr [rbp+4A0h+var_4F0.Data1], xmm1
0x18000c6cd  cmp     ebx, 1
0x18000c6d0  jnz     loc_18000CFDE
0x18000c6d6  test    r14, r14
0x18000c6d9  jz      loc_18000CFDE
0x18000c6df  lea     rcx, g_TaskHostContextListLock
0x18000c6e6  mov     [rsp+5A0h+arg_8], r13
0x18000c6ee  call    cs:__imp_RtlAcquireSRWLockShared
0x18000c6f4  cmp     dword ptr [r12], 63484255h
0x18000c6fc  lea     rcx, g_TaskHostContextListLock
0x18000c703  jnz     loc_18000CFE8
0x18000c709  test    byte ptr [r12+68h], 4
0x18000c70f  jnz     loc_18000D03B
0x18000c715  call    cs:__imp_RtlReleaseSRWLockShared
0x18000c71b  lea     rcx, [r12+50h]
0x18000c720  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000c726  call    cs:__imp_GetCurrentThreadId
0x18000c72c  lea     rcx, [r12+40h]
0x18000c731  mov     [r12+58h], eax
0x18000c736  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000c73c  call    cs:__imp_GetCurrentThreadId
0x18000c742  mov     esi, [rbp+4A0h+arg_28]
0x18000c748  lea     rbx, [r12+0C8h]
0x18000c750  mov     [r12+48h], eax
0x18000c755  mov     eax, [r12+20h]
0x18000c75a  mov     dword ptr [rbp+4A0h+var_510], eax
0x18000c75d  mov     rax, [rbx]
0x18000c760  mov     [rbp+4A0h+var_508], rax
0x18000c764  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000c76b  cmp     rax, rbx
0x18000c76e  jz      loc_18000CFF8
0x18000c774  cmp     [rax+28h], esi
0x18000c777  lea     r13, [rax-10h]
0x18000c77b  jnz     loc_18000D08E
0x18000c781  cmp     [r13+60h], rdi
0x18000c785  jz      loc_18000D08E
0x18000c78b  lea     rcx, [r13+20h]; Uuid1
0x18000c78f  mov     rdx, r15; Uuid2
0x18000c792  lea     r8, [rbp+4A0h+var_510+4]; Status
0x18000c796  call    cs:__imp_UuidEqual
0x18000c79c  test    eax, eax
0x18000c79e  jz      loc_18000D08A
0x18000c7a4  test    byte ptr [r13+68h], 1
0x18000c7a9  jnz     loc_18000D0DA
0x18000c7af  mov     ebx, edi
0x18000c7b1  mov     [rbp+4A0h+var_520], ebx
0x18000c7b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7bb  lea     rax, WPP_GLOBAL_Control
0x18000c7c2  cmp     rcx, rax
0x18000c7c5  jnz     loc_18000CD4F
0x18000c7cb  movups  xmm0, xmmword ptr [r13+3Ch]
0x18000c7d0  movups  xmmword ptr [rbp+4A0h+Uuid2.Data1], xmm0
0x18000c7d4  or      byte ptr [r13+68h], 1
0x18000c7d9  movups  xmm0, xmmword ptr [r13+6Ch]
0x18000c7de  mov     r9d, [r13+7Ch]; int
0x18000c7e2  movups  xmmword ptr [rbp+4A0h+var_4F0.Data1], xmm0
0x18000c7e6  movzx   r15d, word ptr [r13+6Ah]
0x18000c7eb  test    r15w, r15w
0x18000c7ef  jnz     loc_18000CBD5
0x18000c7f5  mov     rdx, [r13+50h]
0x18000c7f9  lea     r9, [rbp+4A0h+var_440]
0x18000c7fd  mov     r8d, 7FFFFFFEh
0x18000c803  mov     r11d, 100h
0x18000c809  mov     ecx, r8d
0x18000c80c  mov     r10d, r11d
0x18000c80f  nop
0x18000c810  test    rcx, rcx
0x18000c813  jz      short loc_18000C832
0x18000c815  movzx   eax, word ptr [rdx]
0x18000c818  test    ax, ax
0x18000c81b  jz      short loc_18000C832
0x18000c81d  mov     [r9], ax
0x18000c821  add     rdx, 2
0x18000c825  add     r9, 2
0x18000c829  dec     rcx
0x18000c82c  sub     r10, 1
0x18000c830  jnz     short loc_18000C810
0x18000c832  test    r10, r10
0x18000c835  lea     rcx, [r9-2]
0x18000c839  cmovnz  rcx, r9
0x18000c83d  mov     [rcx], di
0x18000c840  mov     rcx, [r13+58h]
0x18000c844  test    rcx, rcx
0x18000c847  jz      short loc_18000C87F
0x18000c849  lea     rdx, [rbp+4A0h+var_240]
0x18000c850  test    r8, r8
0x18000c853  jz      short loc_18000C871
0x18000c855  movzx   eax, word ptr [rcx]
0x18000c858  test    ax, ax
0x18000c85b  jz      short loc_18000C871
0x18000c85d  mov     [rdx], ax
0x18000c860  add     rcx, 2
0x18000c864  add     rdx, 2
0x18000c868  dec     r8
0x18000c86b  sub     r11, 1
0x18000c86f  jnz     short loc_18000C850
0x18000c871  test    r11, r11
0x18000c874  lea     rcx, [rdx-2]
0x18000c878  cmovnz  rcx, rdx
0x18000c87c  mov     [rcx], di
0x18000c87f  mov     r14d, 1
0x18000c885  cmp     r15w, r14w
0x18000c889  jbe     loc_18000CEC1
0x18000c88f  movzx   eax, word ptr [r12+0C4h]
0x18000c898  test    ax, ax
0x18000c89b  jz      loc_18000CBBE
0x18000c8a1  dec     ax
0x18000c8a4  mov     [r12+0C4h], ax
0x18000c8ad  test    ax, ax
0x18000c8b0  jz      loc_18000CBBE
0x18000c8b6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c8bd  lock xadd [r13+8], rax
0x18000c8c3  cmp     rax, r14
0x18000c8c6  jnz     loc_18000C9BE
0x18000c8cc  mov     rdx, [rbp+4A0h+var_508]
0x18000c8d0  mov     rax, [rdx]
0x18000c8d3  cmp     [rax+8], rdx
0x18000c8d7  jnz     loc_18000CD96
0x18000c8dd  mov     rcx, [rdx+8]
0x18000c8e1  cmp     [rcx], rdx
0x18000c8e4  jnz     loc_18000CD96
0x18000c8ea  mov     [rcx], rax
0x18000c8ed  mov     [rax+8], rcx
0x18000c8f1  mov     [rdx+8], rdx
0x18000c8f5  mov     [rdx], rdx
0x18000c8f8  mov     rcx, [r13+0C0h]; hObject
0x18000c8ff  call    ?UbpmUtilsSystemPowerOff@@YAKPEAX@Z; UbpmUtilsSystemPowerOff(void *)
0x18000c904  mov     r8, [r13+0A8h]; P
0x18000c90b  test    r8, r8
0x18000c90e  jz      short loc_18000C925
0x18000c910  mov     rcx, gs:60h
0x18000c919  xor     edx, edx; Flags
0x18000c91b  mov     rcx, [rcx+30h]; HeapHandle
0x18000c91f  call    cs:__imp_RtlFreeHeap
0x18000c925  mov     r8, [r13+0B8h]; P
0x18000c92c  test    r8, r8
0x18000c92f  jz      short loc_18000C946
0x18000c931  mov     rcx, gs:60h
0x18000c93a  xor     edx, edx; Flags
0x18000c93c  mov     rcx, [rcx+30h]; HeapHandle
0x18000c940  call    cs:__imp_RtlFreeHeap
0x18000c946  mov     r8, [r13+98h]; P
0x18000c94d  test    r8, r8
0x18000c950  jz      short loc_18000C967
0x18000c952  mov     rcx, gs:60h
0x18000c95b  xor     edx, edx; Flags
0x18000c95d  mov     rcx, [rcx+30h]; HeapHandle
0x18000c961  call    cs:__imp_RtlFreeHeap
0x18000c967  mov     r8, [r13+50h]; P
0x18000c96b  test    r8, r8
0x18000c96e  jz      short loc_18000C985
0x18000c970  mov     rcx, gs:60h
0x18000c979  xor     edx, edx; Flags
0x18000c97b  mov     rcx, [rcx+30h]; HeapHandle
0x18000c97f  call    cs:__imp_RtlFreeHeap
0x18000c985  mov     r8, [r13+58h]; P
0x18000c989  test    r8, r8
0x18000c98c  jz      short loc_18000C9A3
0x18000c98e  mov     rcx, gs:60h
0x18000c997  xor     edx, edx; Flags
0x18000c999  mov     rcx, [rcx+30h]; HeapHandle
0x18000c99d  call    cs:__imp_RtlFreeHeap
0x18000c9a3  mov     rcx, gs:60h
0x18000c9ac  mov     r8, r13; P
0x18000c9af  xor     edx, edx; Flags
0x18000c9b1  mov     rcx, [rcx+30h]; HeapHandle
0x18000c9b5  call    cs:__imp_RtlFreeHeap
0x18000c9bb  mov     r13, rdi
0x18000c9be  lea     rcx, [r12+40h]
0x18000c9c3  mov     [rcx+8], edi
0x18000c9c6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000c9cc  lea     rcx, [r12+50h]
0x18000c9d1  mov     [r12+58h], edi
0x18000c9d6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000c9dc  mov     ebx, cs:UbpmpLockTrackerId
0x18000c9e2  xorps   xmm0, xmm0
0x18000c9e5  xor     eax, eax
0x18000c9e7  mov     [rbp+4A0h+var_450], rax
0x18000c9eb  movups  [rbp+4A0h+TlsValue], xmm0
0x18000c9ef  movups  [rbp+4A0h+var_4C0], xmm0
0x18000c9f3  movups  [rbp+4A0h+var_4B0], xmm0
0x18000c9f7  movups  [rbp+4A0h+var_4A0], xmm0
0x18000c9fb  movups  [rbp+4A0h+var_490], xmm0
0x18000c9ff  movups  [rbp+4A0h+var_480], xmm0
0x18000ca03  movups  [rbp+4A0h+var_470], xmm0
0x18000ca07  movups  [rbp+4A0h+var_460], xmm0
0x18000ca0b  cmp     ebx, 0FFFFFFFFh
0x18000ca0e  jz      short loc_18000CA2D
0x18000ca10  mov     ecx, ebx; dwTlsIndex
0x18000ca12  call    cs:__imp_TlsGetValue
0x18000ca18  test    rax, rax
0x18000ca1b  jnz     loc_18000D096
0x18000ca21  lea     rdx, [rbp+4A0h+TlsValue]; lpTlsValue
0x18000ca25  mov     ecx, ebx; dwTlsIndex
0x18000ca27  call    cs:__imp_TlsSetValue
0x18000ca2d  lea     r8, [rbp+4A0h+var_500]
0x18000ca31  xor     edx, edx; String2
0x18000ca33  lea     rcx, [rbp+4A0h+Uuid2]; Uuid2
0x18000ca37  call    UbpmpOpenTriggerConsumer
0x18000ca3c  mov     ebx, cs:UbpmpLockTrackerId
0x18000ca42  mov     esi, eax
0x18000ca44  cmp     ebx, 0FFFFFFFFh
0x18000ca47  jz      short loc_18000CA64
0x18000ca49  mov     ecx, ebx; dwTlsIndex
0x18000ca4b  call    cs:__imp_TlsGetValue
0x18000ca51  cmp     [rax], rdi
0x18000ca54  jnz     loc_18000D09D
0x18000ca5a  xor     edx, edx; lpTlsValue
0x18000ca5c  mov     ecx, ebx; dwTlsIndex
0x18000ca5e  call    cs:__imp_TlsSetValue
0x18000ca64  mov     rdi, [rbp+4A0h+var_500]
0x18000ca68  test    esi, esi
0x18000ca6a  jz      loc_18000CD9D
0x18000ca70  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca77  lea     rbx, WPP_GLOBAL_Control
0x18000ca7e  cmp     rcx, rbx
0x18000ca81  jnz     loc_18000D0A4
0x18000ca87  mov     r15, [rbp+4A0h+P]
0x18000ca8b  xor     esi, esi
0x18000ca8d  mov     r13d, [rbp+4A0h+var_520]
0x18000ca91  cmp     r13d, 1
0x18000ca95  jz      loc_18000CEF3
0x18000ca9b  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000caa2  test    rdi, rdi
0x18000caa5  jz      loc_18000CB76
0x18000caab  mov     ebx, cs:UbpmpLockTrackerId
0x18000cab1  xorps   xmm0, xmm0
0x18000cab4  xor     eax, eax
0x18000cab6  mov     [rbp+4A0h+var_450], rax
0x18000caba  movups  [rbp+4A0h+TlsValue], xmm0
0x18000cabe  movups  [rbp+4A0h+var_4C0], xmm0
0x18000cac2  movups  [rbp+4A0h+var_4B0], xmm0
0x18000cac6  movups  [rbp+4A0h+var_4A0], xmm0
0x18000caca  movups  [rbp+4A0h+var_490], xmm0
0x18000cace  movups  [rbp+4A0h+var_480], xmm0
0x18000cad2  movups  [rbp+4A0h+var_470], xmm0
0x18000cad6  movups  [rbp+4A0h+var_460], xmm0
0x18000cada  cmp     ebx, 0FFFFFFFFh
0x18000cadd  jz      short loc_18000CAFC
0x18000cadf  mov     ecx, ebx; dwTlsIndex
0x18000cae1  call    cs:__imp_TlsGetValue
0x18000cae7  test    rax, rax
0x18000caea  jnz     loc_18000D188
0x18000caf0  lea     rdx, [rbp+4A0h+TlsValue]; lpTlsValue
0x18000caf4  mov     ecx, ebx; dwTlsIndex
0x18000caf6  call    cs:__imp_TlsSetValue
0x18000cafc  lea     rcx, [rdi+30h]
0x18000cb00  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000cb06  call    cs:__imp_GetCurrentThreadId
0x18000cb0c  mov     [rdi+38h], eax
0x18000cb0f  lock xadd [rdi+40h], r13
0x18000cb15  dec     r13
0x18000cb18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb1f  lea     r14, WPP_GLOBAL_Control
0x18000cb26  cmp     rcx, r14
0x18000cb29  jz      short loc_18000CB35
0x18000cb2b  test    byte ptr [rcx+1Ch], 8
0x18000cb2f  jnz     loc_18000D18F
0x18000cb35  test    r13, r13
0x18000cb38  jz      loc_18000CC79
0x18000cb3e  lea     rcx, [rdi+30h]
0x18000cb42  mov     dword ptr [rdi+38h], 0
0x18000cb49  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000cb4f  mov     ebx, cs:UbpmpLockTrackerId
0x18000cb55  cmp     ebx, 0FFFFFFFFh
0x18000cb58  jz      short loc_18000CB76
0x18000cb5a  mov     ecx, ebx; dwTlsIndex
  ... truncated ...
```
