# RpcServer::Runtimes(ushort const *,_SYSTEMTIME *,_SYSTEMTIME *,ulong,ulong,ulong *,_SYSTEMTIME * *)

- ea: `0x180021ca0`
- end: `0x1800225f1`
- name: `?Runtimes@RpcServer@@QEAAJPEBGPEAU_SYSTEMTIME@@1KKPEAKPEAPEAU2@@Z`
- size: `2385`
- prototype: `int(RpcServer *__hidden this, const unsigned __int16 *, struct _SYSTEMTIME *, struct _SYSTEMTIME *, unsigned int, unsigned int, unsigned int *, struct _SYSTEMTIME **)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ad40`

## callees

- `0x180007ec0`
- `0x18000e4c0`
- `0x18000e510`
- `0x1800150b0`
- `0x180016c00`
- `0x1800199c0`
- `0x18001a260`
- `0x18001a430`
- `0x180020854`
- `0x180021300`
- `0x180021ca0`
- `0x180022600`
- `0x1800230c0`
- `0x1800244ac`
- `0x180025310`
- `0x180030f80`
- `0x180031d90`
- `0x1800322a0`
- `0x180035570`
- `0x180039b6c`
- `0x180039d00`
- `0x18003adf0`
- `0x18003f600`
- `0x1800503d0`
- `0x180050454`
- `0x18005790c`
- `0x180069c74`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f90`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180021e8a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180021f78`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180021e8a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180021f78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800221d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800224a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800221d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800224a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021e2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021e2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021e53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800221c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002226d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002248b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022573`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002259f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021e53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800221c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002226d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002248b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022573`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002259f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022282`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021dd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021dd5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021dec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021dec`
- `RPCRT4!RpcImpersonateClient` at `0x180021d6a`
- `RPCRT4!RpcImpersonateClient` at `0x180021d6a`
- `RPCRT4!RpcRevertToSelf` at `0x180021e0b`
- `RPCRT4!RpcRevertToSelf` at `0x180021e1b`
- `RPCRT4!RpcRevertToSelf` at `0x180021e0b`
- `RPCRT4!RpcRevertToSelf` at `0x180021e1b`

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
    *(_QWORD *)v88 = &qword_1800A4718;
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
      *(_QWORD *)v88 = &qword_1800A4718;
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
      *(_QWORD *)v88 = &qword_1800A4718;
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
0x180021ca0  mov     rax, rsp
0x180021ca3  mov     [rax+8], rbx
0x180021ca7  push    rbp
0x180021ca8  push    rsi
0x180021ca9  push    rdi
0x180021caa  push    r12
0x180021cac  push    r13
0x180021cae  push    r14
0x180021cb0  push    r15
0x180021cb2  lea     rbp, [rax-368h]
0x180021cb9  sub     rsp, 430h
0x180021cc0  movaps  xmmword ptr [rax-48h], xmm6
0x180021cc4  movaps  xmmword ptr [rax-58h], xmm7
0x180021cc8  mov     rax, cs:__security_cookie
0x180021ccf  xor     rax, rsp
0x180021cd2  mov     [rbp+360h+var_60], rax
0x180021cd9  mov     r15, r9
0x180021cdc  mov     rsi, r8
0x180021cdf  mov     rbx, rdx
0x180021ce2  mov     rdi, rcx
0x180021ce5  mov     r13d, [rbp+360h+arg_28]
0x180021cec  mov     r14, [rbp+360h+arg_30]
0x180021cf3  mov     qword ptr [rsp+460h+var_3F8], r14
0x180021cf8  mov     r12, [rbp+360h+arg_38]
0x180021cff  mov     [rbp+360h+var_398], r12
0x180021d03  test    rdx, rdx
0x180021d06  jz      loc_1800225B8
0x180021d0c  cmp     [rbp+360h+arg_20], 0
0x180021d13  jnz     loc_1800225B8
0x180021d19  test    r14, r14
0x180021d1c  jz      loc_1800225B8
0x180021d22  test    r12, r12
0x180021d25  jz      loc_1800225B8
0x180021d2b  xor     eax, eax
0x180021d2d  mov     [rbp+360h+psz], ax
0x180021d34  xor     edx, edx; Val
0x180021d36  mov     r8d, 208h; Size
0x180021d3c  lea     rcx, [rbp+360h+var_26E]; void *
0x180021d43  call    memset_0
0x180021d48  mov     rdx, rbx; unsigned __int16 *
0x180021d4b  lea     rcx, [rbp+360h+psz]; this
0x180021d52  call    ?TaskPathCanonicalize@tsched@@YAJPEAGPEBG@Z; tsched::TaskPathCanonicalize(ushort *,ushort const *)
0x180021d57  test    eax, eax
0x180021d59  js      loc_1800225BD
0x180021d5f  mov     [rsp+460h+TokenHandle], 0
0x180021d68  xor     ecx, ecx; BindingHandle
0x180021d6a  call    cs:__imp_RpcImpersonateClient
0x180021d70  mov     ebx, eax
0x180021d72  test    eax, eax
0x180021d74  jz      short loc_180021DD5
0x180021d76  mov     r9d, eax; unsigned int
0x180021d79  lea     r8, aRuntimes; "Runtimes"
0x180021d80  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180021d87  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180021d8c  xor     eax, eax
0x180021d8e  mov     byte ptr [rbp+360h+pExceptionObject+8], al
0x180021d91  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180021d98  mov     qword ptr [rbp+360h+pExceptionObject], rcx
0x180021d9c  lea     rcx, qword_1800A4718
0x180021da3  mov     qword ptr [rbp+360h+var_300], rcx
0x180021da7  mov     qword ptr [rbp+360h+var_300+8], rax
0x180021dab  mov     qword ptr [rbp+360h+var_2F0], rax
0x180021daf  mov     dword ptr [rbp+360h+var_2F0+8], ebx
0x180021db2  mov     dword ptr [rbp+360h+var_2F0+0Ch], 0FFFFFFFFh
0x180021db9  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021dbd  mov     dword ptr [rbp+360h+var_2E0], r14d
0x180021dc4  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180021dcb  lea     rcx, [rbp+360h+pExceptionObject]; pExceptionObject
0x180021dcf  call    _CxxThrowException_0
0x180021dd5  call    cs:__imp_GetCurrentThread
0x180021ddb  mov     rcx, rax; ThreadHandle
0x180021dde  lea     r9, [rsp+460h+TokenHandle]; TokenHandle
0x180021de3  mov     edx, 8; DesiredAccess
0x180021de8  lea     r8d, [rdx-7]; OpenAsSelf
0x180021dec  call    cs:__imp_OpenThreadToken
0x180021df2  test    eax, eax
0x180021df4  jnz     short loc_180021E1B
0x180021df6  call    cs:__imp_GetLastError
0x180021dfc  mov     ebx, eax
0x180021dfe  test    eax, eax
0x180021e00  jle     short loc_180021E0B
0x180021e02  movzx   ebx, ax
0x180021e05  or      ebx, 80070000h
0x180021e0b  call    cs:__imp_RpcRevertToSelf
0x180021e11  test    ebx, ebx
0x180021e13  js      loc_1800225AA
0x180021e19  jmp     short loc_180021E21
0x180021e1b  call    cs:__imp_RpcRevertToSelf
0x180021e21  lea     rbx, [rdi+10h]
0x180021e25  mov     [rbp+360h+var_358], rbx
0x180021e29  mov     rcx, rbx; SRWLock
0x180021e2c  call    cs:__imp_AcquireSRWLockShared
0x180021e32  nop
0x180021e33  mov     r8d, 1; DesiredAccess
0x180021e39  lea     rdx, [rbp+360h+psz]; psz
0x180021e40  mov     rcx, [rsp+460h+TokenHandle]; ClientToken
0x180021e45  call    ?TaskAccessCheck@@YAJPEAXPEBGK@Z; TaskAccessCheck(void *,ushort const *,ulong)
0x180021e4a  mov     edi, eax
0x180021e4c  test    eax, eax
0x180021e4e  jns     short loc_180021E60
0x180021e50  mov     rcx, rbx; SRWLock
0x180021e53  call    cs:__imp_ReleaseSRWLockShared
0x180021e59  mov     ebx, edi
0x180021e5b  jmp     loc_1800225AA
0x180021e60  xor     edi, edi
0x180021e62  mov     [r14], edi
0x180021e65  mov     [r12], rdi
0x180021e69  test    rsi, rsi
0x180021e6c  jz      loc_180021F08
0x180021e72  lea     r8d, [rdi+1]
0x180021e76  mov     eax, edi
0x180021e78  mov     qword ptr [rsp+460h+FileTime.dwLowDateTime+8], rax
0x180021e7d  cmp     di, [rsi]
0x180021e80  jz      short loc_180021E98
0x180021e82  lea     rdx, [rsp+460h+FileTime.dwLowDateTime+8]; lpFileTime
0x180021e87  mov     rcx, rsi; lpSystemTime
0x180021e8a  call    cs:__imp_SystemTimeToFileTime
0x180021e90  mov     r8d, eax
0x180021e93  mov     rax, qword ptr [rsp+460h+FileTime.dwLowDateTime+8]
0x180021e98  mov     [rsp+460h+var_408], rax
0x180021e9d  test    r8d, r8d
0x180021ea0  jnz     short loc_180021EF0
0x180021ea2  call    cs:__imp_GetLastError
0x180021ea8  mov     byte ptr [rbp+360h+pExceptionObject+8], dil
0x180021eac  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180021eb3  mov     qword ptr [rbp+360h+pExceptionObject], rcx
0x180021eb7  lea     rcx, qword_1800A4718
0x180021ebe  mov     qword ptr [rbp+360h+var_300], rcx
0x180021ec2  mov     qword ptr [rbp+360h+var_300+8], rdi
0x180021ec6  mov     qword ptr [rbp+360h+var_2F0], rdi
0x180021eca  mov     dword ptr [rbp+360h+var_2F0+8], eax
0x180021ecd  mov     dword ptr [rbp+360h+var_2F0+0Ch], 0FFFFFFFFh
0x180021ed4  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021ed8  mov     dword ptr [rbp+360h+var_2E0], r14d
0x180021edf  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180021ee6  lea     rcx, [rbp+360h+pExceptionObject]; pExceptionObject
0x180021eea  call    _CxxThrowException_0
0x180021ef0  mov     cl, 1
0x180021ef2  movsd   xmm0, qword ptr [rsp+460h+var_418+9]
0x180021ef8  mov     eax, dword ptr [rsp+460h+var_408+1]
0x180021efc  movzx   edx, word ptr [rsp+460h+var_408+5]
0x180021f01  mov     r8b, byte ptr [rsp+460h+var_408+7]
0x180021f06  jmp     short loc_180021F3E
0x180021f08  mov     cl, dil
0x180021f0b  mov     eax, dword ptr [rsp+460h+var_418+9]
0x180021f0f  mov     [rsp+460h+FileTime.dwLowDateTime+9], eax
0x180021f13  movzx   eax, word ptr [rsp+460h+var_418+0Dh]
0x180021f18  mov     word ptr [rsp+460h+FileTime.dwHighDateTime+9], ax
0x180021f1d  mov     al, byte ptr [rsp+460h+var_418+0Fh]
0x180021f21  mov     byte ptr [rsp+460h+FileTime.dwHighDateTime+0Bh], al
0x180021f25  mov     qword ptr [rsp+460h+var_418], rdi
0x180021f2a  mov     r8b, byte ptr [rsp+460h+var_418+7]
0x180021f2f  movzx   edx, word ptr [rsp+460h+var_418+5]
0x180021f34  mov     eax, dword ptr [rsp+460h+var_418+1]
0x180021f38  movsd   xmm0, qword ptr [rsp+460h+FileTime.dwLowDateTime+9]
0x180021f3e  mov     byte ptr [rbp+360h+var_3E0], cl
0x180021f41  movsd   qword ptr [rbp+360h+var_3E0+1], xmm0
0x180021f46  mov     dword ptr [rbp+360h+var_3E0+9], eax
0x180021f49  mov     word ptr [rbp+360h+var_3E0+0Dh], dx
0x180021f4d  mov     byte ptr [rbp+360h+var_3E0+0Fh], r8b
0x180021f51  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021f55  test    r15, r15
0x180021f58  jz      loc_180021FF2
0x180021f5e  lea     r8d, [r14+2]
0x180021f62  mov     rax, rdi
0x180021f65  mov     qword ptr [rsp+460h+FileTime.dwLowDateTime+8], rax
0x180021f6a  cmp     di, [r15]
0x180021f6e  jz      short loc_180021F86
0x180021f70  lea     rdx, [rsp+460h+FileTime.dwLowDateTime+8]; lpFileTime
0x180021f75  mov     rcx, r15; lpSystemTime
0x180021f78  call    cs:__imp_SystemTimeToFileTime
0x180021f7e  mov     r8d, eax
0x180021f81  mov     rax, qword ptr [rsp+460h+FileTime.dwLowDateTime+8]
0x180021f86  mov     [rsp+460h+var_408], rax
0x180021f8b  test    r8d, r8d
0x180021f8e  jnz     short loc_180021FDA
0x180021f90  call    cs:__imp_GetLastError
0x180021f96  mov     byte ptr [rbp+360h+pExceptionObject+8], dil
0x180021f9a  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180021fa1  mov     qword ptr [rbp+360h+pExceptionObject], rcx
0x180021fa5  lea     rcx, qword_1800A4718
0x180021fac  mov     qword ptr [rbp+360h+var_300], rcx
0x180021fb0  mov     qword ptr [rbp+360h+var_300+8], rdi
0x180021fb4  mov     qword ptr [rbp+360h+var_2F0], rdi
0x180021fb8  mov     dword ptr [rbp+360h+var_2F0+8], eax
0x180021fbb  mov     dword ptr [rbp+360h+var_2F0+0Ch], 0FFFFFFFFh
0x180021fc2  mov     dword ptr [rbp+360h+var_2E0], r14d
0x180021fc9  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180021fd0  lea     rcx, [rbp+360h+pExceptionObject]; pExceptionObject
0x180021fd4  call    _CxxThrowException_0
0x180021fda  mov     cl, 1
0x180021fdc  movsd   xmm0, qword ptr [rsp+460h+var_418+9]
0x180021fe2  mov     eax, dword ptr [rsp+460h+var_408+1]
0x180021fe6  movzx   edx, word ptr [rsp+460h+var_408+5]
0x180021feb  mov     r8b, byte ptr [rsp+460h+var_408+7]
0x180021ff0  jmp     short loc_180022028
0x180021ff2  mov     cl, dil
0x180021ff5  mov     eax, dword ptr [rsp+460h+var_418+9]
0x180021ff9  mov     [rsp+460h+FileTime.dwLowDateTime+9], eax
0x180021ffd  movzx   eax, word ptr [rsp+460h+var_418+0Dh]
0x180022002  mov     word ptr [rsp+460h+FileTime.dwHighDateTime+9], ax
0x180022007  mov     al, byte ptr [rsp+460h+var_418+0Fh]
0x18002200b  mov     byte ptr [rsp+460h+FileTime.dwHighDateTime+0Bh], al
0x18002200f  mov     qword ptr [rsp+460h+var_418], r14
0x180022014  mov     r8b, byte ptr [rsp+460h+var_418+7]
0x180022019  movzx   edx, word ptr [rsp+460h+var_418+5]
0x18002201e  mov     eax, dword ptr [rsp+460h+var_418+1]
0x180022022  movsd   xmm0, qword ptr [rsp+460h+FileTime.dwLowDateTime+9]
0x180022028  mov     byte ptr [rsp+460h+var_3F8+8], cl
0x18002202c  movsd   qword ptr [rsp+460h+var_3F8+9], xmm0
0x180022032  mov     [rsp+460h+var_3E7], eax
0x180022036  mov     [rsp+460h+var_3E3], dx
0x18002203b  mov     [rsp+460h+var_3E1], r8b
0x180022040  mov     r12d, 0FDEh
0x180022046  test    r13d, r13d
0x180022049  cmovnz  r12d, r13d
0x18002204d  lea     r13, WPP_GLOBAL_Control
0x180022054  mov     rax, cs:WPP_GLOBAL_Control
0x18002205b  cmp     rax, r13
0x18002205e  jz      loc_18002217A
0x180022064  mov     esi, 200h
0x180022069  test    [rax+1Ch], esi
0x18002206c  jz      loc_18002217A
0x180022072  movups  xmm0, xmmword ptr cs:aFirsttime; "::FirstTime"
0x180022079  movups  [rbp+360h+pExceptionObject], xmm0
0x18002207d  movsd   xmm1, qword ptr cs:aFirsttime+10h; "ime"
0x180022085  movsd   qword ptr [rbp+360h+var_300], xmm1
0x18002208a  xorps   xmm0, xmm0
0x18002208d  xor     eax, eax
0x18002208f  movups  [rbp+360h+var_300+8], xmm0
0x180022093  movups  [rbp+360h+var_2F0+4], xmm0
0x180022097  movups  xmm0, xmmword ptr cs:aLasttime; "::LastTime"
0x18002209e  movups  xmmword ptr [rbp+360h+var_2B0], xmm0
0x1800220a5  movsd   xmm1, qword ptr cs:aLasttime+0Eh; "ime"
0x1800220ad  movsd   qword ptr [rbp+360h+var_2B0+0Eh], xmm1
0x1800220b5  xorps   xmm0, xmm0
0x1800220b8  movups  xmmword ptr [rbp+360h+var_29A], xmm0
0x1800220bf  movups  xmmword ptr [rbp+360h+var_29A+0Eh], xmm0
0x1800220c6  mov     byte ptr [rsp+460h+var_418+8], dil
0x1800220cb  mov     [rsp+460h+var_408], rdi
0x1800220d0  lea     rdx, [rsp+460h+var_418+8]
0x1800220d5  lea     rcx, [rbp+360h+var_3E0]
0x1800220d9  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x1800220de  mov     r15d, 1Ah
0x1800220e4  test    al, al
0x1800220e6  jz      short loc_1800220F8
0x1800220e8  mov     r8d, r15d; int
0x1800220eb  lea     rdx, [rbp+360h+pExceptionObject]; unsigned __int16 *
0x1800220ef  lea     rcx, [rbp+360h+var_3E0]; this
0x1800220f3  call    ?ToString@TSTime@@QEBAXPEAGH@Z; TSTime::ToString(ushort *,int)
0x1800220f8  mov     byte ptr [rsp+460h+var_418+8], dil
0x1800220fd  mov     [rsp+460h+var_408], r14
0x180022102  lea     rdx, [rsp+460h+var_418+8]
0x180022107  lea     rcx, [rsp+460h+var_3F8+8]
0x18002210c  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x180022111  test    al, al
0x180022113  jz      short loc_180022129
0x180022115  mov     r8d, r15d; int
0x180022118  lea     rdx, [rbp+360h+var_2B0]; unsigned __int16 *
0x18002211f  lea     rcx, [rsp+460h+var_3F8+8]; this
0x180022124  call    ?ToString@TSTime@@QEBAXPEAGH@Z; TSTime::ToString(ushort *,int)
0x180022129  mov     rcx, cs:WPP_GLOBAL_Control
0x180022130  cmp     rcx, r13
0x180022133  jz      short loc_18002217A
0x180022135  test    [rcx+1Ch], esi
0x180022138  jz      short loc_18002217A
0x18002213a  cmp     byte ptr [rcx+19h], 4
0x18002213e  jb      short loc_18002217A
0x180022140  mov     edx, 4Ah ; 'J'
0x180022145  mov     [rsp+460h+FileTime.dwLowDateTime], r12d
0x18002214a  mov     [rsp+460h+var_430], edi
0x18002214e  lea     rax, [rbp+360h+var_2B0]
0x180022155  mov     [rsp+460h+var_438], rax
0x18002215a  lea     rax, [rbp+360h+pExceptionObject]
0x18002215e  mov     [rsp+460h+var_440], rax
0x180022163  lea     r9, [rbp+360h+psz]
0x18002216a  lea     r8, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids
0x180022171  mov     rcx, [rcx+10h]
0x180022175  call    WPP_SF_SSSDd
0x18002217a  lea     rcx, [rbp+360h+var_390]; this
0x18002217e  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180022183  nop
0x180022184  xor     r8d, r8d; unsigned __int16 *
0x180022187  lea     rdx, [rbp+360h+psz]; psz
0x18002218e  lea     rcx, [rbp+360h+iid]; lpiid
0x180022192  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x180022197  nop
0x180022198  lea     rcx, [rbp+360h+iid]; this
0x18002219c  call    ?SetExistingId@JobMoniker@@QEAAJXZ; JobMoniker::SetExistingId(void)
0x1800221a1  mov     edi, eax
0x1800221a3  xor     r13d, r13d
0x1800221a6  test    eax, eax
0x1800221a8  jns     short loc_1800221E4
0x1800221aa  lea     rcx, [rbp+360h+iid]; this
0x1800221ae  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x1800221b3  nop
0x1800221b4  lea     rcx, [rbp+360h+var_390]; this
0x1800221b8  call    ??1Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::~Trigulator(void)
0x1800221bd  nop
0x1800221be  mov     rcx, rbx; SRWLock
  ... truncated ...
```
