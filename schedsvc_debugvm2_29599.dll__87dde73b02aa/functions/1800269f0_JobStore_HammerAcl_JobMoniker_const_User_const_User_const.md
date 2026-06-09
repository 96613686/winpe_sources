# JobStore::HammerAcl(JobMoniker const &,User const &,User const *)

- ea: `0x1800269f0`
- end: `0x1800276b1`
- name: `?HammerAcl@JobStore@@QEBAJAEBVJobMoniker@@AEBVUser@@PEBV3@@Z`
- size: `3265`
- prototype: `int(JobStore *__hidden this, const struct JobMoniker *, const struct User *, const struct User *)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180029978`
- `0x180045df0`

## callees

- `0x18001a260`
- `0x18001fc54`
- `0x18002132c`
- `0x180025040`
- `0x180026938`
- `0x1800269f0`
- `0x1800276c0`
- `0x180027780`
- `0x1800277e4`
- `0x180027838`
- `0x180027b74`
- `0x180027bc8`
- `0x180027ee0`
- `0x180028894`
- `0x1800288c4`
- `0x180042fa4`
- `0x180045284`
- `0x180045c88`
- `0x18004a660`
- `0x18004b228`
- `0x18004be38`
- `0x1800504b4`
- `0x180051d44`
- `0x1800522ac`
- `0x180052584`
- `0x1800528ac`
- `0x180056794`
- `0x18005b250`
- `0x1800679e0`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180026b92`
- `msvcrt!_wcsnicmp` at `0x180026b92`
- `msvcrt!memmove_s` at `0x1800271f6`
- `msvcrt!memmove_s` at `0x1800273df`
- `msvcrt!memmove_s` at `0x1800271f6`
- `msvcrt!memmove_s` at `0x1800273df`
- `msvcrt!free` at `0x180026eef`
- `msvcrt!free` at `0x1800275fe`
- `msvcrt!free` at `0x18002761a`
- `msvcrt!free` at `0x180027640`
- `msvcrt!free` at `0x180026eef`
- `msvcrt!free` at `0x1800275fe`
- `msvcrt!free` at `0x18002761a`
- `msvcrt!free` at `0x180027640`
- `OLEAUT32!__imp_SysStringLen` at `0x180026a98`
- `OLEAUT32!__imp_SysStringLen` at `0x180026a98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026ca2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800274ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026ca2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800274ed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026b1f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026b1f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180026b6e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180026b6e`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180026bab`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180026bab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026cab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026cab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026f2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002767b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026f2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002767b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026a61`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026a61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026f00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027651`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026f00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027651`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180027008`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180027008`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180026ff7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180026ff7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800272b1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800272b1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002702c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002702c`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800274e3`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800274e3`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180026cfd`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180026cfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall JobStore::HammerAcl(
        JobStore *this,
        const struct JobMoniker *a2,
        const struct User *a3,
        struct _SID *a4)
{
  const struct User *v4; // rdi
  const struct JobMoniker *v5; // r13
  BSTR *v7; // rax
  UINT v8; // eax
  _QWORD *v9; // rax
  __int64 v10; // rdx
  int XmlFileSystemPath; // ebx
  wchar_t *v13; // r15
  HANDLE FileW; // rbx
  __int64 v15; // r14
  int v16; // edx
  tsched *v17; // rcx
  int v18; // edx
  tsched *v19; // rcx
  int LastHrError; // eax
  int v21; // edi
  signed int SecurityInfo; // eax
  unsigned int v23; // r12d
  const struct _ACL *v24; // rbx
  tsched *v25; // rcx
  unsigned int v26; // edi
  WCHAR *v27; // rbx
  __int64 v28; // rax
  int updated; // ebx
  struct _SID *v30; // rbx
  DWORD LengthSid; // eax
  unsigned int v32; // r8d
  unsigned __int8 v33; // r9
  unsigned int Error; // eax
  unsigned __int8 v35; // di
  unsigned int v36; // ebx
  __int64 i; // rdi
  void *v38; // rax
  errno_t v39; // eax
  unsigned int v40; // ecx
  _DWORD *v41; // rbx
  int v42; // edi
  char v43; // al
  unsigned int v44; // ecx
  _DWORD *v45; // rbx
  int v46; // edi
  char v47; // al
  unsigned __int64 v48; // rbx
  char *v49; // rdi
  char *v50; // rdi
  errno_t v51; // eax
  _BYTE *v52; // rdx
  tsched *v54; // rcx
  int v55; // eax
  unsigned __int8 v56; // al
  struct _ACL *PACL; // rax
  DWORD v58; // ebx
  unsigned int Path; // eax
  _BYTE v60[32]; // [rsp+0h] [rbp-4F8h] BYREF
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-4D0h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-4C8h]
  PSECURITY_DESCRIPTOR *ppSecurityDescriptor; // [rsp+38h] [rbp-4C0h]
  unsigned __int8 v64; // [rsp+40h] [rbp-4B8h] BYREF
  char v65; // [rsp+41h] [rbp-4B7h]
  unsigned int v66; // [rsp+44h] [rbp-4B4h]
  unsigned int v67[2]; // [rsp+48h] [rbp-4B0h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+50h] [rbp-4A8h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-4A0h] BYREF
  void **v70; // [rsp+60h] [rbp-498h] BYREF
  void *Block; // [rsp+68h] [rbp-490h]
  char v72; // [rsp+70h] [rbp-488h]
  int v73; // [rsp+74h] [rbp-484h]
  void *v74[3]; // [rsp+78h] [rbp-480h] BYREF
  int v75; // [rsp+90h] [rbp-468h]
  User *v76; // [rsp+98h] [rbp-460h]
  __int128 v77; // [rsp+A0h] [rbp-458h] BYREF
  struct _SID *v78; // [rsp+B0h] [rbp-448h] BYREF
  PACL ppDacl; // [rsp+B8h] [rbp-440h] BYREF
  struct _SID *v80; // [rsp+C0h] [rbp-438h]
  const struct JobMoniker *v81; // [rsp+C8h] [rbp-430h]
  const struct User *v82; // [rsp+D0h] [rbp-428h]
  User *v83; // [rsp+D8h] [rbp-420h]
  void **v84; // [rsp+E0h] [rbp-418h] BYREF
  _BYTE pDestinationSid[68]; // [rsp+E8h] [rbp-410h] BYREF
  char v86; // [rsp+12Ch] [rbp-3CCh]
  int v87; // [rsp+130h] [rbp-3C8h]
  __int64 v88; // [rsp+138h] [rbp-3C0h]
  __int64 v89; // [rsp+140h] [rbp-3B8h]
  __int64 v90; // [rsp+148h] [rbp-3B0h]
  __int64 v91; // [rsp+150h] [rbp-3A8h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+160h] [rbp-398h] BYREF
  char v93[8]; // [rsp+1A0h] [rbp-358h] BYREF
  char pSid1[120]; // [rsp+1A8h] [rbp-350h] BYREF
  _BYTE v95[128]; // [rsp+220h] [rbp-2D8h] BYREF
  WCHAR szFilePath[264]; // [rsp+2A0h] [rbp-258h] BYREF

  v80 = a4;
  v4 = a3;
  v5 = a2;
  v78 = a4;
  v82 = a3;
  v81 = a2;
  v83 = a3;
  v76 = (User *)a4;
  while ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 23, 0, 0) )
    Sleep(0x64u);
  if ( !*(_DWORD *)(*((_QWORD *)this + 10) + 184LL) || !*(_QWORD *)v4 )
    return 0;
  lpFileName = 0;
  v7 = (BSTR *)*((_QWORD *)v5 + 2);
  if ( v7 && (!*v7 ? (v8 = 0) : (v8 = SysStringLen(*v7)), v8) )
  {
    v9 = (_QWORD *)*((_QWORD *)v5 + 2);
    if ( v9 )
      v10 = *v9 + 14LL;
    else
      v10 = 14;
  }
  else
  {
    v10 = 0;
  }
  XmlFileSystemPath = JobStore::GetXmlFileSystemPath(this, v10, &lpFileName);
  if ( XmlFileSystemPath < 0 )
  {
    operator delete((void *)lpFileName);
    return (unsigned int)XmlFileSystemPath;
  }
  v77 = 0;
  v13 = (wchar_t *)lpFileName;
  FileW = CreateFileW(lpFileName, 0x42000000u, 1u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFinalPathNameByHandleW(FileW, szFilePath, 0x105u, 0) - 1 > 0x103 )
    {
      if ( (int)tsched::GetLastHrError(v17, v16) >= 0 )
      {
LABEL_23:
        v15 = (__int64)FileW;
        goto LABEL_24;
      }
    }
    else if ( !_wcsnicmp(szFilePath, v13, 0x105u)
           && GetFileInformationByHandle(FileW, &FileInformation)
           && FileInformation.nNumberOfLinks <= 1 )
    {
      goto LABEL_23;
    }
    v15 = -1;
    *(_QWORD *)v67 = -1;
    SetLastError(5u);
    CloseHandle(FileW);
    goto LABEL_25;
  }
  v15 = -1;
LABEL_24:
  *(_QWORD *)v67 = v15;
LABEL_25:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids, v15);
  }
  tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v77);
  *(_QWORD *)&v77 = v15;
  if ( v15 == -1 )
  {
    LastHrError = tsched::GetLastHrError(v19, v18);
    v21 = LastHrError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        (_DWORD)v13,
        LastHrError);
    }
    goto LABEL_34;
  }
  *((_QWORD *)&v77 + 1) = v13;
  ppDacl = 0;
  hMem = 0;
  SecurityInfo = GetSecurityInfo((HANDLE)v15, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &hMem);
  v23 = SecurityInfo;
  if ( SecurityInfo )
  {
    if ( SecurityInfo > 0 )
      v23 = (unsigned __int16)SecurityInfo | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        (_DWORD)v13,
        v23);
    }
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hMem);
    tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v77);
    operator delete(v13);
    return v23;
  }
  Block = 0;
  v72 = 0;
  v73 = 2;
  v70 = &ATL::CDacl::`vftable';
  memset(v74, 0, sizeof(v74));
  v75 = 0;
  v24 = ppDacl;
  ATL::CDacl::RemoveAllAces((ATL::CDacl *)&v70);
  try
  {
    ATL::CDacl::Copy((ATL::CDacl *)&v70, v24);
  }
  catch ( ... )
  {
    v66 = tsched::GetLastHrError(v25, (int)v60);
    v26 = v66;
    if ( (v66 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        v27 = (WCHAR *)lpFileName;
      }
      else
      {
        v27 = (WCHAR *)lpFileName;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          65,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          (_DWORD)lpFileName,
          v66);
      }
      ATL::CDacl::~CDacl((ATL::CDacl *)&v70);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hMem);
      tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v77);
      operator delete(v27);
      return v26;
    }
    v13 = (wchar_t *)lpFileName;
    v15 = *(_QWORD *)v67;
    v80 = v78;
    v4 = v82;
    v5 = v81;
  }
  v28 = *(_QWORD *)v4;
  if ( *(_QWORD *)v4 )
  {
    if ( *(_BYTE *)v28 )
    {
      updated = -2147418113;
      goto LABEL_60;
    }
    if ( !*(_QWORD *)(v28 + 32) )
    {
      updated = User::UpdateEntry(v83);
      if ( updated < 0 )
        goto LABEL_60;
    }
    v78 = *(struct _SID **)(*(_QWORD *)v4 + 32LL);
    v30 = v78;
    v84 = &ATL::CSid::`vftable';
    v86 = 0;
    v87 = 7;
    v88 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v89 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v90 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v91 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !IsValidSid(v30) || (LengthSid = GetLengthSid(v30), LengthSid > 0x44) )
      ATL::PrivateAtlThrow(0x80070057);
    v86 = 1;
    if ( !CopySid(LengthSid, pDestinationSid, v30) )
    {
      Error = ATL::AtlHresultFromLastError();
      v86 = 0;
      ATL::PrivateAtlThrow(Error);
    }
    v35 = 1;
    v65 = 0;
    v36 = (unsigned int)v74[1];
    v66 = (unsigned int)v74[1];
    if ( !LODWORD(v74[1]) )
      goto LABEL_111;
    ATL::CSid::CSid((ATL::CSid *)v93);
    v67[0] = 0;
    v64 = 0;
    if ( v76 && *(_QWORD *)&v80->Revision )
    {
      v21 = User::LookupSid(v76, (void **)&v78);
      if ( v21 < 0 )
      {
        ATL::CSid::~CSid((ATL::CSid *)v93);
LABEL_74:
        ATL::CSid::~CSid((ATL::CSid *)&v84);
        ATL::CDacl::~CDacl((ATL::CDacl *)&v70);
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hMem);
LABEL_34:
        tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v77);
        operator delete(v13);
        return (unsigned int)v21;
      }
      ATL::CSid::CSid((ATL::CSid *)v95, v78);
      if ( !(unsigned __int8)ATL::operator==(v95, &v84) )
      {
        for ( i = v36 - 1; (int)i >= 0; i = (unsigned int)(i - 1) )
        {
          ATL::CAcl::GetAclEntry(
            (ATL::CAcl *)&v70,
            i,
            (struct ATL::CSid *)v93,
            v67,
            &v64,
            *(unsigned __int8 **)dwFlagsAndAttributes,
            (struct _GUID *)hTemplateFile,
            (struct _GUID *)ppSecurityDescriptor);
          if ( v67[0] == 1179785 && !v64 && (unsigned __int8)ATL::operator==(v93, v95) )
          {
            v38 = (void *)(i + 1);
            if ( i + 1 < (unsigned __int64)(unsigned int)i || v38 > v74[1] )
              ATL::PrivateAtlThrow(0x80070057);
            v65 = 1;
            v76 = (User *)((char *)v74[1] - (char *)v38);
            ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
              (char *)v74[0] + 8 * i,
              1);
            if ( v76 )
            {
              v39 = memmove_s((char *)v74[0] + 8 * i, 8LL * (_QWORD)v76, (char *)v74[0] + 8 * i + 8, 8LL * (_QWORD)v76);
              ATL::AtlCrtErrorCheck(v39);
            }
            --v74[1];
            v66 = --v36;
          }
        }
      }
      ATL::CSid::~CSid((ATL::CSid *)v95);
    }
    v40 = 0;
    while ( 1 )
    {
      v67[0] = v40;
      if ( v40 >= v36 )
      {
        v35 = 1;
        goto LABEL_110;
      }
      v41 = (_DWORD *)((__int64 (__fastcall *)(void ***, _QWORD))v70[4])(&v70, v40);
      ATL::CSid::operator=(v93, v41 + 2);
      v42 = v41[32];
      v43 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v41 + 24LL))(v41);
      if ( v42 == 1179785
        && !v43
        && ATL::CSid::IsValid((ATL::CSid *)v93)
        && ATL::CSid::IsValid((ATL::CSid *)&v84)
        && EqualSid(pSid1, pDestinationSid) )
      {
        break;
      }
      v40 = v67[0] + 1;
      v36 = v66;
    }
    v35 = 0;
    v64 = 0;
    v44 = v66 - 1;
    v66 = v44;
    if ( v44 > v67[0] )
    {
      do
      {
        v45 = (_DWORD *)((__int64 (__fastcall *)(void ***, _QWORD))v70[4])(&v70, v44);
        ATL::CSid::operator=(v93, v45 + 2);
        v46 = v45[32];
        v47 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v45 + 24LL))(v45);
        if ( v46 == 1179785 && !v47 && (unsigned __int8)ATL::operator==(v93, &v84) )
        {
          v48 = v66 + 1LL;
          if ( v48 < v66 || v66 == -1 || (v49 = (char *)v74[1], (void *)v48 > v74[1]) )
            ATL::PrivateAtlThrow(0x80070057);
          v65 = 1;
          v76 = (User *)(8LL * v66);
          ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
            (char *)v74[0] + (unsigned __int64)v76,
            1);
          v50 = &v49[-v48];
          if ( v50 )
          {
            v51 = memmove_s(
                    (char *)v74[0] + (unsigned __int64)v76,
                    8LL * (_QWORD)v50,
                    (char *)v74[0] + 8 * v48,
                    8LL * (_QWORD)v50);
            ATL::AtlCrtErrorCheck(v51);
          }
          --v74[1];
        }
        v44 = v66 - 1;
        v66 = v44;
      }
      while ( v44 > v67[0] );
      v35 = v64;
    }
LABEL_110:
    ATL::CSid::~CSid((ATL::CSid *)v93);
    if ( v35 )
    {
LABEL_111:
      if ( !ATL::CDacl::AddAllowedAce((ATL::CDacl *)&v70, (const struct ATL::CSid *)&v84, v32, v33) )
      {
        v55 = tsched::GetLastHrError(v54, (int)v52);
        v21 = v55;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            66,
            (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
            (_DWORD)v13,
            v55);
        }
        goto LABEL_74;
      }
    }
    v64 = 0;
    if ( v35 || v65 )
    {
      try
      {
        if ( v15 )
        {
          PACL = (struct _ACL *)ATL::CAcl::GetPACL((ATL::CAcl *)&v70);
          v58 = SetSecurityInfo((HANDLE)v15, SE_FILE_OBJECT, 4u, 0, 0, PACL, 0);
          SetLastError(v58);
          v56 = v58 == 0;
        }
        else
        {
          v56 = 0;
        }
        v64 = v56;
      }
      catch ( ... )
      {
        v52 = v60;
        v13 = (wchar_t *)lpFileName;
        v56 = v64;
        v5 = v81;
      }
      if ( !v56 )
      {
        v21 = tsched::GetLastHrError((tsched *)&ATL::CSid::`vftable', (int)v52);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          Path = (unsigned int)JobMoniker::GetPath(v5);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            67,
            (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
            Path,
            v21);
        }
        goto LABEL_74;
      }
    }
    v84 = &ATL::CSid::`vftable';
    ATL::CStringData::Release((ATL::CStringData *)(v91 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v90 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v89 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v88 - 24));
    v70 = &ATL::CDacl::`vftable';
    if ( v74[0] )
    {
      ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
        v74[0],
        v74[1]);
      free(v74[0]);
      v74[0] = 0;
    }
    *(_OWORD *)&v74[1] = 0;
    free(Block);
    Block = 0;
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(v74);
    v70 = &ATL::CAcl::`vftable';
    free(Block);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v77);
    if ( v13 )
      HeapFree(g_PrivateHeap, 0, v13);
    return 0;
  }
  updated = -2147418113;
LABEL_60:
  v70 = &ATL::CDacl::`vftable';
  ATL::CDacl::RemoveAllAces((ATL::CDacl *)&v70);
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(v74);
  v70 = &ATL::CAcl::`vftable';
  free(Block);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v77);
  if ( v13 )
    HeapFree(g_PrivateHeap, 0, v13);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800269f0  push    rbx
0x1800269f2  push    rsi
0x1800269f3  push    rdi
0x1800269f4  push    r12
0x1800269f6  push    r13
0x1800269f8  push    r14
0x1800269fa  push    r15
0x1800269fc  sub     rsp, 4C0h
0x180026a03  mov     rax, cs:__security_cookie
0x180026a0a  xor     rax, rsp
0x180026a0d  mov     [rsp+4F8h+var_48], rax
0x180026a15  mov     rax, r9
0x180026a18  mov     [rsp+4F8h+var_438], rax
0x180026a20  mov     rdi, r8
0x180026a23  mov     r13, rdx
0x180026a26  mov     rbx, rcx
0x180026a29  mov     [rsp+4F8h+var_448], rax
0x180026a31  mov     [rsp+4F8h+var_428], r8
0x180026a39  mov     [rsp+4F8h+var_430], rdx
0x180026a41  mov     [rsp+4F8h+var_420], r8
0x180026a49  mov     [rsp+4F8h+var_460], rax
0x180026a51  xor     esi, esi
0x180026a53  xor     eax, eax
0x180026a55  lock cmpxchg [rbx+5Ch], esi
0x180026a5a  jnz     short loc_180026A69
0x180026a5c  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180026a61  call    cs:__imp_Sleep
0x180026a67  jmp     short loc_180026A53
0x180026a69  mov     rax, [rbx+50h]
0x180026a6d  cmp     [rax+0B8h], esi
0x180026a73  jz      loc_180027681
0x180026a79  cmp     [rdi], rsi
0x180026a7c  jz      loc_180027681
0x180026a82  mov     [rsp+4F8h+lpFileName], rsi
0x180026a87  mov     rax, [r13+10h]
0x180026a8b  test    rax, rax
0x180026a8e  jz      short loc_180026AC1
0x180026a90  mov     rcx, [rax]; pbstr
0x180026a93  test    rcx, rcx
0x180026a96  jz      short loc_180026AA0
0x180026a98  call    cs:__imp_SysStringLen
0x180026a9e  jmp     short loc_180026AA2
0x180026aa0  mov     eax, esi
0x180026aa2  test    eax, eax
0x180026aa4  jz      short loc_180026AC1
0x180026aa6  mov     rax, [r13+10h]
0x180026aaa  test    rax, rax
0x180026aad  jz      short loc_180026AB8
0x180026aaf  mov     rcx, [rax]
0x180026ab2  lea     rdx, [rcx+0Eh]
0x180026ab6  jmp     short loc_180026AC4
0x180026ab8  mov     rcx, rsi
0x180026abb  lea     rdx, [rcx+0Eh]
0x180026abf  jmp     short loc_180026AC4
0x180026ac1  mov     rdx, rsi
0x180026ac4  lea     r8, [rsp+4F8h+lpFileName]
0x180026ac9  mov     rcx, rbx
0x180026acc  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180026ad1  mov     ebx, eax
0x180026ad3  test    eax, eax
0x180026ad5  jns     short loc_180026AE8
0x180026ad7  mov     rcx, [rsp+4F8h+lpFileName]; void *
0x180026adc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026ae1  mov     eax, ebx
0x180026ae3  jmp     loc_180027683
0x180026ae8  xorps   xmm0, xmm0
0x180026aeb  movdqu  [rsp+4F8h+var_458], xmm0
0x180026af4  mov     r15, [rsp+4F8h+lpFileName]
0x180026af9  mov     [rsp+4F8h+hTemplateFile], rsi; hTemplateFile
0x180026afe  mov     [rsp+4F8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180026b06  mov     [rsp+4F8h+dwCreationDisposition], 3; dwCreationDisposition
0x180026b0e  xor     r9d, r9d; lpSecurityAttributes
0x180026b11  mov     edx, 42000000h; dwDesiredAccess
0x180026b16  mov     r8d, 1; dwShareMode
0x180026b1c  mov     rcx, r15; lpFileName
0x180026b1f  call    cs:__imp_CreateFileW
0x180026b25  mov     rbx, rax
0x180026b28  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026b2c  jnz     short loc_180026B36
0x180026b2e  mov     r14, rax
0x180026b31  jmp     loc_180026BCA
0x180026b36  xorps   xmm0, xmm0
0x180026b39  xor     eax, eax
0x180026b3b  movups  xmmword ptr [rsp+4F8h+FileInformation.dwFileAttributes], xmm0
0x180026b43  movups  xmmword ptr [rsp+4F8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180026b4b  movups  xmmword ptr [rsp+4F8h+FileInformation.nFileSizeHigh], xmm0
0x180026b53  mov     [rsp+4F8h+FileInformation.nFileIndexLow], eax
0x180026b5a  xor     r9d, r9d; dwFlags
0x180026b5d  mov     r8d, 105h; cchFilePath
0x180026b63  lea     rdx, [rsp+4F8h+szFilePath]; lpszFilePath
0x180026b6b  mov     rcx, rbx; hFile
0x180026b6e  call    cs:__imp_GetFinalPathNameByHandleW
0x180026b74  dec     eax
0x180026b76  cmp     eax, 103h
0x180026b7b  ja      loc_180026C84
0x180026b81  mov     r8d, 105h; MaxCount
0x180026b87  mov     rdx, r15; String2
0x180026b8a  lea     rcx, [rsp+4F8h+szFilePath]; String1
0x180026b92  call    cs:__imp__wcsnicmp
0x180026b98  test    eax, eax
0x180026b9a  jnz     loc_180026C91
0x180026ba0  lea     rdx, [rsp+4F8h+FileInformation]; lpFileInformation
0x180026ba8  mov     rcx, rbx; hFile
0x180026bab  call    cs:__imp_GetFileInformationByHandle
0x180026bb1  test    eax, eax
0x180026bb3  jz      loc_180026C91
0x180026bb9  cmp     [rsp+4F8h+FileInformation.nNumberOfLinks], 1
0x180026bc1  ja      loc_180026C91
0x180026bc7  mov     r14, rbx
0x180026bca  mov     qword ptr [rsp+4F8h+var_4B0], r14
0x180026bcf  lea     rbx, WPP_GLOBAL_Control
0x180026bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180026bdd  cmp     rcx, rbx
0x180026be0  jz      short loc_180026C09
0x180026be2  test    dword ptr [rcx+1Ch], 10000h
0x180026be9  jz      short loc_180026C09
0x180026beb  cmp     byte ptr [rcx+19h], 4
0x180026bef  jb      short loc_180026C09
0x180026bf1  mov     edx, 10h
0x180026bf6  mov     r9, r14
0x180026bf9  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x180026c00  mov     rcx, [rcx+10h]
0x180026c04  call    WPP_SF_q
0x180026c09  lea     rcx, [rsp+4F8h+var_458]; this
0x180026c11  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180026c16  mov     qword ptr [rsp+4F8h+var_458], r14
0x180026c1e  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180026c22  jnz     loc_180026CB6
0x180026c28  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180026c2d  mov     edi, eax
0x180026c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c36  cmp     rcx, rbx
0x180026c39  jz      short loc_180026C67
0x180026c3b  test    dword ptr [rcx+1Ch], 40000h
0x180026c42  jz      short loc_180026C67
0x180026c44  cmp     byte ptr [rcx+19h], 2
0x180026c48  jb      short loc_180026C67
0x180026c4a  mov     edx, 3Fh ; '?'
0x180026c4f  mov     [rsp+4F8h+dwCreationDisposition], eax
0x180026c53  mov     r9, r15
0x180026c56  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180026c5d  mov     rcx, [rcx+10h]
0x180026c61  call    WPP_SF_Sd
0x180026c66  nop
0x180026c67  lea     rcx, [rsp+4F8h+var_458]; this
0x180026c6f  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180026c74  nop
0x180026c75  mov     rcx, r15; void *
0x180026c78  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026c7d  mov     eax, edi
0x180026c7f  jmp     loc_180027683
0x180026c84  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180026c89  test    eax, eax
0x180026c8b  jns     loc_180026BC7
0x180026c91  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180026c98  mov     qword ptr [rsp+4F8h+var_4B0], r14
0x180026c9d  mov     ecx, 5; dwErrCode
0x180026ca2  call    cs:__imp_SetLastError
0x180026ca8  mov     rcx, rbx; hObject
0x180026cab  call    cs:__imp_CloseHandle
0x180026cb1  jmp     loc_180026BCF
0x180026cb6  mov     qword ptr [rsp+4F8h+var_458+8], r15
0x180026cbe  mov     [rsp+4F8h+ppDacl], rsi
0x180026cc6  mov     [rsp+4F8h+hMem], rsi
0x180026ccb  lea     rax, [rsp+4F8h+hMem]
0x180026cd0  mov     [rsp+4F8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180026cd5  mov     [rsp+4F8h+hTemplateFile], rsi; ppSacl
0x180026cda  lea     rax, [rsp+4F8h+ppDacl]
0x180026ce2  mov     qword ptr [rsp+4F8h+dwFlagsAndAttributes], rax; ppDacl
0x180026ce7  mov     qword ptr [rsp+4F8h+dwCreationDisposition], rsi; ppsidGroup
0x180026cec  xor     r9d, r9d; ppsidOwner
0x180026cef  mov     edx, 1; ObjectType
0x180026cf4  mov     r8d, 4; SecurityInfo
0x180026cfa  mov     rcx, r14; handle
0x180026cfd  call    cs:__imp_GetSecurityInfo
0x180026d03  mov     r12d, eax
0x180026d06  test    eax, eax
0x180026d08  jz      short loc_180026D79
0x180026d0a  jle     short loc_180026D17
0x180026d0c  movzx   r12d, ax
0x180026d10  or      r12d, 80070000h
0x180026d17  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d1e  cmp     rcx, rbx
0x180026d21  jz      short loc_180026D50
0x180026d23  test    dword ptr [rcx+1Ch], 40000h
0x180026d2a  jz      short loc_180026D50
0x180026d2c  cmp     byte ptr [rcx+19h], 2
0x180026d30  jb      short loc_180026D50
0x180026d32  mov     edx, 40h ; '@'
0x180026d37  mov     [rsp+4F8h+dwCreationDisposition], r12d
0x180026d3c  mov     r9, r15
0x180026d3f  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180026d46  mov     rcx, [rcx+10h]
0x180026d4a  call    WPP_SF_Sd
0x180026d4f  nop
0x180026d50  lea     rcx, [rsp+4F8h+hMem]
0x180026d55  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180026d5a  nop
0x180026d5b  lea     rcx, [rsp+4F8h+var_458]; this
0x180026d63  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180026d68  nop
0x180026d69  mov     rcx, r15; void *
0x180026d6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026d71  mov     eax, r12d
0x180026d74  jmp     loc_180027683
0x180026d79  mov     [rsp+4F8h+Block], rsi
0x180026d7e  mov     [rsp+4F8h+var_488], 0
0x180026d83  mov     [rsp+4F8h+var_484], 2
0x180026d8b  lea     r12, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x180026d92  mov     [rsp+4F8h+var_498], r12
0x180026d97  xorps   xmm0, xmm0
0x180026d9a  movdqu  xmmword ptr [rsp+4F8h+var_480], xmm0
0x180026da0  mov     [rsp+4F8h+var_470], rsi
0x180026da8  mov     [rsp+4F8h+var_468], esi
0x180026daf  mov     rbx, [rsp+4F8h+ppDacl]
0x180026db7  lea     rcx, [rsp+4F8h+var_498]; this
0x180026dbc  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180026dc1  mov     rdx, rbx; struct _ACL *
0x180026dc4  lea     rcx, [rsp+4F8h+var_498]; this
0x180026dc9  call    ?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z; ATL::CDacl::Copy(_ACL const &)
0x180026dce  nop
0x180026dcf  jmp     loc_180026E8C
0x180026dd4  mov     edi, [rsp+4F8h+var_4B4]
0x180026dd8  test    edi, edi
0x180026dda  jns     short loc_180026E59
0x180026ddc  lea     rbx, WPP_GLOBAL_Control
0x180026de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180026dea  cmp     rcx, rbx
0x180026ded  jz      short loc_180026E21
0x180026def  test    dword ptr [rcx+1Ch], 40000h
0x180026df6  jz      short loc_180026E21
0x180026df8  cmp     byte ptr [rcx+19h], 2
0x180026dfc  jb      short loc_180026E21
0x180026dfe  mov     edx, 41h ; 'A'
0x180026e03  mov     [rsp+4F8h+dwCreationDisposition], edi
0x180026e07  mov     rbx, [rsp+4F8h+lpFileName]
0x180026e0c  mov     r9, rbx
0x180026e0f  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180026e16  mov     rcx, [rcx+10h]
0x180026e1a  call    WPP_SF_Sd
0x180026e1f  jmp     short loc_180026E26
0x180026e21  mov     rbx, [rsp+4F8h+lpFileName]
0x180026e26  lea     rcx, [rsp+4F8h+var_498]; this
0x180026e2b  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x180026e30  nop
0x180026e31  lea     rcx, [rsp+4F8h+hMem]
0x180026e36  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180026e3b  nop
0x180026e3c  lea     rcx, [rsp+4F8h+var_458]; this
0x180026e44  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180026e49  nop
0x180026e4a  mov     rcx, rbx; void *
0x180026e4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026e52  mov     eax, edi
0x180026e54  jmp     loc_180027683
0x180026e59  xor     esi, esi
0x180026e5b  lea     r12, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x180026e62  mov     r15, [rsp+4F8h+lpFileName]
0x180026e67  mov     r14, qword ptr [rsp+4F8h+var_4B0]
0x180026e6c  mov     rax, [rsp+4F8h+var_448]
0x180026e74  mov     [rsp+4F8h+var_438], rax
0x180026e7c  mov     rdi, [rsp+4F8h+var_428]
0x180026e84  mov     r13, [rsp+4F8h+var_430]
0x180026e8c  mov     rax, [rdi]
0x180026e8f  test    rax, rax
0x180026e92  jnz     short loc_180026E9B
0x180026e94  mov     ebx, 8000FFFFh
0x180026e99  jmp     short loc_180026EC5
0x180026e9b  cmp     byte ptr [rax], 0
0x180026e9e  jz      short loc_180026EA7
0x180026ea0  mov     ebx, 8000FFFFh
0x180026ea5  jmp     short loc_180026EC5
0x180026ea7  cmp     qword ptr [rax+20h], 0
0x180026eac  jnz     loc_180026F37
0x180026eb2  mov     rcx, [rsp+4F8h+var_420]; this
0x180026eba  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180026ebf  mov     ebx, eax
0x180026ec1  test    eax, eax
0x180026ec3  jns     short loc_180026F37
0x180026ec5  mov     [rsp+4F8h+var_498], r12
0x180026eca  lea     rcx, [rsp+4F8h+var_498]; this
0x180026ecf  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180026ed4  lea     rcx, [rsp+4F8h+var_480]
0x180026ed9  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x180026ede  lea     rax, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x180026ee5  mov     [rsp+4F8h+var_498], rax
0x180026eea  mov     rcx, [rsp+4F8h+Block]; Block
0x180026eef  call    cs:__imp_free
0x180026ef5  nop
0x180026ef6  mov     rcx, [rsp+4F8h+hMem]; hMem
0x180026efb  test    rcx, rcx
0x180026efe  jz      short loc_180026F0B
0x180026f00  call    cs:__imp_LocalFree
0x180026f06  mov     [rsp+4F8h+hMem], rsi
0x180026f0b  lea     rcx, [rsp+4F8h+var_458]; this
0x180026f13  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180026f18  nop
0x180026f19  test    r15, r15
0x180026f1c  jz      short loc_180026F30
0x180026f1e  mov     r8, r15; lpMem
  ... truncated ...
```
