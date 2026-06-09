# RpcServer::Runtimes(ushort const *,_SYSTEMTIME *,_SYSTEMTIME *,ulong,ulong,ulong *,_SYSTEMTIME * *)

- ea: `0x18001e06c`
- end: `0x18001ea36`
- name: `?Runtimes@RpcServer@@QEAAJPEBGPEAU_SYSTEMTIME@@1KKPEAKPEAPEAU2@@Z`
- size: `2506`
- prototype: `int(RpcServer *__hidden this, const unsigned __int16 *, struct _SYSTEMTIME *, struct _SYSTEMTIME *, unsigned int, unsigned int, unsigned int *, struct _SYSTEMTIME **)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004d190`

## callees

- `0x180009d90`
- `0x18000bb10`
- `0x18000cc40`
- `0x18000ff40`
- `0x180010390`
- `0x1800138d8`
- `0x180013a90`
- `0x180015030`
- `0x1800170b0`
- `0x18001d130`
- `0x18001d67c`
- `0x18001e06c`
- `0x18001ea40`
- `0x18001f060`
- `0x180020110`
- `0x180024730`
- `0x180027910`
- `0x18002db40`
- `0x18002f814`
- `0x180037b40`
- `0x18003d070`
- `0x18004113c`
- `0x180045c4c`
- `0x18005176c`
- `0x1800517f4`
- `0x18005a2bc`
- `0x18006d0ac`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e39e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e39e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001e286`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001e380`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001e286`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001e380`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e5f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e8d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e5f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e8d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e21c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e21c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e249`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e5d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e68d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e8b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e9ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e9dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e249`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e5d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e68d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e8b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e9ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e9dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e1a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e1a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e1c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e1c4`
- `RPCRT4!RpcImpersonateClient` at `0x18001e136`
- `RPCRT4!RpcImpersonateClient` at `0x18001e136`
- `RPCRT4!RpcRevertToSelf` at `0x18001e1ef`
- `RPCRT4!RpcRevertToSelf` at `0x18001e205`
- `RPCRT4!RpcRevertToSelf` at `0x18001e1ef`
- `RPCRT4!RpcRevertToSelf` at `0x18001e205`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RpcServer::Runtimes(
        RTL_SRWLOCK *this,
        unsigned __int16 *a2,
        struct _SYSTEMTIME *a3,
        struct _SYSTEMTIME *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7,
        struct _SYSTEMTIME **a8)
{
  const unsigned __int16 *v12; // r8
  __int64 result; // rax
  RPC_STATUS v14; // eax
  EventManager *v15; // rcx
  RPC_STATUS v16; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v19; // ebx
  RTL_SRWLOCK *v20; // rbx
  int v21; // edi
  BOOL v22; // r8d
  struct _FILETIME v23; // rax
  DWORD v24; // eax
  char v25; // cl
  __int64 v26; // xmm0_8
  int v27; // eax
  __int16 v28; // dx
  char v29; // r8
  BOOL v30; // r8d
  struct _FILETIME v31; // rax
  DWORD v32; // eax
  char v33; // cl
  __int64 v34; // xmm0_8
  int v35; // eax
  __int16 v36; // dx
  char v37; // r8
  unsigned int v38; // r12d
  int v39; // edi
  HKEY v40; // rdi
  int v41; // esi
  JobMoniker *v42; // rdi
  __int64 v43; // rdi
  __int128 v44; // xmm6
  __int128 v45; // xmm7
  unsigned int v46; // esi
  _QWORD *v47; // rax
  _QWORD *i; // rdi
  __int64 v49; // rcx
  bool v50; // zf
  _QWORD *v51; // rdi
  __int64 v52; // rax
  int RunTimes; // eax
  unsigned int v54; // r15d
  CDLink *k; // rcx
  CDLink *v56; // rdi
  void (__fastcall ***v57)(_QWORD, __int64); // rcx
  unsigned int v58; // eax
  unsigned int *v59; // r14
  int v60; // r15d
  CDLink *j; // rdi
  void *v62; // [rsp+28h] [rbp-E0h]
  const struct _GUID *v63; // [rsp+30h] [rbp-D8h]
  struct _FILETIME FileTime_8[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v65; // [rsp+58h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int *v67; // [rsp+70h] [rbp-98h]
  __int128 v68; // [rsp+78h] [rbp-90h] BYREF
  __int128 v69; // [rsp+88h] [rbp-80h] BYREF
  void **v70; // [rsp+98h] [rbp-70h] BYREF
  CDLink *v71[2]; // [rsp+A0h] [rbp-68h]
  __int64 v72; // [rsp+B0h] [rbp-58h]
  __int64 v73; // [rsp+B8h] [rbp-50h]
  unsigned int v74; // [rsp+C0h] [rbp-48h]
  unsigned int v75; // [rsp+C4h] [rbp-44h]
  int v76; // [rsp+C8h] [rbp-40h]
  struct _SYSTEMTIME **v77; // [rsp+D0h] [rbp-38h]
  _BYTE v78[32]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD *v79; // [rsp+F8h] [rbp-10h]
  struct JobBucket *v80; // [rsp+108h] [rbp+0h]
  RTL_SRWLOCK *v81; // [rsp+110h] [rbp+8h]
  GUID iid; // [rsp+118h] [rbp+10h] BYREF
  char v83[8]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v84; // [rsp+130h] [rbp+28h]
  __int64 v85; // [rsp+138h] [rbp+30h] BYREF
  struct _SYSTEMTIME v86; // [rsp+140h] [rbp+38h] BYREF
  __int128 pExceptionObject; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v88[48]; // [rsp+168h] [rbp+60h] BYREF
  __int128 v89; // [rsp+198h] [rbp+90h]
  __int64 v90; // [rsp+1A8h] [rbp+A0h]
  _OWORD v91[4]; // [rsp+1B8h] [rbp+B0h] BYREF
  OLECHAR psz; // [rsp+1F8h] [rbp+F0h] BYREF
  char v93[526]; // [rsp+1FAh] [rbp+F2h] BYREF

  v67 = a7;
  v77 = a8;
  if ( !a2 || a5 || !a7 || !a8 )
    return 2147942487LL;
  psz = 0;
  memset_0(v93, 0, 0x208u);
  result = tsched::TaskPathCanonicalize((tsched *)&psz, a2, v12);
  if ( (int)result < 0 )
    return result;
  TokenHandle = 0;
  v14 = RpcImpersonateClient(0);
  v16 = v14;
  if ( v14 )
  {
    EventManager::EvtReport(v15, &IMPERSONATION_FAILURE, L"Runtimes", v14, v62, v63);
    BYTE8(pExceptionObject) = 0;
    *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
    *(_QWORD *)v88 = &qword_1800A8718;
    *(_QWORD *)&v88[8] = 0;
    *(_QWORD *)&v88[16] = 0;
    *(_DWORD *)&v88[24] = v16;
    *(_DWORD *)&v88[28] = -1;
    *(_DWORD *)&v88[32] = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    RpcRevertToSelf();
  }
  else
  {
    LastError = GetLastError();
    v19 = LastError;
    if ( LastError > 0 )
      v19 = (unsigned __int16)LastError | 0x80070000;
    RpcRevertToSelf();
    if ( v19 < 0 )
      goto LABEL_86;
  }
  v20 = this + 2;
  v81 = this + 2;
  AcquireSRWLockShared(this + 2);
  v21 = TaskAccessCheck(TokenHandle, &psz, 1u);
  if ( v21 < 0 )
    goto LABEL_15;
  *a7 = 0;
  *a8 = 0;
  if ( a3 )
  {
    v22 = 1;
    v23 = 0;
    FileTime_8[0] = 0;
    if ( a3->wYear )
    {
      v22 = SystemTimeToFileTime(a3, FileTime_8);
      v23 = FileTime_8[0];
    }
    *((struct _FILETIME *)&v65 + 1) = v23;
    if ( !v22 )
    {
      v24 = GetLastError();
      BYTE8(pExceptionObject) = 0;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      *(_QWORD *)v88 = &qword_1800A8718;
      *(_QWORD *)&v88[8] = 0;
      *(_QWORD *)&v88[16] = 0;
      *(_DWORD *)&v88[24] = v24;
      *(_DWORD *)&v88[28] = -1;
      *(_DWORD *)&v88[32] = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v25 = 1;
    v26 = *(_QWORD *)((char *)&v65 + 1);
    v27 = *(_DWORD *)((char *)&v65 + 9);
    v28 = *(_WORD *)((char *)&v65 + 13);
    v29 = HIBYTE(v65);
  }
  else
  {
    v25 = 0;
    *(DWORD *)((char *)&FileTime_8[0].dwLowDateTime + 1) = *(_DWORD *)((char *)&v65 + 1);
    *(_WORD *)((char *)&FileTime_8[0].dwHighDateTime + 1) = *(_WORD *)((char *)&v65 + 5);
    HIBYTE(FileTime_8[0].dwHighDateTime) = BYTE7(v65);
    FileTime_8[1] = 0;
    v29 = 0;
    v28 = 0;
    v27 = 0;
    v26 = *(__int64 *)((char *)FileTime_8 + 1);
  }
  LOBYTE(v69) = v25;
  *(_QWORD *)((char *)&v69 + 1) = v26;
  *(_DWORD *)((char *)&v69 + 9) = v27;
  *(_WORD *)((char *)&v69 + 13) = v28;
  HIBYTE(v69) = v29;
  if ( a4 )
  {
    v30 = 1;
    v31 = 0;
    FileTime_8[0] = 0;
    if ( a4->wYear )
    {
      v30 = SystemTimeToFileTime(a4, FileTime_8);
      v31 = FileTime_8[0];
    }
    *((struct _FILETIME *)&v65 + 1) = v31;
    if ( !v30 )
    {
      v32 = GetLastError();
      BYTE8(pExceptionObject) = 0;
      *(_QWORD *)&pExceptionObject = &wmi::GenericException::`vftable';
      *(_QWORD *)v88 = &qword_1800A8718;
      *(_QWORD *)&v88[8] = 0;
      *(_QWORD *)&v88[16] = 0;
      *(_DWORD *)&v88[24] = v32;
      *(_DWORD *)&v88[28] = -1;
      *(_DWORD *)&v88[32] = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v33 = 1;
    v34 = *(_QWORD *)((char *)&v65 + 1);
    v35 = *(_DWORD *)((char *)&v65 + 9);
    v36 = *(_WORD *)((char *)&v65 + 13);
    v37 = HIBYTE(v65);
  }
  else
  {
    v33 = 0;
    *(DWORD *)((char *)&FileTime_8[0].dwLowDateTime + 1) = *(_DWORD *)((char *)&v65 + 1);
    *(_WORD *)((char *)&FileTime_8[0].dwHighDateTime + 1) = *(_WORD *)((char *)&v65 + 5);
    HIBYTE(FileTime_8[0].dwHighDateTime) = BYTE7(v65);
    FileTime_8[1] = (struct _FILETIME)-1LL;
    v37 = -1;
    v36 = -1;
    v35 = -1;
    v34 = *(__int64 *)((char *)FileTime_8 + 1);
  }
  LOBYTE(v68) = v33;
  *(_QWORD *)((char *)&v68 + 1) = v34;
  *(_DWORD *)((char *)&v68 + 9) = v35;
  *(_WORD *)((char *)&v68 + 13) = v36;
  HIBYTE(v68) = v37;
  v38 = 4062;
  if ( a6 )
    v38 = a6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    pExceptionObject = *(_OWORD *)L"::FirstTime";
    *(_QWORD *)v88 = *(_QWORD *)L"ime";
    memset(&v88[8], 0, 28);
    v91[0] = *(_OWORD *)L"::LastTime";
    *(_QWORD *)((char *)v91 + 14) = *(_QWORD *)L"ime";
    memset((char *)&v91[1] + 6, 0, 30);
    LOBYTE(v65) = 0;
    *((_QWORD *)&v65 + 1) = 0;
    if ( (unsigned __int8)TSTime::operator!=(&v69, &v65) )
      TSTime::ToString((TSTime *)&v69, (unsigned __int16 *)&pExceptionObject, 26);
    LOBYTE(v65) = 0;
    *((_QWORD *)&v65 + 1) = -1;
    if ( (unsigned __int8)TSTime::operator!=(&v68, &v65) )
      TSTime::ToString((TSTime *)&v68, (unsigned __int16 *)v91, 26);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SSSDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (unsigned int)&psz,
        (__int64)&pExceptionObject,
        (__int64)v91,
        0,
        v38);
    }
  }
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v78);
  JobMoniker::JobMoniker(&iid, &psz, 0);
  v39 = JobMoniker::SetExistingId((JobMoniker *)&iid);
  if ( v39 >= 0 )
  {
    FileTime_8[0] = 0;
    v21 = JobStore::RegOpenTaskKey(JobStore::m_pCommonStore, (struct JobMoniker *)&iid, (HKEY *)FileTime_8, 0x20019u);
    if ( v21 < 0 )
    {
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)FileTime_8);
      JobMoniker::~JobMoniker((JobMoniker *)&iid);
      Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v78);
