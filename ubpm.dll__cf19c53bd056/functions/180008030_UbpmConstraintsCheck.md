# UbpmConstraintsCheck

- ea: `0x180008030`
- end: `0x180008f22`
- name: `UbpmConstraintsCheck`
- size: `3826`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180006650`

## callees

- `0x180003890`
- `0x180008030`
- `0x18000a03c`
- `0x18000a198`
- `0x180013180`
- `0x18001e9f4`
- `0x18001f05c`
- `0x18001f520`
- `0x18001f870`
- `0x1800207e8`
- `0x180024df0`
- `0x1800291f0`
- `0x18002e764`
- `0x180032370`
- `0x180032dd8`
- `0x180034f3c`
- `0x180035f88`
- `0x180036378`
- `0x18003644c`
- `0x180036518`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800085bb`
- `ntdll!EtwEventWrite` at `0x1800085bb`
- `ntdll!EtwEventEnabled` at `0x18000858d`
- `ntdll!EtwEventEnabled` at `0x18000858d`
- `ntdll!RtlFindLeastSignificantBit` at `0x18000810d`
- `ntdll!RtlFindLeastSignificantBit` at `0x1800088da`
- `ntdll!RtlFindLeastSignificantBit` at `0x18000810d`
- `ntdll!RtlFindLeastSignificantBit` at `0x1800088da`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800082b4`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800086ab`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800082b4`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800086ab`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800082a0`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008698`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800082a0`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dd3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800083fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008ad7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800083fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008ad7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800083cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008a6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800083cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008a6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000840d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ae9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000840d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ae9`
- `RPCRT4!UuidEqual` at `0x1800084b3`
- `RPCRT4!UuidEqual` at `0x1800086fd`
- `RPCRT4!UuidEqual` at `0x1800084b3`
- `RPCRT4!UuidEqual` at `0x1800086fd`
- `RPCRT4!UuidIsNil` at `0x180008470`
- `RPCRT4!UuidIsNil` at `0x180008470`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008604`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008604`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180008363`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180008363`

## string_xrefs

