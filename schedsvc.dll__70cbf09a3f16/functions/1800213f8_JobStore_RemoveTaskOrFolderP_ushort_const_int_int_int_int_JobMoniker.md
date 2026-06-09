# JobStore::RemoveTaskOrFolderP(ushort const *,int,int,int,int &,JobMoniker &)

- ea: `0x1800213f8`
- end: `0x180021c99`
- name: `?RemoveTaskOrFolderP@JobStore@@AEAAJPEBGHHHAEAHAEAVJobMoniker@@@Z`
- size: `2209`
- prototype: `__int64 __fastcall(JobStore *this, unsigned __int16 *, int, int, int, int *, struct JobMoniker *)`
- caller_count: `2`
- callee_count: `52`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021374`
- `0x18004fbe0`

## callees

- `0x180007ddc`
- `0x180007ec0`
- `0x18000b4e0`
- `0x18000dc30`
- `0x18000e4c0`
- `0x18000e510`
- `0x18000e910`
- `0x180016e3c`
- `0x180019130`
- `0x1800199c0`
- `0x18001a260`
- `0x18001a430`
- `0x18001ec90`
- `0x18001fdb0`
- `0x180021300`
- `0x18002132c`
- `0x1800213f8`
- `0x180022600`
- `0x1800244ac`
- `0x1800245dc`
- `0x180024690`
- `0x180025040`
- `0x180025310`
- `0x180025870`
- `0x18002643c`
- `0x180026460`
- `0x1800265fc`
- `0x180027c30`
- `0x1800290f0`
- `0x18002db7c`
- `0x18002e4e4`
- `0x1800322a0`
- `0x1800339c0`
- `0x1800349c0`
- `0x180038000`
- `0x180039b6c`
- `0x1800403e8`
- `0x180040590`
- `0x180041af8`
- `0x180041f20`
- `0x18004bca4`
- `0x18004d50c`
- `0x180056794`
- `0x18005790c`
- `0x18006baac`
- `0x18006d27c`
- `0x18006e530`
- `0x18006e7d4`
- `0x18006f488`
- `0x18007e68a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021c41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021c41`
- `RPCRT4!RpcImpersonateClient` at `0x18002185b`
- `RPCRT4!RpcImpersonateClient` at `0x18002185b`
- `RPCRT4!RpcRevertToSelf` at `0x180021635`
- `RPCRT4!RpcRevertToSelf` at `0x1800216ad`
- `RPCRT4!RpcRevertToSelf` at `0x1800218cf`
- `RPCRT4!RpcRevertToSelf` at `0x180021a00`
- `RPCRT4!RpcRevertToSelf` at `0x180021b61`
- `RPCRT4!RpcRevertToSelf` at `0x180021635`
- `RPCRT4!RpcRevertToSelf` at `0x1800216ad`
- `RPCRT4!RpcRevertToSelf` at `0x1800218cf`
- `RPCRT4!RpcRevertToSelf` at `0x180021a00`
- `RPCRT4!RpcRevertToSelf` at `0x180021b61`

## string_xrefs

- `0x18002160f`: `JobStore::RemoveTaskOrFolderP`
- `0x180021683`: `JobStore::RemoveTaskOrFolderP`
- `0x18002186a`: `JobStore::RemoveTaskOrFolderP`
- `0x1800219d3`: `JobStore::RemoveTaskOrFolderP`
- `0x180021ae6`: `JobStore::RemoveTaskOrFolderP`

## pseudocode

```c
__int64 __fastcall JobStore::RemoveTaskOrFolderP(
        JobStore *this,
        unsigned __int16 *a2,
        int a3,
        int a4,
        int a5,
        int *a6,
        struct JobMoniker *a7)
{
  struct JobMoniker *v11; // r13
  unsigned __int16 *v12; // rdi
  const unsigned __int16 *v13; // r8
  int TreeInfo; // esi
  JobMoniker *v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rbx
  unsigned __int16 *v18; // rcx
  const unsigned __int16 *v20; // rdx
  __int64 v21; // rcx
  int v22; // edx
  int v23; // r15d
  char v24; // r15
  char v25; // r13
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rcx
  JobMoniker *v28; // rbx
  __int64 v29; // rbx
  int v30; // edx
  HKEY v31; // rbx
  int v32; // edx
  unsigned int v33; // r9d
  unsigned __int64 v34; // rcx
  bool IsErrorNotFound; // al
  int v36; // ecx
  int v37; // r8d
  RPC_STATUS v38; // eax
  EventManager *v39; // rcx
  RPC_STATUS v40; // esi
  int v41; // edx
  __int64 v42; // rcx
  int v43; // eax
  int v44; // eax
  EventManager *v45; // rcx
  __int64 DomainAccount; // rax
  const unsigned __int16 *v47; // r9
  __int64 v48; // r8
  __int64 v49; // rcx
  char v50; // r14
  unsigned int Path; // eax
  __int64 v52; // rbx
  struct Actions::ActionCollection *v53; // [rsp+20h] [rbp-E0h]
  BYTE *lpData; // [rsp+28h] [rbp-D8h]
  BOOL v55; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v58; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v59; // [rsp+50h] [rbp-B0h] BYREF
  int v60; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v61; // [rsp+60h] [rbp-A0h] BYREF
  char v62[8]; // [rsp+68h] [rbp-98h] BYREF
  struct JobMoniker *v63; // [rsp+70h] [rbp-90h]
  int *v64; // [rsp+78h] [rbp-88h]
  _BYTE v65[24]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v66; // [rsp+98h] [rbp-68h]
  _BYTE v67[56]; // [rsp+A0h] [rbp-60h] BYREF
  GUID iid; // [rsp+D8h] [rbp-28h] BYREF
  __int64 *v69; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v70; // [rsp+F0h] [rbp-10h]
  __int64 v71; // [rsp+F8h] [rbp-8h] BYREF
  GUID pExceptionObject; // [rsp+100h] [rbp+0h] BYREF
  const unsigned __int16 *v73; // [rsp+110h] [rbp+10h]
  __int64 v74; // [rsp+118h] [rbp+18h]
  __int64 v75; // [rsp+120h] [rbp+20h]
  RPC_STATUS v76; // [rsp+128h] [rbp+28h]
  __int64 v77; // [rsp+12Ch] [rbp+2Ch]
  struct _GUID v78; // [rsp+138h] [rbp+38h] BYREF
  OLECHAR psz[264]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v80; // [rsp+360h] [rbp+260h] BYREF
  char v81[526]; // [rsp+362h] [rbp+262h] BYREF

