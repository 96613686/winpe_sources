# RpcServer::SetSecurity(ushort const *,ushort const *,ulong)

- ea: `0x180023c4c`
- end: `0x180024584`
- name: `?SetSecurity@RpcServer@@QEAAJPEBG0K@Z`
- size: `2360`
- prototype: `int(RpcServer *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007ba90`

## callees

- `0x1800044fc`
- `0x18000bb10`
- `0x18000cc40`
- `0x18000fe50`
- `0x18000ff40`
- `0x180011e40`
- `0x1800138d8`
- `0x180013a90`
- `0x180015030`
- `0x180017740`
- `0x18001ea40`
- `0x18001fe10`
- `0x180020110`
- `0x180020350`
- `0x1800206a0`
- `0x1800213d8`
- `0x180021ba0`
- `0x180022d80`
- `0x180023c4c`
- `0x180024590`
- `0x1800246a8`
- `0x180024730`
- `0x180027910`
- `0x18002b210`
- `0x18002db40`
- `0x18002f814`
- `0x180034c40`
- `0x180037490`
- `0x18003be50`
- `0x180042200`
- `0x1800437e0`
- `0x180043ffc`
- `0x18004595c`
- `0x180054550`
- `0x180054c80`
- `0x18005a2bc`
- `0x180071af8`
- `0x18007e438`
- `0x180082720`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002451f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002451f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023d4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023d4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023dd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023e23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023e83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023fa8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800240f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800243db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024503`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023dd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023e23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023e83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023fa8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800240f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800243db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024503`
- `RPCRT4!RpcImpersonateClient` at `0x180024121`
- `RPCRT4!RpcImpersonateClient` at `0x1800241ce`
- `RPCRT4!RpcImpersonateClient` at `0x18002441a`
- `RPCRT4!RpcImpersonateClient` at `0x180024121`
- `RPCRT4!RpcImpersonateClient` at `0x1800241ce`
- `RPCRT4!RpcImpersonateClient` at `0x18002441a`
- `RPCRT4!RpcRevertToSelf` at `0x1800241b0`
- `RPCRT4!RpcRevertToSelf` at `0x18002424d`
- `RPCRT4!RpcRevertToSelf` at `0x18002425e`
- `RPCRT4!RpcRevertToSelf` at `0x180024360`
- `RPCRT4!RpcRevertToSelf` at `0x180024375`
- `RPCRT4!RpcRevertToSelf` at `0x1800244dd`
- `RPCRT4!RpcRevertToSelf` at `0x1800241b0`
- `RPCRT4!RpcRevertToSelf` at `0x18002424d`
- `RPCRT4!RpcRevertToSelf` at `0x18002425e`
- `RPCRT4!RpcRevertToSelf` at `0x180024360`
- `RPCRT4!RpcRevertToSelf` at `0x180024375`
- `RPCRT4!RpcRevertToSelf` at `0x1800244dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024057`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002453a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024057`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002453a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180024031`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180024031`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023d07`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023d07`

## string_xrefs

- `0x180023d2d`: `SetSecurity`
- `0x180024139`: `RpcServer::SetSecurity`
- `0x1800241e3`: `RpcServer::SetSecurity`
- `0x180024311`: `RpcServer::SetSecurity`
- `0x180024430`: `RpcServer::SetSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall RpcServer::SetSecurity(RTL_SRWLOCK *this, unsigned __int16 *a2, unsigned __int16 *a3, int a4)
{
  int v7; // r14d
  WCHAR *v9; // rbx
  const unsigned __int16 *v10; // r8
  int LastHrError; // edi
  int v12; // edx
  tsched *v13; // rcx
  RTL_SRWLOCK *v14; // rsi
  JobStore *v15; // r12
  char v16; // r13
  int v17; // r14d
  int v18; // edx
  tsched *v19; // rcx
  int v20; // r15d
  unsigned __int16 *v21; // rdi
  RPC_STATUS v22; // eax
  EventManager *v23; // rcx
  RPC_STATUS v24; // edi
  unsigned __int16 *v25; // r15
  int v26; // edi
  RPC_STATUS v27; // eax
  EventManager *v28; // rcx
  RPC_STATUS v29; // edi
  CredStore *v30; // rdi
  _QWORD *Account; // rax
  const unsigned __int16 *v32; // rdx
  const struct JobMoniker *v33; // rax
  RPC_STATUS v34; // eax
  EventManager *v35; // rcx
  RPC_STATUS v36; // r14d
  const unsigned __int16 *v37; // rdx
  const unsigned __int16 *v38; // r9
  PULONG StringSecurityDescriptorLen; // [rsp+20h] [rbp-E0h]
  const struct _GUID *v40; // [rsp+28h] [rbp-D8h]
  struct _SID StringSecurityDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  int v46; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v47; // [rsp+68h] [rbp-98h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v49; // [rsp+78h] [rbp-88h]
  RTL_SRWLOCK *v50; // [rsp+80h] [rbp-80h]
  _BYTE v51[56]; // [rsp+88h] [rbp-78h] BYREF
  GUID pExceptionObject; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v53; // [rsp+D0h] [rbp-30h]
  __int64 v54; // [rsp+D8h] [rbp-28h]
  __int64 v55; // [rsp+E0h] [rbp-20h]
  RPC_STATUS v56; // [rsp+E8h] [rbp-18h]
  __int64 v57; // [rsp+ECh] [rbp-14h]
  struct _GUID v58; // [rsp+F8h] [rbp-8h] BYREF
  OLECHAR psz; // [rsp+110h] [rbp+10h] BYREF
  char v60[526]; // [rsp+112h] [rbp+12h] BYREF

  v47 = a3;
  v7 = a4 | 0x60000000;
  if ( (a4 & 0x60000000) != 0 )
    v7 = a4;
  if ( (v7 & 0x9FFFFFEF) != 0 )
    return 2147942487LL;
  v9 = 0;
  v49 = 0;
  psz = 0;
  memset_0(v60, 0, 0x208u);
  LastHrError = tsched::TaskPathCanonicalize((tsched *)&psz, a2, v10);
  if ( LastHrError < 0 )
    goto LABEL_32;
  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  if ( a3 && !ConvertStringSecurityDescriptorToSecurityDescriptorW(a3, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    LastHrError = tsched::GetLastHrError(v13, v12);
LABEL_31:
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
    goto LABEL_32;
  }
  hObject = 0;
  LastHrError = GetCallerToken(L"SetSecurity", &hObject);
  if ( LastHrError < 0 )
  {
LABEL_30:
    wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&hObject);
    goto LABEL_31;
  }
  v14 = this + 2;
  v50 = this + 2;
  AcquireSRWLockExclusive(this + 2);
  v15 = JobStore::m_pCommonStore;
  v58 = 0;
  v44 = 0;
  pSecurityDescriptor = 0;
  v46 = 0;
  LastHrError = JobStore::RegJobSecurityQuery(
                  JobStore::m_pCommonStore,
                  &psz,
                  (struct JobSecurity *)&pSecurityDescriptor);
  if ( LastHrError < 0 )
    goto LABEL_29;
  if ( JobStore::RegGetTreeInfo(v15, &psz, &v58, 0) < 0 )
  {
    v16 = 0;
    if ( (v7 & 0x20000000) == 0 )
    {
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      wmi::AutoRef<User::UserEntry>::Release(&v44);
      ReleaseSRWLockExclusive(v14);
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&hObject);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
      LastHrError = -2147024894;
      goto LABEL_32;
    }
  }
  else
  {
    v16 = 1;
    if ( (v7 & 0x40000000) == 0 )
    {
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      wmi::AutoRef<User::UserEntry>::Release(&v44);
      ReleaseSRWLockExclusive(v14);
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&hObject);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
      LastHrError = -2147024893;
LABEL_32:
      operator delete(0);
      return (unsigned int)LastHrError;
    }
  }
  LastHrError = JobAccessCheck(hObject, pSecurityDescriptor, 0xC0000u);
  if ( LastHrError < 0 )
  {
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
    wmi::AutoRef<User::UserEntry>::Release(&v44);
    ReleaseSRWLockExclusive(v14);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( SecurityDescriptor )
    {
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
    }
    goto LABEL_32;
  }
  v17 = v7 & 0x10;
  if ( v17 || !v16 )
    goto LABEL_34;
  LastHrError = JobAccessCheck(hObject, pSecurityDescriptor, 1u);
  if ( LastHrError < 0 )
  {
LABEL_29:
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
    wmi::AutoRef<User::UserEntry>::Release(&v44);
    ReleaseSRWLockExclusive(v14);
    goto LABEL_30;
  }
  JobMoniker::JobMoniker((JobMoniker *)&pExceptionObject, &psz, &v58);
  *(_QWORD *)&StringSecurityDescriptor.Revision = 0;
  LastHrError = JobStore::RegOpenTaskKey(
                  v15,
                  (struct JobMoniker *)&pExceptionObject,
                  (HKEY *)&StringSecurityDescriptor,
                  0x20019u);
  if ( LastHrError < 0 )
  {
LABEL_28:
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&StringSecurityDescriptor);
    JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
    goto LABEL_29;
  }
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v51);
  LastHrError = Triggers::Trigulator::StreamIn(
                  (Triggers::Trigulator *)v51,
                  *(HKEY *)&StringSecurityDescriptor.Revision,
                  2u,
                  0);
  if ( LastHrError < 0
    || (LastHrError = Triggers::Trigulator::GetBucket(
                        (Triggers::Trigulator *)v51,
                        (struct JobMoniker *)&pExceptionObject),
        LastHrError < 0) )
  {
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v51);
    goto LABEL_28;
  }
  wmi::AutoRef<User::UserEntry>::operator=(&v44, *(_QWORD *)(v55 + 64));
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v51);
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&StringSecurityDescriptor);
  JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
