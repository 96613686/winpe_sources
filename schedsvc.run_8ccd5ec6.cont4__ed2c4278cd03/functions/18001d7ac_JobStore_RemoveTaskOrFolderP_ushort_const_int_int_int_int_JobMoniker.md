# JobStore::RemoveTaskOrFolderP(ushort const *,int,int,int,int &,JobMoniker &)

- ea: `0x18001d7ac`
- end: `0x18001e063`
- name: `?RemoveTaskOrFolderP@JobStore@@AEAAJPEBGHHHAEAHAEAVJobMoniker@@@Z`
- size: `2231`
- prototype: `__int64 __usercall@<rax>(JobStore *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, int@<r9d>, int, int *, struct JobMoniker *)`
- caller_count: `2`
- callee_count: `52`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d724`
- `0x1800524d4`

## callees

- `0x18000ba20`
- `0x18000bb10`
- `0x18000bc60`
- `0x18000cc40`
- `0x18000fe50`
- `0x18000ff40`
- `0x180010390`
- `0x180011e40`
- `0x1800138d8`
- `0x180013a90`
- `0x180015030`
- `0x18001d130`
- `0x18001d7ac`
- `0x18001ea40`
- `0x18001fe10`
- `0x180020110`
- `0x1800206a0`
- `0x18002123c`
- `0x180021260`
- `0x180021418`
- `0x180022aa0`
- `0x180024e68`
- `0x18002b210`
- `0x18002c470`
- `0x18002db40`
- `0x18002db74`
- `0x18002dbc4`
- `0x18002f814`
- `0x180030620`
- `0x180032c30`
- `0x180036020`
- `0x180037490`
- `0x18003a1f0`
- `0x18003bd70`
- `0x180042200`
- `0x180042438`
- `0x1800433ac`
- `0x180043ffc`
- `0x1800441c0`
- `0x180044280`
- `0x18004e184`
- `0x18004f898`
- `0x180059140`
- `0x18005a2bc`
- `0x18006f0b0`
- `0x18007094c`
- `0x180071c5c`
- `0x180071f14`
- `0x180072c4c`
- `0x1800829fa`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e005`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e005`
- `RPCRT4!RpcImpersonateClient` at `0x18001dc07`
- `RPCRT4!RpcImpersonateClient` at `0x18001dc07`
- `RPCRT4!RpcRevertToSelf` at `0x18001d9d5`
- `RPCRT4!RpcRevertToSelf` at `0x18001da53`
- `RPCRT4!RpcRevertToSelf` at `0x18001dc81`
- `RPCRT4!RpcRevertToSelf` at `0x18001ddb8`
- `RPCRT4!RpcRevertToSelf` at `0x18001df1f`
- `RPCRT4!RpcRevertToSelf` at `0x18001d9d5`
- `RPCRT4!RpcRevertToSelf` at `0x18001da53`
- `RPCRT4!RpcRevertToSelf` at `0x18001dc81`
- `RPCRT4!RpcRevertToSelf` at `0x18001ddb8`
- `RPCRT4!RpcRevertToSelf` at `0x18001df1f`

## string_xrefs

- `0x18001d9af`: `JobStore::RemoveTaskOrFolderP`
- `0x18001da29`: `JobStore::RemoveTaskOrFolderP`
- `0x18001dc1c`: `JobStore::RemoveTaskOrFolderP`
- `0x18001dd8b`: `JobStore::RemoveTaskOrFolderP`
- `0x18001dea4`: `JobStore::RemoveTaskOrFolderP`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
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
  __int64 v16; // rbx
  unsigned __int16 *v17; // rcx
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rcx
  int v21; // edx
  int v22; // r15d
  char v23; // r15
  char v24; // r13
  const unsigned __int16 *v25; // rdx
  __int64 v26; // rcx
  JobMoniker *v27; // rbx
  __int64 v28; // rbx
  int v29; // edx
  HKEY v30; // rbx
  int v31; // edx
  unsigned int v32; // r9d
  unsigned __int64 v33; // rcx
  bool IsErrorNotFound; // al
  int v35; // ecx
  int v36; // r8d
  RPC_STATUS v37; // eax
  EventManager *v38; // rcx
  RPC_STATUS v39; // esi
  int v40; // edx
  bool v41; // r8
  __int64 v42; // rcx
  int TaskXmlFromCollections; // eax
  int v44; // eax
  EventManager *v45; // rcx
  __int64 DomainAccount; // rax
  const unsigned __int16 *v47; // r9
  __int64 v48; // r8
  __int64 v49; // rcx
  char v50; // r14
  unsigned int Path; // eax
  __int64 v52; // rbx
  BOOL v53; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v56; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v57; // [rsp+50h] [rbp-B0h] BYREF
  int v58; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v59; // [rsp+60h] [rbp-A0h] BYREF
  char v60[8]; // [rsp+68h] [rbp-98h] BYREF
  struct JobMoniker *v61; // [rsp+70h] [rbp-90h]
  int *v62; // [rsp+78h] [rbp-88h]
  _BYTE v63[24]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v64; // [rsp+98h] [rbp-68h]
  _BYTE v65[56]; // [rsp+A0h] [rbp-60h] BYREF
  GUID iid; // [rsp+D8h] [rbp-28h] BYREF
  __int64 *v67; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v68; // [rsp+F0h] [rbp-10h]
  __int64 v69; // [rsp+F8h] [rbp-8h] BYREF
  GUID pExceptionObject; // [rsp+100h] [rbp+0h] BYREF
  const unsigned __int16 *v71; // [rsp+110h] [rbp+10h]
  __int64 v72; // [rsp+118h] [rbp+18h]
  __int64 v73; // [rsp+120h] [rbp+20h]
  RPC_STATUS v74; // [rsp+128h] [rbp+28h]
  __int64 v75; // [rsp+12Ch] [rbp+2Ch]
  struct _GUID v76; // [rsp+138h] [rbp+38h] BYREF
  OLECHAR psz[264]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v78; // [rsp+360h] [rbp+260h] BYREF
  char v79[526]; // [rsp+362h] [rbp+262h] BYREF

  v56 = a2;
  v11 = a7;
  v61 = a7;
  v62 = a6;
  JobMoniker::JobMoniker(&iid, 0, 0);
  v57 = 0;
  v58 = 0;
  v76 = 0;
  memset_0(psz, 0, 0x20Au);
  v53 = a5 != 0;
  v12 = 0;
  v59 = 0;
  v64 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v65);
  Actions::ActionCollection::ActionCollection((Actions::ActionCollection *)v63);
  TreeInfo = tsched::TaskPathCanonicalize((tsched *)psz, a2, v13);
  if ( TreeInfo < 0 )
    goto LABEL_8;
  v15 = JobMoniker::JobMoniker(&pExceptionObject, psz, 0);
  _bstr_t::operator=(&v67, (char *)v15 + 16);
  v68 = *((_QWORD *)v15 + 3);
  iid = *(GUID *)v15;
  v16 = *((_QWORD *)v15 + 4);
  if ( v16 )
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
  wmi::AutoRef<JobBucket>::Release(&v69);
  v69 = v16;
  JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
  if ( psz[0] && (psz[1] || psz[0] != 92) )
  {
    TreeInfo = JobStore::RegJobSecurityQuery(this, psz, (struct JobSecurity *)&v57);
    if ( TreeInfo < 0 )
      goto LABEL_8;
    if ( _bstr_t::length((_bstr_t *)&v67) )
    {
      if ( v67 )
        v20 = *v67;
      else
        v20 = 0;
      v19 = (const unsigned __int16 *)(v20 + 14);
    }
    else
    {
      v19 = 0;
    }
    TreeInfo = JobStore::RegGetTreeInfo(this, v19, &v76, 0);
    if ( TreeInfo >= 0 )
    {
      v23 = 0;
      v24 = 0;
      if ( _bstr_t::length((_bstr_t *)&v67) )
      {
        if ( v67 )
          v26 = *v67;
        else
          v26 = 0;
        v25 = (const unsigned __int16 *)(v26 + 14);
      }
      else
      {
        v25 = 0;
      }
      v27 = JobMoniker::JobMoniker((JobMoniker *)&pExceptionObject, v25, &v76);
      _bstr_t::operator=(&v67, (char *)v27 + 16);
      v68 = *((_QWORD *)v27 + 3);
      iid = *(GUID *)v27;
      v28 = *((_QWORD *)v27 + 4);
      if ( v28 )
        _InterlockedIncrement((volatile signed __int32 *)(v28 + 8));
      wmi::AutoRef<JobBucket>::Release(&v69);
      v69 = v28;
      JobMoniker::~JobMoniker((JobMoniker *)&pExceptionObject);
      hKey = 0;
      TreeInfo = JobStore::RegOpenTaskKey(this, (struct JobMoniker *)&iid, &hKey, 0x20019u);
      v30 = hKey;
      if ( TreeInfo >= 0 )
      {
        if ( (int)Triggers::Trigulator::StreamIn((Triggers::Trigulator *)v65, hKey, 0xFu, 0) >= 0
          && (int)Triggers::Trigulator::GetBucket((Triggers::Trigulator *)v65, (struct JobMoniker *)&iid) >= 0 )
        {
          v23 = 1;
        }
        if ( (int)Actions::ActionCollection::StreamIn((Actions::ActionCollection *)v63, v30, 0) >= 0 )
          v24 = 1;
      }
      if ( tsched::IsErrorNotFound((tsched *)(unsigned int)TreeInfo, v29)
        || TreeInfo == -2147216607
        || TreeInfo == -2147216621
        || TreeInfo >= 0 )
      {
        if ( qword_1800C1720 )
          v33 = (unsigned int)qword_1800C1720(psz);
        else
          v33 = v32;
        IsErrorNotFound = tsched::IsErrorNotFound((tsched *)v33, v31);
        TreeInfo = v36;
        if ( !IsErrorNotFound )
          TreeInfo = v35;
        if ( TreeInfo >= 0 )
        {
          LODWORD(StringSecurityDescriptor) = a4;
          if ( a4 )
          {
            v37 = RpcImpersonateClient(0);
            v39 = v37;
            if ( v37 )
            {
              EventManager::EvtReport(v38, &IMPERSONATION_FAILURE, L"JobStore::RemoveTaskOrFolderP", v37);
              pExceptionObject.Data4[0] = 0;
              *(_QWORD *)&pExceptionObject.Data1 = &wmi::GenericException::`vftable';
              v71 = &qword_1800A8718;
              v72 = 0;
              v73 = 0;
              v74 = v39;
              v75 = -1;
              throw (wmi::GenericException *)&pExceptionObject;
            }
          }
          TreeInfo = JobStore::FileRemoveTaskXml(this, (const struct JobMoniker *)&iid);
          if ( a4 )
            RpcRevertToSelf();
          if ( !tsched::IsErrorNotFound((tsched *)(unsigned int)TreeInfo, v40) && TreeInfo < 0
            || (TreeInfo = JobStore::RemoveTaskEntryP(this, (OLECHAR ***)&iid, v53), TreeInfo < 0) )
          {
            if ( v23 && v24 )
            {
              StringSecurityDescriptor = 0;
              if ( JobSecurity::GetSddl((JobSecurity *)&v57, 7u, (unsigned __int16 **)&StringSecurityDescriptor) >= 0 )
              {
                if ( (*(_DWORD *)(v69 + 16) & 0x200000) != 0
                  && !PlugIn::IsRegistering((PlugIn *)&PlugIn::s_singleton, v56, 0) )
                {
                  v78 = 0;
                  memset_0(v79, 0, 0x208u);
                  PlugIn::RegisterTask((PlugIn *)&PlugIn::s_singleton, psz, 0, 0, 2u, &v78);
                }
                TaskXmlFromCollections = JobStore::GenerateTaskXmlFromCollections(
                                           v42,
                                           (__int64)&iid,
                                           (__int64)v65,
                                           (Actions::ActionCollection *)v63,
                                           (LPVOID *)&v59);
                v12 = v59;
                if ( TaskXmlFromCollections >= 0 && (int)JobStore::ComputeHash((struct JobMoniker *)&iid, v59) >= 0 )
                {
                  RpcAutoImpersonate::RpcAutoImpersonate(
                    (RpcAutoImpersonate *)&v53,
                    L"JobStore::RemoveTaskOrFolderP",
                    a4);
                  JobStore::XmlSaveTaskFile(this, (const struct JobMoniker *)&iid, v12, StringSecurityDescriptor);
                  if ( v53 )
                    RpcRevertToSelf();
                }
                JobStore::RegTaskEntryCreate(
                  this,
                  (const struct JobMoniker *)&iid,
                  (const struct JobSecurity *)&v57,
                  (const struct Triggers::Trigulator *)v65,
                  (const struct Actions::ActionCollection *)v63,
                  0);
              }
              operator delete((void *)StringSecurityDescriptor);
            }
            wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
            goto LABEL_8;
          }
          if ( v23 )
          {
            if ( (((*(_DWORD *)(v69 + 16) & 0xFC000) - 0x40000) & 0xFFFBFFFF) == 0 )
            {
              v44 = CredStore::DeleteNtCredential(
                      (CredStore *)CredStore::g_pCommonStore,
                      (const struct User *)(v69 + 64),
                      v41);
              if ( v44 < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  78,
                  (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
                  (_DWORD)v56,
                  v44);
              }
            }
            TreeInfo = 0;
            _bstr_t::_bstr_t((_bstr_t *)&StringSecurityDescriptor, L"SYSTEM");
            if ( a4 )
            {
              RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v53, L"JobStore::RemoveTaskOrFolderP", a4);
              v56 = 0;
              TreeInfo = RpcAutoImpersonate::GetClientUser((RpcAutoImpersonate *)&v53, (struct User *)&v56);
              if ( TreeInfo >= 0 )
              {
                DomainAccount = User::GetDomainAccount(&v56, v60);
                _bstr_t::operator=(&StringSecurityDescriptor, DomainAccount);
                _bstr_t::~_bstr_t((_bstr_t *)v60);
              }
              else
              {
                TreeInfo = 0;
                _bstr_t::operator=(&StringSecurityDescriptor, L"N/A");
              }
              wmi::AutoRef<User::UserEntry>::Release(&v56);
              if ( v53 )
                RpcRevertToSelf();
            }
            if ( StringSecurityDescriptor )
              v47 = *(const unsigned __int16 **)StringSecurityDescriptor;
            else
              v47 = 0;
            EventManager::EvtReport(v45, &TASK_DELETED, psz, v47);
            _bstr_t::~_bstr_t((_bstr_t *)&StringSecurityDescriptor);
          }
          if ( a4 )
          {
            if ( _bstr_t::length((_bstr_t *)&v67) )
            {
              v49 = v67 ? *v67 : 0LL;
              v48 = v49 + 14;
            }
            else
            {
              v48 = 0;
            }
            v50 = Auditor::AuditJobOperation((__int64 *)g_pAuditor, 1, v48, 0);
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
          if ( v30 )
            RegCloseKey(v30);
          v22 = 1;
          v11 = v61;
          goto LABEL_106;
        }
      }
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    }
    else if ( a3 )
    {
      RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v53, L"JobStore::RemoveTaskOrFolderP", a4);
      TreeInfo = JobStore::FileTaskFolderRemove(this, psz);
      if ( v53 )
        RpcRevertToSelf();
      if ( !tsched::IsErrorNotFound((tsched *)(unsigned int)TreeInfo, v21) && TreeInfo < 0
        || (TreeInfo = JobStore::RemoveTaskFolderEntry(this, psz), v22 = 0, TreeInfo < 0) )
      {
        hKey = 0;
        if ( JobSecurity::GetSddl((JobSecurity *)&v57, 7u, (unsigned __int16 **)&hKey) >= 0 )
        {
          RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v53, L"JobStore::RemoveTaskOrFolderP", a4);
          JobStore::CreateXmlFolder(this, psz, (const unsigned __int16 *)hKey);
          if ( v53 )
            RpcRevertToSelf();
        }
        JobStore::RegFolderEntryCreate(this, psz, (const struct JobSecurity *)&v57);
        operator delete(hKey);
        goto LABEL_8;
      }