LABEL_15:
      ReleaseSRWLockShared(v20);
      v19 = v21;
LABEL_86:
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      return (unsigned int)v19;
    }
    v40 = (HKEY)FileTime_8[0];
    v41 = Triggers::Trigulator::StreamIn((Triggers::Trigulator *)v78, *(HKEY *)FileTime_8, 6u, 0);
    if ( v41 < 0 )
    {
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)FileTime_8);
      JobMoniker::~JobMoniker((JobMoniker *)&iid);
      Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v78);
      ReleaseSRWLockShared(v20);
      v19 = v41;
      goto LABEL_86;
    }
    if ( v40 )
      RegCloseKey(v40);
    if ( !v80 )
    {
      JobMoniker::~JobMoniker((JobMoniker *)&iid);
      Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v78);
      ReleaseSRWLockShared(v20);
      v19 = -2147418113;
      goto LABEL_86;
    }
    v42 = JobMoniker::JobMoniker((JobMoniker *)v91, (const struct JobMoniker *)&iid, v80);
    _bstr_t::operator=(v83, (char *)v42 + 16);
    v84 = *((_QWORD *)v42 + 3);
    iid = *(GUID *)v42;
    v43 = *((_QWORD *)v42 + 4);
    if ( v43 )
      _InterlockedIncrement((volatile signed __int32 *)(v43 + 8));
    wmi::AutoRef<JobBucket>::Release(&v85);
    v85 = v43;
    JobMoniker::~JobMoniker((JobMoniker *)v91);
    v70 = &RunListItem::`vftable';
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v75 = v38;
    v76 = 1;
    v71[0] = (CDLink *)&v70;
    v71[1] = (CDLink *)&v70;
    v44 = v68;
    v45 = v69;
    v46 = 267013;
    v47 = v79;
    for ( i = (_QWORD *)*v79; i != v47; i = (_QWORD *)*i )
    {
      v49 = i[2];
      if ( v49 )
      {
        v50 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v49 + 72LL))(v49) == 56797;
        v47 = v79;
        if ( v50 )
        {
          v51 = (_QWORD *)*v79;
          while ( v51 != v47 )
          {
            if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v51[2] + 72LL))(v51[2]) == 56797 )
            {
              v52 = v51[2];
              pExceptionObject = *(_OWORD *)(v52 + 8);
              *(_OWORD *)v88 = *(_OWORD *)(v52 + 24);
              *(_OWORD *)&v88[16] = *(_OWORD *)(v52 + 40);
              *(_OWORD *)&v88[32] = *(_OWORD *)(v52 + 56);
              v89 = *(_OWORD *)(v52 + 72);
              v90 = *(_QWORD *)(v52 + 88);
              v65 = v44;
              *(_OWORD *)&FileTime_8[0].dwLowDateTime = v45;
              RunTimes = Scheduling::JobSchedule::GetRunTimes(&pExceptionObject, FileTime_8, &v65, &v70, v38);
              v54 = RunTimes;
              if ( RunTimes < 0 )
                goto LABEL_71;
              if ( v46 != 1 && ((unsigned int)RunTimes <= 1 || v46 == 267013) )
                v46 = RunTimes;
            }
            v51 = (_QWORD *)*v51;
            v47 = v79;
          }
          break;
        }
      }
    }
    if ( v46 <= 1 )
    {
      v58 = v74;
      *v67 = v74;
      if ( v58 )
      {
        v67 = 0;
        v59 = (unsigned int *)operator new(saturated_mul(v58, 0x10u));
        v67 = v59;
        v60 = 0;
        for ( j = v71[0]; *((_DWORD *)j + 6) || *((_DWORD *)j + 7); j = (CDLink *)*((_QWORD *)j + 1) )
        {
          LOBYTE(v65) = 0;
          *((_QWORD *)&v65 + 1) = *((_QWORD *)j + 3);
          v65 = *(_OWORD *)TSTime::ToLocal(&v65, FileTime_8);
          *(struct _SYSTEMTIME *)&v59[4 * v60++] = *TSTime::ToSYSTEMTIME((TSTime *)&v65, &v86);
        }
        *v77 = (struct _SYSTEMTIME *)v59;
        operator delete(0);
      }
      RunList::~RunList((RunList *)&v70);
      JobMoniker::~JobMoniker((JobMoniker *)&iid);
      Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v78);
      ReleaseSRWLockShared(v20);
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      return v46;
    }
    else
    {
      v54 = v46;
LABEL_71:
      for ( k = v71[0]; *((_DWORD *)k + 6) || *((_DWORD *)k + 7); k = v56 )
      {
        v56 = (CDLink *)*((_QWORD *)k + 1);
        CDLink::UnLink(k);
        --v74;
        (**v57)(v57, 1);
      }
      v70 = &RunListItem::`vftable';
      *(_OWORD *)v71 = 0;
      JobMoniker::~JobMoniker((JobMoniker *)&iid);
      Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v78);
      ReleaseSRWLockShared(v20);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      return v54;
    }
  }
  else
  {
    JobMoniker::~JobMoniker((JobMoniker *)&iid);
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v78);
    ReleaseSRWLockShared(v20);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return (unsigned int)v39;
  }
}

