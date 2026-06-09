# RpcServer::RunTask(ushort const *,ulong,ushort const * *,ulong,ulong,ushort const *,_GUID *)

- ea: `0x18004c6d0`
- end: `0x18004ceeb`
- name: `?RunTask@RpcServer@@QEAAJPEBGKPEAPEBGKK0PEAU_GUID@@@Z`
- size: `2075`
- prototype: `__int64 __fastcall(RpcServer *this, OLECHAR *p_psz, int, const unsigned __int16 **, unsigned int, DWORD SessionId, const unsigned __int16 *StringSid, struct _GUID *)`
- caller_count: `1`
- callee_count: `49`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004c670`

## callees

- `0x18000110c`
- `0x180007ddc`
- `0x180007ec0`
- `0x18000b4e0`
- `0x18000dc30`
- `0x18000e510`
- `0x180015740`
- `0x1800199c0`
- `0x18001a430`
- `0x18001ec90`
- `0x180021300`
- `0x18002132c`
- `0x180022600`
- `0x1800230c0`
- `0x1800244ac`
- `0x1800245dc`
- `0x180024690`
- `0x180025040`
- `0x180025310`
- `0x1800291c0`
- `0x18002ab20`
- `0x18002ab90`
- `0x18002af2c`
- `0x18002b1d0`
- `0x18002f040`
- `0x18002f3e0`
- `0x180031c84`
- `0x1800339c0`
- `0x180039d00`
- `0x180039d30`
- `0x180040590`
- `0x180040900`
- `0x180040b70`
- `0x180041af8`
- `0x180041f20`
- `0x18004510c`
- `0x18004a8f0`
- `0x18004ac58`
- `0x18004c6d0`
- `0x180050f58`
- `0x1800517ec`
- `0x180051b3c`
- `0x180051f48`
- `0x180064d20`
- `0x180066064`
- `0x180067648`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004c849`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004c849`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004c86f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004c8ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004c96a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004c86f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004c8ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004c96a`
- `RPCRT4!RpcRevertToSelf` at `0x18004c9e9`
- `RPCRT4!RpcRevertToSelf` at `0x18004c9fb`
- `RPCRT4!RpcRevertToSelf` at `0x18004c9e9`
- `RPCRT4!RpcRevertToSelf` at `0x18004c9fb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004ca21`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004ca21`

## string_xrefs

- `0x18004c827`: `RunTask`
- `0x18004c9bb`: `RpcServer::RunTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RpcServer::RunTask(
        RpcServer *this,
        OLECHAR *p_psz,
        int a3,
        const unsigned __int16 **a4,
        unsigned int a5,
        DWORD SessionId,
        const unsigned __int16 *StringSid,
        struct _GUID *a8)
{
  __int64 v10; // rbx
  __int64 v11; // rcx
  void *v12; // r8
  int v13; // r9d
  signed int CallerToken; // edi
  DWORD v15; // r13d
  const unsigned __int16 *v16; // r8
  const unsigned __int16 *v17; // rdx
  RTL_SRWLOCK *v18; // rsi
  JobStore *v19; // r15
  const unsigned __int16 *Path; // rax
  const unsigned __int16 *v21; // rax
  JobMoniker *v22; // rax
  unsigned int v23; // esi
  signed int LastError; // eax
  char v25; // r15
  unsigned int v26; // edi
  __int64 v27; // rax
  unsigned int v28; // esi
  __int64 v29; // r14
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 *v32; // rcx
  struct _GUID *v33; // rbx
  const unsigned __int16 *v34; // rax
  const struct _EVENT_DESCRIPTOR *v35; // rdx
  EventManager *v36; // rcx
  __int64 *v38; // [rsp+28h] [rbp-D8h]
  const struct _GUID *v39; // [rsp+30h] [rbp-D0h]
  PSID Sid; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  enum _SID_NAME_USE v44[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v51[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID *v52; // [rsp+C0h] [rbp-40h]
  _BYTE v53[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v54[24]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v55[56]; // [rsp+F0h] [rbp-10h] BYREF
  struct _GUID v56; // [rsp+128h] [rbp+28h] BYREF
  GUID iid; // [rsp+138h] [rbp+38h] BYREF
  __int64 v58; // [rsp+158h] [rbp+58h]
  _BYTE v59[40]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v60[12]; // [rsp+188h] [rbp+88h] BYREF
  OLECHAR psz; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v62[526]; // [rsp+1A2h] [rbp+A2h] BYREF

  v51[0] = a4;
  LODWORD(v43) = a3;
  v52 = a8;
  std::map<_bstr_t,_bstr_t>::map<_bstr_t,_bstr_t>(v53);
  v50 = 0;
  v49 = 0;
  v48 = 0;
  v46 = 0;
  v45 = 0;
  v41 = 0;
  v10 = 0;
  v42 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v55);
  Actions::ActionCollection::ActionCollection((Actions::ActionCollection *)v54);
  TokenHandle = 0;
  JobMoniker::JobMoniker(&iid, p_psz, 0);
  if ( (unsigned int)dword_1800BC358 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v11,
      byte_1800ADB41);
  if ( (a5 & 0xFFFFFFF0) != 0 )
  {
    CallerToken = -2147024809;
    v15 = SessionId;
    goto LABEL_93;
  }
  if ( (a5 & 4) != 0 )
  {
    v15 = SessionId;
    if ( ((SessionId + 1) & 0xFFFFFFFE) == 0 )
    {
LABEL_7:
      CallerToken = -2147024809;
      goto LABEL_93;
    }
  }
  else
  {
    v15 = -1;
  }
  psz = 0;
  memset_0(v62, 0, 0x208u);
  CallerToken = tsched::TaskPathCanonicalize((tsched *)&psz, p_psz, v16);
  if ( CallerToken >= 0 )
  {
    p_psz = &psz;
    if ( tsched::IsRoot((tsched *)&psz, v17) )
      goto LABEL_7;
    CallerToken = GetCallerToken(L"RunTask", &TokenHandle);
    if ( CallerToken >= 0 )
    {
      v18 = (RTL_SRWLOCK *)((char *)this + 16);
      *(_QWORD *)v44 = v18;
      AcquireSRWLockShared(v18);
      CallerToken = TaskAccessCheck(TokenHandle, &psz, 1u);
      if ( CallerToken < 0 )
      {
        ReleaseSRWLockShared(v18);
        goto LABEL_93;
      }
      v19 = JobStore::m_pCommonStore;
      v56 = 0;
      Path = JobMoniker::GetPath((JobMoniker *)&iid);
      CallerToken = JobStore::RegGetTreeInfo(v19, Path, &v56, 0);
      if ( CallerToken < 0 )
        goto LABEL_15;
      v21 = JobMoniker::GetPath((JobMoniker *)&iid);
      v22 = JobMoniker::JobMoniker((JobMoniker *)v59, v21, &v56);
      JobMoniker::operator=(&iid, v22);
      JobMoniker::~JobMoniker((JobMoniker *)v59);
      Sid = 0;
      CallerToken = JobStore::RegOpenTaskKey(v19, (struct JobMoniker *)&iid, (HKEY *)&Sid, 0x20019u);
      if ( CallerToken < 0
        || (CallerToken = Triggers::Trigulator::StreamIn((Triggers::Trigulator *)v55, (HKEY)Sid, 3u, 0), CallerToken < 0)
        || (CallerToken = Triggers::Trigulator::GetBucket((Triggers::Trigulator *)v55, (struct JobMoniker *)&iid),
            CallerToken < 0)
        || (CallerToken = Actions::ActionCollection::StreamIn((Actions::ActionCollection *)v54, (HKEY)Sid, 0),
            CallerToken < 0) )
      {
        wmi::AutoRegKey::Close((wmi::AutoRegKey *)&Sid);
LABEL_15:
        ReleaseSRWLockShared(v18);
LABEL_92:
        p_psz = &psz;
        goto LABEL_93;
      }
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&Sid);
      ReleaseSRWLockShared(v18);
      if ( (*(_DWORD *)(v58 + 16) & 0x100) == 0 )
      {
        CallerToken = -2147216600;
        goto LABEL_92;
      }
      if ( (*(_DWORD *)(v58 + 16) & 0x400000) == 0 )
      {
        CallerToken = -2147216602;
        goto LABEL_92;
      }
      v23 = *(_DWORD *)(v58 + 16);
      wmi::AutoRef<User::UserEntry>::operator=(&v46, *(_QWORD *)(v58 + 64));
      if ( (a5 & 2) != 0 )
        v23 = v23 & 0xFBFFC30D | 0x400;
      RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)v44, L"RpcServer::RunTask", 1);
      CallerToken = User::FromImpersonationToken((struct User *)&v45, 0);
      if ( CallerToken < 0 )
      {
        if ( v44[0] )
          RpcRevertToSelf();
        goto LABEL_92;
      }
      if ( v44[0] )
        RpcRevertToSelf();
      if ( StringSid )
      {
        if ( (a5 & 8) != 0 )
        {
          Sid = 0;
          if ( !ConvertStringSidToSidW(StringSid, &Sid) )
          {
            LastError = GetLastError();
            CallerToken = LastError;
            if ( LastError > 0 )
              CallerToken = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_35;
          }
          CallerToken = User::FromSid((struct User *)&v42, Sid, SidTypeUnknown);
          if ( CallerToken < 0 )
          {
LABEL_35:
            tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&Sid);
            goto LABEL_92;
          }
          tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&Sid);
        }
        else
        {
          CallerToken = User::FromUsername((struct User *)&v42, StringSid);
          if ( CallerToken < 0 )
            goto LABEL_92;
        }
        v10 = v42;
      }
      if ( (a5 & 4) != 0 )
      {
        CallerToken = User::FromUserSession((struct User *)&v48, v15, v12);
        if ( CallerToken < 0 )
          goto LABEL_92;
      }
      wmi::AutoRef<User::UserEntry>::operator=(&v41, v46);
      v25 = 0;
      if ( (a5 & 4) != 0 )
      {
        if ( v10 )
        {
          if ( !(unsigned __int8)User::operator==(&v48, &v42) )
          {
LABEL_45:
            CallerToken = -2147024809;
            goto LABEL_92;
          }
          v10 = v42;
        }
        v23 = v23 & 0xFFF03FFF | 0x10000;
        wmi::AutoRef<User::UserEntry>::operator=(&v41, v48);
        v25 = 1;
      }
      v26 = a5;
      if ( (a5 & 1) != 0 )
      {
        if ( (a5 & 4) != 0 && !(unsigned __int8)User::operator==(&v48, &v45) )
          goto LABEL_45;
        if ( v10 )
        {
          if ( !(unsigned __int8)User::operator==(&v45, &v42) )
            goto LABEL_45;
          v10 = v42;
        }
        v23 = v23 & 0xFFF03FFF | 0x10000;
        wmi::AutoRef<User::UserEntry>::operator=(&v41, v45);
        v25 = 1;
      }
      if ( v10 )
      {
        v23 = v23 & 0xFFF03FFF | 0x10000;
        wmi::AutoRef<User::UserEntry>::operator=(&v41, v10);
        v25 = 1;
      }
      if ( !(unsigned __int8)User::operator==(&v45, &v41) )
      {
        v27 = User::User(&Sid, &v41);
        CallerToken = IsPrincipalAllowed(v27, v23);
        if ( CallerToken < 0 )
        {
          if ( (unsigned __int8)User::operator==(&v41, &v46) )
          {
            CallerToken = TaskAccessCheck(TokenHandle, &psz, 0x20u);
            if ( CallerToken < 0 )
              goto LABEL_92;
          }
          else
          {
            if ( (a5 & 4) == 0 )
              goto LABEL_92;
            CallerToken = TaskAccessCheck(TokenHandle, &psz, 0x20u);
            if ( CallerToken < 0 )
              goto LABEL_92;
            v44[0] = 0;
            LODWORD(Sid) = 0;
            CallerToken = User::LookupType((User *)&v46, v44);
            if ( CallerToken < 0 )
              goto LABEL_92;
            CallerToken = User::LookupType((User *)&v41, (enum _SID_NAME_USE *)&Sid);
            if ( CallerToken < 0 )
              goto LABEL_92;
            SLODWORD(v11) = v44[0];
            if ( ((v44[0] - 2) & 0xFFFFFFFC) != 0
              || v44[0] == SidTypeDomain
              || (_DWORD)Sid != 1
              || !RpcServer::UserGroupCheck(v15, (const struct User *)&v41, (const struct User *)&v46) )
            {
              CallerToken = -2147024891;
              goto LABEL_92;
            }
          }
        }
        v26 = a5;
      }
      v28 = v43;
      if ( (unsigned int)v43 <= 0x20 )
      {
        v11 = 0;
        if ( !(_DWORD)v43 )
        {
LABEL_71:
          if ( (*(_DWORD *)(v58 + 16) & 0x2000000) != 0 )
          {
            v43 = 0;
            v32 = &v43;
            if ( v25 )
              v32 = &v41;
            v33 = v52;
            LODWORD(v39) = v15;
            v38 = v32;
            CallerToken = (*((__int64 (__fastcall **)(void ***, GUID *, _BYTE *, _BYTE *, unsigned int))UbpmProxySingleton::s_singleton[0]
                           + 4))(
                            UbpmProxySingleton::s_singleton,
                            &iid,
                            v55,
                            v54,
                            v26);
            if ( CallerToken < 0 )
            {
              wmi::AutoRef<User::UserEntry>::Release(&v43);
              goto LABEL_92;
            }
            wmi::AutoRef<User::UserEntry>::Release(&v43);
          }
          else
          {
            CallerToken = -2147467263;
            v33 = v52;
          }
          v34 = *(const unsigned __int16 **)User::GetAccount(&v41, v51);
          if ( v34 )
            v34 = *(const unsigned __int16 **)v34;
          EventManager::EvtReport(v36, v35, &psz, v33, v34, v38, v39);
          _bstr_t::~_bstr_t((_bstr_t *)v51);
          goto LABEL_92;
        }
        v29 = v51[0];
        while ( *(_QWORD *)(v51[0] + 8 * v11) )
        {
          v11 = (unsigned int)(v11 + 1);
          if ( (unsigned int)v11 >= (unsigned int)v43 )
          {
            v30 = 0;
            do
            {
              if ( (int)StringCchPrintfW(v60, 0xAu, L"Arg%d", (unsigned int)v30) >= 0 )
              {
                _bstr_t::operator=(&v50, v60);
                _bstr_t::operator=(&v49, *(_QWORD *)(v29 + 8 * v30));
                v31 = std::pair<_bstr_t,_bstr_t>::pair<_bstr_t,_bstr_t>(&v56, &v50, &v49);
                std::_Tree<std::_Tmap_traits<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>,0>>::insert(
                  v53,
                  v51,
                  v31);
                std::pair<_bstr_t const,_bstr_t>::~pair<_bstr_t const,_bstr_t>((_bstr_t *)&v56);
              }
              v30 = (unsigned int)(v30 + 1);
            }
            while ( (unsigned int)v30 < v28 );
            goto LABEL_71;
          }
        }
      }
      goto LABEL_45;
    }
  }
