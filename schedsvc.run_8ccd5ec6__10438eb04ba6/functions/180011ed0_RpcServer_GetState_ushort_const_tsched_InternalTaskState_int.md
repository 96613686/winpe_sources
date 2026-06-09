# RpcServer::GetState(ushort const *,tsched::InternalTaskState *,int *)

- ea: `0x180011ed0`
- end: `0x180012d36`
- name: `?GetState@RpcServer@@AEAAJPEBGPEAW4InternalTaskState@tsched@@PEAH@Z`
- size: `3686`
- prototype: `__int64 __fastcall(RpcServer *__hidden this, const unsigned __int16 *, enum tsched::InternalTaskState *, int *)`
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180041870`

## callees

- `0x18000ba20`
- `0x18000bb10`
- `0x18000cb10`
- `0x18000d160`
- `0x18000fda4`
- `0x18000ff40`
- `0x180010390`
- `0x1800103d4`
- `0x180011e40`
- `0x180011ed0`
- `0x1800138d8`
- `0x180013a90`
- `0x180015030`
- `0x18001d130`
- `0x18001ea40`
- `0x18001f060`
- `0x180024730`
- `0x180027910`
- `0x18002b210`
- `0x18002f814`
- `0x18003b1f0`
- `0x180047c88`
- `0x18004d278`
- `0x1800529a0`
- `0x180054824`
- `0x180056714`
- `0x180059140`
- `0x18005a2bc`
- `0x18005a2d6`
- `0x180069f84`
- `0x18006a08c`
- `0x180071b54`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001238c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800125cd`
- `OLEAUT32!__imp_SysAllocString` at `0x180012623`
- `OLEAUT32!__imp_SysAllocString` at `0x180012672`
- `OLEAUT32!__imp_SysAllocString` at `0x18001238c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800125cd`
- `OLEAUT32!__imp_SysAllocString` at `0x180012623`
- `OLEAUT32!__imp_SysAllocString` at `0x180012672`
- `OLEAUT32!__imp_SysFreeString` at `0x180012379`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124be`
- `OLEAUT32!__imp_SysFreeString` at `0x180012379`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124be`
- `OLEAUT32!__imp_SysStringLen` at `0x1800126e0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800126fc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800126e0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800126fc`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001272f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001272f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012cf6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001223d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001223d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800122ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012bc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800122ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012bc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800123f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800123f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012435`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012435`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800121a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800121a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800121c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800121c6`
- `RPCRT4!RpcImpersonateClient` at `0x1800120de`
- `RPCRT4!RpcImpersonateClient` at `0x1800120de`
- `RPCRT4!RpcRevertToSelf` at `0x1800121f1`
- `RPCRT4!RpcRevertToSelf` at `0x180012212`
- `RPCRT4!RpcRevertToSelf` at `0x1800121f1`
- `RPCRT4!RpcRevertToSelf` at `0x180012212`

## string_xrefs

- `0x18001261c`: `NT TASK`
- `0x1800125c6`: `NT TASK\`

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
  __int64 v75; // r8
  JobBucket *v76; // rcx
  __int64 v77; // rcx
  int v78; // r13d
  __int64 v79; // rdx
  __int64 v80; // r8
  volatile signed __int32 *v81; // rbx
  JobBucket *v82; // rbx
  JobBucket *v83; // rcx
  __int64 v84; // rcx
  int v85; // eax
  void (__fastcall ***v86)(_QWORD, __int64); // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  const struct _GUID *lpcbData; // [rsp+28h] [rbp-D8h]
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v90; // [rsp+34h] [rbp-CCh]
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  enum tsched::InternalTaskState *v95; // [rsp+58h] [rbp-A8h]
  BSTR *v96; // [rsp+60h] [rbp-A0h]
  HKEY v97; // [rsp+68h] [rbp-98h] BYREF
  HKEY v98; // [rsp+70h] [rbp-90h] BYREF
  GUID pExceptionObject; // [rsp+78h] [rbp-88h] BYREF
  __int128 v100; // [rsp+88h] [rbp-78h]
  JobBucket *v101; // [rsp+98h] [rbp-68h] BYREF
  __int128 v102; // [rsp+A0h] [rbp-60h] BYREF
  JobStore *v103; // [rsp+B0h] [rbp-50h]
  int *v104; // [rsp+B8h] [rbp-48h]
  _QWORD v105[4]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v106[32]; // [rsp+E0h] [rbp-20h] BYREF
  char v107[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v108; // [rsp+110h] [rbp+10h]
  GUID v109; // [rsp+118h] [rbp+18h] BYREF
  __int128 v110; // [rsp+128h] [rbp+28h] BYREF
  JobBucket *v111; // [rsp+138h] [rbp+38h] BYREF
  __int64 v112; // [rsp+140h] [rbp+40h]
  __int64 v113; // [rsp+148h] [rbp+48h]
  GUID v114; // [rsp+150h] [rbp+50h] BYREF
  __int128 v115; // [rsp+160h] [rbp+60h] BYREF
  JobBucket *v116; // [rsp+170h] [rbp+70h] BYREF
  GUID iid; // [rsp+178h] [rbp+78h] BYREF
  char v118[8]; // [rsp+188h] [rbp+88h] BYREF
  __int64 v119; // [rsp+190h] [rbp+90h]
  __int64 v120; // [rsp+198h] [rbp+98h] BYREF
  struct _GUID v121; // [rsp+1A0h] [rbp+A0h] BYREF
  OLECHAR psz[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  v104 = a4;
  v4 = a3;
  v95 = a3;
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
    *(_QWORD *)&v100 = &qword_1800A8718;
    *((_QWORD *)&v100 + 1) = 0;
    v101 = 0;
    LODWORD(v102) = v28;
    *(_QWORD *)((char *)&v102 + 4) = -1;
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
  v105[3] = this + 2;
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
  v103 = JobStore::m_pCommonStore;
  v121 = 0;
  JobMoniker::JobMoniker(&v114, 0, 0);
  v38 = 0;
  v97 = 0;
  v98 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)&pExceptionObject);
  v105[1] = 0;
  v105[0] = std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(v39, 0, 0);
  v105[2] = 0;
  TreeInfo = JobStore::RegGetTreeInfo(v37, psz, &v121, 0);
  if ( TreeInfo < 0 )
    goto LABEL_185;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v41 = 0;
  v42 = 0;
  v90 = 0;
  if ( *((_QWORD *)v37 + 4) )
  {
    SysFreeString(0);
    v41 = SysAllocString(psz);
    v96 = (BSTR *)v41;
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
        v90 = v42;
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
  *(_QWORD *)&v110 = 0;
  v111 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qS_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v47, (unsigned int)&v109, (__int64)psz, (__int64)&v121);
  }
  v48 = (JobBucket *)operator new(0xD8u);
  v96 = (BSTR *)v48;
  if ( v48 )
  {
    v49 = JobBucket::JobBucket(v48);
    v50 = v49;
    if ( v49 )
      _InterlockedIncrement((volatile signed __int32 *)v49 + 2);
  }
  else
  {
    v50 = 0;
  }
  v51 = v111;
  if ( v111 && _InterlockedExchangeAdd((volatile signed __int32 *)v111 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v51)(v51, 1);
  v111 = v50;
  if ( psz[0] == 92 || psz[0] == 47 )
  {
    _bstr_t::~_bstr_t((_bstr_t *)&v110);
    v56 = (BSTR *)operator new(0x18u);
    v53 = v56;
    v96 = v56;
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
    _bstr_t::~_bstr_t((_bstr_t *)&v110);
    v52 = (BSTR *)operator new(0x18u);
    v53 = v52;
    v96 = v52;
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
  *(_QWORD *)&v110 = v53;
  v59 = (BSTR *)operator new(0x18u);
  v61 = v59;
  v96 = v59;
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
  v96 = v61;
  if ( !v61 )
    _com_raise_error(-2147024882, v60);
  v63 = (HKEY)operator new(0x18u);
  v65 = v63;
  hKey = v63;
  if ( v63 )
  {
    *((_QWORD *)v63 + 1) = 0;
    *((_DWORD *)v63 + 4) = 1;
    if ( (_QWORD)v110 && *(_QWORD *)v110 )
      v66 = SysStringLen(*(BSTR *)v110);
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
      if ( (_QWORD)v110 && *(_QWORD *)v110 )
        memcpy_0(v70, *(const void **)v110, 2LL * (v66 + 1));
      if ( *v61 )
        memcpy_0((void *)(*v65 + 2LL * v66), *v61, 2LL * (unsigned int)(*(_DWORD *)Data + 1));
    }
    else if ( v68 )
    {
      _com_raise_error(-2147024882, v69);
    }
    v37 = v103;
  }
  else
  {
    v65 = 0;
  }
  _bstr_t::~_bstr_t((_bstr_t *)&v110);
  *(_QWORD *)&v110 = v65;
  _bstr_t::Data_t::Release((_bstr_t::Data_t *)v61);
  if ( (_QWORD)v110 )
    v71 = *(__int16 **)v110;
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
    *((_QWORD *)&v110 + 1) = ++v71;
  }
  v109 = v121;
  *((_DWORD *)v111 + 15) = 0;
  if ( (_QWORD)v110 )
    _InterlockedIncrement((volatile signed __int32 *)(v110 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v115);
  v115 = v110;
  v114 = v109;
  v73 = v111;
  if ( v111 )
    _InterlockedIncrement((volatile signed __int32 *)v111 + 2);
  wmi::AutoRef<JobBucket>::Release(&v116);
  v116 = v73;
  v74 = v111;
  if ( v111 && _InterlockedExchangeAdd((volatile signed __int32 *)v111 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v74)(v74, 1);
  v111 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v110);
  TreeInfo = JobStore::RegOpenTaskKey(v37, (struct JobMoniker *)&v114, &v97, 0x20019u);
  if ( TreeInfo < 0 || v90 && (TreeInfo = JobStore::RegOpenTaskOverrideKey(v37, psz, 0x20019u, 2u, &v98), TreeInfo < 0) )
  {
    v38 = v97;
    v4 = v95;
    goto LABEL_185;
  }
  v38 = v97;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)&v109);
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v106);
  hKey = 0;
  TreeInfo = Triggers::Trigulator::StreamIn((Triggers::Trigulator *)&v109, v38, 2u, (unsigned __int64 *)&hKey);
  if ( TreeInfo >= 0 )
  {
    if ( v98 )
    {
      TreeInfo = Triggers::Trigulator::StreamIn((Triggers::Trigulator *)v106, v98, 2u, (unsigned __int64 *)&hKey);
      v78 = v90;
      if ( TreeInfo >= 0 )
      {
        if ( (v90 & 1) != 0 )
          std::list<Triggers::Trigger *>::operator=(&v111, v107);
        if ( (v78 & 2) != 0 )
          *(_DWORD *)(v113 + 16) = *(_DWORD *)(v108 + 16);
        Triggers::Trigulator::operator=(&pExceptionObject, &v109);
        TreeInfo = 0;
      }
      goto LABEL_162;
    }
    pExceptionObject = v109;
    v100 = v110;
    std::list<Triggers::Trigger *>::clear(&v101, 0, v75);
    v76 = v101;
    v101 = v111;
    v111 = v76;
    v77 = v102;
    *(_QWORD *)&v102 = v112;
    v112 = v77;
    wmi::AutoRef<JobBucket>::Release((char *)&v102 + 8);
    *((_QWORD *)&v102 + 1) = v113;
    v113 = 0;
    TreeInfo = 0;
  }
  v78 = v90;
LABEL_162:
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v106);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v109);
  if ( TreeInfo < 0 )
  {
LABEL_177:
    v4 = v95;
    goto LABEL_185;
  }
  v81 = (volatile signed __int32 *)*((_QWORD *)&v102 + 1);
  if ( *((_QWORD *)&v102 + 1) )
  {
    *(_QWORD *)&v110 = 0;
    v111 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v79, v80, &v109, &v114, *((_QWORD *)&v102 + 1));
    }
    if ( v81 )
      _InterlockedIncrement(v81 + 2);
    wmi::AutoRef<JobBucket>::Release(&v111);
    v111 = (JobBucket *)v81;
    if ( (_QWORD)v115 )
      _InterlockedIncrement((volatile signed __int32 *)(v115 + 16));
    _bstr_t::~_bstr_t((_bstr_t *)&v110);
    v110 = v115;
    v109 = v114;
    if ( (_QWORD)v115 )
      _InterlockedIncrement((volatile signed __int32 *)(v115 + 16));
    _bstr_t::~_bstr_t((_bstr_t *)&v115);
    v115 = v110;
    v114 = v109;
    v82 = v111;
    if ( v111 )
      _InterlockedIncrement((volatile signed __int32 *)v111 + 2);
    wmi::AutoRef<JobBucket>::Release(&v116);
    v116 = v82;
    wmi::AutoRef<JobBucket>::Release(&v111);
    _bstr_t::~_bstr_t((_bstr_t *)&v110);
    *((_DWORD *)v116 + 5) = v78;
    TreeInfo = 0;
    _bstr_t::operator=(v118, &v115);
    v119 = *((_QWORD *)&v115 + 1);
    iid = v114;
    wmi::AutoRef<JobBucket>::operator=(&v120, v116);
    goto LABEL_177;
  }
  TreeInfo = -2147418113;
  v4 = v95;
LABEL_185:
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v105);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&pExceptionObject);
  if ( v98 )
    RegCloseKey(v98);
  if ( v38 )
    RegCloseKey(v38);
  v83 = v116;
  if ( v116 && _InterlockedExchangeAdd((volatile signed __int32 *)v116 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v83)(v83, 1);
  v116 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v115);
  ReleaseSRWLockShared(v35);
  if ( TreeInfo < 0 )
  {
    JobMoniker::~JobMoniker((JobMoniker *)&iid);
LABEL_194:
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return (unsigned int)TreeInfo;
  }
  v84 = v120;
  if ( v4 )
  {
    if ( (*(_DWORD *)(v120 + 16) & 0x2000000) != 0 )
    {
      v85 = (*((__int64 (__fastcall **)(void ***, GUID *, enum tsched::InternalTaskState *))UbpmProxySingleton::s_singleton[0]
             + 11))(
              UbpmProxySingleton::s_singleton,
              &iid,
              v4);
      TreeInfo = 0;
      if ( v85 != -2147023728 )
        TreeInfo = v85;
      if ( TreeInfo < 0 )
      {
        v86 = (void (__fastcall ***)(_QWORD, __int64))v120;
        if ( v120 && _InterlockedExchangeAdd((volatile signed __int32 *)(v120 + 8), 0xFFFFFFFF) == 1 )
          (**v86)(v86, 1);
        v120 = 0;
        _bstr_t::~_bstr_t((_bstr_t *)v118);
        goto LABEL_194;
      }
      v84 = v120;
    }
    if ( !*(_DWORD *)v4 )
      *(_DWORD *)v4 = ((*(_DWORD *)(v84 + 16) & 0x400000) == 0) + 3;
  }
  if ( v104 )
    *v104 = (*(_DWORD *)(v84 + 16) >> 22) & 1;
  if ( v84 && _InterlockedExchangeAdd((volatile signed __int32 *)(v84 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v84)(v84, 1);
  v120 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)v118);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180011ed0  mov     [rsp-8+arg_0], rbx
0x180011ed5  push    rbp
0x180011ed6  push    rsi
0x180011ed7  push    rdi
0x180011ed8  push    r12
0x180011eda  push    r13
0x180011edc  push    r14
0x180011ede  push    r15
0x180011ee0  lea     rbp, [rsp-2D0h]
0x180011ee8  sub     rsp, 3D0h
0x180011eef  mov     rax, cs:__security_cookie
0x180011ef6  xor     rax, rsp
0x180011ef9  mov     [rbp+300h+var_40], rax
0x180011f00  mov     [rbp+300h+var_348], r9
0x180011f04  mov     r12, r8
0x180011f07  mov     [rsp+400h+var_3A8], r8
0x180011f0c  mov     rbx, rdx
0x180011f0f  mov     r14, rcx
0x180011f12  test    rdx, rdx
0x180011f15  jz      loc_180012D06
0x180011f1b  xor     edx, edx; Val
0x180011f1d  mov     r8d, 20Ah; Size
0x180011f23  lea     rcx, [rbp+300h+psz]; void *
0x180011f2a  call    memset_0
0x180011f2f  movzx   eax, word ptr [rbx]
0x180011f32  mov     edx, 7FFFFFFEh
0x180011f37  xor     esi, esi
0x180011f39  mov     r8d, 105h
0x180011f3f  test    ax, ax
0x180011f42  jz      loc_18001214E
0x180011f48  cmp     ax, 5Ch ; '\'
0x180011f4c  jz      short loc_180011FA5
0x180011f4e  mov     r9d, edx
0x180011f51  lea     rax, asc_1800A7EC0; "\\"
0x180011f58  mov     r11d, r8d
0x180011f5b  lea     r10, [rbp+300h+psz]
0x180011f62  test    r9, r9
0x180011f65  jz      short loc_180011FA1
0x180011f67  movzx   ecx, word ptr [rax]
0x180011f6a  test    cx, cx
0x180011f6d  jz      short loc_180011F90
0x180011f6f  add     rax, 2
0x180011f73  mov     [r10], cx
0x180011f77  add     r10, 2
0x180011f7b  dec     r9
0x180011f7e  sub     r11, 1
0x180011f82  jnz     short loc_180011F62
0x180011f84  mov     ecx, 8007007Ah
0x180011f89  mov     eax, ecx
0x180011f8b  jmp     loc_180012D0B
0x180011f90  test    r11, r11
0x180011f93  jnz     short loc_180011FA1
0x180011f95  mov     ecx, 8007007Ah
0x180011f9a  mov     eax, ecx
0x180011f9c  jmp     loc_180012D0B
0x180011fa1  mov     [r10], si
0x180011fa5  movzx   r11d, si
0x180011fa9  mov     ecx, esi
0x180011fab  nop     dword ptr [rax+rax+00h]
0x180011fb0  cmp     ecx, r8d
0x180011fb3  jge     short loc_180011FFA
0x180011fb5  movsxd  rdi, ecx
0x180011fb8  movzx   r10d, word ptr [rbx+rdi*2]
0x180011fbd  test    r10w, r10w
0x180011fc1  jz      short loc_180012022
0x180011fc3  mov     r9d, r10d
0x180011fc6  cmp     r10d, 5Ch ; '\'
0x180011fca  jz      short loc_180012013
0x180011fcc  sub     r9d, 20h ; ' '
0x180011fd0  jz      short loc_180012006
0x180011fd2  sub     r9d, 0Eh
0x180011fd6  jz      short loc_180011FE4
0x180011fd8  sub     r9d, 1
0x180011fdc  jz      short loc_180011FFA
0x180011fde  cmp     r9d, 0Bh
0x180011fe2  jmp     short loc_180012018
0x180011fe4  cmp     r11w, 2Eh ; '.'
0x180011fe9  jz      short loc_180011FFA
0x180011feb  cmp     r11w, 5Ch ; '\'
0x180011ff0  jnz     short loc_18001201A
0x180011ff2  cmp     [rbx+rdi*2+2], r11w
0x180011ff8  jnz     short loc_18001201A
0x180011ffa  mov     ecx, 8007007Bh
0x180011fff  mov     eax, ecx
0x180012001  jmp     loc_180012D0B
0x180012006  cmp     r11w, 5Ch ; '\'
0x18001200b  jz      short loc_180011FFA
0x18001200d  test    r11w, r11w
0x180012011  jmp     short loc_180012018
0x180012013  cmp     r11w, 5Ch ; '\'
0x180012018  jz      short loc_180011FFA
0x18001201a  movzx   r11d, r10w
0x18001201e  inc     ecx
0x180012020  jmp     short loc_180011FB0
0x180012022  cmp     r11w, 5Ch ; '\'
0x180012027  jnz     short loc_18001202E
0x180012029  cmp     ecx, 1
0x18001202c  jg      short loc_180011FFA
0x18001202e  mov     r9, r8
0x180012031  lea     rax, [rbp+300h+psz]
0x180012038  cmp     [rax], si
0x18001203b  jz      short loc_180012047
0x18001203d  add     rax, 2
0x180012041  sub     r9, 1
0x180012045  jnz     short loc_180012038
0x180012047  mov     ecx, 80070057h
0x18001204c  test    r9, r9
0x18001204f  cmovnz  ecx, esi
0x180012052  mov     rax, r8
0x180012055  sub     rax, r9
0x180012058  test    r9, r9
0x18001205b  cmovz   rax, rsi
0x18001205f  jz      loc_1800121A0
0x180012065  sub     r8, rax
0x180012068  lea     r9, [rbp+300h+psz]
0x18001206f  lea     r9, [r9+rax*2]
0x180012073  jz      short loc_180012097
0x180012075  test    rdx, rdx
0x180012078  jz      short loc_180012097
0x18001207a  movzx   eax, word ptr [rbx]
0x18001207d  test    ax, ax
0x180012080  jz      short loc_180012097
0x180012082  add     rbx, 2
0x180012086  mov     [r9], ax
0x18001208a  add     r9, 2
0x18001208e  dec     rdx
0x180012091  sub     r8, 1
0x180012095  jnz     short loc_180012075
0x180012097  mov     ecx, 8007007Ah
0x18001209c  test    r8, r8
0x18001209f  cmovnz  ecx, esi
0x1800120a2  lea     rax, [r9-2]
0x1800120a6  cmovnz  rax, r9
0x1800120aa  mov     [rax], si
0x1800120ad  jz      loc_1800121A0
0x1800120b3  movzx   eax, [rbp+300h+psz]
0x1800120ba  test    ax, ax
0x1800120bd  jz      loc_180012D06
0x1800120c3  cmp     [rbp+300h+var_24E], 0
0x1800120cb  jnz     short loc_1800120D7
0x1800120cd  cmp     ax, 5Ch ; '\'
0x1800120d1  jz      loc_180012D06
0x1800120d7  mov     [rsp+400h+TokenHandle], rsi
0x1800120dc  xor     ecx, ecx; BindingHandle
0x1800120de  call    cs:__imp_RpcImpersonateClient
0x1800120e5  nop     dword ptr [rax+rax+00h]
0x1800120ea  mov     ebx, eax
0x1800120ec  test    eax, eax
0x1800120ee  jz      loc_1800121A7
0x1800120f4  mov     r9d, eax; unsigned int
0x1800120f7  lea     r8, aGetstate; "GetState"
0x1800120fe  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180012105  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18001210a  mov     byte ptr [rbp+300h+pExceptionObject+8], 0
0x18001210e  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012115  mov     qword ptr [rsp+400h+pExceptionObject], rax
0x18001211a  lea     rax, qword_1800A8718
0x180012121  mov     qword ptr [rbp+300h+var_378], rax
0x180012125  mov     qword ptr [rbp+300h+var_378+8], rsi
0x180012129  mov     [rbp+300h+var_368], 0
0x180012131  mov     dword ptr [rbp+300h+var_360], ebx
0x180012134  mov     [rbp+300h+var_360+4], 0FFFFFFFFFFFFFFFFh
0x18001213c  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012143  lea     rcx, [rsp+400h+pExceptionObject]; pExceptionObject
0x180012148  call    _CxxThrowException_0
0x18001214e  lea     rax, asc_1800A7EC0; "\\"
0x180012155  lea     r9, [rbp+300h+psz]
0x18001215c  mov     ecx, esi
0x18001215e  xchg    ax, ax
0x180012160  test    rdx, rdx
0x180012163  jz      short loc_180012194
0x180012165  movzx   r10d, word ptr [rax]
0x180012169  test    r10w, r10w
0x18001216d  jz      short loc_180012186
0x18001216f  add     rax, 2
0x180012173  mov     [r9], r10w
0x180012177  add     r9, 2
0x18001217b  dec     rdx
0x18001217e  sub     r8, 1
0x180012182  jnz     short loc_180012160
0x180012184  jmp     short loc_18001218B
0x180012186  test    r8, r8
0x180012189  jnz     short loc_180012194
0x18001218b  sub     r9, 2
0x18001218f  mov     ecx, 8007007Ah
0x180012194  mov     [r9], si
0x180012198  test    ecx, ecx
0x18001219a  jns     loc_1800120B3
0x1800121a0  mov     eax, ecx
0x1800121a2  jmp     loc_180012D0B
0x1800121a7  call    cs:__imp_GetCurrentThread
0x1800121ae  nop     dword ptr [rax+rax+00h]
0x1800121b3  mov     rcx, rax; ThreadHandle
0x1800121b6  lea     r9, [rsp+400h+TokenHandle]; TokenHandle
0x1800121bb  mov     edx, 8; DesiredAccess
0x1800121c0  mov     r8d, 1; OpenAsSelf
0x1800121c6  call    cs:__imp_OpenThreadToken
0x1800121cd  nop     dword ptr [rax+rax+00h]
0x1800121d2  test    eax, eax
0x1800121d4  jnz     short loc_180012212
0x1800121d6  call    cs:__imp_GetLastError
0x1800121dd  nop     dword ptr [rax+rax+00h]
0x1800121e2  mov     ebx, eax
0x1800121e4  test    eax, eax
0x1800121e6  jle     short loc_1800121F1
0x1800121e8  movzx   ebx, ax
0x1800121eb  or      ebx, 80070000h
0x1800121f1  call    cs:__imp_RpcRevertToSelf
0x1800121f8  nop     dword ptr [rax+rax+00h]
0x1800121fd  test    ebx, ebx
0x1800121ff  jns     short loc_18001221E
0x180012201  lea     rcx, [rsp+400h+TokenHandle]; this
0x180012206  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18001220b  mov     eax, ebx
0x18001220d  jmp     loc_180012D0B
0x180012212  call    cs:__imp_RpcRevertToSelf
0x180012219  nop     dword ptr [rax+rax+00h]
0x18001221e  xor     r8d, r8d; unsigned __int16 *
0x180012221  lea     rdx, [rbp+300h+psz]; psz
0x180012228  lea     rcx, [rbp+300h+iid]; lpiid
0x18001222c  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x180012231  nop
0x180012232  lea     rdi, [r14+10h]
0x180012236  mov     [rbp+300h+var_328], rdi
0x18001223a  mov     rcx, rdi; SRWLock
0x18001223d  call    cs:__imp_AcquireSRWLockShared
0x180012244  nop     dword ptr [rax+rax+00h]
0x180012249  nop
0x18001224a  mov     r8d, 1; DesiredAccess
0x180012250  lea     rdx, [rbp+300h+psz]; psz
0x180012257  mov     rcx, [rsp+400h+TokenHandle]; ClientToken
0x18001225c  call    ?TaskAccessCheck@@YAJPEAXPEBGK@Z; TaskAccessCheck(void *,ushort const *,ulong)
0x180012261  mov     ebx, eax
0x180012263  test    eax, eax
0x180012265  jns     short loc_1800122D5
0x180012267  lea     rax, WPP_GLOBAL_Control
0x18001226e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012275  cmp     rcx, rax
0x180012278  jz      short loc_1800122AA
0x18001227a  test    dword ptr [rcx+1Ch], 200h
0x180012281  jz      short loc_1800122AA
0x180012283  cmp     byte ptr [rcx+19h], 2
0x180012287  jb      short loc_1800122AA
0x180012289  mov     edx, 4Eh ; 'N'
0x18001228e  mov     dword ptr [rsp+400h+phkResult], ebx
0x180012292  lea     r9, [rbp+300h+psz]
0x180012299  lea     r8, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids
0x1800122a0  mov     rcx, [rcx+10h]
0x1800122a4  call    WPP_SF_Sd
0x1800122a9  nop
0x1800122aa  mov     rcx, rdi; SRWLock
0x1800122ad  call    cs:__imp_ReleaseSRWLockShared
0x1800122b4  nop     dword ptr [rax+rax+00h]
0x1800122b9  nop
0x1800122ba  lea     rcx, [rbp+300h+iid]; this
0x1800122be  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x1800122c3  nop
0x1800122c4  lea     rcx, [rsp+400h+TokenHandle]; this
0x1800122c9  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x1800122ce  mov     eax, ebx
0x1800122d0  jmp     loc_180012D0B
0x1800122d5  mov     r13, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x1800122dc  mov     [rbp+300h+var_350], r13
0x1800122e0  xorps   xmm0, xmm0
0x1800122e3  movups  xmmword ptr [rbp+300h+var_260.Data1], xmm0
0x1800122ea  xor     r8d, r8d; unsigned __int16 *
0x1800122ed  xor     edx, edx; psz
0x1800122ef  lea     rcx, [rbp+300h+var_2B0]; lpiid
0x1800122f3  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x1800122f8  nop
0x1800122f9  mov     r15, rsi
0x1800122fc  mov     [rsp+400h+var_398], rsi
0x180012301  mov     [rsp+400h+var_390], rsi
0x180012306  lea     rcx, [rsp+400h+pExceptionObject]; this
0x18001230b  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180012310  nop
0x180012311  mov     [rbp+300h+var_338], rsi
0x180012315  xor     r8d, r8d
0x180012318  xor     edx, edx
0x18001231a  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAUTrigger@Triggers@@V?$allocator@PEAUTrigger@Triggers@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAUTrigger@Triggers@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(std::_List_node<Triggers::Trigger *,void *> *,std::_List_node<Triggers::Trigger *,void *> *)
0x18001231f  mov     [rbp+300h+var_340], rax
0x180012323  mov     [rbp+300h+var_330], rsi
0x180012327  xor     r9d, r9d; enum JobStore::TaskIndex *
0x18001232a  lea     r8, [rbp+300h+var_260]; struct _GUID *
0x180012331  lea     rdx, [rbp+300h+psz]; unsigned __int16 *
0x180012338  mov     rcx, r13; this
0x18001233b  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x180012340  mov     ebx, eax
0x180012342  test    eax, eax
0x180012344  js      loc_180012B3F
0x18001234a  mov     [rsp+400h+Type], esi
0x18001234e  mov     [rsp+400h+cbData], esi
0x180012352  mov     dword ptr [rsp+400h+Data], esi
0x180012356  mov     [rsp+400h+hKey], rsi
0x18001235b  mov     rbx, rsi
0x18001235e  mov     r14d, esi
0x180012361  mov     [rsp+400h+var_3CC], esi
0x180012365  cmp     qword ptr [r13+20h], 0
0x18001236a  jnz     short loc_180012377
0x18001236c  mov     r8d, 32h ; '2'
  ... truncated ...
```