- `0x1800085dd`: `NT TASK`
- `0x1800085cc`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall UbpmConstraintsCheck(UUID **a1, ULONGLONG a2, __int16 *a3, unsigned __int16 *a4, _BYTE *a5)
{
  UUID *v7; // rax
  const WCHAR *v8; // rdi
  __int64 v9; // rax
  unsigned __int16 v10; // r12
  unsigned __int16 v11; // bx
  unsigned __int16 v12; // dx
  __int64 v13; // r10
  unsigned int v14; // r9d
  unsigned __int16 v15; // r8
  UUID *v16; // rcx
  int v17; // eax
  int v18; // r14d
  PVOID *v19; // r10
  unsigned int v20; // ebx
  __int16 *v21; // r14
  UUID *v22; // rcx
  UUID *v24; // rdi
  _QWORD *v25; // rcx
  __int16 v26; // r8
  int v27; // edx
  char v28; // bl
  int v29; // ecx
  __int64 *v30; // r11
  int *v31; // rdx
  int v32; // r14d
  _DWORD *v33; // rcx
  __int64 v34; // rdx
  UUID *v35; // rcx
  __int64 v36; // r9
  unsigned __int64 v37; // rax
  UUID *v38; // r14
  UUID *v39; // rdx
  UUID *v40; // rcx
  _DWORD *v41; // rcx
  int v42; // eax
  __int64 *v43; // r8
  int *v44; // rcx
  void *v45; // rcx
  EventManager *v46; // rsi
  unsigned int v47; // eax
  EventManager *v48; // rcx
  char v49; // bl
  UUID *v50; // rcx
  void *v51; // rcx
  __int64 v52; // r9
  int v53; // edx
  char v54; // al
  unsigned __int16 LeastSignificantBit; // cx
  __int64 v56; // rdx
  int *v57; // rax
  struct _GUID *v58; // rcx
  UUID *v59; // rdx
  __int64 v60; // rax
  void *v61; // rcx
  __int64 *v62; // r10
  int *v63; // rax
  int v64; // r8d
  int v65; // r11d
  DWORD LastError; // eax
  char v67; // al
  char v68; // al
  LPDWORD lpcbData; // [rsp+28h] [rbp-59h]
  const struct _GUID *v70; // [rsp+30h] [rbp-51h]
  BYTE Data[4]; // [rsp+40h] [rbp-41h] BYREF
  DWORD Type; // [rsp+44h] [rbp-3Dh] BYREF
  int v73; // [rsp+48h] [rbp-39h] BYREF
  RPC_STATUS Status; // [rsp+4Ch] [rbp-35h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-29h] BYREF
  int v77; // [rsp+60h] [rbp-21h] BYREF
  __int16 *v78; // [rsp+68h] [rbp-19h]
  struct _GUID v79; // [rsp+70h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v80; // [rsp+80h] [rbp-1h] BYREF

  *a3 = 0;
  v79 = 0;
  Status = 0;
  *a5 = 0;
  v7 = *a1;
  v78 = a3;
  v80.Ptr = a2;
  v8 = *(const WCHAR **)(*(_QWORD *)v7[1].Data4 + 8LL);
  if ( v8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    if ( (unsigned int)v9 > 8 && CompareStringW(0x7Fu, 1u, v8, 7, L"NT TASK", 7) == 2 )
      v8 += 7;
  }
  v10 = 0;
  v11 = -1;
  v12 = 0;
  v13 = *(_QWORD *)(*a1)[1].Data4;
  v14 = *(_DWORD *)(v13 + 32);
  while ( v12 < v14 )
  {
    v15 = v12 + 1;
    if ( (UUID *)(*(_QWORD *)(v13 + 40) + 40LL * v12) == a1[1] )
    {
      v11 = v12;
      while ( v15 < v14 )
      {
        v16 = a1[8];
        if ( _bittest64((const __int64 *)&v16, v15) )
        {
          v10 = v15;
          goto LABEL_10;
        }
        ++v15;
      }
      break;
    }
    ++v12;
  }
LABEL_10:
  *a4 = v11;
  if ( RtlFindLeastSignificantBit((ULONGLONG)a1[8]) != v11 )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(*a1)[1].Data4 + 16LL) & 2) != 0
      && !(unsigned __int8)UbpmpRemoveQueuedSerialActions(a1[6], 0, 0, v11 + 1) )
    {
      v20 = 4320;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v62 = (__int64 *)a1[1];
        v63 = (int *)v62[4];
        if ( v63 )
          v64 = *v63;
        else
          LOBYTE(v64) = 0;
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
          *v62,
          v64);
      }
      return v20;
    }
    v18 = 1;
    goto LABEL_13;
  }
  v17 = *((_DWORD *)a1 + 14);
  if ( (v17 & 0x10000) == 0 )
  {
    v18 = 0;
LABEL_13:
    v19 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v43 = (__int64 *)a1[1];
  v44 = (int *)v43[4];
  if ( v44 && (*v44 & 1) == 0 )
  {
    v20 = 4320;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
        *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
        *v43,
        *v44);
    return v20;
  }
  if ( (v17 & 1) == 0 )
  {
    v20 = UbpmpSignalImmediateTrigger(a1, a5);
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
          *(_QWORD *)&a1[1]->Data1,
          v20);
      return v20;
    }
    goto LABEL_69;
  }
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( v44 )
      v65 = *v44;
    else
      LOBYTE(v65) = 0;
    WPP_SF_SSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
      *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
      *v43,
      v65);
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  v18 = 1;
LABEL_17:
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x10) != 0 )
  {
    WPP_SF_Sidd(
      (unsigned int)v19[2],
      18,
      (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
      *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
      (char)a1[8],
      v11,
      v18);
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v18 )
  {
    RtlAcquireSRWLockShared(&g_SystemSetup);
    v28 = unk_18004CA50;
    RtlReleaseSRWLockShared(&g_SystemSetup);
    if ( (v28 & 2) != 0
      || UbpmUtilsSearchMultiString(*(PCNZWCH *)(*(_QWORD *)(*a1)[1].Data4 + 8LL), g_OOBEExemptedTasks)
      || (RtlAcquireSRWLockShared(&g_SystemSetup),
          v49 = unk_18004CA50,
          RtlReleaseSRWLockShared(&g_SystemSetup),
          (v49 & 1) != 0)
      && !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 40LL) + 24LL) + 32LL) )
    {
      v19 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_19;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_SSLL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
        *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
        *(_QWORD *)&a1[1]->Data1,
        **(_DWORD **)&a1[1][2].Data1,
        *((_DWORD *)a1 + 14));
    UbpmpQueueActionInstance(2, a1);
    v20 = 0;
    *a5 = 1;
