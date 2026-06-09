# UbpmpLaunchOneTask(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_ACTION_PARAMS *,ulong,void *,void * *,void *,_GUID *,ulong,unsigned __int64,ulong,unsigned __int64,uchar,ushort const * *,ulong,uchar *,ulong,void *,uchar,ushort const * *,uchar *)

- ea: `0x180006650`
- end: `0x18000745a`
- name: `?UbpmpLaunchOneTask@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAU_UBPM_ACTION_PARAMS@@KPEAXPEAPEAX3PEAU_GUID@@K_KK6EPEAPEBGKPEAEK3E78@Z`
- size: `3594`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, struct _UBPM_CONSTRAINT_PRECHECK_INFO *, struct _UBPM_ACTION_PARAMS *, unsigned int, PSID pSid, void **, void *, struct _GUID *, unsigned int, unsigned __int64, unsigned int, unsigned __int64, unsigned __int8, const unsigned __int16 **, unsigned int, unsigned __int8 *, unsigned int, void *, unsigned __int8, const unsigned __int16 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180019fb0`
- `0x18001a8a8`
- `0x18001acb0`

## callees

- `0x180004240`
- `0x1800046c0`
- `0x180004e10`
- `0x180004f40`
- `0x1800051b0`
- `0x180005ed0`
- `0x180006650`
- `0x180007460`
- `0x180007990`
- `0x180008030`
- `0x180019d90`
- `0x18001e9f4`
- `0x18001eb04`
- `0x18001f560`
- `0x18001f600`
- `0x18001f764`
- `0x180021060`
- `0x180023e04`
- `0x180023f68`
- `0x1800255e0`
- `0x18002c188`
- `0x18002ea04`
- `0x180032dd8`
- `0x180036028`
- `0x18003d7de`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800066d0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800066d0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006ee2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006ee2`
- `ntdll!RtlFreeHeap` at `0x18000690f`
- `ntdll!RtlFreeHeap` at `0x180006c4a`
- `ntdll!RtlFreeHeap` at `0x180006d32`
- `ntdll!RtlFreeHeap` at `0x180006d50`
- `ntdll!RtlFreeHeap` at `0x180006d6d`
- `ntdll!RtlFreeHeap` at `0x18000690f`
- `ntdll!RtlFreeHeap` at `0x180006c4a`
- `ntdll!RtlFreeHeap` at `0x180006d32`
- `ntdll!RtlFreeHeap` at `0x180006d50`
- `ntdll!RtlFreeHeap` at `0x180006d6d`
- `ntdll!RtlAllocateHeap` at `0x18000673b`
- `ntdll!RtlAllocateHeap` at `0x18000673b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180006c85`
- `ntdll!RtlReleaseSRWLockShared` at `0x180006c85`
- `ntdll!RtlAcquireSRWLockShared` at `0x180006c66`
- `ntdll!RtlAcquireSRWLockShared` at `0x180006c66`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006795`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006795`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180006d14`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180006d14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000679b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000679b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ef0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800072f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800072f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800068d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800068d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007363`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007363`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006b57`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006b57`
- `RPCRT4!UuidEqual` at `0x180006f9c`
- `RPCRT4!UuidEqual` at `0x180006f9c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180006ebc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180006ebc`

## string_xrefs

- `0x180006e95`: `NT TASK`
- `0x180006c27`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x180006cd5`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x180006e25`: `ReportTaskEvent(0x%x) --> ret=%d`

## pseudocode

```c
__int64 __fastcall UbpmpLaunchOneTask(
        struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1,
        struct _UBPM_CONSTRAINT_PRECHECK_INFO *a2,
        struct _UBPM_ACTION_PARAMS *a3,
        unsigned int a4,
        PSID pSid,
        void **a6,
        void *a7,
        struct _GUID *a8,
        unsigned int a9,
        unsigned __int64 a10,
        unsigned int a11,
        unsigned __int64 a12,
        unsigned __int8 a13,
        const unsigned __int16 **a14,
        unsigned int a15,
        unsigned __int8 *a16,
        unsigned int a17,
        void *a18,
        unsigned __int8 a19,
        const unsigned __int16 **a20,
        unsigned __int8 *a21)
{
  PSID v23; // rbx
  DWORD LengthSid; // r14d
  __int64 v25; // rax
  __int64 v26; // r13
  const WCHAR *v27; // rdi
  __int64 v28; // rax
  char *Heap; // rax
  char *v30; // rsi
  unsigned __int8 *v31; // r12
  __int64 v32; // r8
  void *v33; // r9
  int v34; // r14d
  bool v35; // r12
  unsigned int ConsumerUserPropertiesKeyName; // eax
  WCHAR *v37; // r14
  LSTATUS v38; // eax
  __int64 v39; // r12
  __int64 v40; // r8
  __int64 v41; // rax
  unsigned __int8 v42; // cl
  unsigned __int8 *v43; // r14
  __int64 v44; // rcx
  __int64 v45; // rcx
  struct _UBPM_ACTION_PARAMS *v46; // r13
  int v47; // edx
  int v48; // eax
  struct _GUID *v49; // r13
  struct _GUID v50; // xmm0
  unsigned int v51; // eax
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v52; // rcx
  const struct _EVENT_DESCRIPTOR *v53; // rdx
  int v54; // r8d
  PVOID v55; // rbx
  const unsigned __int16 *v56; // r9
  int v57; // eax
  __int64 v58; // r8
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v59; // rbx
  int v60; // r13d
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v61; // rsi
  const unsigned __int16 *v62; // rcx
  int v63; // eax
  __int64 v64; // r8
  __int64 v65; // rdx
  DWORD v67; // ebx
  __int64 v68; // rdx
  __int64 v69; // rax
  int v70; // eax
  __int64 v71; // r8
  DWORD LastError; // ebx
  __int64 v73; // r13
  bool v74; // zf
  unsigned __int16 *v75; // r12
  const unsigned __int16 *v76; // rdx
  __int64 v77; // rax
  unsigned int v78; // edx
  const unsigned __int16 *v79; // rcx
  unsigned int v80; // r12d
  PVOID v81; // rbx
  const unsigned __int16 *v82; // r9
  _DWORD *v83; // rax
  LSTATUS v84; // eax
  const unsigned __int16 *v85; // rdx
  const struct _GUID *phkResult; // [rsp+20h] [rbp-E0h]
  void *cchCount2; // [rsp+28h] [rbp-D8h]
  struct _GUID *v88; // [rsp+30h] [rbp-D0h]
  const struct _GUID *v89; // [rsp+38h] [rbp-C8h]
  __int16 v90; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  RPC_STATUS Status; // [rsp+60h] [rbp-A0h] BYREF
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v95; // [rsp+68h] [rbp-98h] BYREF
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v96; // [rsp+70h] [rbp-90h] BYREF
  PVOID P; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  PVOID v99; // [rsp+88h] [rbp-78h] BYREF
  PVOID v100; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp-68h] BYREF
  __int128 v102; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v103; // [rsp+B0h] [rbp-50h]
  PSID Sid[2]; // [rsp+C0h] [rbp-40h]
  __int128 v105; // [rsp+D0h] [rbp-30h]
  __int128 v106; // [rsp+E0h] [rbp-20h]
  __int128 v107; // [rsp+F0h] [rbp-10h]
  __int128 v108; // [rsp+100h] [rbp+0h]
  const unsigned __int16 **v109; // [rsp+110h] [rbp+10h]
  _QWORD v110[5]; // [rsp+120h] [rbp+20h] BYREF
  int v111; // [rsp+148h] [rbp+48h]
  __int16 v112; // [rsp+14Ch] [rbp+4Ch]
  unsigned __int64 v113; // [rsp+150h] [rbp+50h]
  unsigned int v114; // [rsp+158h] [rbp+58h]
  PSID v115; // [rsp+160h] [rbp+60h]
  void *v116; // [rsp+168h] [rbp+68h]
  int v117; // [rsp+174h] [rbp+74h]
  unsigned __int64 v118; // [rsp+178h] [rbp+78h]
  const unsigned __int16 *v119; // [rsp+180h] [rbp+80h]
  unsigned int v120; // [rsp+188h] [rbp+88h]
  unsigned int v121; // [rsp+18Ch] [rbp+8Ch]
  unsigned __int8 *v122; // [rsp+190h] [rbp+90h]
  unsigned __int8 v123; // [rsp+198h] [rbp+98h]
  const unsigned __int16 **v124; // [rsp+1A0h] [rbp+A0h]
  unsigned int v125; // [rsp+1A8h] [rbp+A8h]
  const unsigned __int16 *v126; // [rsp+1B0h] [rbp+B0h]
  unsigned __int8 v127; // [rsp+1B8h] [rbp+B8h]
  const unsigned __int16 **v128; // [rsp+1C0h] [rbp+C0h]
  unsigned __int16 v129; // [rsp+220h] [rbp+120h] BYREF
  struct _UBPM_CONSTRAINT_PRECHECK_INFO *v130; // [rsp+228h] [rbp+128h]
  struct _UBPM_ACTION_PARAMS *v131; // [rsp+230h] [rbp+130h]
  unsigned int v132; // [rsp+238h] [rbp+138h]

  v132 = a4;
  v131 = a3;
  v130 = a2;
  v90 = 0;
  memset_0(v110, 0, 0xA8u);
  v23 = pSid;
  v109 = 0;
  v102 = 0;
  v103 = 0;
  *(_OWORD *)Sid = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  if ( pSid )
    LengthSid = GetLengthSid(pSid);
  else
    LengthSid = 0;
  v25 = *((_QWORD *)a1 + 3);
  v26 = -1;
  P = 0;
  v99 = 0;
  v100 = 0;
  v95 = 0;
  v96 = 0;
  v129 = 0;
  Status = 0;
  v27 = *(const WCHAR **)(v25 + 8);
  if ( v27 )
  {
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    if ( (unsigned int)v28 > 8 && CompareStringW(0x7Fu, 1u, v27, 7, L"NT TASK", 7) == 2 )
      v27 += 7;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, LengthSid + 120);
  v30 = Heap;
  if ( Heap )
  {
    if ( v23 )
    {
      *((_QWORD *)Heap + 11) = Heap + 120;
      if ( !CopySid(LengthSid, Heap + 120, v23) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
            *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
            LastError);
        UBPM_MIDL_user_free(v30);
        return LastError;
      }
    }
    LOBYTE(pSid) = 0;
    *((_QWORD *)v30 + 1) = v30;
    *(_QWORD *)v30 = v30;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
        *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
    UbpmpActionContextCleanup(a1);
    if ( *(_QWORD *)(*((_QWORD *)a1 + 3) + 48LL) )
    {
      RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
      dword_18004CEE8 = GetCurrentThreadId();
      LOBYTE(pSid) = 1;
    }
    *(_QWORD *)&v106 = a10;
    DWORD2(v106) = a11;
    *(_QWORD *)&v107 = a12;
    BYTE8(v107) = a13;
    *(_QWORD *)&v108 = a14;
    BYTE12(v108) = a19;
    v109 = a20;
    DWORD2(v108) = a17;
    DWORD2(v105) = a9;
    Sid[0] = (PSID)__PAIR64__(v132, a15);
    *((_QWORD *)&v102 + 1) = a3;
    v31 = a21;
    *(_QWORD *)&v105 = a8;
    *((_QWORD *)&v103 + 1) = a16;
    *(_QWORD *)&v102 = a1;
    Sid[1] = v23;
    v34 = UbpmConstraintsCheck((unsigned int)&v102, (_DWORD)v130, (unsigned int)&v90, (unsigned int)&v129, (__int64)a21);
    if ( v34 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
          v34);
    }
    else
    {
      if ( *v31 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
            *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
        goto LABEL_66;
      }
      if ( Sid[1] )
      {
        hKey = 0;
        v35 = 0;
        lpSubKey = 0;
        *(_DWORD *)Data = 0;
        Type = 0;
        cbData = 0;
        ConsumerUserPropertiesKeyName = UbpmpGetConsumerUserPropertiesKeyName(
                                          *(PCNZWCH *)(*(_QWORD *)(v102 + 24) + 8LL),
                                          Sid[1],
                                          (unsigned __int16 **)&lpSubKey);
        v37 = (WCHAR *)lpSubKey;
        if ( !ConsumerUserPropertiesKeyName )
        {
          v38 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 1u, &hKey);
          if ( (unsigned int)(v38 - 2) > 1 && !v38 )
          {
            cbData = 4;
            v84 = RegQueryValueExW(hKey, L"Disabled", 0, &Type, Data, &cbData);
            if ( (unsigned int)(v84 - 2) > 1 && !v84 && Type == 4 && cbData == 4 )
              v35 = *(_DWORD *)Data != 0;
          }
        }
        if ( hKey )
          RegCloseKey(hKey);
        if ( v37 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
        if ( v35 )
        {
          v34 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              73,
              (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
              *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
              0);
          goto LABEL_66;
        }
      }
      v39 = a17;
      if ( a17 != 0xFFFF )
      {
        v68 = *((_QWORD *)a1 + 3);
        v69 = *(_QWORD *)(v68 + 24);
        if ( *(_DWORD *)(v69 + 48LL * a17) == 1
          && *(_DWORD *)(*(_QWORD *)(v69 + 48LL * a17 + 8) + 56LL) == 4
          && (a9 & 0x20) != 0
          && *(char *)(v68 + 16) >= 0 )
        {
          v70 = EventManager::EvtReport(g_hTaskEventManager, &MISSED_TASK_REJECTED, v27, v33, phkResult);
          v71 = (unsigned __int16)v70;
          if ( v70 >= 0 )
            v71 = 0;
          TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", &MISSED_TASK_REJECTED, v71);
          v34 = 4320;
          goto LABEL_86;
        }
      }
      v40 = *((_QWORD *)a1 + 3);
      v111 = *((_DWORD *)a1 + 11);
      v110[0] = v131;
      v110[4] = a8;
      v110[1] = *(_QWORD *)v40;
      v110[2] = v27;
      v110[3] = *(_QWORD *)(v40 + 8);
      v113 = a10;
      v114 = v132;
      v112 = v90;
      v116 = a7;
      v41 = *((_QWORD *)v131 + 4);
      v115 = v23;
      if ( v41 )
        v117 = *(_DWORD *)(v41 + 20);
      else
        v117 = 0;
      v118 = a12;
      if ( v129 >= a13 )
        v119 = 0;
      else
        v119 = a14[v129];
      v42 = a19;
      v125 = a9;
      if ( v129 < a19 )
      {
        v126 = a20[v129];
        v42 = a19;
      }
      else
      {
        v126 = 0;
      }
      v43 = a16;
      v120 = a17;
      if ( (*(_BYTE *)(v40 + 16) & 2) != 0 )
      {
        v121 = a15;
        v123 = a13;
        v124 = a14;
        v127 = v42;
        v128 = a20;
        v122 = a16;
      }
      if ( !v23 )
      {
        v77 = *(_QWORD *)(*((_QWORD *)v131 + 3) + 32LL);
        if ( v77 )
          v23 = *(PSID *)(*(_QWORD *)(v77 + 8) + 8LL);
        else
          LODWORD(v23) = (_DWORD)::pSid;
      }
      UbpmpActionLogTriggered(a1, a17, a9, a18, a8);
      if ( (_DWORD)v39 == 0xFFFF )
        goto LABEL_35;
      v44 = *(_QWORD *)(*((_QWORD *)a1 + 3) + 24LL);
      if ( *(_DWORD *)(v44 + 48 * v39) != 1 )
        goto LABEL_35;
      v45 = *(_QWORD *)(v44 + 48 * v39 + 8);
      if ( *(_DWORD *)(v45 + 56) != 1 )
        goto LABEL_35;
      if ( !UuidEqual(**(UUID ***)(v45 + 64), (UUID *)&TRIGGER_EMULATOR_PROVIDER_GUID, &Status) )
        goto LABEL_35;
      if ( Status )
        goto LABEL_35;
      v32 = a15 >> 1;
      if ( !(a15 >> 1) || !v43 || *(_WORD *)&v43[2 * (unsigned int)(v32 - 1)] )
        goto LABEL_35;
      do
        ++v26;
      while ( *(_WORD *)&v43[2 * v26] );
      v73 = (unsigned int)(v26 + 1);
      if ( (unsigned int)v73 < (unsigned int)v32 && (v32 = (unsigned int)(v32 - v73), (a15 = v32) != 0) )
      {
        v74 = *(_WORD *)&v43[2 * v73] == 0;
        v75 = (unsigned __int16 *)&v43[2 * v73];
        v46 = v131;
        if ( !v74 )
        {
          if ( !v119 )
          {
            v76 = *(const unsigned __int16 **)(*((_QWORD *)v131 + 3) + 16LL);
            if ( v76 )
            {
              v34 = UbpmpExpandString((unsigned __int16 **)&v99, v76, v75, v32);
              if ( v34 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    74,
                    (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                    *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
                    v34);
                goto LABEL_65;
              }
              v32 = a15;
              v119 = (const unsigned __int16 *)v99;
            }
          }
          if ( !v126 )
          {
            v85 = *(const unsigned __int16 **)(*((_QWORD *)v46 + 3) + 24LL);
            if ( v85 )
            {
              v34 = UbpmpExpandString((unsigned __int16 **)&v100, v85, v75, v32);
              if ( v34 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    75,
                    (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                    *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
                    v34);
                goto LABEL_65;
              }
              v126 = (const unsigned __int16 *)v100;
            }
          }
        }
        LODWORD(v39) = a17;
      }
      else
      {
LABEL_35:
        v46 = v131;
      }
      v47 = **(_DWORD **)(v110[0] + 24LL);
      v95 = 0;
      v96 = 0;
      if ( (unsigned int)(v47 - 1) > 1 )
      {
        if ( v47 == 3 )
          v48 = UbpmLaunchTaskSignal(v110, a6, v32);
        else
          v48 = UbpmLaunchTaskPublish(v110, a6, v32);
      }
      else
      {
        v48 = UbpmpHostLaunchTaskExe((struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *)v110, a6, &v95, &v96);
      }
      v34 = v48;
      if ( !v129 && (DWORD2(v105) & 0x80000) != 0 )
      {
        v83 = *(_DWORD **)(*((_QWORD *)&v102 + 1) + 32LL);
        if ( v83 )
        {
          if ( (*v83 & 0x1C0) == 0x1C0 )
            *((_BYTE *)a1 + 304) = 0;
        }
      }
      if ( v34 )
      {
        if ( v34 > 0 )
          v78 = (unsigned __int16)v34 | 0x80070000;
        else
          v78 = v34;
        v79 = L"NULL";
        if ( *((_QWORD *)v46 + 1) )
          v79 = (const unsigned __int16 *)*((_QWORD *)v46 + 1);
        ReportTaskEvent(g_hTaskEventManager, &ACTION_LAUNCH_FAILURE, v27, a8, v79, v78);
        if ( !v129 )
        {
          UbpmUtilsGetAccountNamesFromSid((_DWORD)v23, 1, 0, 0, (__int64)&P);
          if ( v34 > 0 )
            v80 = (unsigned __int16)v34 | 0x80070000;
          else
            v80 = v34;
          v81 = P;
          v82 = L"(NONE)";
          if ( P )
            v82 = (const unsigned __int16 *)P;
          ReportTaskEvent(g_hTaskEventManager, &JOB_START_FAILED, v27, v82, v80);
          UBPM_MIDL_user_free(v81);
        }
        UbpmScheduleRestartOnFailure(a1, 1);
      }
      else
      {
        *((_QWORD *)v30 + 3) = v46;
        v49 = a8;
        *((_QWORD *)v30 + 4) = v95;
        *((_QWORD *)v30 + 5) = v96;
        *((_DWORD *)v30 + 12) = v132;
        v50 = *v49;
        *((_QWORD *)v30 + 10) = a12;
        v51 = a9;
        *(struct _GUID *)(v30 + 52) = v50;
        *((_DWORD *)v30 + 25) = v51;
        *((_QWORD *)v30 + 13) = a1;
        *((_DWORD *)v30 + 24) = v39;
        GetSystemTimeAsFileTime((LPFILETIME)v30 + 14);
        _InterlockedIncrement64((volatile signed __int64 *)a1 + 8);
        v52 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK **)*((_QWORD *)a1 + 29);
        if ( *v52 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)a1 + 224) )
          __fastfail(3u);
        *(_QWORD *)v30 = (char *)a1 + 224;
        *((_QWORD *)v30 + 1) = v52;
        *v52 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v30;
        *((_QWORD *)a1 + 29) = v30;
        if ( *(_QWORD *)(*((_QWORD *)a1 + 3) + 48LL) )
          UbpmpMaintenanceTaskStartedCallout(a1, v30);
        UbpmTriggerConsumerPublishStateChange(a1);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_SqqddL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v132,
            v54,
            *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
            (char)v30,
            (char)v95,
            v90,
            v132,
            a9);
        if ( !v129 )
        {
          UbpmUtilsGetAccountNamesFromSid((_DWORD)v23, 1, 0, 0, (__int64)&P);
          v55 = P;
          v56 = L"(NONE)";
          if ( P )
            v56 = (const unsigned __int16 *)P;
          v57 = EventManager::EvtReport(g_hTaskEventManager, &JOB_START, v27, v56, v49, cchCount2, v88);
          v58 = (unsigned __int16)v57;
          if ( v57 >= 0 )
            v58 = 0;
          TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", &JOB_START, v58);
          if ( v55 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v55);
        }
        v59 = v95;
        LOBYTE(v60) = 0;
        if ( v95 )
        {
          v61 = v96;
          RtlAcquireSRWLockShared((char *)v95 + 64);
          if ( (!v61 || (*((_BYTE *)v61 + 104) & 1) == 0) && (*((_BYTE *)v59 + 104) & 4) == 0 )
            v60 = *((_DWORD *)v59 + 8);
          RtlReleaseSRWLockShared((char *)v59 + 64);
        }
        v62 = (const unsigned __int16 *)*((_QWORD *)v131 + 1);
        if ( !v62 )
          v62 = L"NULL";
        v63 = EventManager::EvtReport(g_hTaskEventManager, v53, v27, v62, a8, v60, v88, v89);
        v64 = (unsigned __int16)v63;
        if ( v63 >= 0 )
          v64 = 0;
        TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", ACTION_START, v64);
        v30 = 0;
      }
    }
