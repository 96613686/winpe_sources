# CReportStore::EnsureStoreRootDirectoryPresent(tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18001d128`
- end: `0x18001da79`
- name: `?EnsureStoreRootDirectoryPresent@CReportStore@@IEAAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `2385`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004683c`
- `0x180076938`

## callees

- `0x18000716c`
- `0x18000718c`
- `0x180007e10`
- `0x180007e34`
- `0x180008568`
- `0x180009620`
- `0x18000bc10`
- `0x18000c390`
- `0x18000dad0`
- `0x18000ea64`
- `0x18001a2cc`
- `0x18001c9cc`
- `0x18001d128`
- `0x18001da80`
- `0x18001dc24`
- `0x180027884`
- `0x180028dac`
- `0x18002d1ec`
- `0x18002fcf8`
- `0x18002ffc4`
- `0x180030408`
- `0x18003db78`
- `0x18003f0c0`
- `0x180042918`
- `0x180049938`
- `0x180050db0`
- `0x1800517cc`
- `0x18005b8d1`
- `0x1800650ac`
- `0x180076ad8`
- `0x180076d74`
- `0x180097c3c`
- `0x180098fa0`
- `0x1800aa000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d22e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d3a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d22e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d3a1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001d397`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001d397`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d210`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d295`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d47b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d59a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d210`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d295`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d47b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d59a`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x18001d1af`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x18001d1af`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001d335`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001d335`

## string_xrefs

- `0x18001d17c`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001d1ee`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001d21a`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001d346`: `onecore\windows\feedback\core\werdll\lib\securityattributes.cpp`
- `0x18001d5f5`: `Failed setting security on temp folder.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CReportStore::EnsureStoreRootDirectoryPresent(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v5; // rbx
  int ParentDirectory; // eax
  unsigned int v7; // esi
  BOOL v8; // esi
  int v9; // r13d
  int v10; // r12d
  int v11; // eax
  int v12; // r15d
  int v13; // r15d
  const char *v14; // r9
  int LastError; // eax
  DWORD v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  const WCHAR *StorePath; // rax
  int v21; // ebx
  __int64 v22; // rdx
  unsigned int v23; // edx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  const wchar_t *v27; // rcx
  int v28; // eax
  int v29; // r12d
  const WCHAR *v30; // rax
  int v31; // eax
  int v32; // eax
  __int64 v33; // rdx
  int v34; // eax
  int v36; // eax
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+28h] [rbp-D8h]
  __int64 v41; // [rsp+30h] [rbp-D0h] BYREF
  DWORD FileAttributesW; // [rsp+38h] [rbp-C8h]
  LPCWSTR lpSrc[4]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v44[4]; // [rsp+60h] [rbp-A0h] BYREF
  struct _SECURITY_ATTRIBUTES v45; // [rsp+80h] [rbp-80h] BYREF
  __int128 v46; // [rsp+98h] [rbp-68h]
  __int128 v47; // [rsp+A8h] [rbp-58h]
  __int64 v48; // [rsp+B8h] [rbp-48h]
  __int128 v49; // [rsp+C0h] [rbp-40h]
  LPCWSTR v50[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v51; // [rsp+F0h] [rbp-10h]
  LPCWSTR v52[4]; // [rsp+F8h] [rbp-8h] BYREF
  LPCWSTR v53[4]; // [rsp+118h] [rbp+18h] BYREF
  wchar_t *v54[4]; // [rsp+138h] [rbp+38h] BYREF
  LPCWSTR lpFileName[5]; // [rsp+158h] [rbp+58h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+180h] [rbp+80h] BYREF
  __int128 v57; // [rsp+198h] [rbp+98h]
  __int128 v58; // [rsp+1A8h] [rbp+A8h]
  __int64 v59; // [rsp+1B8h] [rbp+B8h]
  __int128 v60; // [rsp+1C0h] [rbp+C0h]
  struct _SECURITY_ATTRIBUTES v61; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v62; // [rsp+1E8h] [rbp+E8h]
  __int128 v63; // [rsp+1F8h] [rbp+F8h]
  __int64 v64; // [rsp+208h] [rbp+108h]
  __int128 v65; // [rsp+210h] [rbp+110h]
  _BYTE Src[1408]; // [rsp+220h] [rbp+120h] BYREF
  _DWORD v67[352]; // [rsp+7A0h] [rbp+6A0h] BYREF
  __int16 v68; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v69[38]; // [rsp+D22h] [rbp+C22h] BYREF
  int v70; // [rsp+D48h] [rbp+C48h]
  char *v71; // [rsp+D4Ch] [rbp+C4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+12E8h] [rbp+11E8h]

  v51 = a2;
  if ( *(_QWORD *)(a1 + 16) == *(_QWORD *)(a1 + 24) )
  {
    v3 = 245;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)0x80070057LL,
      v37);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v3 = 246;
    goto LABEL_3;
  }
  tlx::unique_any<tlx::file_handle_traits>::reset(a2, 0);
  if ( !(unsigned __int8)XerShouldWerManageRootDirectory() )
    return 0;
  v5 = 0;
  v41 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
  ParentDirectory = UtilGetParentDirectory(*(_QWORD *)(a1 + 16), lpFileName);
  v7 = ParentDirectory;
  if ( ParentDirectory >= 0 )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
    FileAttributesW = GetFileAttributesW(lpFileName[0]);
    if ( FileAttributesW != -1 )
      goto LABEL_33;
    if ( GetLastError() - 2 > 1 )
    {
      v9 = 1;
      v10 = 1;
      goto LABEL_33;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v53);
    v11 = UtilGetParentDirectory(lpFileName[0], v53);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
        (const char *)(unsigned int)v11,
        v37);
