# RpcServer::GetState(ushort const *,tsched::InternalTaskState *,int *)

- ea: `0x18000b5a0`
- end: `0x18000c3ab`
- name: `?GetState@RpcServer@@AEAAJPEBGPEAW4InternalTaskState@tsched@@PEAH@Z`
- size: `3595`
- prototype: `__int64 __fastcall(RpcServer *__hidden this, const unsigned __int16 *, enum tsched::InternalTaskState *, int *)`
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003fde0`

## callees

- `0x180007ddc`
- `0x180007ec0`
- `0x1800086c0`
- `0x18000b438`
- `0x18000b5a0`
- `0x18000dc30`
- `0x18000e468`
- `0x18000e4c0`
- `0x18000e510`
- `0x18000f630`
- `0x1800199c0`
- `0x18001a430`
- `0x18001ec90`
- `0x180022600`
- `0x1800230c0`
- `0x1800244ac`
- `0x180030f80`
- `0x1800322a0`
- `0x180038830`
- `0x180039b6c`
- `0x180039d00`
- `0x180045bb0`
- `0x18004ae48`
- `0x1800504b4`
- `0x180052118`
- `0x180053e54`
- `0x180056794`
- `0x18005790c`
- `0x180057926`
- `0x180066d5c`
- `0x180066e58`
- `0x18006e43c`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000ba24`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bc8b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bcdb`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bd24`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ba24`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bc8b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bcdb`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bd24`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ba17`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb42`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ba17`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb42`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bd8c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bda2`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bd8c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bda2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000bdcb`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000bdcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c26b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c26b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c372`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b8e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b8e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b951`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c248`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b951`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c248`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ba82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ba82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000babf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000babf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c1fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c20a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c1fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c20a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bbb2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bbb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b86f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b86f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b888`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b888`
- `RPCRT4!RpcImpersonateClient` at `0x18000b7ae`
- `RPCRT4!RpcImpersonateClient` at `0x18000b7ae`
- `RPCRT4!RpcRevertToSelf` at `0x18000b8a7`
- `RPCRT4!RpcRevertToSelf` at `0x18000b8c2`
- `RPCRT4!RpcRevertToSelf` at `0x18000b8a7`
- `RPCRT4!RpcRevertToSelf` at `0x18000b8c2`

## string_xrefs