LABEL_93:
  if ( (unsigned int)dword_1800BC358 > 4 )
  {
    LODWORD(v43) = v15;
    LODWORD(Sid) = CallerToken;
    v51[0] = p_psz;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)&byte_1800ADBDF,
      (_DWORD)v12,
      v13,
      (__int64)v51,
      (__int64)&Sid,
      (__int64)&v43);
  }
  JobMoniker::~JobMoniker((JobMoniker *)&iid);
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v54);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v55);
  wmi::AutoRef<User::UserEntry>::Release(&v42);
  wmi::AutoRef<User::UserEntry>::Release(&v41);
  wmi::AutoRef<User::UserEntry>::Release(&v45);
  wmi::AutoRef<User::UserEntry>::Release(&v46);
  wmi::AutoRef<User::UserEntry>::Release(&v48);
  _bstr_t::~_bstr_t((_bstr_t *)&v49);
  _bstr_t::~_bstr_t((_bstr_t *)&v50);
  std::_Tree<std::_Tmap_traits<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>,0>>::~_Tree<std::_Tmap_traits<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>,0>>(v53);
  return (unsigned int)CallerToken;
}

```

## disassembly

```asm
0x18004c6d0  mov     [rsp-8+arg_0], rbx
0x18004c6d5  push    rbp
0x18004c6d6  push    rsi
0x18004c6d7  push    rdi
0x18004c6d8  push    r12
0x18004c6da  push    r13
0x18004c6dc  push    r14
0x18004c6de  push    r15
0x18004c6e0  lea     rbp, [rsp-2C0h]
0x18004c6e8  sub     rsp, 3C0h
0x18004c6ef  mov     rax, cs:__security_cookie
0x18004c6f6  xor     rax, rsp
0x18004c6f9  mov     [rbp+2F0h+var_40], rax
0x18004c700  mov     [rbp+2F0h+var_340], r9
0x18004c704  mov     dword ptr [rsp+3F0h+var_380], r8d
0x18004c709  mov     r15, rdx
0x18004c70c  mov     rsi, rcx
0x18004c70f  mov     r12, [rbp+2F0h+StringSid]
0x18004c716  mov     rax, [rbp+2F0h+arg_38]
0x18004c71d  mov     [rbp+2F0h+var_330], rax
0x18004c721  lea     rcx, [rbp+2F0h+var_328]
0x18004c725  call    ??0?$map@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@@std@@QEAA@XZ; std::map<_bstr_t,_bstr_t>::map<_bstr_t,_bstr_t>(void)
0x18004c72a  nop
0x18004c72b  xor     edi, edi
0x18004c72d  mov     [rbp+2F0h+var_348], rdi
0x18004c731  mov     [rbp+2F0h+var_350], rdi
0x18004c735  mov     [rbp+2F0h+var_358], rdi
0x18004c739  mov     [rbp+2F0h+var_368], rdi
0x18004c73d  mov     [rbp+2F0h+var_370], rdi
0x18004c741  mov     [rsp+3F0h+var_390], rdi
0x18004c746  mov     ebx, edi
0x18004c748  mov     [rsp+3F0h+var_388], rbx
0x18004c74d  lea     rcx, [rbp+2F0h+var_300]; this
0x18004c751  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x18004c756  nop
0x18004c757  lea     rcx, [rbp+2F0h+var_318]; this
0x18004c75b  call    ??0ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::ActionCollection(void)
0x18004c760  nop
0x18004c761  mov     [rbp+2F0h+TokenHandle], rdi
0x18004c765  xor     r8d, r8d; unsigned __int16 *
0x18004c768  mov     rdx, r15; psz
0x18004c76b  lea     rcx, [rbp+2F0h+iid]; lpiid
0x18004c76f  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18004c774  nop
0x18004c775  mov     eax, cs:dword_1800BC358
0x18004c77b  cmp     eax, 5
0x18004c77e  jbe     short loc_18004C78C
0x18004c780  lea     rdx, byte_1800ADB41
0x18004c787  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18004c78c  mov     eax, [rbp+2F0h+arg_20]
0x18004c792  test    eax, 0FFFFFFF0h
0x18004c797  jz      short loc_18004C7AA
0x18004c799  mov     edi, 80070057h
0x18004c79e  mov     r13d, [rbp+2F0h+SessionId]
0x18004c7a5  jmp     loc_18004CE04
0x18004c7aa  mov     r14d, eax
0x18004c7ad  and     r14d, 4
0x18004c7b1  jz      short loc_18004C7CF
0x18004c7b3  mov     r13d, [rbp+2F0h+SessionId]
0x18004c7ba  lea     eax, [r13+1]
0x18004c7be  test    eax, 0FFFFFFFEh
0x18004c7c3  jnz     short loc_18004C7D3
0x18004c7c5  mov     edi, 80070057h
0x18004c7ca  jmp     loc_18004CE04
0x18004c7cf  or      r13d, 0FFFFFFFFh
0x18004c7d3  mov     [rbp+2F0h+psz], di
0x18004c7da  xor     edx, edx; Val
0x18004c7dc  mov     r8d, 208h; Size
0x18004c7e2  lea     rcx, [rbp+2F0h+var_24E]; void *
0x18004c7e9  call    memset_0
0x18004c7ee  mov     rdx, r15; unsigned __int16 *
0x18004c7f1  lea     rcx, [rbp+2F0h+psz]; this
0x18004c7f8  call    ?TaskPathCanonicalize@tsched@@YAJPEAGPEBG@Z; tsched::TaskPathCanonicalize(ushort *,ushort const *)
0x18004c7fd  mov     edi, eax
0x18004c7ff  test    eax, eax
0x18004c801  js      loc_18004CE04
0x18004c807  lea     r15, [rbp+2F0h+psz]
0x18004c80e  mov     [rsp+3F0h+var_3A0], r15
0x18004c813  lea     rcx, [rbp+2F0h+psz]; this
0x18004c81a  call    ?IsRoot@tsched@@YA_NPEBG@Z; tsched::IsRoot(ushort const *)
0x18004c81f  test    al, al
0x18004c821  jnz     short loc_18004C7C5
0x18004c823  lea     rdx, [rbp+2F0h+TokenHandle]; TokenHandle
0x18004c827  lea     rcx, aRuntask; "RunTask"
0x18004c82e  call    ?GetCallerToken@@YAJPEBGPEAPEAX@Z; GetCallerToken(ushort const *,void * *)
0x18004c833  mov     edi, eax
0x18004c835  test    eax, eax
0x18004c837  js      loc_18004CE04
0x18004c83d  add     rsi, 10h
0x18004c841  mov     qword ptr [rsp+3F0h+var_378], rsi
0x18004c846  mov     rcx, rsi; SRWLock
0x18004c849  call    cs:__imp_AcquireSRWLockShared
0x18004c84f  nop
0x18004c850  mov     r8d, 1; DesiredAccess
0x18004c856  lea     rdx, [rbp+2F0h+psz]; psz
0x18004c85d  mov     rcx, [rbp+2F0h+TokenHandle]; ClientToken
0x18004c861  call    ?TaskAccessCheck@@YAJPEAXPEBGK@Z; TaskAccessCheck(void *,ushort const *,ulong)
0x18004c866  mov     edi, eax
0x18004c868  test    eax, eax
0x18004c86a  jns     short loc_18004C87A
0x18004c86c  mov     rcx, rsi; SRWLock
0x18004c86f  call    cs:__imp_ReleaseSRWLockShared
0x18004c875  jmp     loc_18004CE04
0x18004c87a  mov     r15, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18004c881  xorps   xmm0, xmm0
0x18004c884  movups  xmmword ptr [rbp+2F0h+var_2C8.Data1], xmm0
0x18004c888  lea     rcx, [rbp+2F0h+iid]; this
0x18004c88c  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18004c891  mov     rdx, rax; unsigned __int16 *
0x18004c894  xor     r9d, r9d; enum JobStore::TaskIndex *
0x18004c897  lea     r8, [rbp+2F0h+var_2C8]; struct _GUID *
0x18004c89b  mov     rcx, r15; this
0x18004c89e  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x18004c8a3  mov     edi, eax
0x18004c8a5  test    eax, eax
0x18004c8a7  jns     short loc_18004C8B7
0x18004c8a9  mov     rcx, rsi; SRWLock
0x18004c8ac  call    cs:__imp_ReleaseSRWLockShared
0x18004c8b2  jmp     loc_18004CDFF
0x18004c8b7  lea     rcx, [rbp+2F0h+iid]; this
0x18004c8bb  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18004c8c0  mov     rdx, rax; unsigned __int16 *
0x18004c8c3  lea     r8, [rbp+2F0h+var_2C8]; struct _GUID *
0x18004c8c7  lea     rcx, [rbp+2F0h+var_290]; this
0x18004c8cb  call    ??0JobMoniker@@QEAA@PEBGAEBU_GUID@@@Z; JobMoniker::JobMoniker(ushort const *,_GUID const &)
0x18004c8d0  mov     rdx, rax
0x18004c8d3  lea     rcx, [rbp+2F0h+iid]
0x18004c8d7  call    ??4JobMoniker@@QEAAAEAV0@AEBV0@@Z; JobMoniker::operator=(JobMoniker const &)
0x18004c8dc  lea     rcx, [rbp+2F0h+var_290]; this
0x18004c8e0  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18004c8e5  mov     [rsp+3F0h+Sid], 0
0x18004c8ee  mov     r9d, 20019h; unsigned int
0x18004c8f4  lea     r8, [rsp+3F0h+Sid]; HKEY *
0x18004c8f9  lea     rdx, [rbp+2F0h+iid]; struct JobMoniker *
0x18004c8fd  mov     rcx, r15; this
0x18004c900  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x18004c905  mov     edi, eax
0x18004c907  test    eax, eax
0x18004c909  jns     short loc_18004C917
0x18004c90b  lea     rcx, [rsp+3F0h+Sid]; this
0x18004c910  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18004c915  jmp     short loc_18004C8A9
0x18004c917  xor     r9d, r9d; unsigned __int64 *
0x18004c91a  lea     r8d, [r9+3]; unsigned int
0x18004c91e  mov     rdx, [rsp+3F0h+Sid]; HKEY
0x18004c923  lea     rcx, [rbp+2F0h+var_300]; this
0x18004c927  call    ?StreamIn@Trigulator@Triggers@@QEAAJPEAUHKEY__@@KPEA_K@Z; Triggers::Trigulator::StreamIn(HKEY__ *,ulong,unsigned __int64 *)
0x18004c92c  mov     edi, eax
0x18004c92e  test    eax, eax
0x18004c930  js      short loc_18004C90B
0x18004c932  lea     rdx, [rbp+2F0h+iid]; struct JobMoniker *
0x18004c936  lea     rcx, [rbp+2F0h+var_300]; this
0x18004c93a  call    ?GetBucket@Trigulator@Triggers@@QEBAJAEAVJobMoniker@@@Z; Triggers::Trigulator::GetBucket(JobMoniker &)
0x18004c93f  mov     edi, eax
0x18004c941  test    eax, eax
0x18004c943  js      short loc_18004C90B
0x18004c945  xor     r8d, r8d; unsigned __int16 *
0x18004c948  mov     rdx, [rsp+3F0h+Sid]; hKey
0x18004c94d  lea     rcx, [rbp+2F0h+var_318]; this
0x18004c951  call    ?StreamIn@ActionCollection@Actions@@QEAAJPEAUHKEY__@@PEAG@Z; Actions::ActionCollection::StreamIn(HKEY__ *,ushort *)
0x18004c956  mov     edi, eax
0x18004c958  lea     rcx, [rsp+3F0h+Sid]; this
0x18004c95d  test    eax, eax
0x18004c95f  js      short loc_18004C910
0x18004c961  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18004c966  nop
0x18004c967  mov     rcx, rsi; SRWLock
0x18004c96a  call    cs:__imp_ReleaseSRWLockShared
0x18004c970  mov     rdx, [rbp+2F0h+var_298]
0x18004c974  test    dword ptr [rdx+10h], 100h
0x18004c97b  jz      loc_18004CDFA
0x18004c981  test    dword ptr [rdx+10h], 400000h
0x18004c988  jz      loc_18004CDF3
0x18004c98e  mov     esi, [rdx+10h]
0x18004c991  mov     rdx, [rdx+40h]
0x18004c995  lea     rcx, [rbp+2F0h+var_368]
0x18004c999  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18004c99e  mov     r15d, [rbp+2F0h+arg_20]
0x18004c9a5  test    r15b, 2
0x18004c9a9  jz      short loc_18004C9B5
0x18004c9ab  and     esi, 0FBFFC70Dh
0x18004c9b1  bts     esi, 0Ah
0x18004c9b5  mov     r8d, 1; int
0x18004c9bb  lea     rdx, aRpcserverRunta; "RpcServer::RunTask"
0x18004c9c2  lea     rcx, [rsp+3F0h+var_378]; this
0x18004c9c7  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x18004c9cc  nop
0x18004c9cd  xor     edx, edx; void *
0x18004c9cf  lea     rcx, [rbp+2F0h+var_370]; struct User *
0x18004c9d3  call    ?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z; User::FromImpersonationToken(User &,void *)
0x18004c9d8  mov     edi, eax
0x18004c9da  test    eax, eax
0x18004c9dc  jns     short loc_18004C9F4
0x18004c9de  cmp     [rsp+3F0h+var_378], 0
0x18004c9e3  jz      loc_18004CDFF
0x18004c9e9  call    cs:__imp_RpcRevertToSelf
0x18004c9ef  jmp     loc_18004CDFF
0x18004c9f4  cmp     [rsp+3F0h+var_378], 0
0x18004c9f9  jz      short loc_18004CA01
0x18004c9fb  call    cs:__imp_RpcRevertToSelf
0x18004ca01  test    r12, r12
0x18004ca04  jz      loc_18004CA92
0x18004ca0a  test    r15b, 8
0x18004ca0e  jz      short loc_18004CA76
0x18004ca10  mov     [rsp+3F0h+Sid], 0
0x18004ca19  lea     rdx, [rsp+3F0h+Sid]; Sid
0x18004ca1e  mov     rcx, r12; StringSid
0x18004ca21  call    cs:__imp_ConvertStringSidToSidW
0x18004ca27  test    eax, eax
0x18004ca29  jnz     short loc_18004CA4F
0x18004ca2b  call    cs:__imp_GetLastError
0x18004ca31  mov     edi, eax
0x18004ca33  test    eax, eax
0x18004ca35  jle     short loc_18004CA40
0x18004ca37  movzx   edi, ax
0x18004ca3a  or      edi, 80070000h
0x18004ca40  lea     rcx, [rsp+3F0h+Sid]
0x18004ca45  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18004ca4a  jmp     loc_18004CDFF
0x18004ca4f  mov     r8d, 8; enum _SID_NAME_USE
0x18004ca55  mov     rdx, [rsp+3F0h+Sid]; void *
0x18004ca5a  lea     rcx, [rsp+3F0h+var_388]; this
0x18004ca5f  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x18004ca64  mov     edi, eax
0x18004ca66  lea     rcx, [rsp+3F0h+Sid]
0x18004ca6b  test    eax, eax
0x18004ca6d  js      short loc_18004CA45
0x18004ca6f  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18004ca74  jmp     short loc_18004CA8D
0x18004ca76  mov     rdx, r12; lpAccountName
0x18004ca79  lea     rcx, [rsp+3F0h+var_388]; this
0x18004ca7e  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x18004ca83  mov     edi, eax
0x18004ca85  test    eax, eax
0x18004ca87  js      loc_18004CDFF
0x18004ca8d  mov     rbx, [rsp+3F0h+var_388]
0x18004ca92  test    r14d, r14d
0x18004ca95  jz      short loc_18004CAAD
0x18004ca97  mov     edx, r13d; SessionId
0x18004ca9a  lea     rcx, [rbp+2F0h+var_358]; this
0x18004ca9e  call    ?FromUserSession@User@@SAJAEAV1@KPEAX@Z; User::FromUserSession(User &,ulong,void *)
0x18004caa3  mov     edi, eax
0x18004caa5  test    eax, eax
0x18004caa7  js      loc_18004CDFF
0x18004caad  mov     rdx, [rbp+2F0h+var_368]
0x18004cab1  lea     rcx, [rsp+3F0h+var_390]
0x18004cab6  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18004cabb  xor     r15b, r15b
0x18004cabe  mov     r12d, 0FFF13FFFh
0x18004cac4  test    r14d, r14d
0x18004cac7  jz      short loc_18004CB07
0x18004cac9  test    rbx, rbx
0x18004cacc  jz      short loc_18004CAEF
0x18004cace  lea     rdx, [rsp+3F0h+var_388]
0x18004cad3  lea     rcx, [rbp+2F0h+var_358]
0x18004cad7  call    ??8User@@QEBA_NAEBV0@@Z; User::operator==(User const &)
0x18004cadc  test    al, al
0x18004cade  jnz     short loc_18004CAEA
0x18004cae0  mov     edi, 80070057h
0x18004cae5  jmp     loc_18004CDFF
0x18004caea  mov     rbx, [rsp+3F0h+var_388]
0x18004caef  and     esi, r12d
0x18004caf2  bts     esi, 10h
0x18004caf6  mov     rdx, [rbp+2F0h+var_358]
0x18004cafa  lea     rcx, [rsp+3F0h+var_390]
0x18004caff  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18004cb04  mov     r15b, 1
0x18004cb07  mov     edi, [rbp+2F0h+arg_20]
0x18004cb0d  test    dil, 1
0x18004cb11  jz      short loc_18004CB5D
0x18004cb13  test    r14d, r14d
0x18004cb16  jz      short loc_18004CB29
0x18004cb18  lea     rdx, [rbp+2F0h+var_370]
0x18004cb1c  lea     rcx, [rbp+2F0h+var_358]
0x18004cb20  call    ??8User@@QEBA_NAEBV0@@Z; User::operator==(User const &)
0x18004cb25  test    al, al
0x18004cb27  jz      short loc_18004CAE0
0x18004cb29  test    rbx, rbx
0x18004cb2c  jz      short loc_18004CB45
0x18004cb2e  lea     rdx, [rsp+3F0h+var_388]
0x18004cb33  lea     rcx, [rbp+2F0h+var_370]
0x18004cb37  call    ??8User@@QEBA_NAEBV0@@Z; User::operator==(User const &)
0x18004cb3c  test    al, al
0x18004cb3e  jz      short loc_18004CAE0
0x18004cb40  mov     rbx, [rsp+3F0h+var_388]
0x18004cb45  and     esi, r12d
0x18004cb48  bts     esi, 10h
0x18004cb4c  mov     rdx, [rbp+2F0h+var_370]
0x18004cb50  lea     rcx, [rsp+3F0h+var_390]
0x18004cb55  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18004cb5a  mov     r15b, 1
0x18004cb5d  test    rbx, rbx
0x18004cb60  jz      short loc_18004CB79
0x18004cb62  and     esi, r12d
0x18004cb65  bts     esi, 10h
0x18004cb69  mov     rdx, rbx
0x18004cb6c  lea     rcx, [rsp+3F0h+var_390]
0x18004cb71  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18004cb76  mov     r15b, 1
0x18004cb79  lea     rdx, [rsp+3F0h+var_390]
  ... truncated ...
```