LABEL_15:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v53);
LABEL_16:
      v7 = v12;
      goto LABEL_104;
    }
    v13 = 0;
    if ( GetFileAttributesW(v53[0]) == -1 )
      v13 = UtilEnsureDirectory(v53[0], 0);
    if ( v13 >= 0 )
    {
      memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      SecurityDescriptor.nLength = 24;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
              L"O:SYG:SYD:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;0x1200a9;;;BU)(A;;0x1200a9;;;WD)",
              1u,
              &SecurityDescriptor.lpSecurityDescriptor,
              0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x448,
                      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\securityattributes.cpp",
                      v14);
        v12 = LastError;
        if ( LastError < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x142,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)LastError,
            v37);
          CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&SecurityDescriptor);
          goto LABEL_15;
        }
      }
      if ( !CreateDirectoryW(lpFileName[0], &SecurityDescriptor) )
      {
        v16 = GetLastError();
        v17 = ERROR_HR_FROM_WIN32(v16);
        if ( v17 == -2147023589 || v17 == -2147024891 )
          v8 = 1;
        if ( v17 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x150,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)v17,
            v37);
        v10 = 1;
      }
      CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&SecurityDescriptor);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x132,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
        (const char *)(unsigned int)v13,
        v37);
      v10 = 1;
      v8 = v13 == -2147024891;
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v53);
LABEL_33:
    memset(&v45, 0, sizeof(v45));
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v45.nLength = 24;
    v12 = CSecurityAttributes::InitFromSecurityElements((PACL *)&v45, (__int64)&unk_1800B3C10, 8u, 0, 0, 0);
    if ( v12 < 0 )
    {
      v18 = 359;
      goto LABEL_35;
    }
    v12 = -2147418113;
    if ( !v10 )
    {
      if ( GetFileAttributesW(*(LPCWSTR *)(a1 + 16)) == -1 )
      {
        v19 = UtilEnsureDirectory(*(const wchar_t **)(a1 + 16), &v45);
        if ( v19 == -2147024891 )
          v8 = 1;
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x179,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)v19,
            v38);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v52);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v44);
      StorePath = CSettings::GetStorePath((CSettings *)(a1 + 72));
      v21 = UtilExpandEnvironmentStrings(StorePath);
      if ( v21 < 0 )
      {
        v22 = 386;
LABEL_45:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v21,
          v38);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v44);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v52);
        CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v45);
        v7 = v21;
        goto LABEL_104;
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSrc);
      if ( (unsigned int)UtilGetFinalPath(v52[0]) )
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v52, lpSrc);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSrc);
      v21 = CPath::Append(v52[0], L"Temp", v44);
      if ( v21 < 0 )
      {
        v22 = 394;
        goto LABEL_45;
      }
      if ( GetFileAttributesW(v44[0]) == -1 )
      {
        v24 = UtilEnsureDirectory(v44[0], &v45);
        if ( v24 == -2147024891 )
          v8 = 1;
        if ( v24 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x19A,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)v24,
            v38);
      }
      else
      {
        v25 = UtilSetFileSecurity(v44[0], v23, v45.lpSecurityDescriptor);
        if ( v25 < 0 )
        {
          if ( v25 == -2147024891 )
            v9 = 1;
          else
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x1AE,
              (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
              (const char *)(unsigned int)v25,
              (int)"Failed setting security on temp folder.",
              (const char *)pIdentifierAuthority);
        }
      }
      v26 = UtilVerifyAndLockDirectory((wchar_t *)v44[0]);
      v12 = v26;
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B6,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v26,
          v38);
      UtilSetPathToSoftReserve(v44[0]);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v44);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v52);
      v5 = v41;
    }
    if ( v8 || v9 )
    {
      v68 = 0;
      memset_0(v69, 0, 0x576u);
      memset_0(Src, 0, 0x578u);
      memcpy_0(v67, Src, 0x578u);
      v67[0] = 91751760;
      v67[10] = -1073741821;
      v28 = UtilSendMessageToWersvc(v27, (struct _WERSVC_MSG *)v67, (struct _WERSVC_MSG *)&v68, 0);
      v29 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1D4,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v28,
          v38);
        if ( v8 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D4,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)v29,
            v38);
          CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v45);
          v7 = v29;
          goto LABEL_104;
        }
      }
      if ( v29 >= 0 )
      {
        if ( v70 != -1073741824 )
        {
          if ( (int)v71 < 0 )
          {
            v7 = wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)0x1DA,
                   (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
                   (const char *)(unsigned int)v71,
                   v38);
            goto LABEL_76;
          }
LABEL_103:
          CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v45);
          v7 = 0;
          goto LABEL_104;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1D6,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v29,
          v38);
      }
      if ( (unsigned __int64)(v5 + 1) <= 1 )
      {
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v50);
        v30 = CSettings::GetStorePath((CSettings *)(a1 + 72));
        v31 = UtilExpandEnvironmentStrings(v30);
        v7 = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E1,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)v31,
            v38);
