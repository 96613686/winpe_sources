# JobStore::HammerAcl(JobMoniker const &,User const &,User const *)

- ea: `0x180021ba0`
- end: `0x180022890`
- name: `?HammerAcl@JobStore@@QEBAJAEBVJobMoniker@@AEBVUser@@PEBV3@@Z`
- size: `3312`
- prototype: `int(JobStore *__hidden this, const struct JobMoniker *, const struct User *, const struct User *)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180023c4c`
- `0x180047ee0`

## callees

- `0x18000cc40`
- `0x18001fe10`
- `0x18002177c`
- `0x1800217f0`
- `0x180021844`
- `0x180021ba0`
- `0x180022898`
- `0x1800228ec`
- `0x180022920`
- `0x1800229a0`
- `0x180022d80`
- `0x1800237a4`
- `0x1800237dc`
- `0x18002c2f4`
- `0x18002db74`
- `0x180045120`
- `0x180047360`
- `0x180047d54`
- `0x18004ca24`
- `0x18004d530`
- `0x18004e33c`
- `0x1800529a0`
- `0x1800543f0`
- `0x180054a90`
- `0x180054c80`
- `0x180055004`
- `0x180059140`
- `0x18005de10`
- `0x18006acbc`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180021d54`
- `msvcrt!_wcsnicmp` at `0x180021d54`
- `msvcrt!memmove_s` at `0x1800223df`
- `msvcrt!memmove_s` at `0x1800225cf`
- `msvcrt!memmove_s` at `0x1800223df`
- `msvcrt!memmove_s` at `0x1800225cf`
- `msvcrt!free` at `0x1800220cf`
- `msvcrt!free` at `0x18002280f`
- `msvcrt!free` at `0x1800220cf`
- `msvcrt!free` at `0x18002280f`
- `OLEAUT32!__imp_SysStringLen` at `0x180021c4b`
- `OLEAUT32!__imp_SysStringLen` at `0x180021c4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021e67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800226e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021e67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800226e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021cd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021cd5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180021d2a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180021d2a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180021d73`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180021d73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022853`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022853`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021c0e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021c0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800220e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022826`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800220e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022826`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800221e8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800221e8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800221d1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800221d1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800224a0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800224a0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022212`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022212`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800226d9`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800226d9`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180021ecb`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180021ecb`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
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
  unsigned __int64 v38; // rax
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
  __int64 v49; // rdi
  __int64 v50; // rdi
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
  User *v70; // [rsp+60h] [rbp-498h]
  __int128 v71; // [rsp+68h] [rbp-490h] BYREF
  void **v72; // [rsp+78h] [rbp-480h] BYREF
  void *Block; // [rsp+80h] [rbp-478h]
  char v74; // [rsp+88h] [rbp-470h]
  int v75; // [rsp+8Ch] [rbp-46Ch]
  __int128 v76; // [rsp+90h] [rbp-468h] BYREF
  __int64 v77; // [rsp+A0h] [rbp-458h]
  int v78; // [rsp+A8h] [rbp-450h]
  struct _SID *v79; // [rsp+B0h] [rbp-448h] BYREF
  PACL ppDacl; // [rsp+B8h] [rbp-440h] BYREF
  struct _SID *v81; // [rsp+C0h] [rbp-438h]
  const struct JobMoniker *v82; // [rsp+C8h] [rbp-430h]
  const struct User *v83; // [rsp+D0h] [rbp-428h]
  User *v84; // [rsp+D8h] [rbp-420h]
  void **v85; // [rsp+E0h] [rbp-418h] BYREF
  _BYTE pDestinationSid[68]; // [rsp+E8h] [rbp-410h] BYREF
  char v87; // [rsp+12Ch] [rbp-3CCh]
  int v88; // [rsp+130h] [rbp-3C8h]
  __int64 v89; // [rsp+138h] [rbp-3C0h]
  __int64 v90; // [rsp+140h] [rbp-3B8h]
  __int64 v91; // [rsp+148h] [rbp-3B0h]
  __int64 v92; // [rsp+150h] [rbp-3A8h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+160h] [rbp-398h] BYREF
  _BYTE v94[8]; // [rsp+1A0h] [rbp-358h] BYREF
  _BYTE pSid1[120]; // [rsp+1A8h] [rbp-350h] BYREF
  _BYTE v96[128]; // [rsp+220h] [rbp-2D8h] BYREF
  WCHAR szFilePath[264]; // [rsp+2A0h] [rbp-258h] BYREF

  v81 = a4;
  v4 = a3;
  v5 = a2;
  v79 = a4;
  v83 = a3;
  v82 = a2;
  v84 = a3;
  v70 = (User *)a4;
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
  v71 = 0;
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
  tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v71);
  *(_QWORD *)&v71 = v15;
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
  *((_QWORD *)&v71 + 1) = v13;
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
    tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v71);
    operator delete(v13);
    return v23;
  }
  Block = 0;
  v74 = 0;
  v75 = 2;
  v72 = &ATL::CDacl::`vftable';
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v24 = ppDacl;
  ATL::CDacl::RemoveAllAces((ATL::CDacl *)&v72);
  try
  {
    ATL::CDacl::Copy((ATL::CDacl *)&v72, v24);
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
      ATL::CDacl::~CDacl((ATL::CDacl *)&v72);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hMem);
      tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v71);
      operator delete(v27);
      return v26;
    }
    v13 = (wchar_t *)lpFileName;
    v15 = *(_QWORD *)v67;
    v81 = v79;
    v4 = v83;
    v5 = v82;
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
      updated = User::UpdateEntry(v84);
      if ( updated < 0 )
        goto LABEL_60;
    }
    v79 = *(struct _SID **)(*(_QWORD *)v4 + 32LL);
    v30 = v79;
    v85 = &ATL::CSid::`vftable';
    v87 = 0;
    v88 = 7;
    v89 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v90 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v91 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v92 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !IsValidSid(v30) || (LengthSid = GetLengthSid(v30), LengthSid > 0x44) )
      ATL::PrivateAtlThrow(0x80070057);
    v87 = 1;
    if ( !CopySid(LengthSid, pDestinationSid, v30) )
    {
      Error = ATL::AtlHresultFromLastError();
      v87 = 0;
      ATL::PrivateAtlThrow(Error);
    }
    v35 = 1;
    v65 = 0;
    v36 = DWORD2(v76);
    v66 = DWORD2(v76);
    if ( !DWORD2(v76) )
      goto LABEL_109;
    ATL::CSid::CSid((ATL::CSid *)v94);
    v67[0] = 0;
    v64 = 0;
    if ( v70 && *(_QWORD *)&v81->Revision )
    {
      v21 = User::LookupSid(v70, (void **)&v79);
      if ( v21 < 0 )
      {
        ATL::CSid::~CSid((ATL::CSid *)v94);
LABEL_72:
        ATL::CSid::~CSid((ATL::CSid *)&v85);
        ATL::CDacl::~CDacl((ATL::CDacl *)&v72);
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hMem);
LABEL_34:
        tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v71);
        operator delete(v13);
        return (unsigned int)v21;
      }
      ATL::CSid::CSid((ATL::CSid *)v96, v79);
      if ( !(unsigned __int8)ATL::operator==(v96, &v85) )
      {
        for ( i = v36 - 1; (int)i >= 0; i = (unsigned int)(i - 1) )
        {
          ATL::CAcl::GetAclEntry(
            (ATL::CAcl *)&v72,
            i,
            (struct ATL::CSid *)v94,
            v67,
            &v64,
            *(unsigned __int8 **)dwFlagsAndAttributes,
            (struct _GUID *)hTemplateFile,
            (struct _GUID *)ppSecurityDescriptor);
          if ( v67[0] == 1179785 && !v64 && (unsigned __int8)ATL::operator==(v94, v96) )
          {
            v38 = i + 1;
            if ( i + 1 < (unsigned __int64)(unsigned int)i || v38 > *((_QWORD *)&v76 + 1) )
              ATL::PrivateAtlThrow(0x80070057);
            v65 = 1;
            v70 = (User *)(*((_QWORD *)&v76 + 1) - v38);
            ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
              v76 + 8 * i,
              1);
            if ( v70 )
            {
              v39 = memmove_s(
                      (void *const)(v76 + 8 * i),
                      8LL * (_QWORD)v70,
                      (const void *const)(v76 + 8 + 8 * i),
                      8LL * (_QWORD)v70);
              ATL::AtlCrtErrorCheck(v39);
            }
            --*((_QWORD *)&v76 + 1);
            v66 = --v36;
          }
        }
      }
      ATL::CSid::~CSid((ATL::CSid *)v96);
    }
    v40 = 0;
    while ( 1 )
    {
      v67[0] = v40;
      if ( v40 >= v36 )
      {
        v35 = 1;
        goto LABEL_108;
      }
      v41 = (_DWORD *)((__int64 (__fastcall *)(void ***, _QWORD))v72[4])(&v72, v40);
      ATL::CSid::operator=(v94, v41 + 2);
      v42 = v41[32];
      v43 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v41 + 24LL))(v41);
      if ( v42 == 1179785
        && !v43
        && ATL::CSid::IsValid((ATL::CSid *)v94)
        && ATL::CSid::IsValid((ATL::CSid *)&v85)
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
        v45 = (_DWORD *)((__int64 (__fastcall *)(void ***, _QWORD))v72[4])(&v72, v44);
        ATL::CSid::operator=(v94, v45 + 2);
        v46 = v45[32];
        v47 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v45 + 24LL))(v45);
        if ( v46 == 1179785 && !v47 && (unsigned __int8)ATL::operator==(v94, &v85) )
        {
          v48 = v66 + 1LL;
          if ( v48 < v66 || v66 == -1 || (v49 = *((_QWORD *)&v76 + 1), v48 > *((_QWORD *)&v76 + 1)) )
            ATL::PrivateAtlThrow(0x80070057);
          v65 = 1;
          v70 = (User *)(8LL * v66);
          ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
            (char *)v70 + v76,
            1);
          v50 = v49 - v48;
          if ( v50 )
          {
            v51 = memmove_s((char *)v70 + v76, 8 * v50, (const void *const)(v76 + 8 * v48), 8 * v50);
            ATL::AtlCrtErrorCheck(v51);
          }
          --*((_QWORD *)&v76 + 1);
        }
        v44 = v66 - 1;
        v66 = v44;
      }
      while ( v44 > v67[0] );
      v35 = v64;
    }
LABEL_108:
    ATL::CSid::~CSid((ATL::CSid *)v94);
    if ( v35 )
    {
LABEL_109:
      if ( !ATL::CDacl::AddAllowedAce((ATL::CDacl *)&v72, (const struct ATL::CSid *)&v85, v32, v33) )
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
        goto LABEL_72;
      }
    }
    v64 = 0;
    if ( v35 || v65 )
    {
      try
      {
        if ( v15 )
        {
          PACL = (struct _ACL *)ATL::CAcl::GetPACL((ATL::CAcl *)&v72);
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
        v5 = v82;
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
        goto LABEL_72;
      }
    }
    v85 = &ATL::CSid::`vftable';
    ATL::CStringData::Release((ATL::CStringData *)(v92 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v91 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v90 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v89 - 24));
    v72 = &ATL::CDacl::`vftable';
    ATL::CDacl::RemoveAllAces((ATL::CDacl *)&v72);
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(&v76);
    v72 = &ATL::CAcl::`vftable';
    free(Block);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v71);
    if ( v13 )
      HeapFree(g_PrivateHeap, 0, v13);
    return 0;
  }
  updated = -2147418113;