LABEL_65:
    if ( v34 > 0 )
    {
LABEL_86:
      v65 = (unsigned __int16)v34 | 0x80070000;
      goto LABEL_67;
    }
LABEL_66:
    v65 = (unsigned int)v34;
LABEL_67:
    LOBYTE(v32) = 1;
    UbpmpTriggerConsumerReportResult(a1, v65, v32);
    if ( (_BYTE)pSid )
    {
      dword_18004CEE8 = 0;
      RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
    }
    if ( v99 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v99);
    if ( v100 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
    if ( v30 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
    return (unsigned int)v34;
  }
  SetLastError(8u);
  v67 = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
      *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
      v67);
  return v67;
}

```

## disassembly

```asm
0x180006650  mov     [rsp-8+arg_18], r9d
0x180006655  mov     [rsp-8+arg_10], r8
0x18000665a  mov     [rsp-8+arg_8], rdx
0x18000665f  push    rbp
0x180006660  push    rbx
0x180006661  push    rsi
0x180006662  push    rdi
0x180006663  push    r12
0x180006665  push    r13
0x180006667  push    r14
0x180006669  push    r15
0x18000666b  lea     rbp, [rsp-0D8h]
0x180006673  sub     rsp, 1D8h
0x18000667a  mov     r12, r8
0x18000667d  mov     r15, rcx
0x180006680  xor     edi, edi
0x180006682  lea     rcx, [rbp+110h+var_F0]; void *
0x180006686  mov     r8d, 0A8h; Size
0x18000668c  mov     [rsp+210h+var_1C0], di
0x180006691  xor     edx, edx; Val
0x180006693  call    memset_0
0x180006698  mov     rbx, [rbp+110h+pSid]
0x18000669f  xorps   xmm0, xmm0
0x1800066a2  xor     eax, eax
0x1800066a4  mov     [rbp+110h+var_100], rax
0x1800066a8  movups  [rbp+110h+var_170], xmm0
0x1800066ac  movups  [rbp+110h+var_160], xmm0
0x1800066b0  movups  xmmword ptr [rbp+110h+Sid], xmm0
0x1800066b4  movups  [rbp+110h+var_140], xmm0
0x1800066b8  movups  [rbp+110h+var_130], xmm0
0x1800066bc  movups  [rbp+110h+var_120], xmm0
0x1800066c0  movups  [rbp+110h+var_110], xmm0
0x1800066c4  test    rbx, rbx
0x1800066c7  jz      loc_180006DB8
0x1800066cd  mov     rcx, rbx; pSid
0x1800066d0  call    cs:__imp_GetLengthSid
0x1800066d6  mov     r14d, eax
0x1800066d9  mov     rax, [r15+18h]
0x1800066dd  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800066e4  mov     [rsp+210h+P], rdi
0x1800066e9  mov     [rbp+110h+var_188], rdi
0x1800066ed  mov     [rbp+110h+var_180], rdi
0x1800066f1  mov     [rsp+210h+var_1A8], rdi
0x1800066f6  mov     [rsp+210h+var_1A0], rdi
0x1800066fb  mov     [rbp+110h+arg_0], di
0x180006702  mov     [rsp+210h+Status], edi
0x180006706  mov     rdi, [rax+8]
0x18000670a  test    rdi, rdi
0x18000670d  jz      short loc_180006725
0x18000670f  mov     rax, r13
0x180006712  inc     rax
0x180006715  cmp     word ptr [rdi+rax*2], 0
0x18000671a  jnz     short loc_180006712
0x18000671c  cmp     eax, 8
0x18000671f  ja      loc_180006E95
0x180006725  mov     rcx, gs:60h
0x18000672e  lea     r8d, [r14+78h]; Size
0x180006732  mov     edx, 8; Flags
0x180006737  mov     rcx, [rcx+30h]; HeapHandle
0x18000673b  call    cs:__imp_RtlAllocateHeap
0x180006741  mov     rsi, rax
0x180006744  test    rax, rax
0x180006747  jz      loc_180006D78
0x18000674d  test    rbx, rbx
0x180006750  jnz     loc_180006ED4
0x180006756  mov     byte ptr [rbp+110h+pSid], 0
0x18000675d  mov     [rsi+8], rsi
0x180006761  mov     [rsi], rsi
0x180006764  mov     rcx, cs:WPP_GLOBAL_Control
0x18000676b  lea     rax, WPP_GLOBAL_Control
0x180006772  cmp     rcx, rax
0x180006775  jnz     loc_180006E46
0x18000677b  mov     rcx, r15
0x18000677e  call    UbpmpActionContextCleanup
0x180006783  mov     rax, [r15+18h]
0x180006787  cmp     qword ptr [rax+30h], 0
0x18000678c  jz      short loc_1800067AE
0x18000678e  lea     rcx, g_MaintenanceLaunchLock
0x180006795  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000679b  call    cs:__imp_GetCurrentThreadId
0x1800067a1  mov     cs:dword_18004CEE8, eax
0x1800067a7  mov     byte ptr [rbp+110h+pSid], 1
0x1800067ae  mov     rax, [rbp+110h+arg_48]
0x1800067b5  lea     r8, [rsp+210h+var_1C0]
0x1800067ba  mov     edx, [rbp+110h+arg_40]
0x1800067c0  lea     rcx, [rbp+110h+var_170]
0x1800067c4  mov     r9, [rbp+110h+arg_38]
0x1800067cb  mov     qword ptr [rbp+110h+var_130], rax
0x1800067cf  mov     eax, [rbp+110h+arg_50]
0x1800067d5  mov     dword ptr [rbp+110h+var_130+8], eax
0x1800067d8  mov     rax, [rbp+110h+arg_58]
0x1800067df  mov     qword ptr [rbp+110h+var_120], rax
0x1800067e3  movzx   eax, [rbp+110h+arg_60]
0x1800067ea  mov     byte ptr [rbp+110h+var_120+8], al
0x1800067ed  mov     rax, [rbp+110h+arg_68]
0x1800067f4  mov     qword ptr [rbp+110h+var_110], rax
0x1800067f8  movzx   eax, [rbp+110h+arg_90]
0x1800067ff  mov     byte ptr [rbp+110h+var_110+0Ch], al
0x180006802  mov     rax, [rbp+110h+arg_98]
0x180006809  mov     [rbp+110h+var_100], rax
0x18000680d  mov     eax, [rbp+110h+arg_80]
0x180006813  mov     dword ptr [rbp+110h+var_110+8], eax
0x180006816  mov     eax, [rbp+110h+arg_70]
0x18000681c  mov     dword ptr [rbp+110h+var_140+8], edx
0x18000681f  mov     edx, [rbp+110h+arg_18]
0x180006825  mov     dword ptr [rbp+110h+Sid], eax
0x180006828  mov     rax, [rbp+110h+arg_78]
0x18000682f  mov     qword ptr [rbp+110h+var_170+8], r12
0x180006833  mov     r12, [rbp+110h+arg_A0]
0x18000683a  mov     qword ptr [rbp+110h+var_140], r9
0x18000683e  lea     r9, [rbp+110h+arg_0]
0x180006845  mov     dword ptr [rbp+110h+Sid+4], edx
0x180006848  mov     rdx, [rbp+110h+arg_8]
0x18000684f  mov     qword ptr [rbp+110h+var_160+8], rax
0x180006853  mov     qword ptr [rbp+110h+var_170], r15
0x180006857  mov     [rbp+110h+Sid+8], rbx
0x18000685b  mov     [rsp+210h+phkResult], r12
0x180006860  call    UbpmConstraintsCheck
0x180006865  mov     r14d, eax
0x180006868  test    eax, eax
0x18000686a  jnz     loc_180006F41
0x180006870  cmp     [r12], al
0x180006874  jnz     loc_1800071A8
0x18000687a  mov     rdx, [rbp+110h+Sid+8]; Sid
0x18000687e  test    rdx, rdx
0x180006881  jz      loc_18000691E
0x180006887  xor     eax, eax
0x180006889  lea     r8, [rbp+110h+lpSubKey]; unsigned __int16 **
0x18000688d  mov     [rbp+110h+hKey], rax
0x180006891  xor     r12b, r12b
0x180006894  mov     [rbp+110h+lpSubKey], rax
0x180006898  mov     dword ptr [rsp+210h+Data], eax
0x18000689c  mov     [rsp+210h+Type], eax
0x1800068a0  mov     [rsp+210h+cbData], eax
0x1800068a4  mov     rax, qword ptr [rbp+110h+var_170]
0x1800068a8  mov     rcx, [rax+18h]
0x1800068ac  mov     rcx, [rcx+8]; lpString1
0x1800068b0  call    ?UbpmpGetConsumerUserPropertiesKeyName@@YAKPEBGPEAXPEAPEAG@Z; UbpmpGetConsumerUserPropertiesKeyName(ushort const *,void *,ushort * *)
0x1800068b5  mov     r14, [rbp+110h+lpSubKey]
0x1800068b9  test    eax, eax
0x1800068bb  jnz     short loc_1800068EB
0x1800068bd  lea     rax, [rbp+110h+hKey]
0x1800068c1  mov     r9d, 1; samDesired
0x1800068c7  xor     r8d, r8d; ulOptions
0x1800068ca  mov     [rsp+210h+phkResult], rax; struct _GUID *
0x1800068cf  mov     rdx, r14; lpSubKey
0x1800068d2  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800068d9  call    cs:__imp_RegOpenKeyExW
0x1800068df  lea     ecx, [rax-2]
0x1800068e2  cmp     ecx, 1
0x1800068e5  ja      loc_1800072BF
0x1800068eb  mov     rcx, [rbp+110h+hKey]; hKey
0x1800068ef  test    rcx, rcx
0x1800068f2  jnz     loc_180007363
0x1800068f8  test    r14, r14
0x1800068fb  jz      short loc_180006915
0x1800068fd  mov     rcx, gs:60h
0x180006906  mov     r8, r14; P
0x180006909  xor     edx, edx; Flags
0x18000690b  mov     rcx, [rcx+30h]; HeapHandle
0x18000690f  call    cs:__imp_RtlFreeHeap
0x180006915  test    r12b, r12b
0x180006918  jnz     loc_180007274
0x18000691e  mov     r12d, [rbp+110h+arg_80]
0x180006925  mov     r14d, [rbp+110h+arg_40]
0x18000692c  cmp     r12d, 0FFFFh
0x180006933  jnz     loc_180006DC0
0x180006939  mov     eax, [r15+2Ch]
0x18000693d  mov     r8, [r15+18h]
0x180006941  mov     rcx, [rbp+110h+arg_10]
0x180006948  mov     r11, [rbp+110h+arg_38]
0x18000694f  mov     [rbp+110h+var_C8], eax
0x180006952  mov     [rbp+110h+var_F0], rcx
0x180006956  mov     [rbp+110h+var_D0], r11
0x18000695a  mov     rax, [r8]
0x18000695d  mov     [rbp+110h+var_E8], rax
0x180006961  mov     [rbp+110h+var_E0], rdi
0x180006965  mov     rax, [r8+8]
0x180006969  mov     [rbp+110h+var_D8], rax
0x18000696d  mov     rax, [rbp+110h+arg_48]
0x180006974  mov     [rbp+110h+var_C0], rax
0x180006978  mov     eax, [rbp+110h+arg_18]
0x18000697e  mov     [rbp+110h+var_B8], eax
0x180006981  movzx   eax, [rsp+210h+var_1C0]
0x180006986  mov     [rbp+110h+var_C4], ax
0x18000698a  mov     rax, [rbp+110h+arg_30]
0x180006991  mov     [rbp+110h+var_A8], rax
0x180006995  mov     rax, [rcx+20h]
0x180006999  mov     [rbp+110h+var_B0], rbx
0x18000699d  test    rax, rax
0x1800069a0  jz      loc_1800071EB
0x1800069a6  mov     eax, [rax+14h]
0x1800069a9  mov     [rbp+110h+var_9C], eax
0x1800069ac  movzx   r9d, [rbp+110h+arg_60]
0x1800069b4  movzx   edx, [rbp+110h+arg_0]
0x1800069bb  mov     rax, [rbp+110h+arg_58]
0x1800069c2  mov     r10, [rbp+110h+arg_68]
0x1800069c9  mov     [rbp+110h+var_98], rax
0x1800069cd  cmp     dx, r9w
0x1800069d1  jnb     loc_180006E75
0x1800069d7  mov     rcx, [r10+rdx*8]
0x1800069db  mov     [rbp+110h+var_90], rcx
0x1800069e2  movzx   ecx, [rbp+110h+arg_90]
0x1800069e9  mov     [rbp+110h+var_68], r14d
0x1800069f0  cmp     dx, cx
0x1800069f3  jb      loc_18000709F
0x1800069f9  mov     rdx, [rbp+110h+arg_98]
0x180006a00  mov     [rbp+110h+var_60], 0
0x180006a0b  mov     r14, [rbp+110h+arg_78]
0x180006a12  mov     [rbp+110h+var_88], r12d
0x180006a19  test    byte ptr [r8+10h], 2
0x180006a1e  jz      short loc_180006A4E
0x180006a20  mov     eax, [rbp+110h+arg_70]
0x180006a26  mov     [rbp+110h+var_84], eax
0x180006a2c  mov     [rbp+110h+var_78], r9b
0x180006a33  mov     [rbp+110h+var_70], r10
0x180006a3a  mov     [rbp+110h+var_58], cl
0x180006a40  mov     [rbp+110h+var_50], rdx
0x180006a47  mov     [rbp+110h+var_80], r14
0x180006a4e  test    rbx, rbx
0x180006a51  jz      loc_1800070C0
0x180006a57  mov     r9, [rbp+110h+arg_88]; void *
0x180006a5e  mov     edx, r12d; unsigned int
0x180006a61  mov     r8d, [rbp+110h+arg_40]; unsigned int
0x180006a68  mov     rcx, r15; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180006a6b  mov     [rsp+210h+phkResult], r11; struct _GUID *
0x180006a70  call    ?UbpmpActionLogTriggered@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@KKPEAXPEAU_GUID@@@Z; UbpmpActionLogTriggered(_UBPM_TRIGGER_CONSUMER_BLOCK *,ulong,ulong,void *,_GUID *)
0x180006a75  cmp     r12d, 0FFFFh
0x180006a7c  jz      short loc_180006AA2
0x180006a7e  mov     rax, [r15+18h]
0x180006a82  lea     rdx, [r12+r12*2]
0x180006a86  add     rdx, rdx
0x180006a89  mov     rcx, [rax+18h]
0x180006a8d  cmp     dword ptr [rcx+rdx*8], 1
0x180006a91  jnz     short loc_180006AA2
0x180006a93  mov     rcx, [rcx+rdx*8+8]
0x180006a98  cmp     dword ptr [rcx+38h], 1
0x180006a9c  jz      loc_180006F89
0x180006aa2  mov     r13, [rbp+110h+arg_10]
0x180006aa9  mov     rax, [rbp+110h+var_F0]
0x180006aad  mov     rcx, [rax+18h]
0x180006ab1  xor     eax, eax
0x180006ab3  mov     edx, [rcx]
0x180006ab5  lea     rcx, [rbp+110h+var_F0]; struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *
0x180006ab9  mov     [rsp+210h+var_1A8], rax
0x180006abe  mov     [rsp+210h+var_1A0], rax
0x180006ac3  lea     eax, [rdx-1]
0x180006ac6  cmp     eax, 1
0x180006ac9  ja      loc_180007203
0x180006acf  mov     rdx, [rbp+110h+arg_28]; void **
0x180006ad6  lea     r9, [rsp+210h+var_1A0]; struct _UBPM_TASK_HOST_TASK_CONTEXT **
0x180006adb  lea     r8, [rsp+210h+var_1A8]; struct _UBPM_TASK_HOST_CONTEXT_BLOCK **
0x180006ae0  call    ?UbpmpHostLaunchTaskExe@@YAKPEAU_UBPM_TASK_LAUNCH_INPUT_PARAMS@@PEAPEAXPEAPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_UBPM_TASK_HOST_TASK_CONTEXT@@@Z; UbpmpHostLaunchTaskExe(_UBPM_TASK_LAUNCH_INPUT_PARAMS *,void * *,_UBPM_TASK_HOST_CONTEXT_BLOCK * *,_UBPM_TASK_HOST_TASK_CONTEXT * *)
0x180006ae5  cmp     [rbp+110h+arg_0], 0
0x180006aed  mov     r14d, eax
0x180006af0  jnz     short loc_180006AFF
0x180006af2  test    dword ptr [rbp+110h+var_140+8], 80000h
0x180006af9  jnz     loc_18000723A
0x180006aff  test    r14d, r14d
0x180006b02  jnz     loc_1800070E5
0x180006b08  mov     [rsi+18h], r13
0x180006b0c  lea     rcx, [rsi+70h]; lpSystemTimeAsFileTime
0x180006b10  mov     rax, [rsp+210h+var_1A8]
0x180006b15  mov     r13, [rbp+110h+arg_38]
0x180006b1c  mov     [rsi+20h], rax
0x180006b20  mov     rax, [rsp+210h+var_1A0]
0x180006b25  mov     [rsi+28h], rax
0x180006b29  mov     eax, [rbp+110h+arg_18]
0x180006b2f  mov     [rsi+30h], eax
0x180006b32  movups  xmm0, xmmword ptr [r13+0]
0x180006b37  mov     rax, [rbp+110h+arg_58]
0x180006b3e  mov     [rsi+50h], rax
0x180006b42  mov     eax, [rbp+110h+arg_40]
0x180006b48  movups  xmmword ptr [rsi+34h], xmm0
0x180006b4c  mov     [rsi+64h], eax
0x180006b4f  mov     [rsi+68h], r15
0x180006b53  mov     [rsi+60h], r12d
0x180006b57  call    cs:__imp_GetSystemTimeAsFileTime
0x180006b5d  lock inc qword ptr [r15+40h]
0x180006b62  lea     rax, [r15+0E0h]
0x180006b69  mov     rcx, [rax+8]
0x180006b6d  cmp     [rcx], rax
0x180006b70  jnz     loc_180007227
0x180006b76  mov     [rsi], rax
0x180006b79  mov     [rsi+8], rcx
0x180006b7d  mov     [rcx], rsi
0x180006b80  mov     [rax+8], rsi
0x180006b84  mov     rax, [r15+18h]
0x180006b88  cmp     qword ptr [rax+30h], 0
0x180006b8d  jnz     loc_180006E85
0x180006b93  mov     rcx, r15
0x180006b96  call    UbpmTriggerConsumerPublishStateChange
0x180006b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ba2  lea     rax, WPP_GLOBAL_Control
0x180006ba9  cmp     rcx, rax
0x180006bac  jz      short loc_180006BBB
0x180006bae  test    dword ptr [rcx+1Ch], 200h
0x180006bb5  jnz     loc_18000740C
0x180006bbb  cmp     [rbp+110h+arg_0], 0
0x180006bc3  jnz     loc_180006C50
  ... truncated ...
```