LABEL_72:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v50);
LABEL_76:
          CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v45);
          goto LABEL_104;
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSrc);
        if ( (unsigned int)UtilGetFinalPath(v50[0]) )
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v50, lpSrc);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSrc);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v54);
        v32 = CPath::Append(v50[0], L"Temp", v54);
        v7 = v32;
        if ( v32 < 0 )
        {
          v33 = 490;
LABEL_81:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v33,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)v32,
            v38);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v54);
          goto LABEL_72;
        }
        v32 = UtilVerifyAndLockDirectory(v54[0]);
        v7 = v32;
        if ( v32 < 0 )
        {
          v33 = 495;
          goto LABEL_81;
        }
        UtilSetPathToSoftReserve(v54[0]);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v54);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v50);
        v5 = v41;
      }
      v34 = UtilEnsureDirectory(*(const wchar_t **)(a1 + 16), &v45);
      v7 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F4,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v34,
          v38);
        goto LABEL_76;
      }
    }
    if ( v5 == -1 || v5 == 0 )
    {
      if ( v12 >= 0 )
        goto LABEL_36;
      v18 = 503;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
        (const char *)(unsigned int)v12,
        v38);
LABEL_36:
      CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v45);
      goto LABEL_16;
    }
    tlx::unique_any<tlx::file_handle_traits>::operator=(v51, &v41);
    if ( (unsigned int)CSettings::IsCabArchiveCreationEnabled((CSettings *)(a1 + 72)) )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSrc);
      CSettings::GetCabArchiveFolder((CSettings *)(a1 + 72));
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(lpSrc) )
      {
        if ( !UtilFolderExists(lpSrc[0]) )
        {
          memset(&v61, 0, sizeof(v61));
          v62 = 0;
          v63 = 0;
          v64 = 0;
          v65 = 0;
          v61.nLength = 24;
          v36 = CSecurityAttributes::InitFromSecurityElements((PACL *)&v61, (__int64)&unk_1800B3C10, 8u, 0, 0, 0);
          if ( v36 >= 0 )
            UtilEnsureDirectory(lpSrc[0], &v61);
          else
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x207,
              (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
              (const char *)(unsigned int)v36,
              v39);
          CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v61);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x202,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)0x8007000ELL,
          v38);
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSrc);
    }
    if ( !*(_DWORD *)(a1 + 48) && (FileAttributesW == -1 || (FileAttributesW & 0x800) == 0) )
      UtilEnableCompression(*(const wchar_t **)(a1 + 16));
    goto LABEL_103;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x110,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
    (const char *)(unsigned int)ParentDirectory,
    v37);