LABEL_34:
  StringSecurityDescriptor.SubAuthority[0] = 0;
  *(_QWORD *)&StringSecurityDescriptor.Revision = 0;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
         pSecurityDescriptor,
         1u,
         7u,
         (LPWSTR *)&StringSecurityDescriptor,
         StringSecurityDescriptor.SubAuthority) )
  {
    v21 = (unsigned __int16 *)operator new(saturated_mul(StringSecurityDescriptor.SubAuthority[0] + 1, 2u));
    v20 = StringCchCopyNW(
            v21,
            StringSecurityDescriptor.SubAuthority[0] + 1,
            *(const unsigned __int16 **)&StringSecurityDescriptor.Revision,
            StringSecurityDescriptor.SubAuthority[0]);
    if ( v20 >= 0 )
    {
      v9 = v21;
      v49 = v21;
      operator delete(0);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
      v20 = 0;
    }
    else
    {
      operator delete(v21);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
    }
  }
  else
  {
    v20 = tsched::GetLastHrError(v19, v18);
    if ( *(_QWORD *)&StringSecurityDescriptor.Revision )
      LocalFree(*(HLOCAL *)&StringSecurityDescriptor.Revision);
  }
  if ( v20 >= 0 )
  {
    StringSecurityDescriptor.SubAuthority[0] = 1;
    v22 = RpcImpersonateClient(0);
    v24 = v22;
    if ( v22 )
    {
      EventManager::EvtReport(
        v23,
        &IMPERSONATION_FAILURE,
        L"RpcServer::SetSecurity",
        v22,
        StringSecurityDescriptorLen,
        v40);
      pExceptionObject.Data4[0] = 0;
      *(_QWORD *)&pExceptionObject.Data1 = &wmi::GenericException::`vftable';
      v53 = &qword_1800A8718;
      v54 = 0;
      v55 = 0;
      v56 = v24;
      v57 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v25 = v47;
    if ( qword_1800C1728 )
      v26 = qword_1800C1728(&psz, v47);
    else
      v26 = 1;
    RpcRevertToSelf();
    if ( v26 < 0 )
      goto LABEL_70;
    StringSecurityDescriptor.SubAuthority[0] = 1;
    v27 = RpcImpersonateClient(0);
    v29 = v27;
    if ( v27 )
    {
      EventManager::EvtReport(
        v28,
        &IMPERSONATION_FAILURE,
        L"RpcServer::SetSecurity",
        v27,
        StringSecurityDescriptorLen,
        v40);
      pExceptionObject.Data4[0] = 0;
      *(_QWORD *)&pExceptionObject.Data1 = &wmi::GenericException::`vftable';
      v53 = &qword_1800A8718;
      v54 = 0;
      v55 = 0;
      v56 = v29;
      v57 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v26 = JobStore::FileSddlSet(v15, &psz, v25);
    if ( v26 < 0 )
    {
      RpcRevertToSelf();
LABEL_70:
      StringSecurityDescriptor.SubAuthority[0] = 1;
      v34 = RpcImpersonateClient(0);
      v36 = v34;
      if ( v34 )
      {
        EventManager::EvtReport(
          v35,
          &IMPERSONATION_FAILURE,
          L"RpcServer::SetSecurity",
          v34,
          StringSecurityDescriptorLen,
          v40);
        pExceptionObject.Data4[0] = 0;
        *(_QWORD *)&pExceptionObject.Data1 = &wmi::GenericException::`vftable';
        v53 = &qword_1800A8718;
        v54 = 0;
        v55 = 0;
        v56 = v36;
        v57 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      if ( JobStore::GetUseXmlStore(v15) )
      {
        *(_QWORD *)&StringSecurityDescriptor.Revision = 0;
        if ( (int)JobStore::GetXmlFileSystemPath(v15, &psz, &StringSecurityDescriptor) >= 0 )
          tsched::SetJobFileSecurityByName(*(wchar_t **)&StringSecurityDescriptor.Revision, v37, v9, v38);
        operator delete(*(void **)&StringSecurityDescriptor.Revision);
      }
      if ( qword_1800C1728 )
        qword_1800C1728(&psz, v9);
      RpcRevertToSelf();
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      wmi::AutoRef<User::UserEntry>::Release(&v44);
      ReleaseSRWLockExclusive(v14);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      if ( SecurityDescriptor )
      {
        LocalFree(SecurityDescriptor);
        SecurityDescriptor = 0;
      }
      v20 = v26;
      goto LABEL_83;
    }
    RpcRevertToSelf();
    v26 = JobSecurity::Update(&pSecurityDescriptor, SecurityDescriptor, hObject);
    if ( v26 < 0 )
      goto LABEL_70;
    if ( !v17 && v16 )
    {
      User::User(&StringSecurityDescriptor, &v44);
      if ( User::IsAlias((User *)&v44) )
      {
        v30 = (CredStore *)CredStore::g_pCommonStore;
        Account = (_QWORD *)User::GetAccount(&v44, &v47);
        v32 = *Account ? *(const unsigned __int16 **)*Account : 0LL;
        v26 = CredStore::ResolveAlias(v30, v32, (struct User *)&StringSecurityDescriptor);
        _bstr_t::~_bstr_t((_bstr_t *)&v47);
        if ( v26 < 0 )
        {
LABEL_60:
          wmi::AutoRef<User::UserEntry>::Release(&StringSecurityDescriptor);
          goto LABEL_70;
        }
      }
      RpcAutoImpersonate::RpcAutoImpersonate(
        (RpcAutoImpersonate *)StringSecurityDescriptor.SubAuthority,
        L"RpcServer::SetSecurity",
        1);
      v33 = JobMoniker::JobMoniker(&pExceptionObject, &psz, 0);
      v26 = JobStore::HammerAcl(v15, v33, (const struct User *)&StringSecurityDescriptor, &StringSecurityDescriptor);
      JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
      if ( v26 < 0 )
      {
        if ( StringSecurityDescriptor.SubAuthority[0] )
          RpcRevertToSelf();
        goto LABEL_60;
      }
      if ( StringSecurityDescriptor.SubAuthority[0] )
        RpcRevertToSelf();
      v26 = JobSecurity::AddRemovePrincipalAce(
              &pSecurityDescriptor,
              *(void **)(*(_QWORD *)&StringSecurityDescriptor.Revision + 32LL),
              0);
      if ( v26 < 0 )
        goto LABEL_60;
      wmi::AutoRef<User::UserEntry>::Release(&StringSecurityDescriptor);
    }
    v26 = JobStore::RegJobSecuritySet(v15, &psz, (struct JobSecurity *)&pSecurityDescriptor);
    if ( v26 >= 0 )
    {
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      wmi::AutoRef<User::UserEntry>::Release(&v44);
      ReleaseSRWLockExclusive(v14);
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&hObject);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
      operator delete(v9);
      return 0;
    }
    goto LABEL_70;
  }
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
  wmi::AutoRef<User::UserEntry>::Release(&v44);
  ReleaseSRWLockExclusive(v14);
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&hObject);
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
LABEL_83:
  operator delete(v9);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180023c4c  mov     [rsp-8+arg_0], rbx
0x180023c51  push    rbp
0x180023c52  push    rsi
0x180023c53  push    rdi
0x180023c54  push    r12
0x180023c56  push    r13
0x180023c58  push    r14
0x180023c5a  push    r15
0x180023c5c  lea     rbp, [rsp-230h]
0x180023c64  sub     rsp, 330h
0x180023c6b  mov     rax, cs:__security_cookie
0x180023c72  xor     rax, rsp
0x180023c75  mov     [rbp+260h+var_40], rax
0x180023c7c  mov     rsi, r8
0x180023c7f  mov     [rsp+360h+var_2F8], r8
0x180023c84  mov     rdi, rdx
0x180023c87  mov     r15, rcx
0x180023c8a  mov     ecx, 60000000h
0x180023c8f  mov     r14d, r9d
0x180023c92  or      r14d, ecx
0x180023c95  xor     r12d, r12d
0x180023c98  test    ecx, r9d
0x180023c9b  cmovnz  r14d, r9d
0x180023c9f  test    r14d, 9FFFFFEFh
0x180023ca6  jz      short loc_180023CB2
0x180023ca8  mov     eax, 80070057h
0x180023cad  jmp     loc_180024559
0x180023cb2  mov     rbx, r12
0x180023cb5  mov     [rsp+360h+var_2E8], rbx
0x180023cba  mov     [rbp+260h+psz], r12w
0x180023cbf  xor     edx, edx; Val
0x180023cc1  mov     r8d, 208h; Size
0x180023cc7  lea     rcx, [rbp+260h+var_24E]; void *
0x180023ccb  call    memset_0
0x180023cd0  mov     rdx, rdi; unsigned __int16 *
0x180023cd3  lea     rcx, [rbp+260h+psz]; this
0x180023cd7  call    ?TaskPathCanonicalize@tsched@@YAJPEAGPEBG@Z; tsched::TaskPathCanonicalize(ushort *,ushort const *)
0x180023cdc  mov     edi, eax
0x180023cde  test    eax, eax
0x180023ce0  js      loc_180023FCB
0x180023ce6  mov     [rsp+360h+SecurityDescriptorSize], r12d
0x180023ceb  mov     [rsp+360h+SecurityDescriptor], r12
0x180023cf0  test    rsi, rsi
0x180023cf3  jz      short loc_180023D23
0x180023cf5  lea     r9, [rsp+360h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180023cfa  lea     r8, [rsp+360h+SecurityDescriptor]; SecurityDescriptor
0x180023cff  mov     edx, 1; StringSDRevision
0x180023d04  mov     rcx, rsi; StringSecurityDescriptor
0x180023d07  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180023d0e  nop     dword ptr [rax+rax+00h]
0x180023d13  test    eax, eax
0x180023d15  jnz     short loc_180023D23
0x180023d17  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180023d1c  mov     edi, eax
0x180023d1e  jmp     loc_180023FC0
0x180023d23  mov     [rsp+360h+hObject], r12
0x180023d28  lea     rdx, [rsp+360h+hObject]; TokenHandle
0x180023d2d  lea     rcx, aSetsecurity; "SetSecurity"
0x180023d34  call    ?GetCallerToken@@YAJPEBGPEAPEAX@Z; GetCallerToken(ushort const *,void * *)
0x180023d39  mov     edi, eax
0x180023d3b  test    eax, eax
0x180023d3d  js      loc_180023FB5
0x180023d43  lea     rsi, [r15+10h]
0x180023d47  mov     [rbp+260h+var_2E0], rsi
0x180023d4b  mov     rcx, rsi; SRWLock
0x180023d4e  call    cs:__imp_AcquireSRWLockExclusive
0x180023d55  nop     dword ptr [rax+rax+00h]
0x180023d5a  nop
0x180023d5b  mov     r12, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x180023d62  xorps   xmm0, xmm0
0x180023d65  movups  xmmword ptr [rbp+260h+var_268.Data1], xmm0
0x180023d69  xor     r15d, r15d
0x180023d6c  mov     [rsp+360h+var_310], r15
0x180023d71  mov     [rsp+360h+pSecurityDescriptor], r15
0x180023d76  mov     [rsp+360h+var_300], r15d
0x180023d7b  lea     r8, [rsp+360h+pSecurityDescriptor]; struct JobSecurity *
0x180023d80  lea     rdx, [rbp+260h+psz]; unsigned __int16 *
0x180023d84  mov     rcx, r12; this
0x180023d87  call    ?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z; JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)
0x180023d8c  mov     edi, eax
0x180023d8e  test    eax, eax
0x180023d90  js      loc_180023F8F
0x180023d96  xor     r9d, r9d; enum JobStore::TaskIndex *
0x180023d99  lea     r8, [rbp+260h+var_268]; struct _GUID *
0x180023d9d  lea     rdx, [rbp+260h+psz]; unsigned __int16 *
0x180023da1  mov     rcx, r12; this
0x180023da4  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x180023da9  test    eax, eax
0x180023dab  js      short loc_180023E00
0x180023dad  mov     r13b, 1
0x180023db0  bt      r14d, 1Eh
0x180023db5  jb      loc_180023E4F
0x180023dbb  lea     rcx, [rsp+360h+pSecurityDescriptor]
0x180023dc0  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180023dc5  nop
0x180023dc6  lea     rcx, [rsp+360h+var_310]
0x180023dcb  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180023dd0  nop
0x180023dd1  mov     rcx, rsi; SRWLock
0x180023dd4  call    cs:__imp_ReleaseSRWLockExclusive
0x180023ddb  nop     dword ptr [rax+rax+00h]
0x180023de0  nop
0x180023de1  lea     rcx, [rsp+360h+hObject]; this
0x180023de6  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180023deb  nop
0x180023dec  lea     rcx, [rsp+360h+SecurityDescriptor]
0x180023df1  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180023df6  mov     edi, 80070003h
0x180023dfb  jmp     loc_180023FCB
0x180023e00  mov     r13b, r15b
0x180023e03  bt      r14d, 1Dh
0x180023e08  jb      short loc_180023E4F
0x180023e0a  lea     rcx, [rsp+360h+pSecurityDescriptor]
0x180023e0f  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180023e14  nop
0x180023e15  lea     rcx, [rsp+360h+var_310]
0x180023e1a  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180023e1f  nop
0x180023e20  mov     rcx, rsi; SRWLock
0x180023e23  call    cs:__imp_ReleaseSRWLockExclusive
0x180023e2a  nop     dword ptr [rax+rax+00h]
0x180023e2f  nop
0x180023e30  lea     rcx, [rsp+360h+hObject]; this
0x180023e35  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180023e3a  nop
0x180023e3b  lea     rcx, [rsp+360h+SecurityDescriptor]
0x180023e40  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180023e45  mov     edi, 80070002h
0x180023e4a  jmp     loc_180023FCB
0x180023e4f  mov     r8d, 0C0000h; DesiredAccess
0x180023e55  mov     rdx, [rsp+360h+pSecurityDescriptor]; pSecurityDescriptor
0x180023e5a  mov     rcx, [rsp+360h+hObject]; ClientToken
0x180023e5f  call    ?JobAccessCheck@@YAJPEAX0K@Z; JobAccessCheck(void *,void *,ulong)
0x180023e64  mov     edi, eax
0x180023e66  test    eax, eax
0x180023e68  jns     short loc_180023ED4
0x180023e6a  lea     rcx, [rsp+360h+pSecurityDescriptor]
0x180023e6f  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180023e74  nop
0x180023e75  lea     rcx, [rsp+360h+var_310]
0x180023e7a  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180023e7f  nop
0x180023e80  mov     rcx, rsi; SRWLock
0x180023e83  call    cs:__imp_ReleaseSRWLockExclusive
0x180023e8a  nop     dword ptr [rax+rax+00h]
0x180023e8f  nop
0x180023e90  mov     rcx, [rsp+360h+hObject]; hObject
0x180023e95  lea     rax, [rcx-1]
0x180023e99  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023e9d  ja      short loc_180023EB0
0x180023e9f  call    cs:__imp_CloseHandle
0x180023ea6  nop     dword ptr [rax+rax+00h]
0x180023eab  mov     [rsp+360h+hObject], r15
0x180023eb0  mov     rcx, [rsp+360h+SecurityDescriptor]; hMem
0x180023eb5  test    rcx, rcx
0x180023eb8  jz      loc_180023FCB
0x180023ebe  call    cs:__imp_LocalFree
0x180023ec5  nop     dword ptr [rax+rax+00h]
0x180023eca  mov     [rsp+360h+SecurityDescriptor], r15
0x180023ecf  jmp     loc_180023FCB
0x180023ed4  and     r14d, 10h
0x180023ed8  jnz     loc_18002400A
0x180023ede  test    r13b, r13b
0x180023ee1  jz      loc_18002400A
0x180023ee7  lea     r8d, [r14+1]; DesiredAccess
0x180023eeb  mov     rdx, [rsp+360h+pSecurityDescriptor]; pSecurityDescriptor
0x180023ef0  mov     rcx, [rsp+360h+hObject]; ClientToken
0x180023ef5  call    ?JobAccessCheck@@YAJPEAX0K@Z; JobAccessCheck(void *,void *,ulong)
0x180023efa  mov     edi, eax
0x180023efc  test    eax, eax
0x180023efe  js      loc_180023F8F
0x180023f04  lea     r8, [rbp+260h+var_268]; struct _GUID *
0x180023f08  lea     rdx, [rbp+260h+psz]; unsigned __int16 *
0x180023f0c  lea     rcx, [rbp+260h+pExceptionObject]; this
0x180023f10  call    ??0JobMoniker@@QEAA@PEBGAEBU_GUID@@@Z; JobMoniker::JobMoniker(ushort const *,_GUID const &)
0x180023f15  nop
0x180023f16  mov     [rsp+360h+StringSecurityDescriptor], r15
0x180023f1b  mov     r9d, 20019h; unsigned int
0x180023f21  lea     r8, [rsp+360h+StringSecurityDescriptor]; HKEY *
0x180023f26  lea     rdx, [rbp+260h+pExceptionObject]; struct JobMoniker *
0x180023f2a  mov     rcx, r12; this
0x180023f2d  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x180023f32  mov     edi, eax
0x180023f34  test    eax, eax
0x180023f36  js      short loc_180023F7A
0x180023f38  lea     rcx, [rbp+260h+var_2D8]; this
0x180023f3c  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180023f41  nop
0x180023f42  xor     r9d, r9d; unsigned __int64 *
0x180023f45  lea     r8d, [r14+2]; unsigned int
0x180023f49  mov     rdx, [rsp+360h+StringSecurityDescriptor]; HKEY
0x180023f4e  lea     rcx, [rbp+260h+var_2D8]; this
0x180023f52  call    ?StreamIn@Trigulator@Triggers@@QEAAJPEAUHKEY__@@KPEA_K@Z; Triggers::Trigulator::StreamIn(HKEY__ *,ulong,unsigned __int64 *)
0x180023f57  mov     edi, eax
0x180023f59  test    eax, eax
0x180023f5b  js      short loc_180023F70
0x180023f5d  lea     rdx, [rbp+260h+pExceptionObject]; struct JobMoniker *
0x180023f61  lea     rcx, [rbp+260h+var_2D8]; this
0x180023f65  call    ?GetBucket@Trigulator@Triggers@@QEBAJAEAVJobMoniker@@@Z; Triggers::Trigulator::GetBucket(JobMoniker &)
0x180023f6a  mov     edi, eax
0x180023f6c  test    eax, eax
0x180023f6e  jns     short loc_180023FD9
0x180023f70  lea     rcx, [rbp+260h+var_2D8]; this
0x180023f74  call    ??1Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::~Trigulator(void)
0x180023f79  nop
0x180023f7a  lea     rcx, [rsp+360h+StringSecurityDescriptor]; this
0x180023f7f  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180023f84  nop
0x180023f85  lea     rcx, [rbp+260h+pExceptionObject]; this
0x180023f89  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180023f8e  nop
0x180023f8f  lea     rcx, [rsp+360h+pSecurityDescriptor]
0x180023f94  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180023f99  nop
0x180023f9a  lea     rcx, [rsp+360h+var_310]
0x180023f9f  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180023fa4  nop
0x180023fa5  mov     rcx, rsi; SRWLock
0x180023fa8  call    cs:__imp_ReleaseSRWLockExclusive
0x180023faf  nop     dword ptr [rax+rax+00h]
0x180023fb4  nop
0x180023fb5  lea     rcx, [rsp+360h+hObject]; this
0x180023fba  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180023fbf  nop
0x180023fc0  lea     rcx, [rsp+360h+SecurityDescriptor]
0x180023fc5  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180023fca  nop
0x180023fcb  xor     ecx, ecx; void *
0x180023fcd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023fd2  mov     eax, edi
0x180023fd4  jmp     loc_180024559
0x180023fd9  mov     rdx, [rbp+260h+var_280]
0x180023fdd  mov     rdx, [rdx+40h]
0x180023fe1  lea     rcx, [rsp+360h+var_310]
0x180023fe6  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180023feb  nop
0x180023fec  lea     rcx, [rbp+260h+var_2D8]; this
0x180023ff0  call    ??1Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::~Trigulator(void)
0x180023ff5  nop
0x180023ff6  lea     rcx, [rsp+360h+StringSecurityDescriptor]; this
0x180023ffb  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180024000  nop
0x180024001  lea     rcx, [rbp+260h+pExceptionObject]; this
0x180024005  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18002400a  mov     [rsp+360h+var_328], r15d
0x18002400f  mov     [rsp+360h+StringSecurityDescriptor], r15
0x180024014  lea     rax, [rsp+360h+var_328]
0x180024019  mov     [rsp+360h+StringSecurityDescriptorLen], rax; void *
0x18002401e  lea     r9, [rsp+360h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180024023  mov     edx, 1; RequestedStringSDRevision
0x180024028  lea     r8d, [rdx+6]; SecurityInformation
0x18002402c  mov     rcx, [rsp+360h+pSecurityDescriptor]; SecurityDescriptor
0x180024031  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180024038  nop     dword ptr [rax+rax+00h]
0x18002403d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180024041  test    eax, eax
0x180024043  jnz     short loc_180024065
0x180024045  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18002404a  mov     r15d, eax
0x18002404d  mov     rcx, [rsp+360h+StringSecurityDescriptor]; hMem
0x180024052  test    rcx, rcx
0x180024055  jz      short loc_1800240D2
0x180024057  call    cs:__imp_LocalFree
0x18002405e  nop     dword ptr [rax+rax+00h]
0x180024063  jmp     short loc_1800240D2
0x180024065  mov     edx, [rsp+360h+var_328]
0x180024069  inc     edx
0x18002406b  mov     eax, 2
0x180024070  mul     rdx
0x180024073  cmovb   rax, r8
0x180024077  mov     rcx, rax; dwBytes
0x18002407a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002407f  mov     rdi, rax
0x180024082  mov     eax, [rsp+360h+var_328]
0x180024086  mov     r9d, eax; unsigned __int64
0x180024089  lea     edx, [rax+1]; unsigned __int64
0x18002408c  mov     r8, [rsp+360h+StringSecurityDescriptor]; unsigned __int16 *
0x180024091  mov     rcx, rdi; unsigned __int16 *
0x180024094  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180024099  mov     r15d, eax
0x18002409c  test    eax, eax
0x18002409e  jns     short loc_1800240B5
0x1800240a0  mov     rcx, rdi; void *
0x1800240a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800240a8  nop
0x1800240a9  lea     rcx, [rsp+360h+StringSecurityDescriptor]
0x1800240ae  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800240b3  jmp     short loc_1800240D2
0x1800240b5  mov     rbx, rdi
0x1800240b8  mov     [rsp+360h+var_2E8], rbx
0x1800240bd  xor     ecx, ecx; void *
0x1800240bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800240c4  nop
0x1800240c5  lea     rcx, [rsp+360h+StringSecurityDescriptor]
0x1800240ca  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800240cf  xor     r15d, r15d
0x1800240d2  test    r15d, r15d
0x1800240d5  jns     short loc_180024117
0x1800240d7  lea     rcx, [rsp+360h+pSecurityDescriptor]
0x1800240dc  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
  ... truncated ...
```