- `0x18000bcd4`: `NT TASK`
- `0x18000bc84`: `NT TASK\`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall RpcServer::GetState(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        enum tsched::InternalTaskState *a3,
        int *a4)
{
  enum tsched::InternalTaskState *v4; // r12
  const unsigned __int16 *v5; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  const OLECHAR *v10; // rax
  __int64 v11; // r11
  OLECHAR *v12; // r10
  OLECHAR v13; // cx
  unsigned __int16 v15; // r11
  int i; // ecx
  int v17; // r10d
  bool v18; // zf
  __int64 v19; // r9
  OLECHAR *v20; // rax
  unsigned int v21; // ecx
  __int64 v22; // r8
  OLECHAR *v23; // r9
  unsigned __int16 v24; // ax
  OLECHAR *v25; // rax
  RPC_STATUS v26; // eax
  EventManager *v27; // rcx
  RPC_STATUS v28; // ebx
  const OLECHAR *v29; // rax
  OLECHAR *v30; // r9
  OLECHAR v31; // r10
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v34; // ebx
  RTL_SRWLOCK *v35; // rdi
  int v36; // ebx
  JobStore *v37; // r13
  HKEY v38; // r15
  __int64 v39; // rcx
  int TreeInfo; // ebx
  BSTR v41; // rbx
  int v42; // r14d
  char v43; // r8
  __int64 v44; // rax
  LSTATUS v45; // eax
  LSTATUS v46; // eax
  int v47; // r8d
  JobBucket *v48; // rax
  JobBucket *v49; // rax
  JobBucket *v50; // rbx
  JobBucket *v51; // rcx
  BSTR *v52; // rax
  BSTR *v53; // rbx
  BSTR v54; // rax
  struct IErrorInfo *v55; // rdx
  BSTR *v56; // rax
  BSTR v57; // rax
  struct IErrorInfo *v58; // rdx
  BSTR *v59; // rax
  struct IErrorInfo *v60; // rdx
  BSTR *v61; // rbx
  BSTR v62; // rax
  HKEY v63; // rax
  struct IErrorInfo *v64; // rdx
  _QWORD *v65; // r15
  UINT v66; // r13d
  UINT v67; // eax
  UINT v68; // r12d
  struct IErrorInfo *v69; // rdx
  BSTR v70; // rcx
  __int16 *v71; // rcx
  __int16 j; // ax
  JobBucket *v73; // rbx
  JobBucket *v74; // rcx
  JobBucket *v75; // rcx
  __int64 v76; // rcx
  int v77; // r13d
  __int64 v78; // rdx
  __int64 v79; // r8
  volatile signed __int32 *v80; // rbx
  JobBucket *v81; // rbx
  JobBucket *v82; // rcx
  __int64 v83; // rcx
  int v84; // eax
  void (__fastcall ***v85)(_QWORD, __int64); // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  const struct _GUID *lpcbData; // [rsp+28h] [rbp-D8h]
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v89; // [rsp+34h] [rbp-CCh]
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  enum tsched::InternalTaskState *v94; // [rsp+58h] [rbp-A8h]
  BSTR *v95; // [rsp+60h] [rbp-A0h]
  HKEY v96; // [rsp+68h] [rbp-98h] BYREF
  HKEY v97; // [rsp+70h] [rbp-90h] BYREF
  GUID pExceptionObject; // [rsp+78h] [rbp-88h] BYREF
  __int128 v99; // [rsp+88h] [rbp-78h]
  JobBucket *v100; // [rsp+98h] [rbp-68h] BYREF
  __int128 v101; // [rsp+A0h] [rbp-60h] BYREF
  void **v102; // [rsp+B0h] [rbp-50h] BYREF
  char v103; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v104; // [rsp+C0h] [rbp-40h]
  __int64 v105; // [rsp+C8h] [rbp-38h]
  __int64 v106; // [rsp+D0h] [rbp-30h] BYREF
  int v107; // [rsp+D8h] [rbp-28h]
  _BYTE v108[12]; // [rsp+DCh] [rbp-24h]
  JobStore *v109; // [rsp+E8h] [rbp-18h]
  int *v110; // [rsp+F0h] [rbp-10h]
  _QWORD v111[4]; // [rsp+F8h] [rbp-8h] BYREF
  GUID v112; // [rsp+118h] [rbp+18h] BYREF
  __int128 v113; // [rsp+128h] [rbp+28h] BYREF
  JobBucket *v114; // [rsp+138h] [rbp+38h] BYREF
  __int64 v115; // [rsp+140h] [rbp+40h]
  __int64 v116; // [rsp+148h] [rbp+48h]
  GUID v117; // [rsp+150h] [rbp+50h] BYREF
  __int128 v118; // [rsp+160h] [rbp+60h] BYREF
  JobBucket *v119; // [rsp+170h] [rbp+70h] BYREF
  GUID iid; // [rsp+178h] [rbp+78h] BYREF
  char v121[8]; // [rsp+188h] [rbp+88h] BYREF
  __int64 v122; // [rsp+190h] [rbp+90h]
  __int64 v123; // [rsp+198h] [rbp+98h] BYREF
  struct _GUID v124; // [rsp+1A0h] [rbp+A0h] BYREF
  OLECHAR psz[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  v110 = a4;
  v4 = a3;
  v94 = a3;
  v5 = a2;
  if ( !a2 )
    return 2147942487LL;
  memset_0(psz, 0, 0x20Au);
  v7 = 2147483646;
  v8 = 261;
  if ( !*v5 )
  {
    v29 = L"\\";
    v30 = psz;
    v21 = 0;
    do
    {
      if ( !v7 )
        goto LABEL_52;
      v31 = *v29;
      if ( !*v29 )
        goto LABEL_52;
      ++v29;
      *v30++ = v31;
      --v7;
      --v8;
    }
    while ( v8 );
    --v30;
    v21 = -2147024774;
LABEL_52:
    *v30 = 0;
    if ( (v21 & 0x80000000) == 0 )
      goto LABEL_42;
    return v21;
  }
  if ( *v5 != 92 )
  {
    v9 = 2147483646;
    v10 = L"\\";
    v11 = 261;
    v12 = psz;
    while ( v9 )
    {
      v13 = *v10;
      if ( !*v10 )
        break;
      ++v10;
      *v12++ = v13;
      --v9;
      if ( !--v11 )
        return 2147942522LL;
    }
    *v12 = 0;
  }
  v15 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 261 )
      return 2147942523LL;
    v17 = v5[i];
    if ( !(_WORD)v17 )
      break;
    if ( v17 == 92 )
    {
      v18 = v15 == 92;
      goto LABEL_25;
    }
    if ( v17 == 32 )
    {
      if ( v15 == 92 )
        return 2147942523LL;
      v18 = v15 == 0;
LABEL_25:
      if ( v18 )
        return 2147942523LL;
      goto LABEL_26;
    }
    if ( v17 != 46 )
    {
      if ( v17 == 47 )
        return 2147942523LL;
      v18 = v17 == 58;
      goto LABEL_25;
    }
    if ( v15 == 46 || v15 == 92 && v5[i + 1] == 92 )
      return 2147942523LL;
LABEL_26:
    v15 = v5[i];
  }
  if ( v15 == 92 && i > 1 )
    return 2147942523LL;
  v19 = 261;
  v20 = psz;
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v19;
  }
  while ( v19 );
  v21 = -2147024809;
  if ( !v19 )
    return v21;
  v22 = v19;
  v23 = &psz[261 - v19];
  do
  {
    if ( !v7 )
      break;
    v24 = *v5;
    if ( !*v5 )
      break;
    ++v5;
    *v23++ = v24;
    --v7;
    --v22;
  }
  while ( v22 );
  v21 = -2147024774;
  if ( v22 )
    v21 = 0;
  v25 = v23 - 1;
  if ( v22 )
    v25 = v23;
  *v25 = 0;
  if ( !v22 )
    return v21;
LABEL_42:
  if ( !psz[0] || !psz[1] && psz[0] == 92 )
    return 2147942487LL;
  TokenHandle = 0;
  v26 = RpcImpersonateClient(0);
  v28 = v26;
  if ( v26 )
  {
    EventManager::EvtReport(v27, &IMPERSONATION_FAILURE, L"GetState", v26, phkResult, lpcbData);
    pExceptionObject.Data4[0] = 0;
    *(_QWORD *)&pExceptionObject.Data1 = &wmi::GenericException::`vftable';
    *(_QWORD *)&v99 = &qword_1800A4718;
    *((_QWORD *)&v99 + 1) = 0;
    v100 = 0;
    LODWORD(v101) = v28;
    *(_QWORD *)((char *)&v101 + 4) = -1;
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
    v34 = LastError;
    if ( LastError > 0 )
      v34 = (unsigned __int16)LastError | 0x80070000;
    RpcRevertToSelf();
    if ( v34 < 0 )
    {
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      return (unsigned int)v34;
    }
  }
  JobMoniker::JobMoniker(&iid, psz, 0);
  v35 = this + 2;
  v111[3] = this + 2;
  AcquireSRWLockShared(this + 2);
  v36 = TaskAccessCheck(TokenHandle, psz, 1u);
  if ( v36 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (unsigned int)psz,
        v36);
    }
    ReleaseSRWLockShared(this + 2);
    JobMoniker::~JobMoniker((JobMoniker *)&iid);
    wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
    return (unsigned int)v36;
  }
  v37 = JobStore::m_pCommonStore;
  v109 = JobStore::m_pCommonStore;
  v124 = 0;
  JobMoniker::JobMoniker(&v117, 0, 0);
  v38 = 0;
  v96 = 0;
  v97 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)&pExceptionObject);
  v111[1] = 0;
  v111[0] = std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(v39, 0, 0);
  v111[2] = 0;
  TreeInfo = JobStore::RegGetTreeInfo(v37, psz, &v124, 0);
  if ( TreeInfo < 0 )
    goto LABEL_185;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v41 = 0;
  v42 = 0;
  v89 = 0;
  if ( *((_QWORD *)v37 + 4) )
  {
    SysFreeString(0);
    v41 = SysAllocString(psz);
    v95 = (BSTR *)v41;
    if ( !v41 )
      ATL::PrivateAtlThrow(0x8007000E);
    LODWORD(v44) = 0;
    if ( *v41 )
    {
      do
      {
        if ( v41[(unsigned int)v44] == 92 )
          v41[(unsigned int)v44] = 47;
        v44 = (unsigned int)(v44 + 1);
      }
      while ( v41[v44] );
    }
    v45 = RegOpenKeyExW(*((HKEY *)v37 + 4), v41, 0, 0xF003Fu, &hKey);
    v43 = v45;
    if ( !v45 )
    {
      cbData = 4;
      v46 = RegQueryValueExW(hKey, L"StateFlags", 0, &Type, Data, &cbData);
      v43 = v46;
      if ( !v46 && Type == 4 && cbData == 4 )
      {
        if ( (*(_DWORD *)Data | 3) == 3 )
          v42 = *(_DWORD *)Data;
        v89 = v42;
      }
    }
  }
  else
  {
    v43 = 50;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      (unsigned int)psz,
      (__int64)psz,
      v43);
  }
  SysFreeString(v41);
  if ( hKey )
    RegCloseKey(hKey);
  *(_QWORD *)&v113 = 0;
  v114 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qS_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v47, (unsigned int)&v112, (__int64)psz, (__int64)&v124);
  }
  v48 = (JobBucket *)HeapAlloc(g_PrivateHeap, 0, 0xD8u);
  if ( !v48 )
  {
    v103 = 0;
    v104 = &qword_1800A4718;
    v105 = 0;
    v106 = 0;
    v107 = 14;
    *(_QWORD *)v108 = -1;
    v102 = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&v102;
  }
  v49 = JobBucket::JobBucket(v48);
  v50 = v49;
  if ( v49 )
    _InterlockedIncrement((volatile signed __int32 *)v49 + 2);
  v51 = v114;
  if ( v114 && _InterlockedExchangeAdd((volatile signed __int32 *)v114 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v51)(v51, 1);
  v114 = v50;
  if ( psz[0] == 92 || psz[0] == 47 )
  {
    _bstr_t::~_bstr_t((_bstr_t *)&v113);
    v56 = (BSTR *)operator new(0x18u);
    v53 = v56;
    v95 = v56;
    if ( v56 )
    {
      v56[1] = 0;
      *((_DWORD *)v56 + 4) = 1;
      v57 = SysAllocString(L"NT TASK");
      *v53 = v57;
      if ( !v57 )
        _com_raise_error(-2147024882, v58);
    }
    else
    {
      v53 = 0;
    }
  }
  else
  {
    _bstr_t::~_bstr_t((_bstr_t *)&v113);
    v52 = (BSTR *)operator new(0x18u);
    v53 = v52;
    v95 = v52;
    if ( v52 )
    {
      v52[1] = 0;
      *((_DWORD *)v52 + 4) = 1;
      v54 = SysAllocString(L"NT TASK\\");
      *v53 = v54;
      if ( !v54 )
        _com_raise_error(-2147024882, v55);
    }
    else
    {
      v53 = 0;
    }
  }
  *(_QWORD *)&v113 = v53;
  v59 = (BSTR *)operator new(0x18u);
  v61 = v59;
  v95 = v59;
  if ( v59 )
  {
    v59[1] = 0;
    *((_DWORD *)v59 + 4) = 1;
    v62 = SysAllocString(psz);
    *v61 = v62;
    if ( !v62 )
      _com_raise_error(-2147024882, v60);
  }
  else
  {
    v61 = 0;
  }
  v95 = v61;
  if ( !v61 )
    _com_raise_error(-2147024882, v60);
  v63 = (HKEY)operator new(0x18u);
  v65 = v63;
  hKey = v63;
  if ( v63 )
  {
    *((_QWORD *)v63 + 1) = 0;
    *((_DWORD *)v63 + 4) = 1;
    if ( (_QWORD)v113 && *(_QWORD *)v113 )
      v66 = SysStringLen(*(BSTR *)v113);
    else
      v66 = 0;
    if ( *v61 )
      v67 = SysStringLen(*v61);
    else
      v67 = 0;
    *(_DWORD *)Data = v67;
    v68 = v67 + v66;
    if ( v67 + v66 < v66 || (v64 = (struct IErrorInfo *)(2LL * v68), (unsigned __int64)v64 > 0xFFFFFFFF) )
      _com_raise_error(-2147024882, v64);
    v70 = SysAllocStringByteLen(0, (UINT)v64);
    *v65 = v70;
    if ( v70 )
    {
      if ( (_QWORD)v113 && *(_QWORD *)v113 )
        memcpy_0(v70, *(const void **)v113, 2LL * (v66 + 1));
      if ( *v61 )
        memcpy_0((void *)(*v65 + 2LL * v66), *v61, 2LL * (unsigned int)(*(_DWORD *)Data + 1));
    }
    else if ( v68 )
    {
      _com_raise_error(-2147024882, v69);
    }
    v37 = v109;
  }
  else
  {
    v65 = 0;
  }
  _bstr_t::~_bstr_t((_bstr_t *)&v113);
  *(_QWORD *)&v113 = v65;
  _bstr_t::Data_t::Release((_bstr_t::Data_t *)v61);
  if ( (_QWORD)v113 )
    v71 = *(__int16 **)v113;
  else
    v71 = 0;
  for ( j = *v71; *v71; j = *v71 )
  {
    if ( j == 47 )
    {
      *v71 = 92;
    }
    else if ( j != 92 )
    {
      ++v71;
      continue;
    }
    *((_QWORD *)&v113 + 1) = ++v71;
  }
  v112 = v124;
  *((_DWORD *)v114 + 15) = 0;
  if ( (_QWORD)v113 )
    _InterlockedIncrement((volatile signed __int32 *)(v113 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v118);
  v118 = v113;
  v117 = v112;
  v73 = v114;
  if ( v114 )
    _InterlockedIncrement((volatile signed __int32 *)v114 + 2);
  wmi::AutoRef<JobBucket>::Release(&v119);
  v119 = v73;
  v74 = v114;
  if ( v114 && _InterlockedExchangeAdd((volatile signed __int32 *)v114 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v74)(v74, 1);
  v114 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v113);
  TreeInfo = JobStore::RegOpenTaskKey(v37, (struct JobMoniker *)&v117, &v96, 0x20019u);
  if ( TreeInfo < 0 || v89 && (TreeInfo = JobStore::RegOpenTaskOverrideKey(v37, psz, 0x20019u, 2u, &v97), TreeInfo < 0) )
  {
    v38 = v96;
    v4 = v94;
    goto LABEL_185;
  }
  v38 = v96;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)&v112);
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)&v102);
  hKey = 0;
  TreeInfo = Triggers::Trigulator::StreamIn((Triggers::Trigulator *)&v112, v38, 2u, (unsigned __int64 *)&hKey);
  if ( TreeInfo >= 0 )
  {
    if ( v97 )
    {
      TreeInfo = Triggers::Trigulator::StreamIn((Triggers::Trigulator *)&v102, v97, 2u, (unsigned __int64 *)&hKey);
      v77 = v89;
      if ( TreeInfo >= 0 )
      {
        if ( (v89 & 1) != 0 )
          std::list<Triggers::Trigger *>::operator=(&v114, &v106);
        if ( (v77 & 2) != 0 )
          *(_DWORD *)(v116 + 16) = *(_DWORD *)(*(_QWORD *)&v108[4] + 16LL);
        Triggers::Trigulator::operator=(&pExceptionObject, &v112);
        TreeInfo = 0;
      }
      goto LABEL_162;
    }
    pExceptionObject = v112;
    v99 = v113;
    std::list<Triggers::Trigger *>::clear(&v100);
    v75 = v100;
    v100 = v114;
    v114 = v75;
    v76 = v101;
    *(_QWORD *)&v101 = v115;
    v115 = v76;
    wmi::AutoRef<JobBucket>::Release((char *)&v101 + 8);
    *((_QWORD *)&v101 + 1) = v116;
    v116 = 0;
    TreeInfo = 0;
  }
  v77 = v89;