LABEL_60:
  v72 = &ATL::CDacl::`vftable';
  ATL::CDacl::RemoveAllAces((ATL::CDacl *)&v72);
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(&v76);
  v72 = &ATL::CAcl::`vftable';
  free(Block);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)&v71);
  operator delete(v13);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180021ba0  push    rbx
0x180021ba2  push    rsi
0x180021ba3  push    rdi
0x180021ba4  push    r12
0x180021ba6  push    r13
0x180021ba8  push    r14
0x180021baa  push    r15
0x180021bac  sub     rsp, 4C0h
0x180021bb3  mov     rax, cs:__security_cookie
0x180021bba  xor     rax, rsp
0x180021bbd  mov     [rsp+4F8h+var_48], rax
0x180021bc5  mov     rax, r9
0x180021bc8  mov     [rsp+4F8h+var_438], rax
0x180021bd0  mov     rdi, r8
0x180021bd3  mov     r13, rdx
0x180021bd6  mov     rbx, rcx
0x180021bd9  mov     [rsp+4F8h+var_448], rax
0x180021be1  mov     [rsp+4F8h+var_428], r8
0x180021be9  mov     [rsp+4F8h+var_430], rdx
0x180021bf1  mov     [rsp+4F8h+var_420], r8
0x180021bf9  mov     [rsp+4F8h+var_498], rax
0x180021bfe  xor     esi, esi
0x180021c00  xor     eax, eax
0x180021c02  lock cmpxchg [rbx+5Ch], esi
0x180021c07  jnz     short loc_180021C1C
0x180021c09  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180021c0e  call    cs:__imp_Sleep
0x180021c15  nop     dword ptr [rax+rax+00h]
0x180021c1a  jmp     short loc_180021C00
0x180021c1c  mov     rax, [rbx+50h]
0x180021c20  cmp     [rax+0B8h], esi
0x180021c26  jz      loc_18002285F
0x180021c2c  cmp     [rdi], rsi
0x180021c2f  jz      loc_18002285F
0x180021c35  mov     [rsp+4F8h+lpFileName], rsi
0x180021c3a  mov     rax, [r13+10h]
0x180021c3e  test    rax, rax
0x180021c41  jz      short loc_180021C7A
0x180021c43  mov     rcx, [rax]; pbstr
0x180021c46  test    rcx, rcx
0x180021c49  jz      short loc_180021C59
0x180021c4b  call    cs:__imp_SysStringLen
0x180021c52  nop     dword ptr [rax+rax+00h]
0x180021c57  jmp     short loc_180021C5B
0x180021c59  mov     eax, esi
0x180021c5b  test    eax, eax
0x180021c5d  jz      short loc_180021C7A
0x180021c5f  mov     rax, [r13+10h]
0x180021c63  test    rax, rax
0x180021c66  jz      short loc_180021C71
0x180021c68  mov     rcx, [rax]
0x180021c6b  lea     rdx, [rcx+0Eh]
0x180021c6f  jmp     short loc_180021C7D
0x180021c71  mov     rcx, rsi
0x180021c74  lea     rdx, [rcx+0Eh]
0x180021c78  jmp     short loc_180021C7D
0x180021c7a  mov     rdx, rsi
0x180021c7d  lea     r8, [rsp+4F8h+lpFileName]
0x180021c82  mov     rcx, rbx
0x180021c85  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180021c8a  mov     ebx, eax
0x180021c8c  test    eax, eax
0x180021c8e  jns     short loc_180021CA1
0x180021c90  mov     rcx, [rsp+4F8h+lpFileName]; void *
0x180021c95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021c9a  mov     eax, ebx
0x180021c9c  jmp     loc_180022861
0x180021ca1  xorps   xmm0, xmm0
0x180021ca4  movdqu  [rsp+4F8h+var_490], xmm0
0x180021caa  mov     r15, [rsp+4F8h+lpFileName]
0x180021caf  mov     [rsp+4F8h+hTemplateFile], rsi; hTemplateFile
0x180021cb4  mov     [rsp+4F8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180021cbc  mov     [rsp+4F8h+dwCreationDisposition], 3; dwCreationDisposition
0x180021cc4  xor     r9d, r9d; lpSecurityAttributes
0x180021cc7  mov     edx, 42000000h; dwDesiredAccess
0x180021ccc  mov     r8d, 1; dwShareMode
0x180021cd2  mov     rcx, r15; lpFileName
0x180021cd5  call    cs:__imp_CreateFileW
0x180021cdc  nop     dword ptr [rax+rax+00h]
0x180021ce1  mov     rbx, rax
0x180021ce4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021ce8  jnz     short loc_180021CF2
0x180021cea  mov     r14, rax
0x180021ced  jmp     loc_180021D98
0x180021cf2  xorps   xmm0, xmm0
0x180021cf5  xor     eax, eax
0x180021cf7  movups  xmmword ptr [rsp+4F8h+FileInformation.dwFileAttributes], xmm0
0x180021cff  movups  xmmword ptr [rsp+4F8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180021d07  movups  xmmword ptr [rsp+4F8h+FileInformation.nFileSizeHigh], xmm0
0x180021d0f  mov     [rsp+4F8h+FileInformation.nFileIndexLow], eax
0x180021d16  xor     r9d, r9d; dwFlags
0x180021d19  mov     r8d, 105h; cchFilePath
0x180021d1f  lea     rdx, [rsp+4F8h+szFilePath]; lpszFilePath
0x180021d27  mov     rcx, rbx; hFile
0x180021d2a  call    cs:__imp_GetFinalPathNameByHandleW
0x180021d31  nop     dword ptr [rax+rax+00h]
0x180021d36  dec     eax
0x180021d38  cmp     eax, 103h
0x180021d3d  ja      loc_180021E49
0x180021d43  mov     r8d, 105h; MaxCount
0x180021d49  mov     rdx, r15; String2
0x180021d4c  lea     rcx, [rsp+4F8h+szFilePath]; String1
0x180021d54  call    cs:__imp__wcsnicmp
0x180021d5b  nop     dword ptr [rax+rax+00h]
0x180021d60  test    eax, eax
0x180021d62  jnz     loc_180021E56
0x180021d68  lea     rdx, [rsp+4F8h+FileInformation]; lpFileInformation
0x180021d70  mov     rcx, rbx; hFile
0x180021d73  call    cs:__imp_GetFileInformationByHandle
0x180021d7a  nop     dword ptr [rax+rax+00h]
0x180021d7f  test    eax, eax
0x180021d81  jz      loc_180021E56
0x180021d87  cmp     [rsp+4F8h+FileInformation.nNumberOfLinks], 1
0x180021d8f  ja      loc_180021E56
0x180021d95  mov     r14, rbx
0x180021d98  mov     qword ptr [rsp+4F8h+var_4B0], r14
0x180021d9d  lea     rbx, WPP_GLOBAL_Control
0x180021da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180021dab  cmp     rcx, rbx
0x180021dae  jz      short loc_180021DD7
0x180021db0  test    dword ptr [rcx+1Ch], 10000h
0x180021db7  jz      short loc_180021DD7
0x180021db9  cmp     byte ptr [rcx+19h], 4
0x180021dbd  jb      short loc_180021DD7
0x180021dbf  mov     edx, 10h
0x180021dc4  mov     r9, r14
0x180021dc7  lea     r8, WPP_0318f2e21e573bf245f738540b7f5294_Traceguids
0x180021dce  mov     rcx, [rcx+10h]
0x180021dd2  call    WPP_SF_q
0x180021dd7  lea     rcx, [rsp+4F8h+var_490]; this
0x180021ddc  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180021de1  mov     qword ptr [rsp+4F8h+var_490], r14
0x180021de6  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180021dea  jnz     loc_180021E87
0x180021df0  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180021df5  mov     edi, eax
0x180021df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180021dfe  cmp     rcx, rbx
0x180021e01  jz      short loc_180021E2F
0x180021e03  test    dword ptr [rcx+1Ch], 40000h
0x180021e0a  jz      short loc_180021E2F
0x180021e0c  cmp     byte ptr [rcx+19h], 2
0x180021e10  jb      short loc_180021E2F
0x180021e12  mov     edx, 3Fh ; '?'
0x180021e17  mov     [rsp+4F8h+dwCreationDisposition], eax
0x180021e1b  mov     r9, r15
0x180021e1e  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180021e25  mov     rcx, [rcx+10h]
0x180021e29  call    WPP_SF_Sd
0x180021e2e  nop
0x180021e2f  lea     rcx, [rsp+4F8h+var_490]; this
0x180021e34  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180021e39  nop
0x180021e3a  mov     rcx, r15; void *
0x180021e3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021e42  mov     eax, edi
0x180021e44  jmp     loc_180022861
0x180021e49  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180021e4e  test    eax, eax
0x180021e50  jns     loc_180021D95
0x180021e56  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180021e5d  mov     qword ptr [rsp+4F8h+var_4B0], r14
0x180021e62  mov     ecx, 5; dwErrCode
0x180021e67  call    cs:__imp_SetLastError
0x180021e6e  nop     dword ptr [rax+rax+00h]
0x180021e73  mov     rcx, rbx; hObject
0x180021e76  call    cs:__imp_CloseHandle
0x180021e7d  nop     dword ptr [rax+rax+00h]
0x180021e82  jmp     loc_180021D9D
0x180021e87  mov     qword ptr [rsp+4F8h+var_490+8], r15
0x180021e8c  mov     [rsp+4F8h+ppDacl], rsi
0x180021e94  mov     [rsp+4F8h+hMem], rsi
0x180021e99  lea     rax, [rsp+4F8h+hMem]
0x180021e9e  mov     [rsp+4F8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180021ea3  mov     [rsp+4F8h+hTemplateFile], rsi; ppSacl
0x180021ea8  lea     rax, [rsp+4F8h+ppDacl]
0x180021eb0  mov     qword ptr [rsp+4F8h+dwFlagsAndAttributes], rax; ppDacl
0x180021eb5  mov     qword ptr [rsp+4F8h+dwCreationDisposition], rsi; ppsidGroup
0x180021eba  xor     r9d, r9d; ppsidOwner
0x180021ebd  mov     edx, 1; ObjectType
0x180021ec2  mov     r8d, 4; SecurityInfo
0x180021ec8  mov     rcx, r14; handle
0x180021ecb  call    cs:__imp_GetSecurityInfo
0x180021ed2  nop     dword ptr [rax+rax+00h]
0x180021ed7  mov     r12d, eax
0x180021eda  test    eax, eax
0x180021edc  jz      short loc_180021F4A
0x180021ede  jle     short loc_180021EEB
0x180021ee0  movzx   r12d, ax
0x180021ee4  or      r12d, 80070000h
0x180021eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ef2  cmp     rcx, rbx
0x180021ef5  jz      short loc_180021F24
0x180021ef7  test    dword ptr [rcx+1Ch], 40000h
0x180021efe  jz      short loc_180021F24
0x180021f00  cmp     byte ptr [rcx+19h], 2
0x180021f04  jb      short loc_180021F24
0x180021f06  mov     edx, 40h ; '@'
0x180021f0b  mov     [rsp+4F8h+dwCreationDisposition], r12d
0x180021f10  mov     r9, r15
0x180021f13  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180021f1a  mov     rcx, [rcx+10h]
0x180021f1e  call    WPP_SF_Sd
0x180021f23  nop
0x180021f24  lea     rcx, [rsp+4F8h+hMem]
0x180021f29  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180021f2e  nop
0x180021f2f  lea     rcx, [rsp+4F8h+var_490]; this
0x180021f34  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180021f39  nop
0x180021f3a  mov     rcx, r15; void *
0x180021f3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021f42  mov     eax, r12d
0x180021f45  jmp     loc_180022861
0x180021f4a  mov     [rsp+4F8h+Block], rsi
0x180021f52  mov     [rsp+4F8h+var_470], 0
0x180021f5a  mov     [rsp+4F8h+var_46C], 2
0x180021f65  lea     r12, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x180021f6c  mov     [rsp+4F8h+var_480], r12
0x180021f71  xorps   xmm0, xmm0
0x180021f74  movdqu  [rsp+4F8h+var_468], xmm0
0x180021f7d  mov     [rsp+4F8h+var_458], rsi
0x180021f85  mov     [rsp+4F8h+var_450], esi
0x180021f8c  mov     rbx, [rsp+4F8h+ppDacl]
0x180021f94  lea     rcx, [rsp+4F8h+var_480]; this
0x180021f99  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180021f9e  mov     rdx, rbx; struct _ACL *
0x180021fa1  lea     rcx, [rsp+4F8h+var_480]; this
0x180021fa6  call    ?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z; ATL::CDacl::Copy(_ACL const &)
0x180021fab  nop
0x180021fac  jmp     loc_180022066
0x180021fb1  mov     edi, [rsp+4F8h+var_4B4]
0x180021fb5  test    edi, edi
0x180021fb7  jns     short loc_180022033
0x180021fb9  lea     rbx, WPP_GLOBAL_Control
0x180021fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fc7  cmp     rcx, rbx
0x180021fca  jz      short loc_180021FFE
0x180021fcc  test    dword ptr [rcx+1Ch], 40000h
0x180021fd3  jz      short loc_180021FFE
0x180021fd5  cmp     byte ptr [rcx+19h], 2
0x180021fd9  jb      short loc_180021FFE
0x180021fdb  mov     edx, 41h ; 'A'
0x180021fe0  mov     [rsp+4F8h+dwCreationDisposition], edi
0x180021fe4  mov     rbx, [rsp+4F8h+lpFileName]
0x180021fe9  mov     r9, rbx
0x180021fec  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180021ff3  mov     rcx, [rcx+10h]
0x180021ff7  call    WPP_SF_Sd
0x180021ffc  jmp     short loc_180022003
0x180021ffe  mov     rbx, [rsp+4F8h+lpFileName]
0x180022003  lea     rcx, [rsp+4F8h+var_480]; this
0x180022008  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x18002200d  nop
0x18002200e  lea     rcx, [rsp+4F8h+hMem]
0x180022013  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180022018  nop
0x180022019  lea     rcx, [rsp+4F8h+var_490]; this
0x18002201e  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180022023  nop
0x180022024  mov     rcx, rbx; void *
0x180022027  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002202c  mov     eax, edi
0x18002202e  jmp     loc_180022861
0x180022033  xor     esi, esi
0x180022035  lea     r12, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x18002203c  mov     r15, [rsp+4F8h+lpFileName]
0x180022041  mov     r14, qword ptr [rsp+4F8h+var_4B0]
0x180022046  mov     rax, [rsp+4F8h+var_448]
0x18002204e  mov     [rsp+4F8h+var_438], rax
0x180022056  mov     rdi, [rsp+4F8h+var_428]
0x18002205e  mov     r13, [rsp+4F8h+var_430]
0x180022066  mov     rax, [rdi]
0x180022069  test    rax, rax
0x18002206c  jnz     short loc_180022075
0x18002206e  mov     ebx, 8000FFFFh
0x180022073  jmp     short loc_18002209F
0x180022075  cmp     byte ptr [rax], 0
0x180022078  jz      short loc_180022081
0x18002207a  mov     ebx, 8000FFFFh
0x18002207f  jmp     short loc_18002209F
0x180022081  cmp     qword ptr [rax+20h], 0
0x180022086  jnz     loc_180022111
0x18002208c  mov     rcx, [rsp+4F8h+var_420]; this
0x180022094  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180022099  mov     ebx, eax
0x18002209b  test    eax, eax
0x18002209d  jns     short loc_180022111
0x18002209f  mov     [rsp+4F8h+var_480], r12
0x1800220a4  lea     rcx, [rsp+4F8h+var_480]; this
0x1800220a9  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x1800220ae  lea     rcx, [rsp+4F8h+var_468]
0x1800220b6  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x1800220bb  lea     rax, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x1800220c2  mov     [rsp+4F8h+var_480], rax
0x1800220c7  mov     rcx, [rsp+4F8h+Block]; Block
0x1800220cf  call    cs:__imp_free
0x1800220d6  nop     dword ptr [rax+rax+00h]
0x1800220db  nop
0x1800220dc  mov     rcx, [rsp+4F8h+hMem]; hMem
  ... truncated ...
```