LABEL_104:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v41);
  return v7;
}

```

## disassembly

```asm
0x18001d128  mov     [rsp-8+arg_10], rbx
0x18001d12d  push    rbp
0x18001d12e  push    rsi
0x18001d12f  push    rdi
0x18001d130  push    r12
0x18001d132  push    r13
0x18001d134  push    r14
0x18001d136  push    r15
0x18001d138  lea     rbp, [rsp-11B0h]
0x18001d140  mov     eax, 12B0h
0x18001d145  call    _alloca_probe
0x18001d14a  sub     rsp, rax
0x18001d14d  mov     rax, cs:__security_cookie
0x18001d154  xor     rax, rsp
0x18001d157  mov     [rbp+11E0h+var_40], rax
0x18001d15e  mov     r8, rdx
0x18001d161  mov     [rbp+11E0h+var_11F0], rdx
0x18001d165  mov     r14, rcx
0x18001d168  mov     rax, [rcx+18h]
0x18001d16c  cmp     [rcx+10h], rax
0x18001d170  jnz     short loc_18001D199
0x18001d172  mov     edx, 0F5h; void *
0x18001d177  mov     ebx, 80070057h
0x18001d17c  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001d183  mov     r9d, ebx; char *
0x18001d186  mov     rcx, [rbp+11E8h]; this
0x18001d18d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d192  mov     eax, ebx
0x18001d194  jmp     loc_18001DA4F
0x18001d199  test    r8, r8
0x18001d19c  jnz     short loc_18001D1A5
0x18001d19e  mov     edx, 0F6h
0x18001d1a3  jmp     short loc_18001D177
0x18001d1a5  xor     edx, edx
0x18001d1a7  mov     rcx, r8
0x18001d1aa  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18001d1af  call    cs:__imp_XerShouldWerManageRootDirectory
0x18001d1b5  test    al, al
0x18001d1b7  jnz     short loc_18001D1C0
0x18001d1b9  xor     eax, eax
0x18001d1bb  jmp     loc_18001DA4F
0x18001d1c0  xor     ebx, ebx
0x18001d1c2  mov     [rsp+12E0h+var_12B0], rbx
0x18001d1c7  lea     rcx, [rbp+11E0h+lpFileName]; void *
0x18001d1cb  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001d1d0  nop
0x18001d1d1  lea     rdx, [rbp+11E0h+lpFileName]
0x18001d1d5  mov     rcx, [r14+10h]
0x18001d1d9  call    ?UtilGetParentDirectory@@YAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetParentDirectory(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18001d1de  mov     esi, eax
0x18001d1e0  test    eax, eax
0x18001d1e2  jns     short loc_18001D204
0x18001d1e4  mov     rcx, [rbp+11E8h]; this
0x18001d1eb  mov     r9d, eax; char *
0x18001d1ee  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001d1f5  mov     edx, 110h; void *
0x18001d1fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1ff  jmp     loc_18001DA39
0x18001d204  xor     esi, esi
0x18001d206  xor     r13d, r13d
0x18001d209  xor     r12d, r12d
0x18001d20c  mov     rcx, [rbp+11E0h+lpFileName]; lpFileName
0x18001d210  call    cs:__imp_GetFileAttributesW
0x18001d216  mov     [rsp+12E0h+var_12A8], eax
0x18001d21a  lea     rdi, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001d221  lea     r15d, [rsi+1]
0x18001d225  cmp     eax, 0FFFFFFFFh
0x18001d228  jnz     loc_18001D3F3
0x18001d22e  call    cs:__imp_GetLastError
0x18001d234  add     eax, 0FFFFFFFEh
0x18001d237  cmp     eax, r15d
0x18001d23a  jbe     short loc_18001D247
0x18001d23c  mov     r13d, r15d
0x18001d23f  mov     r12d, r15d
0x18001d242  jmp     loc_18001D3F3
0x18001d247  lea     rcx, [rbp+11E0h+var_11C8]; void *
0x18001d24b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001d250  nop
0x18001d251  lea     rdx, [rbp+11E0h+var_11C8]
0x18001d255  mov     rcx, [rbp+11E0h+lpFileName]
0x18001d259  call    ?UtilGetParentDirectory@@YAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetParentDirectory(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18001d25e  mov     r15d, eax
0x18001d261  test    eax, eax
0x18001d263  jns     short loc_18001D28E
0x18001d265  mov     rcx, [rbp+11E8h]; this
0x18001d26c  mov     r9d, eax; char *
0x18001d26f  mov     r8, rdi; unsigned int
0x18001d272  mov     edx, 128h; void *
0x18001d277  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d27c  nop
0x18001d27d  lea     rcx, [rbp+11E0h+var_11C8]; void *
0x18001d281  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001d286  mov     esi, r15d
0x18001d289  jmp     loc_18001DA39
0x18001d28e  xor     r15d, r15d
0x18001d291  mov     rcx, [rbp+11E0h+var_11C8]; lpFileName
0x18001d295  call    cs:__imp_GetFileAttributesW
0x18001d29b  cmp     eax, 0FFFFFFFFh
0x18001d29e  jnz     short loc_18001D2AE
0x18001d2a0  xor     edx, edx; struct _SECURITY_ATTRIBUTES *
0x18001d2a2  mov     rcx, [rbp+11E0h+var_11C8]; wchar_t *
0x18001d2a6  call    ?UtilEnsureDirectory@@YAJPEB_WPEAU_SECURITY_ATTRIBUTES@@@Z; UtilEnsureDirectory(wchar_t const *,_SECURITY_ATTRIBUTES *)
0x18001d2ab  mov     r15d, eax
0x18001d2ae  mov     rcx, [rbp+11E8h]; this
0x18001d2b5  test    r15d, r15d
0x18001d2b8  jns     short loc_18001D2E0
0x18001d2ba  mov     r9d, r15d; char *
0x18001d2bd  mov     r8, rdi; unsigned int
0x18001d2c0  mov     edx, 132h; void *
0x18001d2c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d2ca  xor     esi, esi
0x18001d2cc  lea     r12d, [rsi+1]
0x18001d2d0  cmp     r15d, 80070005h
0x18001d2d7  setz    sil
0x18001d2db  jmp     loc_18001D3EA
0x18001d2e0  xorps   xmm0, xmm0
0x18001d2e3  xor     eax, eax
0x18001d2e5  movups  xmmword ptr [rbp+11E0h+SecurityDescriptor], xmm0
0x18001d2ec  mov     [rbp+11E0h+var_1150], rax
0x18001d2f3  xorps   xmm1, xmm1
0x18001d2f6  movups  [rbp+11E0h+var_1148], xmm1
0x18001d2fd  movups  [rbp+11E0h+var_1138], xmm1
0x18001d304  mov     [rbp+11E0h+var_1128], rax
0x18001d30b  movdqa  [rbp+11E0h+var_1120], xmm0
0x18001d313  mov     dword ptr [rbp+11E0h+SecurityDescriptor], 18h
0x18001d31d  xor     r9d, r9d; SecurityDescriptorSize
0x18001d320  lea     r8, [rbp+11E0h+SecurityDescriptor+8]; SecurityDescriptor
0x18001d327  lea     r15d, [rax+1]
0x18001d32b  mov     edx, r15d; StringSDRevision
0x18001d32e  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;"...
0x18001d335  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001d33b  test    eax, eax
0x18001d33d  jnz     short loc_18001D38C
0x18001d33f  mov     rcx, [rbp+11E8h]; this
0x18001d346  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werdl"...
0x18001d34d  mov     edx, 448h; void *
0x18001d352  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d357  mov     r15d, eax
0x18001d35a  test    eax, eax
0x18001d35c  jns     short loc_18001D386
0x18001d35e  mov     rcx, [rbp+11E8h]; this
0x18001d365  mov     r9d, eax; char *
0x18001d368  mov     r8, rdi; unsigned int
0x18001d36b  mov     edx, 142h; void *
0x18001d370  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d375  lea     rcx, [rbp+11E0h+SecurityDescriptor]; this
0x18001d37c  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18001d381  jmp     loc_18001D27D
0x18001d386  mov     r15d, 1
0x18001d38c  lea     rdx, [rbp+11E0h+SecurityDescriptor]; lpSecurityAttributes
0x18001d393  mov     rcx, [rbp+11E0h+lpFileName]; lpPathName
0x18001d397  call    cs:__imp_CreateDirectoryW
0x18001d39d  test    eax, eax
0x18001d39f  jnz     short loc_18001D3DD
0x18001d3a1  call    cs:__imp_GetLastError
0x18001d3a7  mov     ecx, eax; unsigned int
0x18001d3a9  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001d3ae  cmp     eax, 8007051Bh
0x18001d3b3  jz      short loc_18001D3BC
0x18001d3b5  cmp     eax, 80070005h
0x18001d3ba  jnz     short loc_18001D3BF
0x18001d3bc  mov     esi, r15d
0x18001d3bf  mov     rcx, [rbp+11E8h]; this
0x18001d3c6  test    eax, eax
0x18001d3c8  jns     short loc_18001D3DA
0x18001d3ca  mov     r9d, eax; char *
0x18001d3cd  mov     r8, rdi; unsigned int
0x18001d3d0  mov     edx, 150h; void *
0x18001d3d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d3da  mov     r12d, r15d
0x18001d3dd  lea     rcx, [rbp+11E0h+SecurityDescriptor]; this
0x18001d3e4  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18001d3e9  nop
0x18001d3ea  lea     rcx, [rbp+11E0h+var_11C8]; void *
0x18001d3ee  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001d3f3  xorps   xmm0, xmm0
0x18001d3f6  xor     eax, eax
0x18001d3f8  movups  xmmword ptr [rbp+11E0h+var_1260.nLength], xmm0
0x18001d3fc  mov     qword ptr [rbp+11E0h+var_1260.bInheritHandle], rax
0x18001d400  xorps   xmm1, xmm1
0x18001d403  movups  [rbp+11E0h+var_1248], xmm1
0x18001d407  movups  [rbp+11E0h+var_1238], xmm1
0x18001d40b  mov     [rbp+11E0h+var_1228], rax
0x18001d40f  movdqa  [rbp+11E0h+var_1220], xmm0
0x18001d414  mov     [rbp+11E0h+var_1260.nLength], 18h
0x18001d41b  mov     [rsp+12E0h+pIdentifierAuthority], rax; char *
0x18001d420  mov     [rsp+12E0h+var_12C0], eax; int
0x18001d424  xor     r9d, r9d
0x18001d427  lea     r8d, [rax+8]
0x18001d42b  lea     rdx, unk_1800B3C10
0x18001d432  lea     rcx, [rbp+11E0h+var_1260]; this
0x18001d436  call    ?InitFromSecurityElements@CSecurityAttributes@@QEAAJPEBUSECURITY_ELEMENT@@KPEBV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@K0@Z; CSecurityAttributes::InitFromSecurityElements(SECURITY_ELEMENT const *,ulong,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> const *,ulong,SECURITY_ELEMENT const *)
0x18001d43b  mov     r15d, eax
0x18001d43e  test    eax, eax
0x18001d440  jns     short loc_18001D468
0x18001d442  mov     edx, 167h; void *
0x18001d447  mov     r8, rdi; unsigned int
0x18001d44a  mov     r9d, r15d; char *
0x18001d44d  mov     rcx, [rbp+11E8h]; this
0x18001d454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d459  nop
0x18001d45a  lea     rcx, [rbp+11E0h+var_1260]; this
0x18001d45e  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18001d463  jmp     loc_18001D286
0x18001d468  mov     r15d, 8000FFFFh
0x18001d46e  test    r12d, r12d
0x18001d471  jnz     loc_18001D662
0x18001d477  mov     rcx, [r14+10h]; lpFileName
0x18001d47b  call    cs:__imp_GetFileAttributesW
0x18001d481  cmp     eax, 0FFFFFFFFh
0x18001d484  jnz     short loc_18001D4C3
0x18001d486  lea     rdx, [rbp+11E0h+var_1260]; struct _SECURITY_ATTRIBUTES *
0x18001d48a  mov     rcx, [r14+10h]; wchar_t *
0x18001d48e  call    ?UtilEnsureDirectory@@YAJPEB_WPEAU_SECURITY_ATTRIBUTES@@@Z; UtilEnsureDirectory(wchar_t const *,_SECURITY_ATTRIBUTES *)
0x18001d493  mov     r12d, 80070005h
0x18001d499  cmp     eax, r12d
0x18001d49c  mov     r15d, 1
0x18001d4a2  cmovz   esi, r15d
0x18001d4a6  mov     rcx, [rbp+11E8h]; this
0x18001d4ad  test    eax, eax
0x18001d4af  jns     short loc_18001D4CF
0x18001d4b1  mov     r9d, eax; char *
0x18001d4b4  mov     r8, rdi; unsigned int
0x18001d4b7  mov     edx, 179h; void *
0x18001d4bc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d4c1  jmp     short loc_18001D4CF
0x18001d4c3  mov     r15d, 1
0x18001d4c9  mov     r12d, 80070005h
0x18001d4cf  lea     rcx, [rbp+11E0h+var_11E8]; void *
0x18001d4d3  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001d4d8  nop
0x18001d4d9  lea     rcx, [rsp+12E0h+var_1280]; void *
0x18001d4de  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001d4e3  nop
0x18001d4e4  lea     rcx, [r14+48h]; this
0x18001d4e8  call    ?GetStorePath@CSettings@@QEBAPEB_WXZ; CSettings::GetStorePath(void)
0x18001d4ed  mov     rcx, rax; lpSrc
0x18001d4f0  lea     rdx, [rbp+11E0h+var_11E8]
0x18001d4f4  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001d4f9  mov     ebx, eax
0x18001d4fb  test    eax, eax
0x18001d4fd  jns     short loc_18001D53C
0x18001d4ff  mov     edx, 182h; void *
0x18001d504  mov     r8, rdi; unsigned int
0x18001d507  mov     r9d, ebx; char *
0x18001d50a  mov     rcx, [rbp+11E8h]; this
0x18001d511  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d516  nop
0x18001d517  lea     rcx, [rsp+12E0h+var_1280]; void *
0x18001d51c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001d521  nop
0x18001d522  lea     rcx, [rbp+11E0h+var_11E8]; void *
0x18001d526  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001d52b  nop
0x18001d52c  lea     rcx, [rbp+11E0h+var_1260]; this
0x18001d530  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18001d535  mov     esi, ebx
0x18001d537  jmp     loc_18001DA39
0x18001d53c  lea     rcx, [rsp+12E0h+lpSrc]; void *
0x18001d541  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001d546  lea     rdx, [rsp+12E0h+lpSrc]
0x18001d54b  mov     rcx, [rbp+11E0h+var_11E8]; lpFileName
0x18001d54f  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18001d554  test    eax, eax
0x18001d556  jz      short loc_18001D566
0x18001d558  lea     rdx, [rsp+12E0h+lpSrc]
0x18001d55d  lea     rcx, [rbp+11E0h+var_11E8]
0x18001d561  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18001d566  lea     rcx, [rsp+12E0h+lpSrc]; void *
0x18001d56b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001d570  lea     r8, [rsp+12E0h+var_1280]
0x18001d575  lea     rdx, aTemp; "Temp"
0x18001d57c  mov     rcx, [rbp+11E0h+var_11E8]
0x18001d580  call    ?Append@CPath@@SAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPath::Append(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001d585  mov     ebx, eax
0x18001d587  test    eax, eax
0x18001d589  jns     short loc_18001D595
0x18001d58b  mov     edx, 18Ah
0x18001d590  jmp     loc_18001D504
0x18001d595  mov     rcx, [rsp+12E0h+var_1280]; lpFileName
0x18001d59a  call    cs:__imp_GetFileAttributesW
0x18001d5a0  mov     rcx, [rsp+12E0h+var_1280]; wchar_t *
0x18001d5a5  cmp     eax, 0FFFFFFFFh
0x18001d5a8  jnz     short loc_18001D5D7
0x18001d5aa  lea     rdx, [rbp+11E0h+var_1260]; struct _SECURITY_ATTRIBUTES *
0x18001d5ae  call    ?UtilEnsureDirectory@@YAJPEB_WPEAU_SECURITY_ATTRIBUTES@@@Z; UtilEnsureDirectory(wchar_t const *,_SECURITY_ATTRIBUTES *)
0x18001d5b3  cmp     eax, r12d
0x18001d5b6  cmovz   esi, r15d
0x18001d5ba  mov     rcx, [rbp+11E8h]; this
0x18001d5c1  test    eax, eax
0x18001d5c3  jns     short loc_18001D611
0x18001d5c5  mov     r9d, eax; char *
0x18001d5c8  mov     r8, rdi; unsigned int
0x18001d5cb  mov     edx, 19Ah; void *
0x18001d5d0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d5d5  jmp     short loc_18001D611
0x18001d5d7  mov     r8, [rbp+11E0h+var_1260.lpSecurityDescriptor]; void *
0x18001d5db  call    ?UtilSetFileSecurity@@YAJPEB_WKPEAX@Z; UtilSetFileSecurity(wchar_t const *,ulong,void *)
0x18001d5e0  test    eax, eax
0x18001d5e2  jns     short loc_18001D611
  ... truncated ...
```