```

## disassembly

```asm
0x18001e06c  mov     rax, rsp
0x18001e06f  mov     [rax+8], rbx
0x18001e073  push    rbp
0x18001e074  push    rsi
0x18001e075  push    rdi
0x18001e076  push    r12
0x18001e078  push    r13
0x18001e07a  push    r14
0x18001e07c  push    r15
0x18001e07e  lea     rbp, [rax-368h]
0x18001e085  sub     rsp, 430h
0x18001e08c  movaps  xmmword ptr [rax-48h], xmm6
0x18001e090  movaps  xmmword ptr [rax-58h], xmm7
0x18001e094  mov     rax, cs:__security_cookie
0x18001e09b  xor     rax, rsp
0x18001e09e  mov     [rbp+360h+var_60], rax
0x18001e0a5  mov     r15, r9
0x18001e0a8  mov     rsi, r8
0x18001e0ab  mov     rbx, rdx
0x18001e0ae  mov     rdi, rcx
0x18001e0b1  mov     r13d, [rbp+360h+arg_28]
0x18001e0b8  mov     r14, [rbp+360h+arg_30]
0x18001e0bf  mov     qword ptr [rsp+460h+var_3F8], r14
0x18001e0c4  mov     r12, [rbp+360h+arg_38]
0x18001e0cb  mov     [rbp+360h+var_398], r12
0x18001e0cf  test    rdx, rdx
0x18001e0d2  jz      loc_18001E9FC
0x18001e0d8  cmp     [rbp+360h+arg_20], 0
0x18001e0df  jnz     loc_18001E9FC
0x18001e0e5  test    r14, r14
0x18001e0e8  jz      loc_18001E9FC
0x18001e0ee  test    r12, r12
0x18001e0f1  jz      loc_18001E9FC
0x18001e0f7  xor     eax, eax
0x18001e0f9  mov     [rbp+360h+psz], ax
0x18001e100  xor     edx, edx; Val
0x18001e102  mov     r8d, 208h; Size
0x18001e108  lea     rcx, [rbp+360h+var_26E]; void *
0x18001e10f  call    memset_0
0x18001e114  mov     rdx, rbx; unsigned __int16 *
0x18001e117  lea     rcx, [rbp+360h+psz]; this
0x18001e11e  call    ?TaskPathCanonicalize@tsched@@YAJPEAGPEBG@Z; tsched::TaskPathCanonicalize(ushort *,ushort const *)
0x18001e123  test    eax, eax
0x18001e125  js      loc_18001EA01
0x18001e12b  mov     [rsp+460h+TokenHandle], 0
0x18001e134  xor     ecx, ecx; BindingHandle
0x18001e136  call    cs:__imp_RpcImpersonateClient
0x18001e13d  nop     dword ptr [rax+rax+00h]
0x18001e142  mov     ebx, eax
0x18001e144  test    eax, eax
0x18001e146  jz      short loc_18001E1A7
0x18001e148  mov     r9d, eax; unsigned int
0x18001e14b  lea     r8, aRuntimes; "Runtimes"
0x18001e152  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x18001e159  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18001e15e  xor     eax, eax
0x18001e160  mov     byte ptr [rbp+360h+pExceptionObject+8], al
0x18001e163  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001e16a  mov     qword ptr [rbp+360h+pExceptionObject], rcx
0x18001e16e  lea     rcx, qword_1800A8718
0x18001e175  mov     qword ptr [rbp+360h+var_300], rcx
0x18001e179  mov     qword ptr [rbp+360h+var_300+8], rax
0x18001e17d  mov     qword ptr [rbp+360h+var_2F0], rax
0x18001e181  mov     dword ptr [rbp+360h+var_2F0+8], ebx
0x18001e184  mov     dword ptr [rbp+360h+var_2F0+0Ch], 0FFFFFFFFh
0x18001e18b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001e18f  mov     dword ptr [rbp+360h+var_2E0], r14d
0x18001e196  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001e19d  lea     rcx, [rbp+360h+pExceptionObject]; pExceptionObject
0x18001e1a1  call    _CxxThrowException_0
0x18001e1a7  call    cs:__imp_GetCurrentThread
0x18001e1ae  nop     dword ptr [rax+rax+00h]
0x18001e1b3  mov     rcx, rax; ThreadHandle
0x18001e1b6  lea     r9, [rsp+460h+TokenHandle]; TokenHandle
0x18001e1bb  mov     edx, 8; DesiredAccess
0x18001e1c0  lea     r8d, [rdx-7]; OpenAsSelf
0x18001e1c4  call    cs:__imp_OpenThreadToken
0x18001e1cb  nop     dword ptr [rax+rax+00h]
0x18001e1d0  test    eax, eax
0x18001e1d2  jnz     short loc_18001E205
0x18001e1d4  call    cs:__imp_GetLastError
0x18001e1db  nop     dword ptr [rax+rax+00h]
0x18001e1e0  mov     ebx, eax
0x18001e1e2  test    eax, eax
0x18001e1e4  jle     short loc_18001E1EF
0x18001e1e6  movzx   ebx, ax
0x18001e1e9  or      ebx, 80070000h
0x18001e1ef  call    cs:__imp_RpcRevertToSelf
0x18001e1f6  nop     dword ptr [rax+rax+00h]
0x18001e1fb  test    ebx, ebx
0x18001e1fd  js      loc_18001E9EE
0x18001e203  jmp     short loc_18001E211
0x18001e205  call    cs:__imp_RpcRevertToSelf
0x18001e20c  nop     dword ptr [rax+rax+00h]
0x18001e211  lea     rbx, [rdi+10h]
0x18001e215  mov     [rbp+360h+var_358], rbx
0x18001e219  mov     rcx, rbx; SRWLock
0x18001e21c  call    cs:__imp_AcquireSRWLockShared
0x18001e223  nop     dword ptr [rax+rax+00h]
0x18001e228  nop
0x18001e229  mov     r8d, 1; DesiredAccess
0x18001e22f  lea     rdx, [rbp+360h+psz]; psz
0x18001e236  mov     rcx, [rsp+460h+TokenHandle]; ClientToken
0x18001e23b  call    ?TaskAccessCheck@@YAJPEAXPEBGK@Z; TaskAccessCheck(void *,ushort const *,ulong)
0x18001e240  mov     edi, eax
0x18001e242  test    eax, eax
0x18001e244  jns     short loc_18001E25C
0x18001e246  mov     rcx, rbx; SRWLock
0x18001e249  call    cs:__imp_ReleaseSRWLockShared
0x18001e250  nop     dword ptr [rax+rax+00h]
0x18001e255  mov     ebx, edi
0x18001e257  jmp     loc_18001E9EE
0x18001e25c  xor     edi, edi
0x18001e25e  mov     [r14], edi
0x18001e261  mov     [r12], rdi
0x18001e265  test    rsi, rsi
0x18001e268  jz      loc_18001E310
0x18001e26e  lea     r8d, [rdi+1]
0x18001e272  mov     eax, edi
0x18001e274  mov     qword ptr [rsp+460h+FileTime.dwLowDateTime+8], rax
0x18001e279  cmp     di, [rsi]
0x18001e27c  jz      short loc_18001E29A
0x18001e27e  lea     rdx, [rsp+460h+FileTime.dwLowDateTime+8]; lpFileTime
0x18001e283  mov     rcx, rsi; lpSystemTime
0x18001e286  call    cs:__imp_SystemTimeToFileTime
0x18001e28d  nop     dword ptr [rax+rax+00h]
0x18001e292  mov     r8d, eax
0x18001e295  mov     rax, qword ptr [rsp+460h+FileTime.dwLowDateTime+8]
0x18001e29a  mov     [rsp+460h+var_408], rax
0x18001e29f  test    r8d, r8d
0x18001e2a2  jnz     short loc_18001E2F8
0x18001e2a4  call    cs:__imp_GetLastError
0x18001e2ab  nop     dword ptr [rax+rax+00h]
0x18001e2b0  mov     byte ptr [rbp+360h+pExceptionObject+8], dil
0x18001e2b4  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001e2bb  mov     qword ptr [rbp+360h+pExceptionObject], rcx
0x18001e2bf  lea     rcx, qword_1800A8718
0x18001e2c6  mov     qword ptr [rbp+360h+var_300], rcx
0x18001e2ca  mov     qword ptr [rbp+360h+var_300+8], rdi
0x18001e2ce  mov     qword ptr [rbp+360h+var_2F0], rdi
0x18001e2d2  mov     dword ptr [rbp+360h+var_2F0+8], eax
0x18001e2d5  mov     dword ptr [rbp+360h+var_2F0+0Ch], 0FFFFFFFFh
0x18001e2dc  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001e2e0  mov     dword ptr [rbp+360h+var_2E0], r14d
0x18001e2e7  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001e2ee  lea     rcx, [rbp+360h+pExceptionObject]; pExceptionObject
0x18001e2f2  call    _CxxThrowException_0
0x18001e2f8  mov     cl, 1
0x18001e2fa  movsd   xmm0, qword ptr [rsp+460h+var_418+9]
0x18001e300  mov     eax, dword ptr [rsp+460h+var_408+1]
0x18001e304  movzx   edx, word ptr [rsp+460h+var_408+5]
0x18001e309  mov     r8b, byte ptr [rsp+460h+var_408+7]
0x18001e30e  jmp     short loc_18001E346
0x18001e310  mov     cl, dil
0x18001e313  mov     eax, dword ptr [rsp+460h+var_418+9]
0x18001e317  mov     [rsp+460h+FileTime.dwLowDateTime+9], eax
0x18001e31b  movzx   eax, word ptr [rsp+460h+var_418+0Dh]
0x18001e320  mov     word ptr [rsp+460h+FileTime.dwHighDateTime+9], ax
0x18001e325  mov     al, byte ptr [rsp+460h+var_418+0Fh]
0x18001e329  mov     byte ptr [rsp+460h+FileTime.dwHighDateTime+0Bh], al
0x18001e32d  mov     qword ptr [rsp+460h+var_418], rdi
0x18001e332  mov     r8b, byte ptr [rsp+460h+var_418+7]
0x18001e337  movzx   edx, word ptr [rsp+460h+var_418+5]
0x18001e33c  mov     eax, dword ptr [rsp+460h+var_418+1]
0x18001e340  movsd   xmm0, qword ptr [rsp+460h+FileTime.dwLowDateTime+9]
0x18001e346  mov     byte ptr [rbp+360h+var_3E0], cl
0x18001e349  movsd   qword ptr [rbp+360h+var_3E0+1], xmm0
0x18001e34e  mov     dword ptr [rbp+360h+var_3E0+9], eax
0x18001e351  mov     word ptr [rbp+360h+var_3E0+0Dh], dx
0x18001e355  mov     byte ptr [rbp+360h+var_3E0+0Fh], r8b
0x18001e359  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001e35d  test    r15, r15
0x18001e360  jz      loc_18001E406
0x18001e366  lea     r8d, [r14+2]
0x18001e36a  mov     rax, rdi
0x18001e36d  mov     qword ptr [rsp+460h+FileTime.dwLowDateTime+8], rax
0x18001e372  cmp     di, [r15]
0x18001e376  jz      short loc_18001E394
0x18001e378  lea     rdx, [rsp+460h+FileTime.dwLowDateTime+8]; lpFileTime
0x18001e37d  mov     rcx, r15; lpSystemTime
0x18001e380  call    cs:__imp_SystemTimeToFileTime
0x18001e387  nop     dword ptr [rax+rax+00h]
0x18001e38c  mov     r8d, eax
0x18001e38f  mov     rax, qword ptr [rsp+460h+FileTime.dwLowDateTime+8]
0x18001e394  mov     [rsp+460h+var_408], rax
0x18001e399  test    r8d, r8d
0x18001e39c  jnz     short loc_18001E3EE
0x18001e39e  call    cs:__imp_GetLastError
0x18001e3a5  nop     dword ptr [rax+rax+00h]
0x18001e3aa  mov     byte ptr [rbp+360h+pExceptionObject+8], dil
0x18001e3ae  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001e3b5  mov     qword ptr [rbp+360h+pExceptionObject], rcx
0x18001e3b9  lea     rcx, qword_1800A8718
0x18001e3c0  mov     qword ptr [rbp+360h+var_300], rcx
0x18001e3c4  mov     qword ptr [rbp+360h+var_300+8], rdi
0x18001e3c8  mov     qword ptr [rbp+360h+var_2F0], rdi
0x18001e3cc  mov     dword ptr [rbp+360h+var_2F0+8], eax
0x18001e3cf  mov     dword ptr [rbp+360h+var_2F0+0Ch], 0FFFFFFFFh
0x18001e3d6  mov     dword ptr [rbp+360h+var_2E0], r14d
0x18001e3dd  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001e3e4  lea     rcx, [rbp+360h+pExceptionObject]; pExceptionObject
0x18001e3e8  call    _CxxThrowException_0
0x18001e3ee  mov     cl, 1
0x18001e3f0  movsd   xmm0, qword ptr [rsp+460h+var_418+9]
0x18001e3f6  mov     eax, dword ptr [rsp+460h+var_408+1]
0x18001e3fa  movzx   edx, word ptr [rsp+460h+var_408+5]
0x18001e3ff  mov     r8b, byte ptr [rsp+460h+var_408+7]
0x18001e404  jmp     short loc_18001E43C
0x18001e406  mov     cl, dil
0x18001e409  mov     eax, dword ptr [rsp+460h+var_418+9]
0x18001e40d  mov     [rsp+460h+FileTime.dwLowDateTime+9], eax
0x18001e411  movzx   eax, word ptr [rsp+460h+var_418+0Dh]
0x18001e416  mov     word ptr [rsp+460h+FileTime.dwHighDateTime+9], ax
0x18001e41b  mov     al, byte ptr [rsp+460h+var_418+0Fh]
0x18001e41f  mov     byte ptr [rsp+460h+FileTime.dwHighDateTime+0Bh], al
0x18001e423  mov     qword ptr [rsp+460h+var_418], r14
0x18001e428  mov     r8b, byte ptr [rsp+460h+var_418+7]
0x18001e42d  movzx   edx, word ptr [rsp+460h+var_418+5]
0x18001e432  mov     eax, dword ptr [rsp+460h+var_418+1]
0x18001e436  movsd   xmm0, qword ptr [rsp+460h+FileTime.dwLowDateTime+9]
0x18001e43c  mov     byte ptr [rsp+460h+var_3F8+8], cl
0x18001e440  movsd   qword ptr [rsp+460h+var_3F8+9], xmm0
0x18001e446  mov     [rsp+460h+var_3E7], eax
0x18001e44a  mov     [rsp+460h+var_3E3], dx
0x18001e44f  mov     [rsp+460h+var_3E1], r8b
0x18001e454  mov     r12d, 0FDEh
0x18001e45a  test    r13d, r13d
0x18001e45d  cmovnz  r12d, r13d
0x18001e461  lea     r13, WPP_GLOBAL_Control
0x18001e468  mov     rax, cs:WPP_GLOBAL_Control
0x18001e46f  cmp     rax, r13
0x18001e472  jz      loc_18001E58E
0x18001e478  mov     esi, 200h
0x18001e47d  test    [rax+1Ch], esi
0x18001e480  jz      loc_18001E58E
0x18001e486  movups  xmm0, xmmword ptr cs:aFirsttime; "::FirstTime"
0x18001e48d  movups  [rbp+360h+pExceptionObject], xmm0
0x18001e491  movsd   xmm1, qword ptr cs:aFirsttime+10h; "ime"
0x18001e499  movsd   qword ptr [rbp+360h+var_300], xmm1
0x18001e49e  xorps   xmm0, xmm0
0x18001e4a1  xor     eax, eax
0x18001e4a3  movups  [rbp+360h+var_300+8], xmm0
0x18001e4a7  movups  [rbp+360h+var_2F0+4], xmm0
0x18001e4ab  movups  xmm0, xmmword ptr cs:aLasttime; "::LastTime"
0x18001e4b2  movups  xmmword ptr [rbp+360h+var_2B0], xmm0
0x18001e4b9  movsd   xmm1, qword ptr cs:aLasttime+0Eh; "ime"
0x18001e4c1  movsd   qword ptr [rbp+360h+var_2B0+0Eh], xmm1
0x18001e4c9  xorps   xmm0, xmm0
0x18001e4cc  movups  xmmword ptr [rbp+360h+var_29A], xmm0
0x18001e4d3  movups  xmmword ptr [rbp+360h+var_29A+0Eh], xmm0
0x18001e4da  mov     byte ptr [rsp+460h+var_418+8], dil
0x18001e4df  mov     [rsp+460h+var_408], rdi
0x18001e4e4  lea     rdx, [rsp+460h+var_418+8]
0x18001e4e9  lea     rcx, [rbp+360h+var_3E0]
0x18001e4ed  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x18001e4f2  mov     r15d, 1Ah
0x18001e4f8  test    al, al
0x18001e4fa  jz      short loc_18001E50C
0x18001e4fc  mov     r8d, r15d; int
0x18001e4ff  lea     rdx, [rbp+360h+pExceptionObject]; unsigned __int16 *
0x18001e503  lea     rcx, [rbp+360h+var_3E0]; this
0x18001e507  call    ?ToString@TSTime@@QEBAXPEAGH@Z; TSTime::ToString(ushort *,int)
0x18001e50c  mov     byte ptr [rsp+460h+var_418+8], dil
0x18001e511  mov     [rsp+460h+var_408], r14
0x18001e516  lea     rdx, [rsp+460h+var_418+8]
0x18001e51b  lea     rcx, [rsp+460h+var_3F8+8]
0x18001e520  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x18001e525  test    al, al
0x18001e527  jz      short loc_18001E53D
0x18001e529  mov     r8d, r15d; int
0x18001e52c  lea     rdx, [rbp+360h+var_2B0]; unsigned __int16 *
0x18001e533  lea     rcx, [rsp+460h+var_3F8+8]; this
0x18001e538  call    ?ToString@TSTime@@QEBAXPEAGH@Z; TSTime::ToString(ushort *,int)
0x18001e53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e544  cmp     rcx, r13
0x18001e547  jz      short loc_18001E58E
0x18001e549  test    [rcx+1Ch], esi
0x18001e54c  jz      short loc_18001E58E
0x18001e54e  cmp     byte ptr [rcx+19h], 4
0x18001e552  jb      short loc_18001E58E
0x18001e554  mov     edx, 4Ah ; 'J'
0x18001e559  mov     [rsp+460h+FileTime.dwLowDateTime], r12d
0x18001e55e  mov     [rsp+460h+var_430], edi
0x18001e562  lea     rax, [rbp+360h+var_2B0]
0x18001e569  mov     [rsp+460h+var_438], rax
0x18001e56e  lea     rax, [rbp+360h+pExceptionObject]
0x18001e572  mov     [rsp+460h+var_440], rax
0x18001e577  lea     r9, [rbp+360h+psz]
0x18001e57e  lea     r8, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids
0x18001e585  mov     rcx, [rcx+10h]
0x18001e589  call    WPP_SF_SSSDd
0x18001e58e  lea     rcx, [rbp+360h+var_390]; this
0x18001e592  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x18001e597  nop
0x18001e598  xor     r8d, r8d; unsigned __int16 *
0x18001e59b  lea     rdx, [rbp+360h+psz]; psz
0x18001e5a2  lea     rcx, [rbp+360h+iid]; lpiid
0x18001e5a6  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18001e5ab  nop
0x18001e5ac  lea     rcx, [rbp+360h+iid]; this
  ... truncated ...
```