LABEL_69:
    ReportTaskEvent(v45, &TASK_INSTANCE_QUEUED, v8, a1[6]);
    return v20;
  }
LABEL_19:
  v20 = 0;
  if ( *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 48LL) )
  {
    v20 = UbpmMaintenanceConstraintsCheck(a1, a5);
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SSLL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
          *(_QWORD *)&a1[1]->Data1,
          **(_DWORD **)&a1[1][2].Data1,
          *((_DWORD *)a1 + 14));
      return v20;
    }
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v18 )
    goto LABEL_21;
  v29 = *((_DWORD *)a1 + 14);
  if ( (v29 & 0x80000) != 0 )
  {
    v30 = (__int64 *)a1[1];
    v57 = (int *)v30[4];
    if ( v57 )
    {
      v32 = *v57;
      if ( (*v57 & 0x140) == 0x100 )
      {
        v20 = 4320;
        if ( v19 == &WPP_GLOBAL_Control || (*((_BYTE *)v19 + 28) & 2) == 0 )
          return v20;
        v53 = 21;
        v52 = *(_QWORD *)(*a1)[1].Data4;
LABEL_102:
        WPP_SF_SSLL(
          (unsigned int)v19[2],
          v53,
          (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(v52 + 8),
          *v30,
          v32,
          v29);
        return v20;
      }
    }
  }
  v30 = (__int64 *)a1[1];
  v31 = (int *)v30[4];
  if ( v31 )
  {
    v32 = *v31;
    if ( ((*v31 & 0x40) != 0 || (v29 & 0x100000) != 0)
      && ((_DWORD)a1[7] & 0x80000) != 0
      && (*v31 & 0x40) != 0
      && (*v31 & 0x180) == 0x180
      && !LOBYTE((*a1)[19].Data1) )
    {
      v20 = 4320;
      if ( v19 == &WPP_GLOBAL_Control || (*((_BYTE *)v19 + 28) & 2) == 0 )
        return v20;
      v52 = *(_QWORD *)(*a1)[1].Data4;
      v53 = 22;
      goto LABEL_102;
    }
    if ( (*(_BYTE *)v31 & 2) != 0 )
    {
      if ( UbpmPowerSource() )
      {
        v20 = 4320;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_SSLd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            LastError,
            (unsigned int)a1[1],
            *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
            *(_QWORD *)&a1[1]->Data1,
            **(_DWORD **)&a1[1][2].Data1,
            LastError);
        }
        ReportTaskEvent(v51, &NO_START_ON_BATTERIES, v8);
        return v20;
      }
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v33 = *(_DWORD **)&a1[1][2].Data1;
  if ( v33 && (*v33 & 0x20400) != 0 )
  {
    if ( (unsigned __int8)IsWinStationQueryInformationWPresent() )
    {
      v34 = *((unsigned int *)a1 + 9);
      lpcbData = (LPDWORD)&v77;
      v73 = 0;
      v77 = 0;
      if ( !(unsigned __int8)WinStationQueryInformationW(0, v34, 39, &v73, 4) )
      {
        v20 = 4320;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v54 = GetLastError();
          WPP_SF_SSLdd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            *(_QWORD *)&a1[1][2].Data1,
            *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
            *(_QWORD *)&a1[1]->Data1,
            **(_DWORD **)&a1[1][2].Data1,
            *((_DWORD *)a1 + 9),
            v54);
        }
        return v20;
      }
      if ( (**(_DWORD **)&a1[1][2].Data1 & 0x400) != 0 )
      {
        hKey = 0;
        Type = 0;
        cbData = 4;
        *(_DWORD *)Data = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
        {
          if ( !RegQueryValueExW(hKey, L"EmulateRailSession", 0, &Type, Data, &cbData) && Type != 4 )
            *(_DWORD *)Data = 0;
          RegCloseKey(hKey);
        }
        if ( *(_DWORD *)Data || v73 == 5 )
        {
          v20 = 4320;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v67 = GetLastError();
            WPP_SF_SSLdd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              *(_QWORD *)&a1[1][2].Data1,
              *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
              *(_QWORD *)&a1[1]->Data1,
              **(_DWORD **)&a1[1][2].Data1,
              *((_DWORD *)a1 + 9),
              v67);
          }
          ReportTaskEvent(v61, &NO_START_ON_RAIL_SESSION, v8);
          return v20;
        }
      }
      if ( (**(_DWORD **)&a1[1][2].Data1 & 0x20000) != 0 )
      {
        hKey = 0;
        Type = 0;
        cbData = 4;
        *(_DWORD *)Data = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
        {
          if ( !RegQueryValueExW(hKey, L"EmulateWorkerSession", 0, &Type, Data, &cbData) && Type != 4 )
            *(_DWORD *)Data = 0;
          RegCloseKey(hKey);
        }
        if ( *(_DWORD *)Data || v73 == 8 )
        {
          v20 = 4320;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v68 = GetLastError();
            WPP_SF_SSLdd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              *(_QWORD *)&a1[1][2].Data1,
              *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
              *(_QWORD *)&a1[1]->Data1,
              **(_DWORD **)&a1[1][2].Data1,
              *((_DWORD *)a1 + 9),
              v68);
          }
          v46 = g_hTaskEventManager;
          if ( *(_QWORD *)g_hTaskEventManager )
          {
            if ( (unsigned __int8)EtwEventEnabled(*(_QWORD *)g_hTaskEventManager, NO_START_ON_WORKER_SESSION) )
            {
              CreateDataDescriptor(&v80, v8);
              v47 = EtwEventWrite(*(_QWORD *)v46, NO_START_ON_WORKER_SESSION, 1, &v80);
              if ( v47 )
                EventManager::LogIt(v48, L"EventWrite error", v47);
            }
          }
          return v20;
        }
      }
    }
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  v35 = *a1;
  v36 = *(_QWORD *)(*a1)[1].Data4;
  v37 = -*(_QWORD *)(v36 + 84);
  if ( !*(_QWORD *)(v36 + 84) )
    v37 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] - *(_QWORD *)(v36 + 92);
  if ( v37 && !*(_DWORD *)v80.Ptr )
  {
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 2) != 0 )
      WPP_SF_SSLL(
        (unsigned int)v19[2],
        27,
        (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
        *(_QWORD *)(v36 + 8),
        *(_QWORD *)&a1[1]->Data1,
        **(_DWORD **)&a1[1][2].Data1,
        *((_DWORD *)a1 + 14));
    v20 = 1222;
    ReportTaskEvent(v35, &JOB_NO_START_WO_NETWORK, v8, a1[6]);
    return v20;
  }
  if ( (*(_BYTE *)(v36 + 16) & 0x24) != 0 )
  {
LABEL_21:
    v21 = v78;
    if ( (*(_BYTE *)(*(_QWORD *)(*a1)[1].Data4 + 16LL) & 8) != 0 && !v10 )
    {
      *v78 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL));
    }
    (*a1)[17] = 0;
    v22 = *a1;
    if ( (*(_BYTE *)(*(_QWORD *)(*a1)[1].Data4 + 16LL) & 2) != 0 )
    {
      v24 = *(UUID **)&v22[14].Data1;
      while ( v24 != &(*a1)[14] )
      {
        v50 = v24;
        v24 = *(UUID **)&v24->Data1;
        if ( UuidEqual((UUID *)((char *)v50 + 52), a1[6], &Status) )
        {
          v20 = 4320;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_SSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
              *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
              *(_QWORD *)&a1[1]->Data1,
              *(_DWORD *)(*(_QWORD *)(*a1)[1].Data4 + 16LL));
          return v20;
        }
      }
      if ( v10 )
      {
        *v21 = v10 + 1;
        (*a1)[17] = *a1[6];
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v26 = *v21;
          v27 = 31;
          goto LABEL_175;
        }
      }
    }
    else if ( v10 )
    {
      v22[17] = *a1[6];
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        LOBYTE(v26) = v10;
        v27 = 32;
LABEL_175:
        WPP_SF_Sd(
          v25[2],
          v27,
          (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
          v26);
      }
    }
    return v20;
  }
  if ( UuidIsNil(v35 + 17, &Status) )
    goto LABEL_57;
  v58 = *a1;
  v59 = a1[6];
  v60 = *(_QWORD *)&(*a1)[17].Data1 - *(_QWORD *)&v59->Data1;
  if ( !v60 )
    v60 = *(_QWORD *)v58[17].Data4 - *(_QWORD *)v59->Data4;
  if ( !v60 )
  {
LABEL_57:
    v38 = *(UUID **)&(*a1)[14].Data1;
    while ( v38 != &(*a1)[14] )
    {
      v39 = a1[6];
      v40 = v38;
      v38 = *(UUID **)&v38->Data1;
      v40 = (UUID *)((char *)v40 + 52);
      v79 = *v40;
      if ( !UuidEqual(v40, v39, &Status) )
        goto LABEL_60;
    }
    goto LABEL_21;
  }
  v79 = v58[17];