  v58 = a2;
  v11 = a7;
  v63 = a7;
  v64 = a6;
  JobMoniker::JobMoniker(&iid, 0, 0);
  v59 = 0;
  v60 = 0;
  v78 = 0;
  memset_0(psz, 0, 0x20Au);
  v55 = a5 != 0;
  v12 = 0;
  v61 = 0;
  v66 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v67);
  Actions::ActionCollection::ActionCollection((Actions::ActionCollection *)v65);
  TreeInfo = tsched::TaskPathCanonicalize((tsched *)psz, a2, v13);
  if ( TreeInfo < 0 )
    goto LABEL_10;
  v15 = JobMoniker::JobMoniker(&pExceptionObject, psz, 0);
  v16 = *((_QWORD *)v15 + 2);
  if ( v16 )
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 16));
  _bstr_t::~_bstr_t((_bstr_t *)&v69);
  v69 = (__int64 *)*((_QWORD *)v15 + 2);
  v70 = *((_QWORD *)v15 + 3);
  iid = *(GUID *)v15;
  v17 = *((_QWORD *)v15 + 4);
  if ( v17 )
    _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
  wmi::AutoRef<JobBucket>::Release(&v71);
  v71 = v17;
  JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
  if ( psz[0] && (psz[1] || psz[0] != 92) )
  {
    TreeInfo = JobStore::RegJobSecurityQuery(this, psz, (struct JobSecurity *)&v59);
    if ( TreeInfo < 0 )
      goto LABEL_10;
    if ( _bstr_t::length((_bstr_t *)&v69) )
    {
      if ( v69 )
        v21 = *v69;
      else
        v21 = 0;
      v20 = (const unsigned __int16 *)(v21 + 14);
    }
    else
    {
      v20 = 0;
    }
    TreeInfo = JobStore::RegGetTreeInfo(this, v20, &v78, 0);
    if ( TreeInfo >= 0 )
    {
      v24 = 0;
      v25 = 0;
      if ( _bstr_t::length((_bstr_t *)&v69) )
      {
        if ( v69 )
          v27 = *v69;
        else
          v27 = 0;
        v26 = (const unsigned __int16 *)(v27 + 14);
      }
      else
      {
        v26 = 0;
      }
      v28 = JobMoniker::JobMoniker((JobMoniker *)&pExceptionObject, v26, &v78);
      _bstr_t::operator=(&v69, (char *)v28 + 16);
      v70 = *((_QWORD *)v28 + 3);
      iid = *(GUID *)v28;
      v29 = *((_QWORD *)v28 + 4);
      if ( v29 )
        _InterlockedIncrement((volatile signed __int32 *)(v29 + 8));
      wmi::AutoRef<JobBucket>::Release(&v71);
      v71 = v29;
      JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
      hKey = 0;
      TreeInfo = JobStore::RegOpenTaskKey(this, (struct JobMoniker *)&iid, &hKey, 0x20019u);
      v31 = hKey;
      if ( TreeInfo >= 0 )
      {
        if ( (int)Triggers::Trigulator::StreamIn((Triggers::Trigulator *)v67, hKey, 0xFu, 0) >= 0
          && (int)Triggers::Trigulator::GetBucket((Triggers::Trigulator *)v67, (struct JobMoniker *)&iid) >= 0 )
        {
          v24 = 1;
        }
        if ( (int)Actions::ActionCollection::StreamIn((Actions::ActionCollection *)v65, v31, 0) >= 0 )
          v25 = 1;
      }
      if ( tsched::IsErrorNotFound((tsched *)(unsigned int)TreeInfo, v30)
        || TreeInfo == -2147216607
        || TreeInfo == -2147216621
        || TreeInfo >= 0 )
      {
        if ( qword_1800BD620 )
          v34 = (unsigned int)qword_1800BD620(psz);
        else
          v34 = v33;
        IsErrorNotFound = tsched::IsErrorNotFound((tsched *)v34, v32);
        TreeInfo = v37;
        if ( !IsErrorNotFound )
          TreeInfo = v36;
        if ( TreeInfo >= 0 )
        {
          LODWORD(StringSecurityDescriptor) = a4;
          if ( a4 )
          {
            v38 = RpcImpersonateClient(0);
            v40 = v38;
            if ( v38 )
            {
              EventManager::EvtReport(
                v39,
                &IMPERSONATION_FAILURE,
                L"JobStore::RemoveTaskOrFolderP",
                v38,
                v53,
                (const struct _GUID *)lpData);
              pExceptionObject.Data4[0] = 0;
              *(_QWORD *)&pExceptionObject.Data1 = &wmi::GenericException::`vftable';
              v73 = &qword_1800A4718;
              v74 = 0;
              v75 = 0;
              v76 = v40;
              v77 = -1;
              throw (wmi::GenericException *)&pExceptionObject;
            }
          }
          TreeInfo = JobStore::FileRemoveTaskXml(this, (const struct JobMoniker *)&iid);
          if ( a4 )
            RpcRevertToSelf();
          if ( !tsched::IsErrorNotFound((tsched *)(unsigned int)TreeInfo, v41) && TreeInfo < 0
            || (TreeInfo = JobStore::RemoveTaskEntryP(this, (OLECHAR ***)&iid, v55), TreeInfo < 0) )
          {
            if ( v24 && v25 )
            {
              StringSecurityDescriptor = 0;
              if ( JobSecurity::GetSddl((JobSecurity *)&v59, 7u, (unsigned __int16 **)&StringSecurityDescriptor) >= 0 )
              {
                if ( (*(_DWORD *)(v71 + 16) & 0x200000) != 0
                  && !PlugIn::IsRegistering((PlugIn *)&PlugIn::s_singleton, v58, 0) )
                {
                  v80 = 0;
                  memset_0(v81, 0, 0x208u);
                  PlugIn::RegisterTask((PlugIn *)&PlugIn::s_singleton, psz, 0, 0, 2u, &v80);
                }
                v43 = JobStore::GenerateTaskXmlFromCollections(v42, &iid, v67, v65, &v61);
                v12 = v61;
                if ( v43 >= 0 && (int)JobStore::ComputeHash((struct JobMoniker *)&iid, v61) >= 0 )
                {
                  RpcAutoImpersonate::RpcAutoImpersonate(
                    (RpcAutoImpersonate *)&v55,
                    L"JobStore::RemoveTaskOrFolderP",
                    a4);
                  JobStore::XmlSaveTaskFile(this, (const struct JobMoniker *)&iid, v12, StringSecurityDescriptor);
                  if ( v55 )
                    RpcRevertToSelf();
                }
                JobStore::RegTaskEntryCreate(
                  this,
                  (const struct JobMoniker *)&iid,
                  (const struct JobSecurity *)&v59,
                  (const struct Triggers::Trigulator *)v67,
                  (const struct Actions::ActionCollection *)v65,
                  0);
              }
              operator delete((void *)StringSecurityDescriptor);
            }
            wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
            goto LABEL_10;
          }
          if ( v24 )
          {
            if ( (((*(_DWORD *)(v71 + 16) & 0xFC000) - 0x40000) & 0xFFFBFFFF) == 0 )
            {
              v44 = CredStore::DeleteNtCredential(CredStore::g_pCommonStore, (const struct User *)(v71 + 64));
              if ( v44 < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  78,
                  (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
                  (_DWORD)v58,
                  v44);
              }
            }
            TreeInfo = 0;
            _bstr_t::_bstr_t((_bstr_t *)&StringSecurityDescriptor, L"SYSTEM");
            if ( a4 )
            {
              RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v55, L"JobStore::RemoveTaskOrFolderP", a4);
              v58 = 0;
              TreeInfo = RpcAutoImpersonate::GetClientUser((RpcAutoImpersonate *)&v55, (struct User *)&v58);
              if ( TreeInfo >= 0 )
              {
                DomainAccount = User::GetDomainAccount(&v58, v62);
                _bstr_t::operator=(&StringSecurityDescriptor, DomainAccount);
                _bstr_t::~_bstr_t((_bstr_t *)v62);
              }
              else
              {
                TreeInfo = 0;
                _bstr_t::operator=(&StringSecurityDescriptor, L"N/A");
              }
              wmi::AutoRef<User::UserEntry>::Release(&v58);
              if ( v55 )
                RpcRevertToSelf();
            }
            if ( StringSecurityDescriptor )
              v47 = *(const unsigned __int16 **)StringSecurityDescriptor;
            else
              v47 = 0;
            EventManager::EvtReport(v45, &TASK_DELETED, psz, v47, v53, (const struct _GUID *)lpData);
            _bstr_t::~_bstr_t((_bstr_t *)&StringSecurityDescriptor);
          }
          if ( a4 )
          {
            if ( _bstr_t::length((_bstr_t *)&v69) )
            {
              v49 = v69 ? *v69 : 0LL;
              v48 = v49 + 14;
            }
            else
            {
              v48 = 0;
            }
            v50 = Auditor::AuditJobOperation(g_pAuditor, 1, v48, 0);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
              && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((TreeInfo >> 31) & 0xFFFFFFFE) + 4 )
            {
              Path = (unsigned int)JobMoniker::GetPath((JobMoniker *)&iid);
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                79,
                (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
                Path,
                v50);
            }
          }
          if ( v31 )
            RegCloseKey(v31);
          v23 = 1;
          v11 = v63;
          goto LABEL_108;
        }
      }
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    }
    else if ( a3 )
    {
      RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v55, L"JobStore::RemoveTaskOrFolderP", a4);
      TreeInfo = JobStore::FileTaskFolderRemove(this, psz);
      if ( v55 )
        RpcRevertToSelf();
      if ( !tsched::IsErrorNotFound((tsched *)(unsigned int)TreeInfo, v22) && TreeInfo < 0
        || (TreeInfo = JobStore::RemoveTaskFolderEntry(this, psz), v23 = 0, TreeInfo < 0) )
      {
        hKey = 0;
        if ( JobSecurity::GetSddl((JobSecurity *)&v59, 7u, (unsigned __int16 **)&hKey) >= 0 )
        {
          RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v55, L"JobStore::RemoveTaskOrFolderP", a4);
          JobStore::CreateXmlFolder(this, psz, (const unsigned __int16 *)hKey);
          if ( v55 )
            RpcRevertToSelf();
        }
        JobStore::RegFolderEntryCreate(this, psz, (const struct JobSecurity *)&v59);
        operator delete(hKey);
        goto LABEL_10;
      }
LABEL_108:
      _bstr_t::operator=((char *)v11 + 16, &v69);
      *((_QWORD *)v11 + 3) = v70;
      *(GUID *)v11 = iid;
      v52 = v71;
      if ( v71 )
        _InterlockedIncrement((volatile signed __int32 *)(v71 + 8));
      wmi::AutoRef<JobBucket>::Release((char *)v11 + 32);
      *((_QWORD *)v11 + 4) = v52;
      *v64 = v23;
      goto LABEL_10;
    }
    Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v65);
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v67);
    operator delete(0);
    v18 = 0;
    goto LABEL_11;
  }
  TreeInfo = -2147024891;
LABEL_10:
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v65);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v67);
  operator delete(0);
  v18 = v12;
LABEL_11:
  operator delete(v18);
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v59);
  JobMoniker::~JobMoniker((JobMoniker *)&iid);
  return (unsigned int)TreeInfo;
}

```

## disassembly

```asm
0x1800213f8  mov     [rsp-8+arg_10], rbx
0x1800213fd  push    rbp
0x1800213fe  push    rsi
0x1800213ff  push    rdi
0x180021400  push    r12
0x180021402  push    r13
0x180021404  push    r14
0x180021406  push    r15
0x180021408  lea     rbp, [rsp-480h]
0x180021410  sub     rsp, 580h
0x180021417  mov     rax, cs:__security_cookie
0x18002141e  xor     rax, rsp
0x180021421  mov     [rbp+4B0h+var_40], rax
0x180021428  mov     r12d, r9d
0x18002142b  mov     r15d, r8d
0x18002142e  mov     rbx, rdx
0x180021431  mov     [rsp+5B0h+var_568], rdx
0x180021436  mov     r14, rcx
0x180021439  mov     r13, [rbp+4B0h+arg_30]
0x180021440  mov     [rsp+5B0h+var_540], r13
0x180021445  mov     rax, [rbp+4B0h+arg_28]
0x18002144c  mov     [rsp+5B0h+var_538], rax
0x180021451  xor     r8d, r8d; unsigned __int16 *
0x180021454  xor     edx, edx; psz
0x180021456  lea     rcx, [rbp+4B0h+iid]; lpiid
0x18002145a  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18002145f  nop
0x180021460  xor     esi, esi
0x180021462  mov     [rsp+5B0h+var_560], rsi
0x180021467  mov     [rsp+5B0h+var_558], esi
0x18002146b  xorps   xmm0, xmm0
0x18002146e  movups  xmmword ptr [rbp+4B0h+var_478.Data1], xmm0
0x180021472  xor     edx, edx; Val
0x180021474  mov     r8d, 20Ah; Size
0x18002147a  lea     rcx, [rbp+4B0h+psz]; void *
0x18002147e  call    memset_0
0x180021483  mov     eax, esi
0x180021485  cmp     [rbp+4B0h+arg_20], esi
0x18002148b  setnz   al
0x18002148e  mov     [rsp+5B0h+var_580], eax
0x180021492  mov     edi, esi
0x180021494  mov     [rsp+5B0h+var_550], rsi
0x180021499  mov     [rbp+4B0h+var_518], rsi
0x18002149d  lea     rcx, [rbp+4B0h+var_510]; this
0x1800214a1  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x1800214a6  nop
0x1800214a7  lea     rcx, [rbp+4B0h+var_530]; this
0x1800214ab  call    ??0ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::ActionCollection(void)
0x1800214b0  nop
0x1800214b1  mov     rdx, rbx; unsigned __int16 *
0x1800214b4  lea     rcx, [rbp+4B0h+psz]; this
0x1800214b8  call    ?TaskPathCanonicalize@tsched@@YAJPEAGPEBG@Z; tsched::TaskPathCanonicalize(ushort *,ushort const *)
0x1800214bd  mov     esi, eax
0x1800214bf  test    eax, eax
0x1800214c1  js      loc_180021547
0x1800214c7  xor     r8d, r8d; unsigned __int16 *
0x1800214ca  lea     rdx, [rbp+4B0h+psz]; psz
0x1800214ce  lea     rcx, [rbp+4B0h+pExceptionObject]; lpiid
0x1800214d2  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x1800214d7  mov     rbx, rax
0x1800214da  mov     rax, [rax+10h]
0x1800214de  test    rax, rax
0x1800214e1  jz      short loc_1800214E7
0x1800214e3  lock inc dword ptr [rax+10h]
0x1800214e7  lea     rcx, [rbp+4B0h+var_4C8]; this
0x1800214eb  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800214f0  mov     rcx, [rbx+10h]
0x1800214f4  mov     [rbp+4B0h+var_4C8], rcx
0x1800214f8  mov     rax, [rbx+18h]
0x1800214fc  mov     [rbp+4B0h+var_4C0], rax
0x180021500  movups  xmm0, xmmword ptr [rbx]
0x180021503  movdqu  xmmword ptr [rbp+4B0h+iid.Data1], xmm0
0x180021508  mov     rbx, [rbx+20h]
0x18002150c  test    rbx, rbx
0x18002150f  jz      short loc_180021515
0x180021511  lock inc dword ptr [rbx+8]
0x180021515  lea     rcx, [rbp+4B0h+var_4B8]
0x180021519  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x18002151e  mov     [rbp+4B0h+var_4B8], rbx
0x180021522  lea     rcx, [rbp+4B0h+pExceptionObject]; this
0x180021526  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18002152b  movzx   eax, [rbp+4B0h+psz]
0x18002152f  xor     ebx, ebx
0x180021531  test    ax, ax
0x180021534  jz      short loc_180021542
0x180021536  cmp     [rbp+4B0h+var_45E], bx
0x18002153a  jnz     short loc_1800215AC
0x18002153c  cmp     ax, 5Ch ; '\'
0x180021540  jnz     short loc_1800215AC
0x180021542  mov     esi, 80070005h
0x180021547  lea     rcx, [rbp+4B0h+var_530]; this
0x18002154b  call    ??1ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::~ActionCollection(void)
0x180021550  nop
0x180021551  lea     rcx, [rbp+4B0h+var_510]; this
0x180021555  call    ??1Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::~Trigulator(void)
0x18002155a  nop
0x18002155b  xor     ecx, ecx; void *
0x18002155d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021562  nop
0x180021563  mov     rcx, rdi; void *
0x180021566  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002156b  nop
0x18002156c  lea     rcx, [rsp+5B0h+var_560]
0x180021571  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180021576  nop
0x180021577  lea     rcx, [rbp+4B0h+iid]; this
0x18002157b  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180021580  mov     eax, esi
0x180021582  mov     rcx, [rbp+4B0h+var_40]
0x180021589  xor     rcx, rsp; StackCookie
0x18002158c  call    __security_check_cookie
0x180021591  mov     rbx, [rsp+5B0h+arg_10]
0x180021599  add     rsp, 580h
0x1800215a0  pop     r15
0x1800215a2  pop     r14
0x1800215a4  pop     r13
0x1800215a6  pop     r12
0x1800215a8  pop     rdi
0x1800215a9  pop     rsi
0x1800215aa  pop     rbp
0x1800215ab  retn
0x1800215ac  lea     r8, [rsp+5B0h+var_560]; struct JobSecurity *
0x1800215b1  lea     rdx, [rbp+4B0h+psz]; unsigned __int16 *
0x1800215b5  mov     rcx, r14; this
0x1800215b8  call    ?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z; JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)
0x1800215bd  mov     esi, eax
0x1800215bf  test    eax, eax
0x1800215c1  js      short loc_180021547
0x1800215c3  lea     rcx, [rbp+4B0h+var_4C8]; this
0x1800215c7  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x1800215cc  test    eax, eax
0x1800215ce  jnz     short loc_1800215D5
0x1800215d0  mov     rdx, rbx
0x1800215d3  jmp     short loc_1800215EA
0x1800215d5  mov     rax, [rbp+4B0h+var_4C8]
0x1800215d9  test    rax, rax
0x1800215dc  jz      short loc_1800215E3
0x1800215de  mov     rcx, [rax]
0x1800215e1  jmp     short loc_1800215E6
0x1800215e3  mov     rcx, rbx
0x1800215e6  lea     rdx, [rcx+0Eh]; unsigned __int16 *
0x1800215ea  xor     r9d, r9d; enum JobStore::TaskIndex *
0x1800215ed  lea     r8, [rbp+4B0h+var_478]; struct _GUID *
0x1800215f1  mov     rcx, r14; this
0x1800215f4  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x1800215f9  mov     esi, eax
0x1800215fb  test    eax, eax
0x1800215fd  jns     loc_1800216D4
0x180021603  test    r15d, r15d
0x180021606  jz      loc_18002182C
0x18002160c  mov     r8d, r12d; int
0x18002160f  lea     rdx, aJobstoreRemove; "JobStore::RemoveTaskOrFolderP"
0x180021616  lea     rcx, [rsp+5B0h+var_580]; this
0x18002161b  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x180021620  nop
0x180021621  lea     rdx, [rbp+4B0h+psz]; unsigned __int16 *
0x180021625  mov     rcx, r14; this
0x180021628  call    ?FileTaskFolderRemove@JobStore@@AEBAJPEBG@Z; JobStore::FileTaskFolderRemove(ushort const *)
0x18002162d  mov     esi, eax
0x18002162f  cmp     [rsp+5B0h+var_580], ebx
0x180021633  jz      short loc_18002163B
0x180021635  call    cs:__imp_RpcRevertToSelf
0x18002163b  mov     ecx, esi; this
0x18002163d  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180021642  test    al, al
0x180021644  jnz     short loc_18002164A
0x180021646  test    esi, esi
0x180021648  js      short loc_180021663
0x18002164a  lea     rdx, [rbp+4B0h+psz]; unsigned __int16 *
0x18002164e  mov     rcx, r14; this
0x180021651  call    ?RemoveTaskFolderEntry@JobStore@@AEBAJPEBG@Z; JobStore::RemoveTaskFolderEntry(ushort const *)
0x180021656  mov     esi, eax
0x180021658  mov     r15d, ebx
0x18002165b  test    eax, eax
0x18002165d  jns     loc_180021C52
0x180021663  mov     [rsp+5B0h+hKey], rbx
0x180021668  lea     r8, [rsp+5B0h+hKey]; unsigned __int16 **
0x18002166d  mov     edx, 7; unsigned int
0x180021672  lea     rcx, [rsp+5B0h+var_560]; this
0x180021677  call    ?GetSddl@JobSecurity@@QEAAJKPEAPEAG@Z; JobSecurity::GetSddl(ulong,ushort * *)
0x18002167c  test    eax, eax
0x18002167e  js      short loc_1800216B3
0x180021680  mov     r8d, r12d; int
0x180021683  lea     rdx, aJobstoreRemove; "JobStore::RemoveTaskOrFolderP"
0x18002168a  lea     rcx, [rsp+5B0h+var_580]; this
0x18002168f  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x180021694  nop
0x180021695  mov     r8, [rsp+5B0h+hKey]; unsigned __int16 *
0x18002169a  lea     rdx, [rbp+4B0h+psz]; unsigned __int16 *
0x18002169e  mov     rcx, r14; this
0x1800216a1  call    ?CreateXmlFolder@JobStore@@QEAAJPEBG0@Z; JobStore::CreateXmlFolder(ushort const *,ushort const *)
0x1800216a6  nop
0x1800216a7  cmp     [rsp+5B0h+var_580], ebx
0x1800216ab  jz      short loc_1800216B3
0x1800216ad  call    cs:__imp_RpcRevertToSelf
0x1800216b3  lea     r8, [rsp+5B0h+var_560]; struct JobSecurity *
0x1800216b8  lea     rdx, [rbp+4B0h+psz]; unsigned __int16 *
0x1800216bc  mov     rcx, r14; this
0x1800216bf  call    ?RegFolderEntryCreate@JobStore@@QEBAJPEBGAEBVJobSecurity@@@Z; JobStore::RegFolderEntryCreate(ushort const *,JobSecurity const &)
0x1800216c4  nop
0x1800216c5  mov     rcx, [rsp+5B0h+hKey]; void *
0x1800216ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800216cf  jmp     loc_180021547
0x1800216d4  movzx   r15d, bl
0x1800216d8  movzx   r13d, bl
0x1800216dc  lea     rcx, [rbp+4B0h+var_4C8]; this
0x1800216e0  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x1800216e5  test    eax, eax
0x1800216e7  jnz     short loc_1800216EE
0x1800216e9  mov     rdx, rbx
0x1800216ec  jmp     short loc_180021703
0x1800216ee  mov     rax, [rbp+4B0h+var_4C8]
0x1800216f2  test    rax, rax
0x1800216f5  jz      short loc_1800216FC
0x1800216f7  mov     rcx, [rax]
0x1800216fa  jmp     short loc_1800216FF
0x1800216fc  mov     rcx, rbx
0x1800216ff  lea     rdx, [rcx+0Eh]; unsigned __int16 *
0x180021703  lea     r8, [rbp+4B0h+var_478]; struct _GUID *
0x180021707  lea     rcx, [rbp+4B0h+pExceptionObject]; this
0x18002170b  call    ??0JobMoniker@@QEAA@PEBGAEBU_GUID@@@Z; JobMoniker::JobMoniker(ushort const *,_GUID const &)
0x180021710  mov     rbx, rax
0x180021713  lea     rdx, [rax+10h]
0x180021717  lea     rcx, [rbp+4B0h+var_4C8]
0x18002171b  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180021720  mov     rcx, [rbx+18h]
0x180021724  mov     [rbp+4B0h+var_4C0], rcx
0x180021728  movups  xmm0, xmmword ptr [rbx]
0x18002172b  movdqu  xmmword ptr [rbp+4B0h+iid.Data1], xmm0
0x180021730  mov     rbx, [rbx+20h]
0x180021734  xor     esi, esi
0x180021736  test    rbx, rbx
0x180021739  jz      short loc_18002173F
0x18002173b  lock inc dword ptr [rbx+8]
0x18002173f  lea     rcx, [rbp+4B0h+var_4B8]
0x180021743  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x180021748  mov     [rbp+4B0h+var_4B8], rbx
0x18002174c  lea     rcx, [rbp+4B0h+pExceptionObject]; this
0x180021750  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180021755  mov     [rsp+5B0h+hKey], rsi
0x18002175a  mov     r9d, 20019h; unsigned int
0x180021760  lea     r8, [rsp+5B0h+hKey]; HKEY *
0x180021765  lea     rdx, [rbp+4B0h+iid]; struct JobMoniker *
0x180021769  mov     rcx, r14; this
0x18002176c  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x180021771  mov     esi, eax
0x180021773  mov     rbx, [rsp+5B0h+hKey]
0x180021778  xor     r8d, r8d
0x18002177b  test    eax, eax
0x18002177d  js      short loc_1800217CC
0x18002177f  xor     r9d, r9d; unsigned __int64 *
0x180021782  lea     r8d, [r9+0Fh]; unsigned int
0x180021786  mov     rdx, rbx; HKEY
0x180021789  lea     rcx, [rbp+4B0h+var_510]; this
0x18002178d  call    ?StreamIn@Trigulator@Triggers@@QEAAJPEAUHKEY__@@KPEA_K@Z; Triggers::Trigulator::StreamIn(HKEY__ *,ulong,unsigned __int64 *)
0x180021792  test    eax, eax
0x180021794  js      short loc_1800217AE
0x180021796  lea     rdx, [rbp+4B0h+iid]; struct JobMoniker *
0x18002179a  lea     rcx, [rbp+4B0h+var_510]; this
0x18002179e  call    ?GetBucket@Trigulator@Triggers@@QEBAJAEAVJobMoniker@@@Z; Triggers::Trigulator::GetBucket(JobMoniker &)
0x1800217a3  test    eax, eax
0x1800217a5  mov     eax, 1
0x1800217aa  cmovns  r15d, eax
0x1800217ae  xor     r8d, r8d; unsigned __int16 *
0x1800217b1  mov     rdx, rbx; hKey
0x1800217b4  lea     rcx, [rbp+4B0h+var_530]; this
0x1800217b8  call    ?StreamIn@ActionCollection@Actions@@QEAAJPEAUHKEY__@@PEAG@Z; Actions::ActionCollection::StreamIn(HKEY__ *,ushort *)
0x1800217bd  xor     r8d, r8d
0x1800217c0  test    eax, eax
0x1800217c2  lea     r9d, [r8+1]
0x1800217c6  cmovns  r13d, r9d
0x1800217ca  jmp     short loc_1800217D2
0x1800217cc  mov     r9d, 1
0x1800217d2  mov     ecx, esi; this
0x1800217d4  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x1800217d9  test    al, al
0x1800217db  jnz     short loc_1800217F1
0x1800217dd  cmp     esi, 80041321h
0x1800217e3  jz      short loc_1800217F1
0x1800217e5  cmp     esi, 80041313h
0x1800217eb  jz      short loc_1800217F1
0x1800217ed  test    esi, esi
0x1800217ef  js      short loc_180021821
0x1800217f1  mov     rax, cs:qword_1800BD620
0x1800217f8  test    rax, rax
0x1800217fb  jz      short loc_18002180D
0x1800217fd  lea     rcx, [rbp+4B0h+psz]
0x180021801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021806  mov     ecx, eax
0x180021808  xor     r8d, r8d
0x18002180b  jmp     short loc_180021810
0x18002180d  mov     ecx, r9d; this
0x180021810  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180021815  mov     esi, r8d
0x180021818  test    al, al
0x18002181a  cmovz   esi, ecx
0x18002181d  test    esi, esi
0x18002181f  jns     short loc_18002184F
0x180021821  lea     rcx, [rsp+5B0h+hKey]; this
0x180021826  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
  ... truncated ...
```
