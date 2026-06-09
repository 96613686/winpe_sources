# CReportStore::EnsureStoreRootDirectoryPresent(tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18001d718`
- end: `0x18001e0a0`
- name: `?EnsureStoreRootDirectoryPresent@CReportStore@@IEAAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `2440`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800485ec`
- `0x180079e2c`

## callees

- `0x1800058a4`
- `0x180007590`
- `0x180007fd8`
- `0x180008004`
- `0x180009684`
- `0x18000a750`
- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x18001c368`
- `0x18001cf20`
- `0x18001d718`
- `0x18001e0a8`
- `0x18001e288`
- `0x180025560`
- `0x180028760`
- `0x180029e58`
- `0x18002a5f8`
- `0x18002ece4`
- `0x1800318c8`
- `0x180031d00`
- `0x18003fb94`
- `0x1800410bc`
- `0x1800459c0`
- `0x18004bb70`
- `0x180053300`
- `0x180053d3c`
- `0x18005dd11`
- `0x180068090`
- `0x180079fd0`
- `0x18007a280`
- `0x18009c010`
- `0x18009d564`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d82a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d82a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9b5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001d9a5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001d9a5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d806`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d897`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001da95`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001dbba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d806`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d897`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001da95`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001dbba`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x18001d79f`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x18001d79f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001d93d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001d93d`

## string_xrefs