LABEL_60:
  v20 = 4320;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
      *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
      *(_QWORD *)&a1[1]->Data1,
      *(_DWORD *)(*(_QWORD *)(*a1)[1].Data4 + 16LL));
  v41 = *(_DWORD **)(*a1)[1].Data4;
  v42 = v41[4];
  if ( (v42 & 8) != 0 )
  {
    LeastSignificantBit = RtlFindLeastSignificantBit((ULONGLONG)a1[8]);
    v56 = *(_QWORD *)(*a1)[1].Data4;
    if ( (unsigned int)LeastSignificantBit < *(_DWORD *)(v56 + 32)
      && (UUID *)(*(_QWORD *)(v56 + 40) + 40LL * LeastSignificantBit) == a1[1] )
    {
      UbpmpQueueActionInstance(0, a1);
      *a5 = 1;
      v20 = 0;
      EventManager::EvtReport(g_hTaskEventManager, &NEW_INSTANCE_QUEUED, v8, a1[6], &v79, lpcbData, v70);
    }
  }
  else if ( (v42 & 0x10) != 0 )
  {
    ReportTaskEvent(v41, &NEW_INSTANCE_IGNORED, v8, &v79);
  }
  return v20;
}

```

## disassembly

```asm
0x180008030  mov     [rsp-8+arg_8], rbx
0x180008035  push    rbp
0x180008036  push    rsi
0x180008037  push    rdi
0x180008038  push    r12
0x18000803a  push    r13
0x18000803c  push    r14
0x18000803e  push    r15
0x180008040  lea     rbp, [rsp-1Fh]
0x180008045  sub     rsp, 0A0h
0x18000804c  mov     rax, cs:__security_cookie
0x180008053  xor     rax, rsp
0x180008056  mov     [rbp+4Fh+var_40], rax
0x18000805a  mov     r13, [rbp+4Fh+arg_20]
0x18000805e  xor     eax, eax
0x180008060  mov     [r8], ax
0x180008064  xorps   xmm0, xmm0
0x180008067  movups  xmmword ptr [rbp+4Fh+var_60.Data1], xmm0
0x18000806b  mov     [rbp+4Fh+Status], 0
0x180008072  mov     rsi, rcx
0x180008075  mov     [r13+0], al
0x180008079  mov     r14, r9
0x18000807c  mov     rax, [rcx]
0x18000807f  mov     [rbp+4Fh+var_68], r8
0x180008083  mov     [rbp+4Fh+var_50.Ptr], rdx
0x180008087  mov     rcx, [rax+18h]
0x18000808b  mov     rdi, [rcx+8]
0x18000808f  test    rdi, rdi
0x180008092  jz      short loc_1800080B3
0x180008094  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000809b  nop     dword ptr [rax+rax+00h]
0x1800080a0  inc     rax
0x1800080a3  cmp     word ptr [rdi+rax*2], 0
0x1800080a8  jnz     short loc_1800080A0
0x1800080aa  cmp     eax, 8
0x1800080ad  ja      loc_1800085DD
0x1800080b3  mov     rax, [rsi]
0x1800080b6  xor     r12d, r12d
0x1800080b9  mov     ebx, 0FFFFh
0x1800080be  xor     edx, edx
0x1800080c0  mov     r10, [rax+18h]
0x1800080c4  mov     r9d, [r10+20h]
0x1800080c8  movzx   eax, dx
0x1800080cb  cmp     eax, r9d
0x1800080ce  jnb     short loc_180008101
0x1800080d0  movzx   eax, dx
0x1800080d3  lea     r8d, [rdx+1]
0x1800080d7  lea     rcx, [rax+rax*4]
0x1800080db  mov     rax, [r10+28h]
0x1800080df  lea     rcx, [rax+rcx*8]
0x1800080e3  cmp     rcx, [rsi+8]
0x1800080e7  jnz     loc_180008AF1
0x1800080ed  mov     rcx, [rsi+40h]
0x1800080f1  movzx   ebx, dx
0x1800080f4  movzx   eax, r8w
0x1800080f8  cmp     eax, r9d
0x1800080fb  jb      loc_180008AFA
0x180008101  mov     [r14], bx
0x180008105  mov     rcx, [rsi+40h]; Value
0x180008109  movzx   r15d, bx
0x18000810d  call    cs:__imp_RtlFindLeastSignificantBit
0x180008113  movsx   ecx, al
0x180008116  lea     rdx, WPP_GLOBAL_Control
0x18000811d  cmp     ecx, r15d
0x180008120  jnz     loc_180008B12
0x180008126  mov     eax, [rsi+38h]
0x180008129  bt      eax, 10h
0x18000812d  jb      loc_180008511
0x180008133  xor     r14d, r14d
0x180008136  mov     r10, cs:WPP_GLOBAL_Control
0x18000813d  jmp     short loc_18000815C
0x18000813f  mov     r10, cs:WPP_GLOBAL_Control
0x180008146  cmp     r10, rdx
0x180008149  jz      short loc_180008156
0x18000814b  test    byte ptr [r10+1Ch], 4
0x180008150  jnz     loc_180008BBF
0x180008156  mov     r14d, 1
0x18000815c  cmp     r10, rdx
0x18000815f  jnz     loc_18000824F
0x180008165  test    r14d, r14d
0x180008168  jz      loc_180008299
0x18000816e  mov     rax, [rsi]
0x180008171  xor     r15d, r15d
0x180008174  mov     ebx, r15d
0x180008177  mov     rcx, [rax+18h]
0x18000817b  cmp     [rcx+30h], rbx
0x18000817f  jnz     loc_180008842
0x180008185  test    r14d, r14d
0x180008188  jz      loc_1800082CF
0x18000818e  mov     rax, [rsi]
0x180008191  mov     r14, [rbp+4Fh+var_68]
0x180008195  mov     rcx, [rax+18h]
0x180008199  test    byte ptr [rcx+10h], 8
0x18000819d  jnz     loc_18000861C
0x1800081a3  lea     r15, WPP_GLOBAL_Control
0x1800081aa  mov     rax, [rsi]
0x1800081ad  xorps   xmm0, xmm0
0x1800081b0  movups  xmmword ptr [rax+110h], xmm0
0x1800081b7  mov     rcx, [rsi]
0x1800081ba  mov     rax, [rcx+18h]
0x1800081be  test    byte ptr [rax+10h], 2
0x1800081c2  jnz     short loc_1800081F7
0x1800081c4  test    r12w, r12w
0x1800081c8  jnz     loc_180008ECC
0x1800081ce  mov     eax, ebx
0x1800081d0  mov     rcx, [rbp+4Fh+var_40]
0x1800081d4  xor     rcx, rsp; StackCookie
0x1800081d7  call    __security_check_cookie
0x1800081dc  mov     rbx, [rsp+0D0h+arg_8]
0x1800081e4  add     rsp, 0A0h
0x1800081eb  pop     r15
0x1800081ed  pop     r14
0x1800081ef  pop     r13
0x1800081f1  pop     r12
0x1800081f3  pop     rdi
0x1800081f4  pop     rsi
0x1800081f5  pop     rbp
0x1800081f6  retn
0x1800081f7  mov     rdi, [rcx+0E0h]
0x1800081fe  mov     rax, [rsi]
0x180008201  add     rax, 0E0h
0x180008207  cmp     rdi, rax
0x18000820a  jnz     loc_1800086EB
0x180008210  test    r12w, r12w
0x180008214  jz      short loc_1800081CE
0x180008216  inc     r12w
0x18000821a  mov     [r14], r12w
0x18000821e  mov     rax, [rsi+30h]
0x180008222  mov     rcx, [rsi]
0x180008225  movups  xmm0, xmmword ptr [rax]
0x180008228  movups  xmmword ptr [rcx+110h], xmm0
0x18000822f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008236  cmp     rcx, r15
0x180008239  jz      short loc_1800081CE
0x18000823b  test    byte ptr [rcx+1Ch], 4
0x18000823f  jz      short loc_1800081CE
0x180008241  movzx   r8d, word ptr [r14]
0x180008245  mov     edx, 1Fh
0x18000824a  jmp     loc_180008EFD
0x18000824f  test    byte ptr [r10+1Ch], 10h
0x180008254  jz      loc_180008165
0x18000825a  mov     rax, [rsi]
0x18000825d  lea     r8, WPP_029c709143543b8b7778781675a35e95_Traceguids
0x180008264  mov     rcx, [r10+10h]
0x180008268  mov     edx, 12h
0x18000826d  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x180008272  mov     dword ptr [rsp+0D0h+lpcbData], r15d
0x180008277  mov     r9, [rax+18h]
0x18000827b  mov     rax, [rsi+40h]
0x18000827f  mov     [rsp+0D0h+phkResult], rax
0x180008284  mov     r9, [r9+8]
0x180008288  call    WPP_SF_Sidd
0x18000828d  mov     r10, cs:WPP_GLOBAL_Control
0x180008294  jmp     loc_180008165
0x180008299  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x1800082a0  call    cs:__imp_RtlAcquireSRWLockShared
0x1800082a6  movzx   ebx, word ptr cs:unk_18004CA50
0x1800082ad  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x1800082b4  call    cs:__imp_RtlReleaseSRWLockShared
0x1800082ba  test    bl, 2
0x1800082bd  jz      loc_180008672
0x1800082c3  mov     r10, cs:WPP_GLOBAL_Control
0x1800082ca  jmp     loc_18000816E
0x1800082cf  mov     ecx, [rsi+38h]
0x1800082d2  mov     r8d, ecx
0x1800082d5  and     r8d, 80000h
0x1800082dc  jnz     loc_180008949
0x1800082e2  mov     r11, [rsi+8]
0x1800082e6  mov     rdx, [r11+20h]
0x1800082ea  test    rdx, rdx
0x1800082ed  jz      short loc_180008311
0x1800082ef  mov     r14d, [rdx]
0x1800082f2  mov     eax, r14d
0x1800082f5  and     eax, 40h
0x1800082f8  jnz     loc_1800087BB
0x1800082fe  bt      ecx, 14h
0x180008302  jb      loc_1800087BB
0x180008308  test    byte ptr [rdx], 2
0x18000830b  jnz     loc_1800087A2
0x180008311  mov     rax, [rsi+8]
0x180008315  mov     rcx, [rax+20h]
0x180008319  test    rcx, rcx
0x18000831c  jz      loc_18000842E
0x180008322  test    dword ptr [rcx], 20400h
0x180008328  jz      loc_18000842E
0x18000832e  call    IsWinStationQueryInformationWPresent
0x180008333  test    al, al
0x180008335  jz      loc_180008427
0x18000833b  mov     edx, [rsi+24h]
0x18000833e  lea     rax, [rbp+4Fh+var_70]
0x180008342  mov     [rsp+0D0h+lpcbData], rax
0x180008347  lea     r9, [rbp+4Fh+var_88]
0x18000834b  mov     r8d, 27h ; '''
0x180008351  mov     dword ptr [rsp+0D0h+phkResult], 4
0x180008359  xor     ecx, ecx
0x18000835b  mov     [rbp+4Fh+var_88], r15d
0x18000835f  mov     [rbp+4Fh+var_70], r15d
0x180008363  call    cs:__imp_WinStationQueryInformationW
0x180008369  test    al, al
0x18000836b  jz      loc_180008863
0x180008371  mov     rax, [rsi+8]
0x180008375  mov     rcx, [rax+20h]
0x180008379  test    dword ptr [rcx], 400h
0x18000837f  jnz     loc_180008A3C
0x180008385  mov     rax, [rsi+8]
0x180008389  mov     r8, [rax+20h]
0x18000838d  test    dword ptr [r8], 20000h
0x180008394  jz      loc_180008427
0x18000839a  lea     rax, [rbp+4Fh+hKey]
0x18000839e  mov     [rbp+4Fh+hKey], r15
0x1800083a2  mov     r9d, 20019h; samDesired
0x1800083a8  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800083ad  xor     r8d, r8d; ulOptions
0x1800083b0  mov     [rbp+4Fh+Type], r15d
0x1800083b4  lea     rdx, SubKey; "System\\CurrentControlSet\\Control"
0x1800083bb  mov     [rbp+4Fh+cbData], 4
0x1800083c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800083c9  mov     dword ptr [rbp+4Fh+Data], r15d
0x1800083cd  call    cs:__imp_RegOpenKeyExW
0x1800083d3  test    eax, eax
0x1800083d5  jnz     short loc_180008413
0x1800083d7  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800083db  lea     rax, [rbp+4Fh+cbData]
0x1800083df  mov     [rsp+0D0h+lpcbData], rax; void *
0x1800083e4  lea     r9, [rbp+4Fh+Type]; lpType
0x1800083e8  lea     rax, [rbp+4Fh+Data]
0x1800083ec  xor     r8d, r8d; lpReserved
0x1800083ef  lea     rdx, aEmulateworkers; "EmulateWorkerSession"
0x1800083f6  mov     [rsp+0D0h+phkResult], rax; lpData
0x1800083fb  call    cs:__imp_RegQueryValueExW
0x180008401  test    eax, eax
0x180008403  jz      loc_180008DB6
0x180008409  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000840d  call    cs:__imp_RegCloseKey
0x180008413  cmp     dword ptr [rbp+4Fh+Data], r15d
0x180008417  jnz     loc_180008557
0x18000841d  cmp     [rbp+4Fh+var_88], 8
0x180008421  jz      loc_180008557
0x180008427  mov     r10, cs:WPP_GLOBAL_Control
0x18000842e  mov     rcx, [rsi]
0x180008431  xorps   xmm0, xmm0
0x180008434  movq    rax, xmm0
0x180008439  mov     r9, [rcx+18h]
0x18000843d  sub     rax, [r9+54h]
0x180008441  jnz     short loc_180008451
0x180008443  psrldq  xmm0, 8
0x180008448  movq    rax, xmm0
0x18000844d  sub     rax, [r9+5Ch]
0x180008451  test    rax, rax
0x180008454  jnz     loc_180008E20
0x18000845a  test    byte ptr [r9+10h], 24h
0x18000845f  jnz     loc_18000818E
0x180008465  add     rcx, 110h; Uuid
0x18000846c  lea     rdx, [rbp+4Fh+Status]; Status
0x180008470  call    cs:__imp_UuidIsNil
0x180008476  test    eax, eax
0x180008478  jz      loc_1800089A1
0x18000847e  mov     rax, [rsi]
0x180008481  mov     r14, [rax+0E0h]
0x180008488  mov     rax, [rsi]
0x18000848b  add     rax, 0E0h
0x180008491  cmp     r14, rax
0x180008494  jz      loc_18000818E
0x18000849a  mov     rdx, [rsi+30h]; Uuid2
0x18000849e  lea     r8, [rbp+4Fh+Status]; Status
0x1800084a2  mov     rcx, r14
0x1800084a5  mov     r14, [r14]
0x1800084a8  add     rcx, 34h ; '4'; Uuid1
0x1800084ac  movups  xmm0, xmmword ptr [rcx]
0x1800084af  movups  xmmword ptr [rbp+4Fh+var_60.Data1], xmm0
0x1800084b3  call    cs:__imp_UuidEqual
0x1800084b9  test    eax, eax
0x1800084bb  jnz     short loc_180008488
0x1800084bd  mov     ebx, 10E0h
0x1800084c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084c9  lea     rdx, WPP_GLOBAL_Control
0x1800084d0  cmp     rcx, rdx
0x1800084d3  jz      short loc_1800084DF
0x1800084d5  test    byte ptr [rcx+1Ch], 2
0x1800084d9  jnz     loc_180008E93
0x1800084df  mov     rax, [rsi]
0x1800084e2  mov     rcx, [rax+18h]; void *
0x1800084e6  mov     eax, [rcx+10h]
0x1800084e9  test    al, 8
0x1800084eb  jnz     loc_1800088D6
0x1800084f1  test    al, 10h
0x1800084f3  jz      loc_1800081CE
0x1800084f9  lea     r9, [rbp+4Fh+var_60]; struct _GUID *
0x1800084fd  mov     r8, rdi; unsigned __int16 *
0x180008500  lea     rdx, NEW_INSTANCE_IGNORED; struct _EVENT_DESCRIPTOR *
0x180008507  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000850c  jmp     loc_1800081CE
0x180008511  mov     r8, [rsi+8]
0x180008515  mov     rcx, [r8+20h]
0x180008519  test    rcx, rcx
0x18000851c  jnz     loc_180008763
0x180008522  test    al, 1
0x180008524  jnz     loc_18000813F
0x18000852a  mov     rdx, r13
0x18000852d  mov     rcx, rsi
  ... truncated ...
```
