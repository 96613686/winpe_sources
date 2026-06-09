# RpcServer::SetSecurity(ushort const *,ushort const *,ulong)

- ea: `0x180029978`
- end: `0x18002a310`
- name: `?SetSecurity@RpcServer@@QEAAJPEBG0K@Z`
- size: `2456`
- prototype: `int(RpcServer *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800779a0`

## callees

- `0x180007ec0`
- `0x18000b4e0`
- `0x18000dc30`
- `0x18000e510`
- `0x1800199c0`
- `0x18001a260`
- `0x18001a430`
- `0x18001ec90`
- `0x180021300`
- `0x180022600`
- `0x1800244ac`
- `0x180024690`
- `0x180025040`
- `0x180025310`
- `0x180025550`
- `0x180025870`
- `0x1800265c4`
- `0x1800269f0`
- `0x180027ee0`
- `0x1800291c0`
- `0x180029978`
- `0x18002ab20`
- `0x18002ab90`
- `0x18002d3d0`
- `0x180030f80`
- `0x180033b40`
- `0x180039b6c`
- `0x180039d00`
- `0x180040590`
- `0x180040d90`
- `0x180041af8`
- `0x180051ed0`
- `0x180052584`
- `0x18005790c`
- `0x18006e3e0`
- `0x18007a26c`
- `0x18007e3dc`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ada`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a2b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a2b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029b10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029b10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029b67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029bcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029c18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029c72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029d95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029ed5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a18e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a2a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029b67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029bcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029c18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029c72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029d95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029ed5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a18e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a2a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029aba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029aba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180029ad0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180029ad0`
- `RPCRT4!RpcImpersonateClient` at `0x180029a54`
- `RPCRT4!RpcImpersonateClient` at `0x180029f00`
- `RPCRT4!RpcImpersonateClient` at `0x180029fa1`
- `RPCRT4!RpcImpersonateClient` at `0x18002a1c7`
- `RPCRT4!RpcImpersonateClient` at `0x180029a54`
- `RPCRT4!RpcImpersonateClient` at `0x180029f00`
- `RPCRT4!RpcImpersonateClient` at `0x180029fa1`
- `RPCRT4!RpcImpersonateClient` at `0x18002a1c7`
- `RPCRT4!RpcRevertToSelf` at `0x180029aef`
- `RPCRT4!RpcRevertToSelf` at `0x180029aff`
- `RPCRT4!RpcRevertToSelf` at `0x180029f89`
- `RPCRT4!RpcRevertToSelf` at `0x18002a01a`
- `RPCRT4!RpcRevertToSelf` at `0x18002a025`
- `RPCRT4!RpcRevertToSelf` at `0x18002a11f`
- `RPCRT4!RpcRevertToSelf` at `0x18002a12e`
- `RPCRT4!RpcRevertToSelf` at `0x18002a282`
- `RPCRT4!RpcRevertToSelf` at `0x180029aef`
- `RPCRT4!RpcRevertToSelf` at `0x180029aff`
- `RPCRT4!RpcRevertToSelf` at `0x180029f89`
- `RPCRT4!RpcRevertToSelf` at `0x18002a01a`
- `RPCRT4!RpcRevertToSelf` at `0x18002a025`
- `RPCRT4!RpcRevertToSelf` at `0x18002a11f`
- `RPCRT4!RpcRevertToSelf` at `0x18002a12e`
- `RPCRT4!RpcRevertToSelf` at `0x18002a282`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2cd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180029e24`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180029e24`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180029a37`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180029a37`

## string_xrefs