- `0x18001d76c`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001d7e4`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001d816`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001d954`: `onecore\windows\feedback\core\werdll\lib\securityattributes.cpp`
- `0x18001dc1b`: `Failed setting security on temp folder.`

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
  wchar_t *CabArchiveFolder; // rax
  int v37; // eax
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+28h] [rbp-D8h]
  __int64 v42; // [rsp+30h] [rbp-D0h] BYREF
  DWORD FileAttributesW; // [rsp+38h] [rbp-C8h]
  LPCWSTR lpSrc[4]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v45[4]; // [rsp+60h] [rbp-A0h] BYREF
  struct _SECURITY_ATTRIBUTES v46; // [rsp+80h] [rbp-80h] BYREF
  __int128 v47; // [rsp+98h] [rbp-68h]
  __int128 v48; // [rsp+A8h] [rbp-58h]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  __int128 v50; // [rsp+C0h] [rbp-40h]
  LPCWSTR v51[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v52; // [rsp+F0h] [rbp-10h]
  LPCWSTR v53[4]; // [rsp+F8h] [rbp-8h] BYREF
  LPCWSTR v54[4]; // [rsp+118h] [rbp+18h] BYREF
  wchar_t *v55[4]; // [rsp+138h] [rbp+38h] BYREF
  LPCWSTR lpFileName[5]; // [rsp+158h] [rbp+58h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+180h] [rbp+80h] BYREF
  __int128 v58; // [rsp+198h] [rbp+98h]
  __int128 v59; // [rsp+1A8h] [rbp+A8h]
  __int64 v60; // [rsp+1B8h] [rbp+B8h]
  __int128 v61; // [rsp+1C0h] [rbp+C0h]
  struct _SECURITY_ATTRIBUTES v62; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v63; // [rsp+1E8h] [rbp+E8h]
  __int128 v64; // [rsp+1F8h] [rbp+F8h]
  __int64 v65; // [rsp+208h] [rbp+108h]
  __int128 v66; // [rsp+210h] [rbp+110h]
  _BYTE Src[1408]; // [rsp+220h] [rbp+120h] BYREF
  _DWORD v68[352]; // [rsp+7A0h] [rbp+6A0h] BYREF
  __int16 v69; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v70[38]; // [rsp+D22h] [rbp+C22h] BYREF
  int v71; // [rsp+D48h] [rbp+C48h]
  char *v72; // [rsp+D4Ch] [rbp+C4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+12E8h] [rbp+11E8h]

  v52 = a2;
  if ( *(_QWORD *)(a1 + 16) == *(_QWORD *)(a1 + 24) )
  {
    v3 = 245;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)0x80070057LL,
      v38);
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
  v42 = 0;
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
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v54);
    v11 = UtilGetParentDirectory(lpFileName[0], v54);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
        (const char *)(unsigned int)v11,
        v38);
LABEL_15:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v54);
LABEL_16:
      v7 = v12;
      goto LABEL_104;
    }
    v13 = 0;
    if ( GetFileAttributesW(v54[0]) == -1 )
      v13 = UtilEnsureDirectory(v54[0], 0);
    if ( v13 >= 0 )
    {
      memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v61 = 0;
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
            v38);
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
            v38);
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
        v38);
      v10 = 1;
      v8 = v13 == -2147024891;
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v54);
LABEL_33:
    memset(&v46, 0, sizeof(v46));
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v46.nLength = 24;
    v12 = CSecurityAttributes::InitFromSecurityElements((PACL *)&v46, (__int64)qword_1800B8B90, 8u, 0, 0, 0);
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
        v19 = UtilEnsureDirectory(*(const wchar_t **)(a1 + 16), &v46);
        if ( v19 == -2147024891 )
          v8 = 1;
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x179,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)v19,
            v39);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v53);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v45);
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
          v39);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v45);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v53);
        CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v46);
        v7 = v21;
        goto LABEL_104;
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSrc);
      if ( (unsigned int)UtilGetFinalPath(v53[0]) )
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v53, lpSrc);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSrc);
      v21 = CPath::Append(v53[0], L"Temp", v45);
      if ( v21 < 0 )
      {
        v22 = 394;
        goto LABEL_45;
      }
      if ( GetFileAttributesW(v45[0]) == -1 )
      {
        v24 = UtilEnsureDirectory(v45[0], &v46);
        if ( v24 == -2147024891 )
          v8 = 1;
        if ( v24 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x19A,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)v24,
            v39);
      }
      else
      {
        v25 = UtilSetFileSecurity(v45[0], v23, v46.lpSecurityDescriptor);
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
      v26 = UtilVerifyAndLockDirectory((wchar_t *)v45[0]);
      v12 = v26;
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B6,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v26,
          v39);
      UtilSetPathToSoftReserve(v45[0]);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v45);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v53);
      v5 = v42;
    }
    if ( v8 || v9 )
    {
      v69 = 0;
      memset_0(v70, 0, 0x576u);
      memset_0(Src, 0, 0x578u);
      memcpy_0(v68, Src, 0x578u);
      v68[0] = 91751760;
      v68[10] = -1073741821;
      v28 = UtilSendMessageToWersvc(v27, (struct _WERSVC_MSG *)v68, (struct _WERSVC_MSG *)&v69, 0);
      v29 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1D4,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v28,
          v39);
        if ( v8 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D4,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)v29,
            v39);
          CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v46);
          v7 = v29;
          goto LABEL_104;
        }
      }
      if ( v29 >= 0 )
      {
        if ( v71 != -1073741824 )
        {
          if ( (int)v72 < 0 )
          {
            v7 = wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)0x1DA,
                   (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
                   (const char *)(unsigned int)v72,
                   v39);
            goto LABEL_76;
          }
LABEL_103:
          CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v46);
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
          v39);
      }
      if ( (unsigned __int64)(v5 + 1) <= 1 )
      {
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v51);
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
            v39);
LABEL_72:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v51);
LABEL_76:
          CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v46);
          goto LABEL_104;
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSrc);
        if ( (unsigned int)UtilGetFinalPath(v51[0]) )
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v51, lpSrc);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSrc);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v55);
        v32 = CPath::Append(v51[0], L"Temp", v55);
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
            v39);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v55);
          goto LABEL_72;
        }
        v32 = UtilVerifyAndLockDirectory(v55[0]);
        v7 = v32;
        if ( v32 < 0 )
        {
          v33 = 495;
          goto LABEL_81;
        }
        UtilSetPathToSoftReserve(v55[0]);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v55);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v51);
        v5 = v42;
      }
      v34 = UtilEnsureDirectory(*(const wchar_t **)(a1 + 16), &v46);
      v7 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F4,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v34,
          v39);
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
        v39);
LABEL_36:
      CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v46);
      goto LABEL_16;
    }
    tlx::unique_any<tlx::file_handle_traits>::operator=(v52, &v42);
    if ( (unsigned int)CSettings::IsCabArchiveCreationEnabled((CSettings *)(a1 + 72)) )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSrc);
      CabArchiveFolder = (wchar_t *)CSettings::GetCabArchiveFolder((CSettings *)(a1 + 72));
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              lpSrc,
                              CabArchiveFolder) )
      {
        if ( !UtilFolderExists(lpSrc[0]) )
        {
          memset(&v62, 0, sizeof(v62));
          v63 = 0;
          v64 = 0;
          v65 = 0;
          v66 = 0;
          v62.nLength = 24;
          v37 = CSecurityAttributes::InitFromSecurityElements((PACL *)&v62, (__int64)qword_1800B8B90, 8u, 0, 0, 0);
          if ( v37 >= 0 )
            UtilEnsureDirectory(lpSrc[0], &v62);
          else
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x207,
              (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
              (const char *)(unsigned int)v37,
              v40);
          CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v62);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x202,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)0x8007000ELL,
          v39);
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
    v38);
LABEL_104:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v42);
  return v7;
}

```

