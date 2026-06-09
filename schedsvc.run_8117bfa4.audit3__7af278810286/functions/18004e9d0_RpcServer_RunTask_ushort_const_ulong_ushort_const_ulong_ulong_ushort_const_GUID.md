# RpcServer::RunTask(ushort const *,ulong,ushort const * *,ulong,ulong,ushort const *,_GUID *)

- ea: `0x18004e9d0`
- end: `0x18004f21c`
- name: `?RunTask@RpcServer@@QEAAJPEBGKPEAPEBGKK0PEAU_GUID@@@Z`
- size: `2124`
- prototype: `int(RpcServer *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 **, unsigned int, unsigned int, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `49`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004e970`

## callees

- `0x180001114`
- `0x180001f8c`
- `0x180002260`
- `0x180007c7c`
- `0x18000a460`
- `0x18000ba20`
- `0x18000bb10`
- `0x18000fe50`
- `0x18000ff40`
- `0x180011e40`
- `0x1800138d8`
- `0x180013a90`
- `0x180015030`
- `0x180017074`
- `0x180017740`
- `0x18001ea40`
- `0x18001f060`
- `0x18001fe10`
- `0x180020110`
- `0x180024590`
- `0x1800246a8`
- `0x180024730`
- `0x180025a3c`
- `0x180025e70`
- `0x18002b210`
- `0x18002db40`
- `0x18002db74`
- `0x180030620`
- `0x180037490`
- `0x18003be50`
- `0x180041610`
- `0x180042200`
- `0x180043478`
- `0x180043ffc`
- `0x1800441c0`
- `0x180044280`
- `0x180047070`
- `0x18004d0cc`
- `0x18004e9d0`
- `0x1800534c8`
- `0x180053d9c`
- `0x180054130`
- `0x1800545c8`
- `0x180067df0`
- `0x1800691e8`
- `0x18006a8f4`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ed55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ed55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004eb49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004eb49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004eb75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004ebb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004ec7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004eb75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004ebb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004ec7c`
- `RPCRT4!RpcRevertToSelf` at `0x18004ed01`
- `RPCRT4!RpcRevertToSelf` at `0x18004ed19`
- `RPCRT4!RpcRevertToSelf` at `0x18004ed01`
- `RPCRT4!RpcRevertToSelf` at `0x18004ed19`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004ed45`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004ed45`

## string_xrefs

- `0x18004ecd3`: `RpcServer::RunTask`
- `0x18004eb27`: `RunTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
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
  int CallerToken; // edi
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
  User *v27; // rax
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
  HANDLE ClientToken; // [rsp+90h] [rbp-70h] BYREF
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
  ClientToken = 0;
  JobMoniker::JobMoniker(&iid, p_psz, 0);
  if ( (unsigned int)dword_1800C0358 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v11,
      byte_1800B1B89);
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
    CallerToken = GetCallerToken(L"RunTask", &ClientToken);
    if ( CallerToken >= 0 )
    {
      v18 = (RTL_SRWLOCK *)((char *)this + 16);
      *(_QWORD *)v44 = v18;
      AcquireSRWLockShared(v18);
      CallerToken = TaskAccessCheck(ClientToken, &psz, 1u);
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
          if ( !(unsigned __int8)User::operator==((User *)&v48, (User *)&v42) )
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
        if ( (a5 & 4) != 0 && !(unsigned __int8)User::operator==((User *)&v48, (User *)&v45) )
          goto LABEL_45;
        if ( v10 )
        {
          if ( !(unsigned __int8)User::operator==((User *)&v45, (User *)&v42) )
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
      if ( !(unsigned __int8)User::operator==((User *)&v45, (User *)&v41) )
      {
        v27 = (User *)User::User(&Sid, &v41);
        CallerToken = IsPrincipalAllowed(v27, v23);
        if ( CallerToken < 0 )
        {
          if ( (unsigned __int8)User::operator==((User *)&v41, (User *)&v46) )
          {
            CallerToken = TaskAccessCheck(ClientToken, &psz, 0x20u);
            if ( CallerToken < 0 )
              goto LABEL_92;
          }
          else
          {
            if ( (a5 & 4) == 0 )
              goto LABEL_92;
            CallerToken = TaskAccessCheck(ClientToken, &psz, 0x20u);
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
  if ( (unsigned int)dword_1800C0358 > 4 )
  {
    LODWORD(v43) = v15;
    LODWORD(Sid) = CallerToken;
    v51[0] = p_psz;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)&byte_1800B1C27,
      (_DWORD)v12,
      v13,
      (__int64)v51,
      (__int64)&Sid,
      (__int64)&v43);
  }
  JobMoniker::~JobMoniker((JobMoniker *)&iid);
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&ClientToken);
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
0x18004e9d0  mov     [rsp-8+arg_0], rbx
0x18004e9d5  push    rbp
0x18004e9d6  push    rsi
0x18004e9d7  push    rdi
0x18004e9d8  push    r12
0x18004e9da  push    r13
0x18004e9dc  push    r14
0x18004e9de  push    r15
0x18004e9e0  lea     rbp, [rsp-2C0h]
0x18004e9e8  sub     rsp, 3C0h
0x18004e9ef  mov     rax, cs:__security_cookie
0x18004e9f6  xor     rax, rsp
0x18004e9f9  mov     [rbp+2F0h+var_40], rax
0x18004ea00  mov     [rbp+2F0h+var_340], r9
0x18004ea04  mov     dword ptr [rsp+3F0h+var_380], r8d
0x18004ea09  mov     r15, rdx
0x18004ea0c  mov     rsi, rcx
0x18004ea0f  mov     r12, [rbp+2F0h+StringSid]
0x18004ea16  mov     rax, [rbp+2F0h+arg_38]
0x18004ea1d  mov     [rbp+2F0h+var_330], rax
0x18004ea21  lea     rcx, [rbp+2F0h+var_328]
0x18004ea25  call    ??0?$map@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@@std@@QEAA@XZ; std::map<_bstr_t,_bstr_t>::map<_bstr_t,_bstr_t>(void)
0x18004ea2a  nop
0x18004ea2b  xor     edi, edi
0x18004ea2d  mov     [rbp+2F0h+var_348], rdi
0x18004ea31  mov     [rbp+2F0h+var_350], rdi
0x18004ea35  mov     [rbp+2F0h+var_358], rdi
0x18004ea39  mov     [rbp+2F0h+var_368], rdi
0x18004ea3d  mov     [rbp+2F0h+var_370], rdi
0x18004ea41  mov     [rsp+3F0h+var_390], rdi
0x18004ea46  mov     ebx, edi
0x18004ea48  mov     [rsp+3F0h+var_388], rbx
0x18004ea4d  lea     rcx, [rbp+2F0h+var_300]; this
0x18004ea51  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x18004ea56  nop
0x18004ea57  lea     rcx, [rbp+2F0h+var_318]; this
0x18004ea5b  call    ??0ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::ActionCollection(void)
0x18004ea60  nop
0x18004ea61  mov     [rbp+2F0h+ClientToken], rdi
0x18004ea65  xor     r8d, r8d; unsigned __int16 *
0x18004ea68  mov     rdx, r15; psz
0x18004ea6b  lea     rcx, [rbp+2F0h+iid]; lpiid
0x18004ea6f  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18004ea74  nop
0x18004ea75  mov     eax, cs:dword_1800C0358
0x18004ea7b  cmp     eax, 5
0x18004ea7e  jbe     short loc_18004EA8C
0x18004ea80  lea     rdx, byte_1800B1B89
0x18004ea87  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18004ea8c  mov     eax, [rbp+2F0h+arg_20]
0x18004ea92  test    eax, 0FFFFFFF0h
0x18004ea97  jz      short loc_18004EAAA
0x18004ea99  mov     edi, 80070057h
0x18004ea9e  mov     r13d, [rbp+2F0h+SessionId]
0x18004eaa5  jmp     loc_18004F134
0x18004eaaa  mov     r14d, eax
0x18004eaad  and     r14d, 4
0x18004eab1  jz      short loc_18004EACF
0x18004eab3  mov     r13d, [rbp+2F0h+SessionId]
0x18004eaba  lea     eax, [r13+1]
0x18004eabe  test    eax, 0FFFFFFFEh
0x18004eac3  jnz     short loc_18004EAD3
0x18004eac5  mov     edi, 80070057h
0x18004eaca  jmp     loc_18004F134
0x18004eacf  or      r13d, 0FFFFFFFFh
0x18004ead3  mov     [rbp+2F0h+psz], di
0x18004eada  xor     edx, edx; Val
0x18004eadc  mov     r8d, 208h; Size
0x18004eae2  lea     rcx, [rbp+2F0h+var_24E]; void *
0x18004eae9  call    memset_0
0x18004eaee  mov     rdx, r15; unsigned __int16 *
0x18004eaf1  lea     rcx, [rbp+2F0h+psz]; this
0x18004eaf8  call    ?TaskPathCanonicalize@tsched@@YAJPEAGPEBG@Z; tsched::TaskPathCanonicalize(ushort *,ushort const *)
0x18004eafd  mov     edi, eax
0x18004eaff  test    eax, eax
0x18004eb01  js      loc_18004F134
0x18004eb07  lea     r15, [rbp+2F0h+psz]
0x18004eb0e  mov     [rsp+3F0h+var_3A0], r15
0x18004eb13  lea     rcx, [rbp+2F0h+psz]; this
0x18004eb1a  call    ?IsRoot@tsched@@YA_NPEBG@Z; tsched::IsRoot(ushort const *)
0x18004eb1f  test    al, al
0x18004eb21  jnz     short loc_18004EAC5
0x18004eb23  lea     rdx, [rbp+2F0h+ClientToken]; TokenHandle
0x18004eb27  lea     rcx, aRuntask; "RunTask"
0x18004eb2e  call    ?GetCallerToken@@YAJPEBGPEAPEAX@Z; GetCallerToken(ushort const *,void * *)
0x18004eb33  mov     edi, eax
0x18004eb35  test    eax, eax
0x18004eb37  js      loc_18004F134
0x18004eb3d  add     rsi, 10h
0x18004eb41  mov     qword ptr [rsp+3F0h+var_378], rsi
0x18004eb46  mov     rcx, rsi; SRWLock
0x18004eb49  call    cs:__imp_AcquireSRWLockShared
0x18004eb50  nop     dword ptr [rax+rax+00h]
0x18004eb55  nop
0x18004eb56  mov     r8d, 1; DesiredAccess
0x18004eb5c  lea     rdx, [rbp+2F0h+psz]; psz
0x18004eb63  mov     rcx, [rbp+2F0h+ClientToken]; ClientToken
0x18004eb67  call    ?TaskAccessCheck@@YAJPEAXPEBGK@Z; TaskAccessCheck(void *,ushort const *,ulong)
0x18004eb6c  mov     edi, eax
0x18004eb6e  test    eax, eax
0x18004eb70  jns     short loc_18004EB86
0x18004eb72  mov     rcx, rsi; SRWLock
0x18004eb75  call    cs:__imp_ReleaseSRWLockShared
0x18004eb7c  nop     dword ptr [rax+rax+00h]
0x18004eb81  jmp     loc_18004F134
0x18004eb86  mov     r15, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18004eb8d  xorps   xmm0, xmm0
0x18004eb90  movups  xmmword ptr [rbp+2F0h+var_2C8.Data1], xmm0
0x18004eb94  lea     rcx, [rbp+2F0h+iid]; this
0x18004eb98  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18004eb9d  mov     rdx, rax; unsigned __int16 *
0x18004eba0  xor     r9d, r9d; enum JobStore::TaskIndex *
0x18004eba3  lea     r8, [rbp+2F0h+var_2C8]; struct _GUID *
0x18004eba7  mov     rcx, r15; this
0x18004ebaa  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x18004ebaf  mov     edi, eax
0x18004ebb1  test    eax, eax
0x18004ebb3  jns     short loc_18004EBC9
0x18004ebb5  mov     rcx, rsi; SRWLock
0x18004ebb8  call    cs:__imp_ReleaseSRWLockShared
0x18004ebbf  nop     dword ptr [rax+rax+00h]
0x18004ebc4  jmp     loc_18004F12F
0x18004ebc9  lea     rcx, [rbp+2F0h+iid]; this
0x18004ebcd  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18004ebd2  mov     rdx, rax; unsigned __int16 *
0x18004ebd5  lea     r8, [rbp+2F0h+var_2C8]; struct _GUID *
0x18004ebd9  lea     rcx, [rbp+2F0h+var_290]; this
0x18004ebdd  call    ??0JobMoniker@@QEAA@PEBGAEBU_GUID@@@Z; JobMoniker::JobMoniker(ushort const *,_GUID const &)
0x18004ebe2  mov     rdx, rax
0x18004ebe5  lea     rcx, [rbp+2F0h+iid]
0x18004ebe9  call    ??4JobMoniker@@QEAAAEAV0@AEBV0@@Z; JobMoniker::operator=(JobMoniker const &)
0x18004ebee  lea     rcx, [rbp+2F0h+var_290]; this
0x18004ebf2  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18004ebf7  mov     [rsp+3F0h+Sid], 0
0x18004ec00  mov     r9d, 20019h; unsigned int
0x18004ec06  lea     r8, [rsp+3F0h+Sid]; HKEY *
0x18004ec0b  lea     rdx, [rbp+2F0h+iid]; struct JobMoniker *
0x18004ec0f  mov     rcx, r15; this
0x18004ec12  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x18004ec17  mov     edi, eax
0x18004ec19  test    eax, eax
0x18004ec1b  jns     short loc_18004EC29
0x18004ec1d  lea     rcx, [rsp+3F0h+Sid]; this
0x18004ec22  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18004ec27  jmp     short loc_18004EBB5
0x18004ec29  xor     r9d, r9d; unsigned __int64 *
0x18004ec2c  lea     r8d, [r9+3]; unsigned int
0x18004ec30  mov     rdx, [rsp+3F0h+Sid]; HKEY
0x18004ec35  lea     rcx, [rbp+2F0h+var_300]; this
0x18004ec39  call    ?StreamIn@Trigulator@Triggers@@QEAAJPEAUHKEY__@@KPEA_K@Z; Triggers::Trigulator::StreamIn(HKEY__ *,ulong,unsigned __int64 *)
0x18004ec3e  mov     edi, eax
0x18004ec40  test    eax, eax
0x18004ec42  js      short loc_18004EC1D
0x18004ec44  lea     rdx, [rbp+2F0h+iid]; struct JobMoniker *
0x18004ec48  lea     rcx, [rbp+2F0h+var_300]; this
0x18004ec4c  call    ?GetBucket@Trigulator@Triggers@@QEBAJAEAVJobMoniker@@@Z; Triggers::Trigulator::GetBucket(JobMoniker &)
0x18004ec51  mov     edi, eax
0x18004ec53  test    eax, eax
0x18004ec55  js      short loc_18004EC1D
0x18004ec57  xor     r8d, r8d; unsigned __int16 *
0x18004ec5a  mov     rdx, [rsp+3F0h+Sid]; hKey
0x18004ec5f  lea     rcx, [rbp+2F0h+var_318]; this
0x18004ec63  call    ?StreamIn@ActionCollection@Actions@@QEAAJPEAUHKEY__@@PEAG@Z; Actions::ActionCollection::StreamIn(HKEY__ *,ushort *)
0x18004ec68  mov     edi, eax
0x18004ec6a  lea     rcx, [rsp+3F0h+Sid]; this
0x18004ec6f  test    eax, eax
0x18004ec71  js      short loc_18004EC22
0x18004ec73  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18004ec78  nop
0x18004ec79  mov     rcx, rsi; SRWLock
0x18004ec7c  call    cs:__imp_ReleaseSRWLockShared
0x18004ec83  nop     dword ptr [rax+rax+00h]
0x18004ec88  mov     rdx, [rbp+2F0h+var_298]
0x18004ec8c  test    dword ptr [rdx+10h], 100h
0x18004ec93  jz      loc_18004F12A
0x18004ec99  test    dword ptr [rdx+10h], 400000h
0x18004eca0  jz      loc_18004F123
0x18004eca6  mov     esi, [rdx+10h]
0x18004eca9  mov     rdx, [rdx+40h]
0x18004ecad  lea     rcx, [rbp+2F0h+var_368]
0x18004ecb1  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18004ecb6  mov     r15d, [rbp+2F0h+arg_20]
0x18004ecbd  test    r15b, 2
0x18004ecc1  jz      short loc_18004ECCD
0x18004ecc3  and     esi, 0FBFFC70Dh
0x18004ecc9  bts     esi, 0Ah
0x18004eccd  mov     r8d, 1; int
0x18004ecd3  lea     rdx, aRpcserverRunta; "RpcServer::RunTask"
0x18004ecda  lea     rcx, [rsp+3F0h+var_378]; this
0x18004ecdf  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x18004ece4  nop
0x18004ece5  xor     edx, edx; void *
0x18004ece7  lea     rcx, [rbp+2F0h+var_370]; struct User *
0x18004eceb  call    ?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z; User::FromImpersonationToken(User &,void *)
0x18004ecf0  mov     edi, eax
0x18004ecf2  test    eax, eax
0x18004ecf4  jns     short loc_18004ED12
0x18004ecf6  cmp     [rsp+3F0h+var_378], 0
0x18004ecfb  jz      loc_18004F12F
0x18004ed01  call    cs:__imp_RpcRevertToSelf
0x18004ed08  nop     dword ptr [rax+rax+00h]
0x18004ed0d  jmp     loc_18004F12F
0x18004ed12  cmp     [rsp+3F0h+var_378], 0
0x18004ed17  jz      short loc_18004ED25
0x18004ed19  call    cs:__imp_RpcRevertToSelf
0x18004ed20  nop     dword ptr [rax+rax+00h]
0x18004ed25  test    r12, r12
0x18004ed28  jz      loc_18004EDC2
0x18004ed2e  test    r15b, 8
0x18004ed32  jz      short loc_18004EDA6
0x18004ed34  mov     [rsp+3F0h+Sid], 0
0x18004ed3d  lea     rdx, [rsp+3F0h+Sid]; Sid
0x18004ed42  mov     rcx, r12; StringSid
0x18004ed45  call    cs:__imp_ConvertStringSidToSidW
0x18004ed4c  nop     dword ptr [rax+rax+00h]
0x18004ed51  test    eax, eax
0x18004ed53  jnz     short loc_18004ED7F
0x18004ed55  call    cs:__imp_GetLastError
0x18004ed5c  nop     dword ptr [rax+rax+00h]
0x18004ed61  mov     edi, eax
0x18004ed63  test    eax, eax
0x18004ed65  jle     short loc_18004ED70
0x18004ed67  movzx   edi, ax
0x18004ed6a  or      edi, 80070000h
0x18004ed70  lea     rcx, [rsp+3F0h+Sid]
0x18004ed75  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18004ed7a  jmp     loc_18004F12F
0x18004ed7f  mov     r8d, 8; enum _SID_NAME_USE
0x18004ed85  mov     rdx, [rsp+3F0h+Sid]; void *
0x18004ed8a  lea     rcx, [rsp+3F0h+var_388]; this
0x18004ed8f  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x18004ed94  mov     edi, eax
0x18004ed96  lea     rcx, [rsp+3F0h+Sid]
0x18004ed9b  test    eax, eax
0x18004ed9d  js      short loc_18004ED75
0x18004ed9f  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18004eda4  jmp     short loc_18004EDBD
0x18004eda6  mov     rdx, r12; lpAccountName
0x18004eda9  lea     rcx, [rsp+3F0h+var_388]; this
0x18004edae  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x18004edb3  mov     edi, eax
0x18004edb5  test    eax, eax
0x18004edb7  js      loc_18004F12F
0x18004edbd  mov     rbx, [rsp+3F0h+var_388]
0x18004edc2  test    r14d, r14d
0x18004edc5  jz      short loc_18004EDDD
0x18004edc7  mov     edx, r13d; SessionId
0x18004edca  lea     rcx, [rbp+2F0h+var_358]; this
0x18004edce  call    ?FromUserSession@User@@SAJAEAV1@KPEAX@Z; User::FromUserSession(User &,ulong,void *)
0x18004edd3  mov     edi, eax
0x18004edd5  test    eax, eax
0x18004edd7  js      loc_18004F12F
0x18004eddd  mov     rdx, [rbp+2F0h+var_368]
0x18004ede1  lea     rcx, [rsp+3F0h+var_390]
0x18004ede6  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18004edeb  xor     r15b, r15b
0x18004edee  mov     r12d, 0FFF13FFFh
0x18004edf4  test    r14d, r14d
0x18004edf7  jz      short loc_18004EE37
0x18004edf9  test    rbx, rbx
0x18004edfc  jz      short loc_18004EE1F
0x18004edfe  lea     rdx, [rsp+3F0h+var_388]; User *
0x18004ee03  lea     rcx, [rbp+2F0h+var_358]; this
0x18004ee07  call    ??8User@@QEBA_NAEBV0@@Z; User::operator==(User const &)
0x18004ee0c  test    al, al
0x18004ee0e  jnz     short loc_18004EE1A
0x18004ee10  mov     edi, 80070057h
0x18004ee15  jmp     loc_18004F12F
0x18004ee1a  mov     rbx, [rsp+3F0h+var_388]
0x18004ee1f  and     esi, r12d
0x18004ee22  bts     esi, 10h
0x18004ee26  mov     rdx, [rbp+2F0h+var_358]
0x18004ee2a  lea     rcx, [rsp+3F0h+var_390]
0x18004ee2f  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18004ee34  mov     r15b, 1
0x18004ee37  mov     edi, [rbp+2F0h+arg_20]
0x18004ee3d  test    dil, 1
0x18004ee41  jz      short loc_18004EE8D
0x18004ee43  test    r14d, r14d
0x18004ee46  jz      short loc_18004EE59
0x18004ee48  lea     rdx, [rbp+2F0h+var_370]; User *
0x18004ee4c  lea     rcx, [rbp+2F0h+var_358]; this
0x18004ee50  call    ??8User@@QEBA_NAEBV0@@Z; User::operator==(User const &)
0x18004ee55  test    al, al
0x18004ee57  jz      short loc_18004EE10
0x18004ee59  test    rbx, rbx
0x18004ee5c  jz      short loc_18004EE75
0x18004ee5e  lea     rdx, [rsp+3F0h+var_388]; User *
0x18004ee63  lea     rcx, [rbp+2F0h+var_370]; this
0x18004ee67  call    ??8User@@QEBA_NAEBV0@@Z; User::operator==(User const &)
0x18004ee6c  test    al, al
0x18004ee6e  jz      short loc_18004EE10
0x18004ee70  mov     rbx, [rsp+3F0h+var_388]
0x18004ee75  and     esi, r12d
0x18004ee78  bts     esi, 10h
0x18004ee7c  mov     rdx, [rbp+2F0h+var_370]
0x18004ee80  lea     rcx, [rsp+3F0h+var_390]
0x18004ee85  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18004ee8a  mov     r15b, 1
0x18004ee8d  test    rbx, rbx
  ... truncated ...
```