LABEL_162:
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v102);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v112);
  if ( TreeInfo < 0 )
  {
LABEL_177:
    v4 = v94;
    goto LABEL_185;
  }
  v80 = (volatile signed __int32 *)*((_QWORD *)&v101 + 1);
  if ( *((_QWORD *)&v101 + 1) )
  {
    *(_QWORD *)&v113 = 0;
    v114 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v78, v79, &v112, &v117, *((_QWORD *)&v101 + 1));
    }
    if ( v80 )
      _InterlockedIncrement(v80 + 2);
    wmi::AutoRef<JobBucket>::Release(&v114);
    v114 = (JobBucket *)v80;
    if ( (_QWORD)v118 )
      _InterlockedIncrement((volatile signed __int32 *)(v118 + 16));
    _bstr_t::~_bstr_t((_bstr_t *)&v113);
    v113 = v118;
    v112 = v117;
    if ( (_QWORD)v118 )
      _InterlockedIncrement((volatile signed __int32 *)(v118 + 16));
    _bstr_t::~_bstr_t((_bstr_t *)&v118);
    v118 = v113;
    v117 = v112;
    v81 = v114;
    if ( v114 )
      _InterlockedIncrement((volatile signed __int32 *)v114 + 2);
    wmi::AutoRef<JobBucket>::Release(&v119);
    v119 = v81;
    wmi::AutoRef<JobBucket>::Release(&v114);
    _bstr_t::~_bstr_t((_bstr_t *)&v113);
    *((_DWORD *)v119 + 5) = v77;
    TreeInfo = 0;
    _bstr_t::operator=(v121, &v118);
    v122 = *((_QWORD *)&v118 + 1);
    iid = v117;
    wmi::AutoRef<JobBucket>::operator=(&v123, v119);
    goto LABEL_177;
  }
  TreeInfo = -2147418113;
  v4 = v94;