- `0x180029f12`: `RpcServer::SetSecurity`
- `0x180029fb0`: `RpcServer::SetSecurity`
- `0x18002a0d0`: `RpcServer::SetSecurity`
- `0x18002a1d6`: `RpcServer::SetSecurity`
- `0x180029a63`: `SetSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RpcServer::SetSecurity(RpcServer *this, unsigned __int16 *a2, unsigned __int16 *a3, int a4)
{
  int v7; // r15d
  char v8; // r12
  WCHAR *v10; // rbx
  const unsigned __int16 *v11; // r8
  signed int LastHrError; // edi
  int v13; // edx
  tsched *v14; // rcx
  RPC_STATUS v15; // eax
  EventManager *v16; // rcx
  RPC_STATUS v17; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  RTL_SRWLOCK *v20; // r14
  JobStore *v21; // r13
  _BYTE *v22; // rdi
  int v23; // esi
  int v24; // r15d
  int v25; // edx
  tsched *v26; // rcx
  int v27; // r12d
  unsigned __int16 *v28; // rsi
  RPC_STATUS v29; // eax
  EventManager *v30; // rcx
  RPC_STATUS v31; // esi
  unsigned __int16 *v32; // r12
  int v33; // esi
  RPC_STATUS v34; // eax
  EventManager *v35; // rcx
  RPC_STATUS v36; // esi
  CredStore *v37; // rdi
  _QWORD *Account; // rax
  const unsigned __int16 *v39; // rdx
  const struct JobMoniker *v40; // rax
  RPC_STATUS v41; // eax
  EventManager *v42; // rcx
  RPC_STATUS v43; // edi
  const unsigned __int16 *v44; // rdx
  const unsigned __int16 *v45; // r9
  PULONG StringSecurityDescriptorLen; // [rsp+20h] [rbp-E0h]
  PULONG StringSecurityDescriptorLena; // [rsp+20h] [rbp-E0h]
  const struct _GUID *v48; // [rsp+28h] [rbp-D8h]
  struct _SID StringSecurityDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v50; // [rsp+3Ch] [rbp-C4h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE *v53; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  int v55; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v56; // [rsp+68h] [rbp-98h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v58; // [rsp+78h] [rbp-88h]
  RTL_SRWLOCK *v59; // [rsp+80h] [rbp-80h]
  _BYTE v60[56]; // [rsp+88h] [rbp-78h] BYREF
  GUID pExceptionObject; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v62; // [rsp+D0h] [rbp-30h]
  __int64 v63; // [rsp+D8h] [rbp-28h]
  __int64 v64; // [rsp+E0h] [rbp-20h]
  RPC_STATUS v65; // [rsp+E8h] [rbp-18h]
  __int64 v66; // [rsp+ECh] [rbp-14h]
  struct _GUID v67; // [rsp+F8h] [rbp-8h] BYREF
  OLECHAR psz; // [rsp+110h] [rbp+10h] BYREF
  char v69[526]; // [rsp+112h] [rbp+12h] BYREF

  v56 = a3;
  v7 = a4 | 0x60000000;
  v8 = 0;
  if ( (a4 & 0x60000000) != 0 )
    v7 = a4;
  if ( (v7 & 0x9FFFFFEF) != 0 )
    return 2147942487LL;
  v10 = 0;
  v58 = 0;
  psz = 0;
  memset_0(v69, 0, 0x208u);
  LastHrError = tsched::TaskPathCanonicalize((tsched *)&psz, a2, v11);
  if ( LastHrError < 0 )
    goto LABEL_41;
  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  if ( a3 && !ConvertStringSecurityDescriptorToSecurityDescriptorW(a3, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    LastHrError = tsched::GetLastHrError(v14, v13);
LABEL_40:
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
    goto LABEL_41;
  }
  TokenHandle = 0;
  v15 = RpcImpersonateClient(0);
  v17 = v15;
  if ( v15 )
  {
    EventManager::EvtReport(v16, &IMPERSONATION_FAILURE, L"SetSecurity", v15, StringSecurityDescriptorLen, v48);
    pExceptionObject.Data4[0] = 0;
    *(_QWORD *)&pExceptionObject.Data1 = &wmi::GenericException::`vftable';
    v62 = &qword_1800A4718;
    v63 = 0;
    v64 = 0;
    v65 = v17;
    v66 = -1;
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
    LastHrError = LastError;
    if ( LastError > 0 )
      LastHrError = (unsigned __int16)LastError | 0x80070000;
    RpcRevertToSelf();
    if ( LastHrError < 0 )
      goto LABEL_39;
  }
  v20 = (RTL_SRWLOCK *)((char *)this + 16);
  v59 = v20;
  AcquireSRWLockExclusive(v20);
  v21 = JobStore::m_pCommonStore;
  v67 = 0;
  v22 = 0;
  v53 = 0;
  pSecurityDescriptor = 0;
  v55 = 0;
  v23 = JobStore::RegJobSecurityQuery(JobStore::m_pCommonStore, &psz, (struct JobSecurity *)&pSecurityDescriptor);
  if ( v23 < 0 )
  {
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
    wmi::AutoRef<User::UserEntry>::Release(&v53);
    ReleaseSRWLockExclusive(v20);
    wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
LABEL_19:
    LastHrError = v23;
LABEL_41:
    operator delete(0);
    return (unsigned int)LastHrError;
  }
  if ( JobStore::RegGetTreeInfo(v21, &psz, &v67, 0) < 0 )
  {
    LOBYTE(StringSecurityDescriptor.SubAuthority[0]) = 0;
    if ( (v7 & 0x20000000) == 0 )
    {
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      wmi::AutoRef<User::UserEntry>::Release(&v53);
      ReleaseSRWLockExclusive(v20);
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
      LastHrError = -2147024894;
      goto LABEL_41;
    }
  }
  else
  {
    v8 = 1;
    LOBYTE(StringSecurityDescriptor.SubAuthority[0]) = 1;
    if ( (v7 & 0x40000000) == 0 )
    {
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      wmi::AutoRef<User::UserEntry>::Release(&v53);
      ReleaseSRWLockExclusive(v20);
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
      LastHrError = -2147024893;
      goto LABEL_41;
    }
  }
  v23 = JobAccessCheck(TokenHandle, pSecurityDescriptor, 0xC0000u);
  if ( v23 < 0 )
  {
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
    wmi::AutoRef<User::UserEntry>::Release(&v53);
    ReleaseSRWLockExclusive(v20);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    if ( SecurityDescriptor )
    {
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
    }
    goto LABEL_19;
  }
  v24 = v7 & 0x10;
  if ( !v24 && v8 )
  {
    LastHrError = JobAccessCheck(TokenHandle, pSecurityDescriptor, 1u);
    if ( LastHrError < 0 )
    {
LABEL_38:
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      wmi::AutoRef<User::UserEntry>::Release(&v53);
      ReleaseSRWLockExclusive(v20);
LABEL_39:
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      goto LABEL_40;
    }
    JobMoniker::JobMoniker((JobMoniker *)&pExceptionObject, &psz, &v67);
    *(_QWORD *)&StringSecurityDescriptor.Revision = 0;
    LastHrError = JobStore::RegOpenTaskKey(
                    v21,
                    (struct JobMoniker *)&pExceptionObject,
                    (HKEY *)&StringSecurityDescriptor,
                    0x20019u);
    if ( LastHrError < 0 )
    {
LABEL_37:
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&StringSecurityDescriptor);
      JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
      goto LABEL_38;
    }
    Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v60);
    LastHrError = Triggers::Trigulator::StreamIn(
                    (Triggers::Trigulator *)v60,
                    *(HKEY *)&StringSecurityDescriptor.Revision,
                    2u,
                    0);
    if ( LastHrError < 0
      || (LastHrError = Triggers::Trigulator::GetBucket(
                          (Triggers::Trigulator *)v60,
                          (struct JobMoniker *)&pExceptionObject),
          LastHrError < 0) )
    {
      Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v60);
      goto LABEL_37;
    }
    wmi::AutoRef<User::UserEntry>::operator=(&v53, *(_QWORD *)(v64 + 64));
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v60);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&StringSecurityDescriptor);
    JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
    v22 = v53;
  }
  v50 = 0;
  *(_QWORD *)&StringSecurityDescriptor.Revision = 0;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
         pSecurityDescriptor,
         1u,
         7u,
         (LPWSTR *)&StringSecurityDescriptor,
         &v50) )
  {
    v28 = (unsigned __int16 *)operator new(saturated_mul(v50 + 1, 2u));
    v27 = StringCchCopyNW(v28, v50 + 1, *(const unsigned __int16 **)&StringSecurityDescriptor.Revision, v50);
    if ( v27 >= 0 )
    {
      v10 = v28;
      v58 = v28;
      operator delete(0);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
      v27 = 0;
    }
    else
    {
      operator delete(v28);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
    }
  }
  else
  {
    v27 = tsched::GetLastHrError(v26, v25);
    if ( *(_QWORD *)&StringSecurityDescriptor.Revision )
      LocalFree(*(HLOCAL *)&StringSecurityDescriptor.Revision);
  }
  if ( v27 >= 0 )
  {
    v50 = 1;
    v29 = RpcImpersonateClient(0);
    v31 = v29;
    if ( v29 )
    {
      EventManager::EvtReport(
        v30,
        &IMPERSONATION_FAILURE,
        L"RpcServer::SetSecurity",
        v29,
        StringSecurityDescriptorLena,
        v48);
      pExceptionObject.Data4[0] = 0;
      *(_QWORD *)&pExceptionObject.Data1 = &wmi::GenericException::`vftable';
      v62 = &qword_1800A4718;
      v63 = 0;
      v64 = 0;
      v65 = v31;
      v66 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v32 = v56;
    if ( qword_1800BD628 )
      v33 = qword_1800BD628(&psz, v56);
    else
      v33 = 1;
    RpcRevertToSelf();
    if ( v33 < 0 )
      goto LABEL_80;
    v50 = 1;
    v34 = RpcImpersonateClient(0);
    v36 = v34;
    if ( v34 )
    {
      EventManager::EvtReport(
        v35,
        &IMPERSONATION_FAILURE,
        L"RpcServer::SetSecurity",
        v34,
        StringSecurityDescriptorLena,
        v48);
      pExceptionObject.Data4[0] = 0;
      *(_QWORD *)&pExceptionObject.Data1 = &wmi::GenericException::`vftable';
      v62 = &qword_1800A4718;
      v63 = 0;
      v64 = 0;
      v65 = v36;
      v66 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v33 = JobStore::FileSddlSet(v21, &psz, v32);
    if ( v33 < 0 )
    {
      RpcRevertToSelf();
LABEL_80:
      v50 = 1;
      v41 = RpcImpersonateClient(0);
      v43 = v41;
      if ( v41 )
      {
        EventManager::EvtReport(
          v42,
          &IMPERSONATION_FAILURE,
          L"RpcServer::SetSecurity",
          v41,
          StringSecurityDescriptorLena,
          v48);
        pExceptionObject.Data4[0] = 0;
        *(_QWORD *)&pExceptionObject.Data1 = &wmi::GenericException::`vftable';
        v62 = &qword_1800A4718;
        v63 = 0;
        v64 = 0;
        v65 = v43;
        v66 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      if ( JobStore::GetUseXmlStore(v21) )
      {
        *(_QWORD *)&StringSecurityDescriptor.Revision = 0;
        if ( (int)JobStore::GetXmlFileSystemPath(v21, &psz, &StringSecurityDescriptor) >= 0 )
          tsched::SetJobFileSecurityByName(*(wchar_t **)&StringSecurityDescriptor.Revision, v44, v10, v45);
        operator delete(*(void **)&StringSecurityDescriptor.Revision);
      }
      if ( qword_1800BD628 )
        qword_1800BD628(&psz, v10);
      RpcRevertToSelf();
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      wmi::AutoRef<User::UserEntry>::Release(&v53);
      ReleaseSRWLockExclusive(v20);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(TokenHandle);
        TokenHandle = 0;
      }
      if ( SecurityDescriptor )
      {
        LocalFree(SecurityDescriptor);
        SecurityDescriptor = 0;
      }
      v27 = v33;
      goto LABEL_93;
    }
    RpcRevertToSelf();
    v33 = JobSecurity::Update(&pSecurityDescriptor, SecurityDescriptor, TokenHandle);
    if ( v33 < 0 )
      goto LABEL_80;
    if ( !v24 && LOBYTE(StringSecurityDescriptor.SubAuthority[0]) )
    {
      User::User(&StringSecurityDescriptor, &v53);
      if ( v22 && *v22 )
      {
        v37 = (CredStore *)CredStore::g_pCommonStore;
        Account = (_QWORD *)User::GetAccount(&v53, &v56);
        v39 = *Account ? *(const unsigned __int16 **)*Account : 0LL;
        v33 = CredStore::ResolveAlias(v37, v39, (struct User *)&StringSecurityDescriptor);
        _bstr_t::~_bstr_t((_bstr_t *)&v56);
        if ( v33 < 0 )
        {
LABEL_70:
          wmi::AutoRef<User::UserEntry>::Release(&StringSecurityDescriptor);
          goto LABEL_80;
        }
      }
      RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v50, L"RpcServer::SetSecurity", 1);
      v40 = JobMoniker::JobMoniker(&pExceptionObject, &psz, 0);
      v33 = JobStore::HammerAcl(v21, v40, (const struct User *)&StringSecurityDescriptor, &StringSecurityDescriptor);
      JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
      if ( v33 < 0 )
      {
        if ( v50 )
          RpcRevertToSelf();
        goto LABEL_70;
      }
      if ( v50 )
        RpcRevertToSelf();
      v33 = JobSecurity::AddRemovePrincipalAce(
              &pSecurityDescriptor,
              *(void **)(*(_QWORD *)&StringSecurityDescriptor.Revision + 32LL),
              0);
      if ( v33 < 0 )
        goto LABEL_70;
      wmi::AutoRef<User::UserEntry>::Release(&StringSecurityDescriptor);
    }
    v33 = JobStore::RegJobSecuritySet(v21, &psz, (struct JobSecurity *)&pSecurityDescriptor);
    if ( v33 >= 0 )
    {
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      wmi::AutoRef<User::UserEntry>::Release(&v53);
      ReleaseSRWLockExclusive(v20);
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
      operator delete(v10);
      return 0;
    }
    goto LABEL_80;
  }
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
  wmi::AutoRef<User::UserEntry>::Release(&v53);
  ReleaseSRWLockExclusive(v20);
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
LABEL_93:
  operator delete(v10);
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x180029978  mov     [rsp-8+arg_0], rbx
0x18002997d  push    rbp
0x18002997e  push    rsi
0x18002997f  push    rdi
0x180029980  push    r12
0x180029982  push    r13
0x180029984  push    r14
0x180029986  push    r15
0x180029988  lea     rbp, [rsp-230h]
0x180029990  sub     rsp, 330h
0x180029997  mov     rax, cs:__security_cookie
0x18002999e  xor     rax, rsp
0x1800299a1  mov     [rbp+260h+var_40], rax
0x1800299a8  mov     rsi, r8
0x1800299ab  mov     [rsp+360h+var_2F8], r8
0x1800299b0  mov     rdi, rdx
0x1800299b3  mov     r14, rcx
0x1800299b6  mov     ecx, 60000000h
0x1800299bb  mov     r15d, r9d
0x1800299be  or      r15d, ecx
0x1800299c1  xor     r12d, r12d
0x1800299c4  test    ecx, r9d
0x1800299c7  cmovnz  r15d, r9d
0x1800299cb  test    r15d, 9FFFFFEFh
0x1800299d2  jz      short loc_1800299DE
0x1800299d4  mov     eax, 80070057h
0x1800299d9  jmp     loc_18002A2E6
0x1800299de  mov     rbx, r12
0x1800299e1  mov     [rsp+360h+var_2E8], rbx
0x1800299e6  mov     [rbp+260h+psz], r12w
0x1800299eb  xor     edx, edx; Val
0x1800299ed  mov     r8d, 208h; Size
0x1800299f3  lea     rcx, [rbp+260h+var_24E]; void *
0x1800299f7  call    memset_0
0x1800299fc  mov     rdx, rdi; unsigned __int16 *
0x1800299ff  lea     rcx, [rbp+260h+psz]; this
0x180029a03  call    ?TaskPathCanonicalize@tsched@@YAJPEAGPEBG@Z; tsched::TaskPathCanonicalize(ushort *,ushort const *)
0x180029a08  mov     edi, eax
0x180029a0a  test    eax, eax
0x180029a0c  js      loc_180029DB2
0x180029a12  mov     [rsp+360h+SecurityDescriptorSize], r12d
0x180029a17  mov     [rsp+360h+SecurityDescriptor], r12
0x180029a1c  mov     r13d, 1
0x180029a22  test    rsi, rsi
0x180029a25  jz      short loc_180029A4D
0x180029a27  lea     r9, [rsp+360h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180029a2c  lea     r8, [rsp+360h+SecurityDescriptor]; SecurityDescriptor
0x180029a31  mov     edx, r13d; StringSDRevision
0x180029a34  mov     rcx, rsi; StringSecurityDescriptor
0x180029a37  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180029a3d  test    eax, eax
0x180029a3f  jnz     short loc_180029A4D
0x180029a41  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180029a46  mov     edi, eax
0x180029a48  jmp     loc_180029DA7
0x180029a4d  mov     [rsp+360h+TokenHandle], r12
0x180029a52  xor     ecx, ecx; BindingHandle
0x180029a54  call    cs:__imp_RpcImpersonateClient
0x180029a5a  mov     edi, eax
0x180029a5c  test    eax, eax
0x180029a5e  jz      short loc_180029ABA
0x180029a60  mov     r9d, eax; unsigned int
0x180029a63  lea     r8, aSetsecurity; "SetSecurity"
0x180029a6a  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180029a71  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180029a76  mov     [rbp+260h+var_298], r12b
0x180029a7a  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180029a81  mov     [rbp+260h+pExceptionObject], rcx
0x180029a85  lea     rcx, qword_1800A4718
0x180029a8c  mov     [rbp+260h+var_290], rcx
0x180029a90  mov     [rbp+260h+var_288], r12
0x180029a94  mov     [rbp+260h+var_280], r12
0x180029a98  mov     [rbp+260h+var_278], edi
0x180029a9b  mov     dword ptr [rbp+260h+var_274], 0FFFFFFFFh
0x180029aa2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029aa6  mov     dword ptr [rbp+260h+var_274+4], eax
0x180029aa9  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180029ab0  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x180029ab4  call    _CxxThrowException_0
0x180029aba  call    cs:__imp_GetCurrentThread
0x180029ac0  mov     rcx, rax; ThreadHandle
0x180029ac3  lea     r9, [rsp+360h+TokenHandle]; TokenHandle
0x180029ac8  mov     r8d, r13d; OpenAsSelf
0x180029acb  mov     edx, 8; DesiredAccess
0x180029ad0  call    cs:__imp_OpenThreadToken
0x180029ad6  test    eax, eax
0x180029ad8  jnz     short loc_180029AFF
0x180029ada  call    cs:__imp_GetLastError
0x180029ae0  mov     edi, eax
0x180029ae2  test    eax, eax
0x180029ae4  jle     short loc_180029AEF
0x180029ae6  movzx   edi, ax
0x180029ae9  or      edi, 80070000h
0x180029aef  call    cs:__imp_RpcRevertToSelf
0x180029af5  test    edi, edi
0x180029af7  js      loc_180029D9C
0x180029afd  jmp     short loc_180029B05
0x180029aff  call    cs:__imp_RpcRevertToSelf
0x180029b05  add     r14, 10h
0x180029b09  mov     [rbp+260h+var_2E0], r14
0x180029b0d  mov     rcx, r14; SRWLock
0x180029b10  call    cs:__imp_AcquireSRWLockExclusive
0x180029b16  nop
0x180029b17  mov     r13, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x180029b1e  xorps   xmm0, xmm0
0x180029b21  movups  xmmword ptr [rbp+260h+var_268.Data1], xmm0
0x180029b25  mov     rdi, r12
0x180029b28  mov     [rsp+360h+var_310], r12
0x180029b2d  mov     [rsp+360h+pSecurityDescriptor], r12
0x180029b32  mov     [rsp+360h+var_300], r12d
0x180029b37  lea     r8, [rsp+360h+pSecurityDescriptor]; struct JobSecurity *
0x180029b3c  lea     rdx, [rbp+260h+psz]; unsigned __int16 *
0x180029b40  mov     rcx, r13; this
0x180029b43  call    ?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z; JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)
0x180029b48  mov     esi, eax
0x180029b4a  test    eax, eax
0x180029b4c  jns     short loc_180029B8A
0x180029b4e  lea     rcx, [rsp+360h+pSecurityDescriptor]
0x180029b53  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180029b58  nop
0x180029b59  lea     rcx, [rsp+360h+var_310]
0x180029b5e  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180029b63  nop
0x180029b64  mov     rcx, r14; SRWLock
0x180029b67  call    cs:__imp_ReleaseSRWLockExclusive
0x180029b6d  nop
0x180029b6e  lea     rcx, [rsp+360h+TokenHandle]; this
0x180029b73  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180029b78  nop
0x180029b79  lea     rcx, [rsp+360h+SecurityDescriptor]
0x180029b7e  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180029b83  mov     edi, esi
0x180029b85  jmp     loc_180029DB2
0x180029b8a  xor     r9d, r9d; enum JobStore::TaskIndex *
0x180029b8d  lea     r8, [rbp+260h+var_268]; struct _GUID *
0x180029b91  lea     rdx, [rbp+260h+psz]; unsigned __int16 *
0x180029b95  mov     rcx, r13; this
0x180029b98  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x180029b9d  test    eax, eax
0x180029b9f  js      short loc_180029BF3
0x180029ba1  mov     r12b, 1
0x180029ba4  mov     [rsp+360h+var_328], r12b
0x180029ba9  bt      r15d, 1Eh
0x180029bae  jb      loc_180029C3E
0x180029bb4  lea     rcx, [rsp+360h+pSecurityDescriptor]
0x180029bb9  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180029bbe  nop
0x180029bbf  lea     rcx, [rsp+360h+var_310]
0x180029bc4  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180029bc9  nop
0x180029bca  mov     rcx, r14; SRWLock
0x180029bcd  call    cs:__imp_ReleaseSRWLockExclusive
0x180029bd3  nop
0x180029bd4  lea     rcx, [rsp+360h+TokenHandle]; this
0x180029bd9  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180029bde  nop
0x180029bdf  lea     rcx, [rsp+360h+SecurityDescriptor]
0x180029be4  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180029be9  mov     edi, 80070003h
0x180029bee  jmp     loc_180029DB2
0x180029bf3  mov     [rsp+360h+var_328], r12b
0x180029bf8  bt      r15d, 1Dh
0x180029bfd  jb      short loc_180029C3E
0x180029bff  lea     rcx, [rsp+360h+pSecurityDescriptor]
0x180029c04  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180029c09  nop
0x180029c0a  lea     rcx, [rsp+360h+var_310]
0x180029c0f  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180029c14  nop
0x180029c15  mov     rcx, r14; SRWLock
0x180029c18  call    cs:__imp_ReleaseSRWLockExclusive
0x180029c1e  nop
0x180029c1f  lea     rcx, [rsp+360h+TokenHandle]; this
0x180029c24  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180029c29  nop
0x180029c2a  lea     rcx, [rsp+360h+SecurityDescriptor]
0x180029c2f  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180029c34  mov     edi, 80070002h
0x180029c39  jmp     loc_180029DB2
0x180029c3e  mov     r8d, 0C0000h; DesiredAccess
0x180029c44  mov     rdx, [rsp+360h+pSecurityDescriptor]; pSecurityDescriptor
0x180029c49  mov     rcx, [rsp+360h+TokenHandle]; ClientToken
0x180029c4e  call    ?JobAccessCheck@@YAJPEAX0K@Z; JobAccessCheck(void *,void *,ulong)
0x180029c53  mov     esi, eax
0x180029c55  test    eax, eax
0x180029c57  jns     short loc_180029CB9
0x180029c59  lea     rcx, [rsp+360h+pSecurityDescriptor]
0x180029c5e  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180029c63  nop
0x180029c64  lea     rcx, [rsp+360h+var_310]
0x180029c69  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180029c6e  nop
0x180029c6f  mov     rcx, r14; SRWLock
0x180029c72  call    cs:__imp_ReleaseSRWLockExclusive
0x180029c78  nop
0x180029c79  mov     rcx, [rsp+360h+TokenHandle]; hObject
0x180029c7e  lea     rax, [rcx-1]
0x180029c82  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029c86  ja      short loc_180029C97
0x180029c88  call    cs:__imp_CloseHandle
0x180029c8e  mov     [rsp+360h+TokenHandle], 0
0x180029c97  mov     rcx, [rsp+360h+SecurityDescriptor]; hMem
0x180029c9c  test    rcx, rcx
0x180029c9f  jz      loc_180029B83
0x180029ca5  call    cs:__imp_LocalFree
0x180029cab  mov     [rsp+360h+SecurityDescriptor], 0
0x180029cb4  jmp     loc_180029B83
0x180029cb9  mov     esi, 2
0x180029cbe  and     r15d, 10h
0x180029cc2  jnz     loc_180029DF6
0x180029cc8  test    r12b, r12b
0x180029ccb  jz      loc_180029DF6
0x180029cd1  lea     r8d, [rsi-1]; DesiredAccess
0x180029cd5  mov     rdx, [rsp+360h+pSecurityDescriptor]; pSecurityDescriptor
0x180029cda  mov     rcx, [rsp+360h+TokenHandle]; ClientToken
0x180029cdf  call    ?JobAccessCheck@@YAJPEAX0K@Z; JobAccessCheck(void *,void *,ulong)
0x180029ce4  mov     edi, eax
0x180029ce6  test    eax, eax
0x180029ce8  js      loc_180029D7C
0x180029cee  lea     r8, [rbp+260h+var_268]; struct _GUID *
0x180029cf2  lea     rdx, [rbp+260h+psz]; unsigned __int16 *
0x180029cf6  lea     rcx, [rbp+260h+pExceptionObject]; this
0x180029cfa  call    ??0JobMoniker@@QEAA@PEBGAEBU_GUID@@@Z; JobMoniker::JobMoniker(ushort const *,_GUID const &)
0x180029cff  nop
0x180029d00  mov     [rsp+360h+StringSecurityDescriptor], 0
0x180029d09  mov     r9d, 20019h; unsigned int
0x180029d0f  lea     r8, [rsp+360h+StringSecurityDescriptor]; HKEY *
0x180029d14  lea     rdx, [rbp+260h+pExceptionObject]; struct JobMoniker *
0x180029d18  mov     rcx, r13; this
0x180029d1b  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x180029d20  mov     edi, eax
0x180029d22  test    eax, eax
0x180029d24  js      short loc_180029D67
0x180029d26  lea     rcx, [rbp+260h+var_2D8]; this
0x180029d2a  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180029d2f  nop
0x180029d30  xor     r9d, r9d; unsigned __int64 *
0x180029d33  mov     r8d, esi; unsigned int
0x180029d36  mov     rdx, [rsp+360h+StringSecurityDescriptor]; HKEY
0x180029d3b  lea     rcx, [rbp+260h+var_2D8]; this
0x180029d3f  call    ?StreamIn@Trigulator@Triggers@@QEAAJPEAUHKEY__@@KPEA_K@Z; Triggers::Trigulator::StreamIn(HKEY__ *,ulong,unsigned __int64 *)
0x180029d44  mov     edi, eax
0x180029d46  test    eax, eax
0x180029d48  js      short loc_180029D5D
0x180029d4a  lea     rdx, [rbp+260h+pExceptionObject]; struct JobMoniker *
0x180029d4e  lea     rcx, [rbp+260h+var_2D8]; this
0x180029d52  call    ?GetBucket@Trigulator@Triggers@@QEBAJAEAVJobMoniker@@@Z; Triggers::Trigulator::GetBucket(JobMoniker &)
0x180029d57  mov     edi, eax
0x180029d59  test    eax, eax
0x180029d5b  jns     short loc_180029DC0
0x180029d5d  lea     rcx, [rbp+260h+var_2D8]; this
0x180029d61  call    ??1Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::~Trigulator(void)
0x180029d66  nop
0x180029d67  lea     rcx, [rsp+360h+StringSecurityDescriptor]; this
0x180029d6c  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180029d71  nop
0x180029d72  lea     rcx, [rbp+260h+pExceptionObject]; this
0x180029d76  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180029d7b  nop
0x180029d7c  lea     rcx, [rsp+360h+pSecurityDescriptor]
0x180029d81  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180029d86  nop
0x180029d87  lea     rcx, [rsp+360h+var_310]
0x180029d8c  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180029d91  nop
0x180029d92  mov     rcx, r14; SRWLock
0x180029d95  call    cs:__imp_ReleaseSRWLockExclusive
0x180029d9b  nop
0x180029d9c  lea     rcx, [rsp+360h+TokenHandle]; this
0x180029da1  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180029da6  nop
0x180029da7  lea     rcx, [rsp+360h+SecurityDescriptor]
0x180029dac  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180029db1  nop
0x180029db2  xor     ecx, ecx; void *
0x180029db4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029db9  mov     eax, edi
0x180029dbb  jmp     loc_18002A2E6
0x180029dc0  mov     rdx, [rbp+260h+var_280]
0x180029dc4  mov     rdx, [rdx+40h]
0x180029dc8  lea     rcx, [rsp+360h+var_310]
0x180029dcd  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180029dd2  nop
0x180029dd3  lea     rcx, [rbp+260h+var_2D8]; this
0x180029dd7  call    ??1Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::~Trigulator(void)
0x180029ddc  nop
0x180029ddd  lea     rcx, [rsp+360h+StringSecurityDescriptor]; this
0x180029de2  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180029de7  nop
0x180029de8  lea     rcx, [rbp+260h+pExceptionObject]; this
0x180029dec  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180029df1  mov     rdi, [rsp+360h+var_310]
0x180029df6  mov     [rsp+360h+var_324], 0
0x180029dfe  mov     [rsp+360h+StringSecurityDescriptor], 0
0x180029e07  lea     rax, [rsp+360h+var_324]
0x180029e0c  mov     [rsp+360h+StringSecurityDescriptorLen], rax; void *
0x180029e11  lea     r9, [rsp+360h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180029e16  mov     edx, 1; RequestedStringSDRevision
0x180029e1b  lea     r8d, [rdx+6]; SecurityInformation
0x180029e1f  mov     rcx, [rsp+360h+pSecurityDescriptor]; SecurityDescriptor
  ... truncated ...
```