LABEL_106:
      _bstr_t::operator=((char *)v11 + 16, &v67);
      *((_QWORD *)v11 + 3) = v68;
      *(GUID *)v11 = iid;
      v52 = v69;
      if ( v69 )
        _InterlockedIncrement((volatile signed __int32 *)(v69 + 8));
      wmi::AutoRef<JobBucket>::Release((char *)v11 + 32);
      *((_QWORD *)v11 + 4) = v52;
      *v62 = v22;
      goto LABEL_8;
    }
    Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v63);
    Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v65);
    operator delete(0);
    v17 = 0;
    goto LABEL_9;
  }
  TreeInfo = -2147024891;
LABEL_8:
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v63);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v65);
  operator delete(0);
  v17 = v12;
LABEL_9:
  operator delete(v17);
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v57);
  JobMoniker::~JobMoniker((JobMoniker *)&iid);
  return (unsigned int)TreeInfo;
}

```

## disassembly

```asm
0x18001d7ac  mov     [rsp-8+arg_10], rbx
0x18001d7b1  push    rbp
0x18001d7b2  push    rsi
0x18001d7b3  push    rdi
0x18001d7b4  push    r12
0x18001d7b6  push    r13
0x18001d7b8  push    r14
0x18001d7ba  push    r15
0x18001d7bc  lea     rbp, [rsp-480h]
0x18001d7c4  sub     rsp, 580h
0x18001d7cb  mov     rax, cs:__security_cookie
0x18001d7d2  xor     rax, rsp
0x18001d7d5  mov     [rbp+4B0h+var_40], rax
0x18001d7dc  mov     r12d, r9d
0x18001d7df  mov     r15d, r8d
0x18001d7e2  mov     rbx, rdx
0x18001d7e5  mov     [rsp+5B0h+var_568], rdx
0x18001d7ea  mov     r14, rcx
0x18001d7ed  mov     r13, [rbp+4B0h+arg_30]
0x18001d7f4  mov     [rsp+5B0h+var_540], r13
0x18001d7f9  mov     rax, [rbp+4B0h+arg_28]
0x18001d800  mov     [rsp+5B0h+var_538], rax
0x18001d805  xor     r8d, r8d; unsigned __int16 *
0x18001d808  xor     edx, edx; psz
0x18001d80a  lea     rcx, [rbp+4B0h+iid]; lpiid
0x18001d80e  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18001d813  nop
0x18001d814  xor     esi, esi
0x18001d816  mov     [rsp+5B0h+var_560], rsi
0x18001d81b  mov     [rsp+5B0h+var_558], esi
0x18001d81f  xorps   xmm0, xmm0
0x18001d822  movups  xmmword ptr [rbp+4B0h+var_478.Data1], xmm0
0x18001d826  xor     edx, edx; Val
0x18001d828  mov     r8d, 20Ah; Size
0x18001d82e  lea     rcx, [rbp+4B0h+psz]; void *
0x18001d832  call    memset_0
0x18001d837  mov     eax, esi
0x18001d839  cmp     [rbp+4B0h+arg_20], esi
0x18001d83f  setnz   al
0x18001d842  mov     [rsp+5B0h+var_580], eax
0x18001d846  mov     edi, esi
0x18001d848  mov     [rsp+5B0h+var_550], rsi
0x18001d84d  mov     [rbp+4B0h+var_518], rsi
0x18001d851  lea     rcx, [rbp+4B0h+var_510]; this
0x18001d855  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x18001d85a  nop
0x18001d85b  lea     rcx, [rbp+4B0h+var_530]; this
0x18001d85f  call    ??0ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::ActionCollection(void)
0x18001d864  nop
0x18001d865  mov     rdx, rbx; unsigned __int16 *
0x18001d868  lea     rcx, [rbp+4B0h+psz]; this
0x18001d86c  call    ?TaskPathCanonicalize@tsched@@YAJPEAGPEBG@Z; tsched::TaskPathCanonicalize(ushort *,ushort const *)
0x18001d871  mov     esi, eax
0x18001d873  test    eax, eax
0x18001d875  js      short loc_18001D8E6
0x18001d877  xor     r8d, r8d; unsigned __int16 *
0x18001d87a  lea     rdx, [rbp+4B0h+psz]; psz
0x18001d87e  lea     rcx, [rbp+4B0h+pExceptionObject]; lpiid
0x18001d882  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18001d887  mov     rbx, rax
0x18001d88a  lea     rdx, [rax+10h]
0x18001d88e  lea     rcx, [rbp+4B0h+var_4C8]
0x18001d892  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001d897  mov     rcx, [rbx+18h]
0x18001d89b  mov     [rbp+4B0h+var_4C0], rcx
0x18001d89f  movups  xmm0, xmmword ptr [rbx]
0x18001d8a2  movdqu  xmmword ptr [rbp+4B0h+iid.Data1], xmm0
0x18001d8a7  mov     rbx, [rbx+20h]
0x18001d8ab  test    rbx, rbx
0x18001d8ae  jz      short loc_18001D8B4
0x18001d8b0  lock inc dword ptr [rbx+8]
0x18001d8b4  lea     rcx, [rbp+4B0h+var_4B8]
0x18001d8b8  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x18001d8bd  mov     [rbp+4B0h+var_4B8], rbx
0x18001d8c1  lea     rcx, [rbp+4B0h+pExceptionObject]; this
0x18001d8c5  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18001d8ca  movzx   eax, [rbp+4B0h+psz]
0x18001d8ce  xor     ebx, ebx
0x18001d8d0  test    ax, ax
0x18001d8d3  jz      short loc_18001D8E1
0x18001d8d5  cmp     [rbp+4B0h+var_45E], bx
0x18001d8d9  jnz     short loc_18001D94C
0x18001d8db  cmp     ax, 5Ch ; '\'
0x18001d8df  jnz     short loc_18001D94C
0x18001d8e1  mov     esi, 80070005h
0x18001d8e6  lea     rcx, [rbp+4B0h+var_530]; this
0x18001d8ea  call    ??1ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::~ActionCollection(void)
0x18001d8ef  nop
0x18001d8f0  lea     rcx, [rbp+4B0h+var_510]; this
0x18001d8f4  call    ??1Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::~Trigulator(void)
0x18001d8f9  nop
0x18001d8fa  xor     ecx, ecx; void *
0x18001d8fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d901  nop
0x18001d902  mov     rcx, rdi; void *
0x18001d905  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d90a  nop
0x18001d90b  lea     rcx, [rsp+5B0h+var_560]
0x18001d910  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001d915  nop
0x18001d916  lea     rcx, [rbp+4B0h+iid]; this
0x18001d91a  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18001d91f  mov     eax, esi
0x18001d921  mov     rcx, [rbp+4B0h+var_40]
0x18001d928  xor     rcx, rsp; StackCookie
0x18001d92b  call    __security_check_cookie
0x18001d930  mov     rbx, [rsp+5B0h+arg_10]
0x18001d938  add     rsp, 580h
0x18001d93f  pop     r15
0x18001d941  pop     r14
0x18001d943  pop     r13
0x18001d945  pop     r12
0x18001d947  pop     rdi
0x18001d948  pop     rsi
0x18001d949  pop     rbp
0x18001d94a  retn
0x18001d94c  lea     r8, [rsp+5B0h+var_560]; struct JobSecurity *
0x18001d951  lea     rdx, [rbp+4B0h+psz]; unsigned __int16 *
0x18001d955  mov     rcx, r14; this
0x18001d958  call    ?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z; JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)
0x18001d95d  mov     esi, eax
0x18001d95f  test    eax, eax
0x18001d961  js      short loc_18001D8E6
0x18001d963  lea     rcx, [rbp+4B0h+var_4C8]; this
0x18001d967  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18001d96c  test    eax, eax
0x18001d96e  jnz     short loc_18001D975
0x18001d970  mov     rdx, rbx
0x18001d973  jmp     short loc_18001D98A
0x18001d975  mov     rax, [rbp+4B0h+var_4C8]
0x18001d979  test    rax, rax
0x18001d97c  jz      short loc_18001D983
0x18001d97e  mov     rcx, [rax]
0x18001d981  jmp     short loc_18001D986
0x18001d983  mov     rcx, rbx
0x18001d986  lea     rdx, [rcx+0Eh]; unsigned __int16 *
0x18001d98a  xor     r9d, r9d; enum JobStore::TaskIndex *
0x18001d98d  lea     r8, [rbp+4B0h+var_478]; struct _GUID *
0x18001d991  mov     rcx, r14; this
0x18001d994  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x18001d999  mov     esi, eax
0x18001d99b  test    eax, eax
0x18001d99d  jns     loc_18001DA80
0x18001d9a3  test    r15d, r15d
0x18001d9a6  jz      loc_18001DBD8
0x18001d9ac  mov     r8d, r12d; int
0x18001d9af  lea     rdx, aJobstoreRemove; "JobStore::RemoveTaskOrFolderP"
0x18001d9b6  lea     rcx, [rsp+5B0h+var_580]; this
0x18001d9bb  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x18001d9c0  nop
0x18001d9c1  lea     rdx, [rbp+4B0h+psz]; unsigned __int16 *
0x18001d9c5  mov     rcx, r14; this
0x18001d9c8  call    ?FileTaskFolderRemove@JobStore@@AEBAJPEBG@Z; JobStore::FileTaskFolderRemove(ushort const *)
0x18001d9cd  mov     esi, eax
0x18001d9cf  cmp     [rsp+5B0h+var_580], ebx
0x18001d9d3  jz      short loc_18001D9E1
0x18001d9d5  call    cs:__imp_RpcRevertToSelf
0x18001d9dc  nop     dword ptr [rax+rax+00h]
0x18001d9e1  mov     ecx, esi; this
0x18001d9e3  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18001d9e8  test    al, al
0x18001d9ea  jnz     short loc_18001D9F0
0x18001d9ec  test    esi, esi
0x18001d9ee  js      short loc_18001DA09
0x18001d9f0  lea     rdx, [rbp+4B0h+psz]; unsigned __int16 *
0x18001d9f4  mov     rcx, r14; this
0x18001d9f7  call    ?RemoveTaskFolderEntry@JobStore@@AEBAJPEBG@Z; JobStore::RemoveTaskFolderEntry(ushort const *)
0x18001d9fc  mov     esi, eax
0x18001d9fe  mov     r15d, ebx
0x18001da01  test    eax, eax
0x18001da03  jns     loc_18001E01C
0x18001da09  mov     [rsp+5B0h+hKey], rbx
0x18001da0e  lea     r8, [rsp+5B0h+hKey]; unsigned __int16 **
0x18001da13  mov     edx, 7; unsigned int
0x18001da18  lea     rcx, [rsp+5B0h+var_560]; this
0x18001da1d  call    ?GetSddl@JobSecurity@@QEAAJKPEAPEAG@Z; JobSecurity::GetSddl(ulong,ushort * *)
0x18001da22  test    eax, eax
0x18001da24  js      short loc_18001DA5F
0x18001da26  mov     r8d, r12d; int
0x18001da29  lea     rdx, aJobstoreRemove; "JobStore::RemoveTaskOrFolderP"
0x18001da30  lea     rcx, [rsp+5B0h+var_580]; this
0x18001da35  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x18001da3a  nop
0x18001da3b  mov     r8, [rsp+5B0h+hKey]; unsigned __int16 *
0x18001da40  lea     rdx, [rbp+4B0h+psz]; unsigned __int16 *
0x18001da44  mov     rcx, r14; this
0x18001da47  call    ?CreateXmlFolder@JobStore@@QEAAJPEBG0@Z; JobStore::CreateXmlFolder(ushort const *,ushort const *)
0x18001da4c  nop
0x18001da4d  cmp     [rsp+5B0h+var_580], ebx
0x18001da51  jz      short loc_18001DA5F
0x18001da53  call    cs:__imp_RpcRevertToSelf
0x18001da5a  nop     dword ptr [rax+rax+00h]
0x18001da5f  lea     r8, [rsp+5B0h+var_560]; struct JobSecurity *
0x18001da64  lea     rdx, [rbp+4B0h+psz]; unsigned __int16 *
0x18001da68  mov     rcx, r14; this
0x18001da6b  call    ?RegFolderEntryCreate@JobStore@@QEBAJPEBGAEBVJobSecurity@@@Z; JobStore::RegFolderEntryCreate(ushort const *,JobSecurity const &)
0x18001da70  nop
0x18001da71  mov     rcx, [rsp+5B0h+hKey]; void *
0x18001da76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001da7b  jmp     loc_18001D8E6
0x18001da80  movzx   r15d, bl
0x18001da84  movzx   r13d, bl
0x18001da88  lea     rcx, [rbp+4B0h+var_4C8]; this
0x18001da8c  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18001da91  test    eax, eax
0x18001da93  jnz     short loc_18001DA9A
0x18001da95  mov     rdx, rbx
0x18001da98  jmp     short loc_18001DAAF
0x18001da9a  mov     rax, [rbp+4B0h+var_4C8]
0x18001da9e  test    rax, rax
0x18001daa1  jz      short loc_18001DAA8
0x18001daa3  mov     rcx, [rax]
0x18001daa6  jmp     short loc_18001DAAB
0x18001daa8  mov     rcx, rbx
0x18001daab  lea     rdx, [rcx+0Eh]; unsigned __int16 *
0x18001daaf  lea     r8, [rbp+4B0h+var_478]; struct _GUID *
0x18001dab3  lea     rcx, [rbp+4B0h+pExceptionObject]; this
0x18001dab7  call    ??0JobMoniker@@QEAA@PEBGAEBU_GUID@@@Z; JobMoniker::JobMoniker(ushort const *,_GUID const &)
0x18001dabc  mov     rbx, rax
0x18001dabf  lea     rdx, [rax+10h]
0x18001dac3  lea     rcx, [rbp+4B0h+var_4C8]
0x18001dac7  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001dacc  mov     rcx, [rbx+18h]
0x18001dad0  mov     [rbp+4B0h+var_4C0], rcx
0x18001dad4  movups  xmm0, xmmword ptr [rbx]
0x18001dad7  movdqu  xmmword ptr [rbp+4B0h+iid.Data1], xmm0
0x18001dadc  mov     rbx, [rbx+20h]
0x18001dae0  xor     esi, esi
0x18001dae2  test    rbx, rbx
0x18001dae5  jz      short loc_18001DAEB
0x18001dae7  lock inc dword ptr [rbx+8]
0x18001daeb  lea     rcx, [rbp+4B0h+var_4B8]
0x18001daef  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x18001daf4  mov     [rbp+4B0h+var_4B8], rbx
0x18001daf8  lea     rcx, [rbp+4B0h+pExceptionObject]; this
0x18001dafc  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18001db01  mov     [rsp+5B0h+hKey], rsi
0x18001db06  mov     r9d, 20019h; unsigned int
0x18001db0c  lea     r8, [rsp+5B0h+hKey]; HKEY *
0x18001db11  lea     rdx, [rbp+4B0h+iid]; struct JobMoniker *
0x18001db15  mov     rcx, r14; this
0x18001db18  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x18001db1d  mov     esi, eax
0x18001db1f  mov     rbx, [rsp+5B0h+hKey]
0x18001db24  xor     r8d, r8d
0x18001db27  test    eax, eax
0x18001db29  js      short loc_18001DB78
0x18001db2b  xor     r9d, r9d; unsigned __int64 *
0x18001db2e  lea     r8d, [r9+0Fh]; unsigned int
0x18001db32  mov     rdx, rbx; HKEY
0x18001db35  lea     rcx, [rbp+4B0h+var_510]; this
0x18001db39  call    ?StreamIn@Trigulator@Triggers@@QEAAJPEAUHKEY__@@KPEA_K@Z; Triggers::Trigulator::StreamIn(HKEY__ *,ulong,unsigned __int64 *)
0x18001db3e  test    eax, eax
0x18001db40  js      short loc_18001DB5A
0x18001db42  lea     rdx, [rbp+4B0h+iid]; struct JobMoniker *
0x18001db46  lea     rcx, [rbp+4B0h+var_510]; this
0x18001db4a  call    ?GetBucket@Trigulator@Triggers@@QEBAJAEAVJobMoniker@@@Z; Triggers::Trigulator::GetBucket(JobMoniker &)
0x18001db4f  test    eax, eax
0x18001db51  mov     eax, 1
0x18001db56  cmovns  r15d, eax
0x18001db5a  xor     r8d, r8d; unsigned __int16 *
0x18001db5d  mov     rdx, rbx; hKey
0x18001db60  lea     rcx, [rbp+4B0h+var_530]; this
0x18001db64  call    ?StreamIn@ActionCollection@Actions@@QEAAJPEAUHKEY__@@PEAG@Z; Actions::ActionCollection::StreamIn(HKEY__ *,ushort *)
0x18001db69  xor     r8d, r8d
0x18001db6c  test    eax, eax
0x18001db6e  lea     r9d, [r8+1]
0x18001db72  cmovns  r13d, r9d
0x18001db76  jmp     short loc_18001DB7E
0x18001db78  mov     r9d, 1
0x18001db7e  mov     ecx, esi; this
0x18001db80  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18001db85  test    al, al
0x18001db87  jnz     short loc_18001DB9D
0x18001db89  cmp     esi, 80041321h
0x18001db8f  jz      short loc_18001DB9D
0x18001db91  cmp     esi, 80041313h
0x18001db97  jz      short loc_18001DB9D
0x18001db99  test    esi, esi
0x18001db9b  js      short loc_18001DBCD
0x18001db9d  mov     rax, cs:qword_1800C1720
0x18001dba4  test    rax, rax
0x18001dba7  jz      short loc_18001DBB9
0x18001dba9  lea     rcx, [rbp+4B0h+psz]
0x18001dbad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbb2  mov     ecx, eax
0x18001dbb4  xor     r8d, r8d
0x18001dbb7  jmp     short loc_18001DBBC
0x18001dbb9  mov     ecx, r9d; this
0x18001dbbc  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18001dbc1  mov     esi, r8d
0x18001dbc4  test    al, al
0x18001dbc6  cmovz   esi, ecx
0x18001dbc9  test    esi, esi
0x18001dbcb  jns     short loc_18001DBFB
0x18001dbcd  lea     rcx, [rsp+5B0h+hKey]; this
0x18001dbd2  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18001dbd7  nop
0x18001dbd8  lea     rcx, [rbp+4B0h+var_530]; this
0x18001dbdc  call    ??1ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::~ActionCollection(void)
  ... truncated ...
```