LABEL_185:
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v111);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&pExceptionObject);
  if ( v97 )
    RegCloseKey(v97);
  if ( v38 )
    RegCloseKey(v38);
  v82 = v119;
  if ( v119 && _InterlockedExchangeAdd((volatile signed __int32 *)v119 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v82)(v82, 1);
  v119 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v118);
  ReleaseSRWLockShared(v35);
  if ( TreeInfo < 0 )
  {
    JobMoniker::~JobMoniker((JobMoniker *)&iid);
LABEL_194:
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return (unsigned int)TreeInfo;
  }
  v83 = v123;
  if ( v4 )
  {
    if ( (*(_DWORD *)(v123 + 16) & 0x2000000) != 0 )
    {
      v84 = (*((__int64 (__fastcall **)(void ***, GUID *, enum tsched::InternalTaskState *))UbpmProxySingleton::s_singleton[0]
             + 11))(
              UbpmProxySingleton::s_singleton,
              &iid,
              v4);
      TreeInfo = 0;
      if ( v84 != -2147023728 )
        TreeInfo = v84;
      if ( TreeInfo < 0 )
      {
        v85 = (void (__fastcall ***)(_QWORD, __int64))v123;
        if ( v123 && _InterlockedExchangeAdd((volatile signed __int32 *)(v123 + 8), 0xFFFFFFFF) == 1 )
          (**v85)(v85, 1);
        v123 = 0;
        _bstr_t::~_bstr_t((_bstr_t *)v121);
        goto LABEL_194;
      }
      v83 = v123;
    }
    if ( !*(_DWORD *)v4 )
      *(_DWORD *)v4 = ((*(_DWORD *)(v83 + 16) & 0x400000) == 0) + 3;
  }
  if ( v110 )
    *v110 = (*(_DWORD *)(v83 + 16) >> 22) & 1;
  if ( v83 && _InterlockedExchangeAdd((volatile signed __int32 *)(v83 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v83)(v83, 1);
  v123 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)v121);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18000b5a0  mov     [rsp-8+arg_0], rbx