## disassembly

```asm
0x18001d718  mov     [rsp-8+arg_10], rbx
0x18001d71d  push    rbp
0x18001d71e  push    rsi
0x18001d71f  push    rdi
0x18001d720  push    r12
0x18001d722  push    r13
0x18001d724  push    r14
0x18001d726  push    r15
0x18001d728  lea     rbp, [rsp-11B0h]
0x18001d730  mov     eax, 12B0h
0x18001d735  call    _alloca_probe
0x18001d73a  sub     rsp, rax
0x18001d73d  mov     rax, cs:__security_cookie
0x18001d744  xor     rax, rsp
0x18001d747  mov     [rbp+11E0h+var_40], rax
0x18001d74e  mov     r8, rdx
0x18001d751  mov     [rbp+11E0h+var_11F0], rdx
0x18001d755  mov     r14, rcx
0x18001d758  mov     rax, [rcx+18h]
0x18001d75c  cmp     [rcx+10h], rax
0x18001d760  jnz     short loc_18001D789
0x18001d762  mov     edx, 0F5h; void *
0x18001d767  mov     ebx, 80070057h
0x18001d76c  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001d773  mov     r9d, ebx; char *
0x18001d776  mov     rcx, [rbp+11E8h]; this
0x18001d77d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d782  mov     eax, ebx
0x18001d784  jmp     loc_18001E075
0x18001d789  test    r8, r8
0x18001d78c  jnz     short loc_18001D795
0x18001d78e  mov     edx, 0F6h
0x18001d793  jmp     short loc_18001D767
0x18001d795  xor     edx, edx
0x18001d797  mov     rcx, r8
0x18001d79a  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18001d79f  call    cs:__imp_XerShouldWerManageRootDirectory
0x18001d7a6  nop     dword ptr [rax+rax+00h]
0x18001d7ab  test    al, al
0x18001d7ad  jnz     short loc_18001D7B6
0x18001d7af  xor     eax, eax
0x18001d7b1  jmp     loc_18001E075
0x18001d7b6  xor     ebx, ebx
0x18001d7b8  mov     [rsp+12E0h+var_12B0], rbx
0x18001d7bd  lea     rcx, [rbp+11E0h+lpFileName]; void *
0x18001d7c1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001d7c6  nop
0x18001d7c7  lea     rdx, [rbp+11E0h+lpFileName]
0x18001d7cb  mov     rcx, [r14+10h]
0x18001d7cf  call    ?UtilGetParentDirectory@@YAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetParentDirectory(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18001d7d4  mov     esi, eax
0x18001d7d6  test    eax, eax
0x18001d7d8  jns     short loc_18001D7FA
0x18001d7da  mov     rcx, [rbp+11E8h]; this
0x18001d7e1  mov     r9d, eax; char *
0x18001d7e4  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001d7eb  mov     edx, 110h; void *
0x18001d7f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d7f5  jmp     loc_18001E05F
0x18001d7fa  xor     esi, esi
0x18001d7fc  xor     r13d, r13d
0x18001d7ff  xor     r12d, r12d
0x18001d802  mov     rcx, [rbp+11E0h+lpFileName]; lpFileName
0x18001d806  call    cs:__imp_GetFileAttributesW
0x18001d80d  nop     dword ptr [rax+rax+00h]
0x18001d812  mov     [rsp+12E0h+var_12A8], eax
0x18001d816  lea     rdi, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001d81d  lea     r15d, [rsi+1]
0x18001d821  cmp     eax, 0FFFFFFFFh
0x18001d824  jnz     loc_18001DA0D
0x18001d82a  call    cs:__imp_GetLastError
0x18001d831  nop     dword ptr [rax+rax+00h]
0x18001d836  add     eax, 0FFFFFFFEh
0x18001d839  cmp     eax, r15d
0x18001d83c  jbe     short loc_18001D849
0x18001d83e  mov     r13d, r15d
0x18001d841  mov     r12d, r15d
0x18001d844  jmp     loc_18001DA0D
0x18001d849  lea     rcx, [rbp+11E0h+var_11C8]; void *
0x18001d84d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001d852  nop
0x18001d853  lea     rdx, [rbp+11E0h+var_11C8]
0x18001d857  mov     rcx, [rbp+11E0h+lpFileName]
0x18001d85b  call    ?UtilGetParentDirectory@@YAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetParentDirectory(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18001d860  mov     r15d, eax
0x18001d863  test    eax, eax
0x18001d865  jns     short loc_18001D890
0x18001d867  mov     rcx, [rbp+11E8h]; this
0x18001d86e  mov     r9d, eax; char *
0x18001d871  mov     r8, rdi; unsigned int
0x18001d874  mov     edx, 128h; void *
0x18001d879  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d87e  nop
0x18001d87f  lea     rcx, [rbp+11E0h+var_11C8]; void *
0x18001d883  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001d888  mov     esi, r15d
0x18001d88b  jmp     loc_18001E05F
0x18001d890  xor     r15d, r15d
0x18001d893  mov     rcx, [rbp+11E0h+var_11C8]; lpFileName
0x18001d897  call    cs:__imp_GetFileAttributesW
0x18001d89e  nop     dword ptr [rax+rax+00h]
0x18001d8a3  cmp     eax, 0FFFFFFFFh
0x18001d8a6  jnz     short loc_18001D8B6
0x18001d8a8  xor     edx, edx; struct _SECURITY_ATTRIBUTES *
0x18001d8aa  mov     rcx, [rbp+11E0h+var_11C8]; wchar_t *
0x18001d8ae  call    ?UtilEnsureDirectory@@YAJPEB_WPEAU_SECURITY_ATTRIBUTES@@@Z; UtilEnsureDirectory(wchar_t const *,_SECURITY_ATTRIBUTES *)
0x18001d8b3  mov     r15d, eax
0x18001d8b6  mov     rcx, [rbp+11E8h]; this
0x18001d8bd  test    r15d, r15d
0x18001d8c0  jns     short loc_18001D8E8
0x18001d8c2  mov     r9d, r15d; char *
0x18001d8c5  mov     r8, rdi; unsigned int
0x18001d8c8  mov     edx, 132h; void *
0x18001d8cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d8d2  xor     esi, esi
0x18001d8d4  lea     r12d, [rsi+1]
0x18001d8d8  cmp     r15d, 80070005h
0x18001d8df  setz    sil
0x18001d8e3  jmp     loc_18001DA04
0x18001d8e8  xorps   xmm0, xmm0
0x18001d8eb  xor     eax, eax
0x18001d8ed  movups  xmmword ptr [rbp+11E0h+SecurityDescriptor], xmm0
0x18001d8f4  mov     [rbp+11E0h+var_1150], rax
0x18001d8fb  xorps   xmm1, xmm1
0x18001d8fe  movups  [rbp+11E0h+var_1148], xmm1
0x18001d905  movups  [rbp+11E0h+var_1138], xmm1
0x18001d90c  mov     [rbp+11E0h+var_1128], rax
0x18001d913  movdqa  [rbp+11E0h+var_1120], xmm0
0x18001d91b  mov     dword ptr [rbp+11E0h+SecurityDescriptor], 18h
0x18001d925  xor     r9d, r9d; SecurityDescriptorSize
0x18001d928  lea     r8, [rbp+11E0h+SecurityDescriptor+8]; SecurityDescriptor
0x18001d92f  lea     r15d, [rax+1]
0x18001d933  mov     edx, r15d; StringSDRevision
0x18001d936  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;"...
0x18001d93d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001d944  nop     dword ptr [rax+rax+00h]
0x18001d949  test    eax, eax
0x18001d94b  jnz     short loc_18001D99A
0x18001d94d  mov     rcx, [rbp+11E8h]; this
0x18001d954  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werdl"...
0x18001d95b  mov     edx, 448h; void *
0x18001d960  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d965  mov     r15d, eax
0x18001d968  test    eax, eax
0x18001d96a  jns     short loc_18001D994
0x18001d96c  mov     rcx, [rbp+11E8h]; this
0x18001d973  mov     r9d, eax; char *
0x18001d976  mov     r8, rdi; unsigned int
0x18001d979  mov     edx, 142h; void *
0x18001d97e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d983  lea     rcx, [rbp+11E0h+SecurityDescriptor]; this
0x18001d98a  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18001d98f  jmp     loc_18001D87F
0x18001d994  mov     r15d, 1
0x18001d99a  lea     rdx, [rbp+11E0h+SecurityDescriptor]; lpSecurityAttributes
0x18001d9a1  mov     rcx, [rbp+11E0h+lpFileName]; lpPathName
0x18001d9a5  call    cs:__imp_CreateDirectoryW
0x18001d9ac  nop     dword ptr [rax+rax+00h]
0x18001d9b1  test    eax, eax
0x18001d9b3  jnz     short loc_18001D9F7
0x18001d9b5  call    cs:__imp_GetLastError
0x18001d9bc  nop     dword ptr [rax+rax+00h]
0x18001d9c1  mov     ecx, eax; unsigned int
0x18001d9c3  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001d9c8  cmp     eax, 8007051Bh
0x18001d9cd  jz      short loc_18001D9D6
0x18001d9cf  cmp     eax, 80070005h
0x18001d9d4  jnz     short loc_18001D9D9
0x18001d9d6  mov     esi, r15d
0x18001d9d9  mov     rcx, [rbp+11E8h]; this
0x18001d9e0  test    eax, eax
0x18001d9e2  jns     short loc_18001D9F4
0x18001d9e4  mov     r9d, eax; char *
0x18001d9e7  mov     r8, rdi; unsigned int
0x18001d9ea  mov     edx, 150h; void *
0x18001d9ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d9f4  mov     r12d, r15d
0x18001d9f7  lea     rcx, [rbp+11E0h+SecurityDescriptor]; this
0x18001d9fe  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18001da03  nop
0x18001da04  lea     rcx, [rbp+11E0h+var_11C8]; void *
0x18001da08  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001da0d  xorps   xmm0, xmm0
0x18001da10  xor     eax, eax
0x18001da12  movups  xmmword ptr [rbp+11E0h+var_1260.nLength], xmm0
0x18001da16  mov     qword ptr [rbp+11E0h+var_1260.bInheritHandle], rax
0x18001da1a  xorps   xmm1, xmm1
0x18001da1d  movups  [rbp+11E0h+var_1248], xmm1
0x18001da21  movups  [rbp+11E0h+var_1238], xmm1
0x18001da25  mov     [rbp+11E0h+var_1228], rax
0x18001da29  movdqa  [rbp+11E0h+var_1220], xmm0
0x18001da2e  mov     [rbp+11E0h+var_1260.nLength], 18h
0x18001da35  mov     [rsp+12E0h+pIdentifierAuthority], rax; char *
0x18001da3a  mov     [rsp+12E0h+var_12C0], eax; int
0x18001da3e  xor     r9d, r9d
0x18001da41  lea     r8d, [rax+8]
0x18001da45  lea     rdx, qword_1800B8B90
0x18001da4c  lea     rcx, [rbp+11E0h+var_1260]; this
0x18001da50  call    ?InitFromSecurityElements@CSecurityAttributes@@QEAAJPEBUSECURITY_ELEMENT@@KPEBV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@K0@Z; CSecurityAttributes::InitFromSecurityElements(SECURITY_ELEMENT const *,ulong,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> const *,ulong,SECURITY_ELEMENT const *)
0x18001da55  mov     r15d, eax
0x18001da58  test    eax, eax
0x18001da5a  jns     short loc_18001DA82
0x18001da5c  mov     edx, 167h; void *
0x18001da61  mov     r8, rdi; unsigned int
0x18001da64  mov     r9d, r15d; char *
0x18001da67  mov     rcx, [rbp+11E8h]; this
0x18001da6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da73  nop
0x18001da74  lea     rcx, [rbp+11E0h+var_1260]; this
0x18001da78  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18001da7d  jmp     loc_18001D888
0x18001da82  mov     r15d, 8000FFFFh
0x18001da88  test    r12d, r12d
0x18001da8b  jnz     loc_18001DC88
0x18001da91  mov     rcx, [r14+10h]; lpFileName
0x18001da95  call    cs:__imp_GetFileAttributesW
0x18001da9c  nop     dword ptr [rax+rax+00h]
0x18001daa1  cmp     eax, 0FFFFFFFFh
0x18001daa4  jnz     short loc_18001DAE3
0x18001daa6  lea     rdx, [rbp+11E0h+var_1260]; struct _SECURITY_ATTRIBUTES *
0x18001daaa  mov     rcx, [r14+10h]; wchar_t *
0x18001daae  call    ?UtilEnsureDirectory@@YAJPEB_WPEAU_SECURITY_ATTRIBUTES@@@Z; UtilEnsureDirectory(wchar_t const *,_SECURITY_ATTRIBUTES *)
0x18001dab3  mov     r12d, 80070005h
0x18001dab9  cmp     eax, r12d
0x18001dabc  mov     r15d, 1
0x18001dac2  cmovz   esi, r15d
0x18001dac6  mov     rcx, [rbp+11E8h]; this
0x18001dacd  test    eax, eax
0x18001dacf  jns     short loc_18001DAEF
0x18001dad1  mov     r9d, eax; char *
0x18001dad4  mov     r8, rdi; unsigned int
0x18001dad7  mov     edx, 179h; void *
0x18001dadc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dae1  jmp     short loc_18001DAEF
0x18001dae3  mov     r15d, 1
0x18001dae9  mov     r12d, 80070005h
0x18001daef  lea     rcx, [rbp+11E0h+var_11E8]; void *
0x18001daf3  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001daf8  nop
0x18001daf9  lea     rcx, [rsp+12E0h+var_1280]; void *
0x18001dafe  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001db03  nop
0x18001db04  lea     rcx, [r14+48h]; this
0x18001db08  call    ?GetStorePath@CSettings@@QEBAPEB_WXZ; CSettings::GetStorePath(void)
0x18001db0d  mov     rcx, rax; lpSrc
0x18001db10  lea     rdx, [rbp+11E0h+var_11E8]
0x18001db14  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001db19  mov     ebx, eax
0x18001db1b  test    eax, eax
0x18001db1d  jns     short loc_18001DB5C
0x18001db1f  mov     edx, 182h; void *
0x18001db24  mov     r8, rdi; unsigned int
0x18001db27  mov     r9d, ebx; char *
0x18001db2a  mov     rcx, [rbp+11E8h]; this
0x18001db31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db36  nop
0x18001db37  lea     rcx, [rsp+12E0h+var_1280]; void *
0x18001db3c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001db41  nop
0x18001db42  lea     rcx, [rbp+11E0h+var_11E8]; void *
0x18001db46  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001db4b  nop
0x18001db4c  lea     rcx, [rbp+11E0h+var_1260]; this
0x18001db50  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18001db55  mov     esi, ebx
0x18001db57  jmp     loc_18001E05F
0x18001db5c  lea     rcx, [rsp+12E0h+lpSrc]; void *
0x18001db61  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001db66  lea     rdx, [rsp+12E0h+lpSrc]
0x18001db6b  mov     rcx, [rbp+11E0h+var_11E8]; lpFileName
0x18001db6f  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18001db74  test    eax, eax
0x18001db76  jz      short loc_18001DB86
0x18001db78  lea     rdx, [rsp+12E0h+lpSrc]
0x18001db7d  lea     rcx, [rbp+11E0h+var_11E8]
0x18001db81  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18001db86  lea     rcx, [rsp+12E0h+lpSrc]; void *
0x18001db8b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001db90  lea     r8, [rsp+12E0h+var_1280]
0x18001db95  lea     rdx, aTemp; "Temp"
0x18001db9c  mov     rcx, [rbp+11E0h+var_11E8]
0x18001dba0  call    ?Append@CPath@@SAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPath::Append(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001dba5  mov     ebx, eax
0x18001dba7  test    eax, eax
0x18001dba9  jns     short loc_18001DBB5
0x18001dbab  mov     edx, 18Ah
0x18001dbb0  jmp     loc_18001DB24
0x18001dbb5  mov     rcx, [rsp+12E0h+var_1280]; lpFileName
0x18001dbba  call    cs:__imp_GetFileAttributesW
0x18001dbc1  nop     dword ptr [rax+rax+00h]
0x18001dbc6  mov     rcx, [rsp+12E0h+var_1280]; wchar_t *
0x18001dbcb  cmp     eax, 0FFFFFFFFh
0x18001dbce  jnz     short loc_18001DBFD
0x18001dbd0  lea     rdx, [rbp+11E0h+var_1260]; struct _SECURITY_ATTRIBUTES *
0x18001dbd4  call    ?UtilEnsureDirectory@@YAJPEB_WPEAU_SECURITY_ATTRIBUTES@@@Z; UtilEnsureDirectory(wchar_t const *,_SECURITY_ATTRIBUTES *)
0x18001dbd9  cmp     eax, r12d
0x18001dbdc  cmovz   esi, r15d
0x18001dbe0  mov     rcx, [rbp+11E8h]; this
0x18001dbe7  test    eax, eax
0x18001dbe9  jns     short loc_18001DC37
  ... truncated ...
```