0x18000b5a5  push    rbp
0x18000b5a6  push    rsi
0x18000b5a7  push    rdi
0x18000b5a8  push    r12
0x18000b5aa  push    r13
0x18000b5ac  push    r14
0x18000b5ae  push    r15
0x18000b5b0  lea     rbp, [rsp-2D0h]
0x18000b5b8  sub     rsp, 3D0h
0x18000b5bf  mov     rax, cs:__security_cookie
0x18000b5c6  xor     rax, rsp
0x18000b5c9  mov     [rbp+300h+var_40], rax
0x18000b5d0  mov     [rbp+300h+var_310], r9
0x18000b5d4  mov     r12, r8
0x18000b5d7  mov     [rsp+400h+var_3A8], r8
0x18000b5dc  mov     rbx, rdx
0x18000b5df  mov     r14, rcx
0x18000b5e2  test    rdx, rdx
0x18000b5e5  jz      loc_18000C37C
0x18000b5eb  xor     edx, edx; Val
0x18000b5ed  mov     r8d, 20Ah; Size
0x18000b5f3  lea     rcx, [rbp+300h+psz]; void *
0x18000b5fa  call    memset_0
0x18000b5ff  movzx   eax, word ptr [rbx]
0x18000b602  mov     edx, 7FFFFFFEh
0x18000b607  xor     esi, esi
0x18000b609  mov     r8d, 105h
0x18000b60f  test    ax, ax
0x18000b612  jz      loc_18000B818
0x18000b618  cmp     ax, 5Ch ; '\'
0x18000b61c  jz      short loc_18000B675
0x18000b61e  mov     r9d, edx
0x18000b621  lea     rax, asc_1800A3DA8; "\\"
0x18000b628  mov     r11d, r8d
0x18000b62b  lea     r10, [rbp+300h+psz]
0x18000b632  test    r9, r9
0x18000b635  jz      short loc_18000B671
0x18000b637  movzx   ecx, word ptr [rax]
0x18000b63a  test    cx, cx
0x18000b63d  jz      short loc_18000B660
0x18000b63f  add     rax, 2
0x18000b643  mov     [r10], cx
0x18000b647  add     r10, 2
0x18000b64b  dec     r9
0x18000b64e  sub     r11, 1
0x18000b652  jnz     short loc_18000B632
0x18000b654  mov     ecx, 8007007Ah
0x18000b659  mov     eax, ecx
0x18000b65b  jmp     loc_18000C381
0x18000b660  test    r11, r11
0x18000b663  jnz     short loc_18000B671
0x18000b665  mov     ecx, 8007007Ah
0x18000b66a  mov     eax, ecx
0x18000b66c  jmp     loc_18000C381
0x18000b671  mov     [r10], si
0x18000b675  movzx   r11d, si
0x18000b679  mov     ecx, esi
0x18000b67b  nop     dword ptr [rax+rax+00h]
0x18000b680  cmp     ecx, r8d
0x18000b683  jge     short loc_18000B6CA
0x18000b685  movsxd  rdi, ecx
0x18000b688  movzx   r10d, word ptr [rbx+rdi*2]
0x18000b68d  test    r10w, r10w
0x18000b691  jz      short loc_18000B6F2
0x18000b693  mov     r9d, r10d
0x18000b696  cmp     r10d, 5Ch ; '\'
0x18000b69a  jz      short loc_18000B6E3
0x18000b69c  sub     r9d, 20h ; ' '
0x18000b6a0  jz      short loc_18000B6D6
0x18000b6a2  sub     r9d, 0Eh
0x18000b6a6  jz      short loc_18000B6B4
0x18000b6a8  sub     r9d, 1
0x18000b6ac  jz      short loc_18000B6CA
0x18000b6ae  cmp     r9d, 0Bh
0x18000b6b2  jmp     short loc_18000B6E8
0x18000b6b4  cmp     r11w, 2Eh ; '.'
0x18000b6b9  jz      short loc_18000B6CA
0x18000b6bb  cmp     r11w, 5Ch ; '\'
0x18000b6c0  jnz     short loc_18000B6EA
0x18000b6c2  cmp     [rbx+rdi*2+2], r11w
0x18000b6c8  jnz     short loc_18000B6EA
0x18000b6ca  mov     ecx, 8007007Bh
0x18000b6cf  mov     eax, ecx
0x18000b6d1  jmp     loc_18000C381
0x18000b6d6  cmp     r11w, 5Ch ; '\'
0x18000b6db  jz      short loc_18000B6CA
0x18000b6dd  test    r11w, r11w
0x18000b6e1  jmp     short loc_18000B6E8
0x18000b6e3  cmp     r11w, 5Ch ; '\'
0x18000b6e8  jz      short loc_18000B6CA
0x18000b6ea  movzx   r11d, r10w
0x18000b6ee  inc     ecx
0x18000b6f0  jmp     short loc_18000B680
0x18000b6f2  cmp     r11w, 5Ch ; '\'
0x18000b6f7  jnz     short loc_18000B6FE
0x18000b6f9  cmp     ecx, 1
0x18000b6fc  jg      short loc_18000B6CA
0x18000b6fe  mov     r9, r8
0x18000b701  lea     rax, [rbp+300h+psz]
0x18000b708  cmp     [rax], si
0x18000b70b  jz      short loc_18000B717
0x18000b70d  add     rax, 2
0x18000b711  sub     r9, 1
0x18000b715  jnz     short loc_18000B708
0x18000b717  mov     ecx, 80070057h
0x18000b71c  test    r9, r9
0x18000b71f  cmovnz  ecx, esi
0x18000b722  mov     rax, r8
0x18000b725  sub     rax, r9
0x18000b728  test    r9, r9
0x18000b72b  cmovz   rax, rsi
0x18000b72f  jz      loc_18000B868
0x18000b735  sub     r8, rax
0x18000b738  lea     r9, [rbp+300h+psz]
0x18000b73f  lea     r9, [r9+rax*2]
0x18000b743  jz      short loc_18000B767
0x18000b745  test    rdx, rdx
0x18000b748  jz      short loc_18000B767
0x18000b74a  movzx   eax, word ptr [rbx]
0x18000b74d  test    ax, ax
0x18000b750  jz      short loc_18000B767
0x18000b752  add     rbx, 2
0x18000b756  mov     [r9], ax
0x18000b75a  add     r9, 2
0x18000b75e  dec     rdx
0x18000b761  sub     r8, 1
0x18000b765  jnz     short loc_18000B745
0x18000b767  mov     ecx, 8007007Ah
0x18000b76c  test    r8, r8
0x18000b76f  cmovnz  ecx, esi
0x18000b772  lea     rax, [r9-2]
0x18000b776  cmovnz  rax, r9
0x18000b77a  mov     [rax], si
0x18000b77d  jz      loc_18000B868
0x18000b783  movzx   eax, [rbp+300h+psz]
0x18000b78a  test    ax, ax
0x18000b78d  jz      loc_18000C37C
0x18000b793  cmp     [rbp+300h+var_24E], 0
0x18000b79b  jnz     short loc_18000B7A7
0x18000b79d  cmp     ax, 5Ch ; '\'
0x18000b7a1  jz      loc_18000C37C
0x18000b7a7  mov     [rsp+400h+TokenHandle], rsi
0x18000b7ac  xor     ecx, ecx; BindingHandle
0x18000b7ae  call    cs:__imp_RpcImpersonateClient
0x18000b7b4  mov     ebx, eax
0x18000b7b6  test    eax, eax
0x18000b7b8  jz      loc_18000B86F
0x18000b7be  mov     r9d, eax; unsigned int
0x18000b7c1  lea     r8, aGetstate; "GetState"
0x18000b7c8  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x18000b7cf  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18000b7d4  mov     byte ptr [rbp+300h+pExceptionObject+8], 0
0x18000b7d8  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000b7df  mov     qword ptr [rsp+400h+pExceptionObject], rax
0x18000b7e4  lea     rax, qword_1800A4718
0x18000b7eb  mov     qword ptr [rbp+300h+var_378], rax
0x18000b7ef  mov     qword ptr [rbp+300h+var_378+8], rsi
0x18000b7f3  mov     [rbp+300h+var_368], 0
0x18000b7fb  mov     dword ptr [rbp+300h+var_360], ebx
0x18000b7fe  mov     [rbp+300h+var_360+4], 0FFFFFFFFFFFFFFFFh
0x18000b806  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b80d  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x18000b812  call    _CxxThrowException_0
0x18000b818  lea     rax, asc_1800A3DA8; "\\"
0x18000b81f  lea     r9, [rbp+300h+psz]
0x18000b826  mov     ecx, esi
0x18000b828  test    rdx, rdx
0x18000b82b  jz      short loc_18000B85C
0x18000b82d  movzx   r10d, word ptr [rax]
0x18000b831  test    r10w, r10w
0x18000b835  jz      short loc_18000B84E
0x18000b837  add     rax, 2
0x18000b83b  mov     [r9], r10w
0x18000b83f  add     r9, 2
0x18000b843  dec     rdx
0x18000b846  sub     r8, 1
0x18000b84a  jnz     short loc_18000B828
0x18000b84c  jmp     short loc_18000B853
0x18000b84e  test    r8, r8
0x18000b851  jnz     short loc_18000B85C
0x18000b853  sub     r9, 2
0x18000b857  mov     ecx, 8007007Ah
0x18000b85c  mov     [r9], si
0x18000b860  test    ecx, ecx
0x18000b862  jns     loc_18000B783
0x18000b868  mov     eax, ecx
0x18000b86a  jmp     loc_18000C381
0x18000b86f  call    cs:__imp_GetCurrentThread
0x18000b875  mov     rcx, rax; ThreadHandle
0x18000b878  lea     r9, [rsp+400h+TokenHandle]; TokenHandle
0x18000b87d  mov     edx, 8; DesiredAccess
0x18000b882  mov     r8d, 1; OpenAsSelf
0x18000b888  call    cs:__imp_OpenThreadToken
0x18000b88e  test    eax, eax
0x18000b890  jnz     short loc_18000B8C2
0x18000b892  call    cs:__imp_GetLastError
0x18000b898  mov     ebx, eax
0x18000b89a  test    eax, eax
0x18000b89c  jle     short loc_18000B8A7
0x18000b89e  movzx   ebx, ax
0x18000b8a1  or      ebx, 80070000h
0x18000b8a7  call    cs:__imp_RpcRevertToSelf
0x18000b8ad  test    ebx, ebx
0x18000b8af  jns     short loc_18000B8C8
0x18000b8b1  lea     rcx, [rsp+400h+TokenHandle]; this
0x18000b8b6  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18000b8bb  mov     eax, ebx
0x18000b8bd  jmp     loc_18000C381
0x18000b8c2  call    cs:__imp_RpcRevertToSelf
0x18000b8c8  xor     r8d, r8d; unsigned __int16 *
0x18000b8cb  lea     rdx, [rbp+300h+psz]; psz
0x18000b8d2  lea     rcx, [rbp+300h+iid]; lpiid
0x18000b8d6  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18000b8db  nop
0x18000b8dc  lea     rdi, [r14+10h]
0x18000b8e0  mov     [rbp+300h+var_2F0], rdi
0x18000b8e4  mov     rcx, rdi; SRWLock
0x18000b8e7  call    cs:__imp_AcquireSRWLockShared
0x18000b8ed  nop
0x18000b8ee  mov     r8d, 1; DesiredAccess
0x18000b8f4  lea     rdx, [rbp+300h+psz]; psz
0x18000b8fb  mov     rcx, [rsp+400h+TokenHandle]; ClientToken
0x18000b900  call    ?TaskAccessCheck@@YAJPEAXPEBGK@Z; TaskAccessCheck(void *,ushort const *,ulong)
0x18000b905  mov     ebx, eax
0x18000b907  test    eax, eax
0x18000b909  jns     short loc_18000B973
0x18000b90b  lea     rax, WPP_GLOBAL_Control
0x18000b912  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b919  cmp     rcx, rax
0x18000b91c  jz      short loc_18000B94E
0x18000b91e  test    dword ptr [rcx+1Ch], 200h
0x18000b925  jz      short loc_18000B94E
0x18000b927  cmp     byte ptr [rcx+19h], 2
0x18000b92b  jb      short loc_18000B94E
0x18000b92d  mov     edx, 4Eh ; 'N'
0x18000b932  mov     dword ptr [rsp+400h+phkResult], ebx
0x18000b936  lea     r9, [rbp+300h+psz]
0x18000b93d  lea     r8, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids
0x18000b944  mov     rcx, [rcx+10h]
0x18000b948  call    WPP_SF_Sd
0x18000b94d  nop
0x18000b94e  mov     rcx, rdi; SRWLock
0x18000b951  call    cs:__imp_ReleaseSRWLockShared
0x18000b957  nop
0x18000b958  lea     rcx, [rbp+300h+iid]; this
0x18000b95c  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18000b961  nop
0x18000b962  lea     rcx, [rsp+400h+TokenHandle]; this
0x18000b967  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18000b96c  mov     eax, ebx
0x18000b96e  jmp     loc_18000C381
0x18000b973  mov     r13, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18000b97a  mov     [rbp+300h+var_318], r13
0x18000b97e  xorps   xmm0, xmm0
0x18000b981  movups  xmmword ptr [rbp+300h+var_260.Data1], xmm0
0x18000b988  xor     r8d, r8d; unsigned __int16 *
0x18000b98b  xor     edx, edx; psz
0x18000b98d  lea     rcx, [rbp+300h+var_2B0]; lpiid
0x18000b991  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18000b996  nop
0x18000b997  mov     r15, rsi
0x18000b99a  mov     [rsp+400h+var_398], rsi
0x18000b99f  mov     [rsp+400h+var_390], rsi
0x18000b9a4  lea     rcx, [rsp+400h+pExceptionObject]; this
0x18000b9a9  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x18000b9ae  nop
0x18000b9af  mov     [rbp+300h+var_300], rsi
0x18000b9b3  xor     r8d, r8d
0x18000b9b6  xor     edx, edx
0x18000b9b8  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAUTrigger@Triggers@@V?$allocator@PEAUTrigger@Triggers@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAUTrigger@Triggers@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(std::_List_node<Triggers::Trigger *,void *> *,std::_List_node<Triggers::Trigger *,void *> *)
0x18000b9bd  mov     [rbp+300h+var_308], rax
0x18000b9c1  mov     [rbp+300h+var_2F8], rsi
0x18000b9c5  xor     r9d, r9d; enum JobStore::TaskIndex *
0x18000b9c8  lea     r8, [rbp+300h+var_260]; struct _GUID *
0x18000b9cf  lea     rdx, [rbp+300h+psz]; unsigned __int16 *
0x18000b9d6  mov     rcx, r13; this
0x18000b9d9  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x18000b9de  mov     ebx, eax
0x18000b9e0  test    eax, eax
0x18000b9e2  js      loc_18000C1D3
0x18000b9e8  mov     [rsp+400h+Type], esi
0x18000b9ec  mov     [rsp+400h+cbData], esi
0x18000b9f0  mov     dword ptr [rsp+400h+Data], esi
0x18000b9f4  mov     [rsp+400h+hKey], rsi
0x18000b9f9  mov     rbx, rsi
0x18000b9fc  mov     r14d, esi
0x18000b9ff  mov     [rsp+400h+var_3CC], esi
0x18000ba03  cmp     qword ptr [r13+20h], 0
0x18000ba08  jnz     short loc_18000BA15
0x18000ba0a  mov     r8d, 32h ; '2'
0x18000ba10  jmp     loc_18000BAEF
0x18000ba15  xor     ecx, ecx; bstrString
0x18000ba17  call    cs:__imp_SysFreeString
0x18000ba1d  lea     rcx, [rbp+300h+psz]; psz
0x18000ba24  call    cs:__imp_SysAllocString
0x18000ba2a  mov     rbx, rax
0x18000ba2d  mov     [rsp+400h+var_3A0], rax
0x18000ba32  test    rax, rax
0x18000ba35  jnz     short loc_18000BA42
  ... truncated ...
```
