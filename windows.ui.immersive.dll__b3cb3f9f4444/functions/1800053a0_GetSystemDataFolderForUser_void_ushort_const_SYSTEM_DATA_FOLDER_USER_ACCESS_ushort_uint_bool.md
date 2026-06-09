# GetSystemDataFolderForUser(void *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort *,uint,bool)

- ea: `0x1800053a0`
- end: `0x18000648a`
- name: `?GetSystemDataFolderForUser@@YAJPEAXPEBGW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEAGI_N@Z`
- size: `4330`
- prototype: `__int64 __fastcall(void *, const WCHAR *, unsigned int, _WORD *, __int64, char)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004b78`
- `0x18000b9fc`
- `0x18000ba88`
- `0x18000c600`

## callees

- `0x1800053a0`
- `0x180006490`
- `0x180006794`
- `0x18000da00`
- `0x18003d244`
- `0x180054130`
- `0x180054ad4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000552a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000584c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005c1c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005dec`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180006331`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000638d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800063e9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000646f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000552a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000584c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005c1c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180005dec`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180006331`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000638d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800063e9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000646f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800055d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800058e3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005a4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005cc3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005e99`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000615f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006232`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800055d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800058e3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005a4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005cc3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005e99`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000615f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006232`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005b6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006177`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000624a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005b6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006177`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000624a`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800056d0`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800059d4`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005a91`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005fc6`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800060e5`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800061b8`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800056d0`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800059d4`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005a91`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005fc6`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800060e5`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800061b8`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180005747`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180005b08`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000603d`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180005747`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180005b08`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000603d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180005508`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000582a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180005bf8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180005dc7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180005508`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000582a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180005bf8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180005dc7`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005553`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005875`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005c45`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005e15`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005553`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005875`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005c45`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180005e15`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005790`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005b51`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006086`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005790`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005b51`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006086`
- `SHELL32!SHGetKnownFolderPath` at `0x18000541a`
- `SHELL32!SHGetKnownFolderPath` at `0x18000541a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800056f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005ab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800056f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005ab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061fa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180005725`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180005ae6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000601b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180005725`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180005ae6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000601b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800053eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800053eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180005a03`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180006114`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800061e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180005a03`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180006114`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800061e7`

## pseudocode

```c
__int64 __fastcall GetSystemDataFolderForUser(
        void *a1,
        const WCHAR *a2,
        unsigned int a3,
        _WORD *a4,
        __int64 a5,
        char a6)
{
  _WORD *v6; // r14
  PWSTR v7; // rcx
  WCHAR *v8; // r9
  PWSTR v9; // r8
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // rbx
  WCHAR *v14; // rdx
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // r8
  WCHAR *v18; // r9
  WCHAR *v19; // rcx
  wchar_t *i; // rax
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  WCHAR *v24; // r9
  __int64 v25; // rdx
  WCHAR *v26; // r8
  WCHAR *v27; // rcx
  const wchar_t *v28; // rdx
  WCHAR *v29; // r9
  __int64 v30; // rcx
  __int64 v31; // r8
  WCHAR *v32; // rcx
  int Error; // ebx
  void *v34; // rax
  void *v35; // r15
  __int64 v36; // rcx
  WCHAR *v37; // rdx
  __int64 v38; // r8
  WCHAR *v39; // r9
  WCHAR *v40; // rcx
  wchar_t *j; // rax
  unsigned __int64 v42; // rbx
  unsigned __int64 v43; // rax
  __int64 v44; // rcx
  WCHAR *v45; // rdx
  __int64 v46; // r8
  WCHAR *v47; // r9
  WCHAR *v48; // rcx
  __int64 result; // rax
  bool v50; // r12
  size_t v51; // rax
  void *v52; // rax
  void *v53; // r15
  int v54; // ebx
  __int64 v55; // rcx
  WCHAR *v56; // rdx
  __int64 v57; // r8
  WCHAR *v58; // r9
  WCHAR *v59; // rcx
  LPWSTR v60; // r12
  __int64 v61; // r15
  HRESULT v62; // ebx
  wchar_t *v63; // rax
  unsigned __int64 v64; // rax
  unsigned __int64 v65; // rbx
  __int64 v66; // rcx
  WCHAR *v67; // rdx
  __int64 v68; // r8
  WCHAR *v69; // r9
  WCHAR *v70; // rcx
  const WCHAR *v71; // r10
  __int64 v72; // rcx
  WCHAR *v73; // r8
  __int64 v74; // rdx
  WCHAR *v75; // r9
  WCHAR *v76; // rcx
  HRESULT v77; // r15d
  LPWSTR v78; // r12
  wchar_t *v79; // rax
  unsigned __int64 v80; // rax
  unsigned __int64 v81; // rbx
  __int64 v82; // rax
  WCHAR *v83; // rdx
  __int64 v84; // r9
  WCHAR *v85; // r10
  WCHAR *v86; // rcx
  const wchar_t *v87; // rdx
  WCHAR *v88; // r9
  __int64 v89; // rcx
  __int64 v90; // r8
  WCHAR *v91; // rcx
  void *v92; // rax
  void *v93; // r15
  bool v94; // r12
  size_t v95; // rax
  bool v96; // r12
  size_t v97; // rax
  WCHAR *v98; // rcx
  _WORD *v99; // rcx
  const wchar_t *v100; // rdx
  WCHAR *v101; // r9
  __int64 v102; // rcx
  __int64 v103; // r8
  WCHAR *v104; // rcx
  DWORD nLengthNeeded[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v107; // [rsp+40h] [rbp-C0h]
  unsigned int v108; // [rsp+44h] [rbp-BCh]
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR ppszPath; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v112; // [rsp+70h] [rbp-90h]
  PCWSTR pszMore; // [rsp+78h] [rbp-88h]
  WCHAR String1[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPathOut[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR pszPath[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  pszMore = a2;
  *a4 = 0;
  StringSid = 0;
  v6 = a4;
  v112 = a4;
  v107 = a3;
  if ( ConvertSidToStringSidW(a1, &StringSid) )
  {
    v108 = 0;
LABEL_3:
    ppszPath = 0;
    if ( SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, &ppszPath) < 0 )
      goto LABEL_81;
    v7 = ppszPath;
    v8 = String1;
    v9 = ppszPath;
    v10 = 2147483646;
    v11 = 2147483646;
    v12 = 260;
    v13 = 260;
    do
    {
      if ( !v11 )
        break;
      if ( !*v9 )
        break;
      *v8++ = *v9++;
      --v11;
      --v13;
    }
    while ( v13 );
    v14 = v8 - 1;
    if ( v13 )
      v14 = v8;
    *v14 = 0;
    CoTaskMemFree(v7);
    ppszPath = 0;
    if ( !v13 )
      goto LABEL_81;
    v15 = 2147483646;
    v16 = String1;
    v17 = 260;
    v18 = pszPath;
    do
    {
      if ( !v15 )
        break;
      if ( !*v16 )
        break;
      *v18++ = *v16++;
      --v15;
      --v17;
    }
    while ( v17 );
    v19 = v18 - 1;
    if ( v17 )
      v19 = v18;
    *v19 = 0;
    if ( !v17 || PathCchAppend(pszPath, 0x104u, L"Microsoft\\Windows\\SystemData") < 0 )
      goto LABEL_81;
    for ( i = wcsstr(pszPath, L"/"); i; i = wcsstr(i, L"/") )
      *i = 92;
    if ( PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0) < 0 )
      goto LABEL_81;
    v21 = -1;
    do
      ++v21;
    while ( String1[v21] );
    if ( v21 > 0xFFFFFFFF )
      goto LABEL_81;
    v22 = -1;
    do
      ++v22;
    while ( pszPathOut[v22] );
    if ( v22 > 0xFFFFFFFF
      || (unsigned int)v22 <= (unsigned int)v21
      || CompareStringOrdinal(String1, v21, pszPathOut, v21, 0) != 2
      || pszPathOut[(unsigned int)v21] != 92 )
    {
      goto LABEL_81;
    }
    v23 = 2147483646;
    v24 = pszPathOut;
    v25 = 260;
    v26 = String1;
    do
    {
      if ( !v23 )
        break;
      if ( !*v24 )
        break;
      *v26++ = *v24++;
      --v23;
      --v25;
    }
    while ( v25 );
    v27 = v26 - 1;
    if ( v25 )
      v27 = v26;
    *v27 = 0;
    if ( !v25 )
      goto LABEL_81;
    if ( a6 )
    {
      v28 = L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)";
      v29 = pszPathOut;
      v30 = 2147483646;
      v31 = 260;
      do
      {
        if ( !v30 )
          break;
        if ( !*v28 )
          break;
        *v29++ = *v28++;
        --v30;
        --v31;
      }
      while ( v31 );
      v32 = v29 - 1;
      Error = -2147024774;
      if ( v31 )
      {
        v32 = v29;
        Error = 0;
      }
      *v32 = 0;
      if ( v31 )
      {
        nLengthNeeded[0] = 0;
        if ( GetFileSecurityW(String1, 7u, 0, 0, nLengthNeeded) )
          goto LABEL_48;
        if ( (unsigned int)ResultFromKnownLastError() != -2147024774 )
          goto LABEL_48;
        v34 = CoTaskMemAlloc(nLengthNeeded[0]);
        v35 = v34;
        if ( !v34 )
          goto LABEL_48;
        v50 = 0;
        v51 = CTCoAllocPolicy::_CoTaskMemSize(v34);
        memset_0(v35, 0, v51);
        if ( GetFileSecurityW(String1, 7u, v35, nLengthNeeded[0], nLengthNeeded) )
        {
          StringSecurityDescriptor = 0;
          if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v35, 1u, 7u, &StringSecurityDescriptor, 0) )
          {
            v50 = CompareStringOrdinal(StringSecurityDescriptor, -1, pszPathOut, -1, 1) == 2;
            LocalFree(StringSecurityDescriptor);
          }
        }
        CoTaskMemFree(v35);
        if ( !v50 )
        {
LABEL_48:
          *(_QWORD *)nLengthNeeded = 0;
          if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                 pszPathOut,
                 1u,
                 (PSECURITY_DESCRIPTOR *)nLengthNeeded,
                 0)
            || (Error = ResultFromKnownLastError(), Error >= 0) )
          {
            if ( SetFileSecurityW(String1, 7u, *(PSECURITY_DESCRIPTOR *)nLengthNeeded) )
            {
              Error = 0;
            }
            else
            {
              Error = ResultFromKnownLastError();
              if ( Error == -2147024894 )
              {
                SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)nLengthNeeded;
                *(_QWORD *)&SecurityAttributes.nLength = 24;
                *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
                if ( CreateDirectoryW(String1, &SecurityAttributes) )
                  Error = 0;
                else
                  Error = ResultFromKnownLastError();
              }
              else if ( Error == -2147024891 )
              {
                Error = 0;
              }
            }
            LocalFree(*(HLOCAL *)nLengthNeeded);
          }
        }
      }
      if ( Error < 0 )
        goto LABEL_81;
    }
    v36 = 2147483646;
    v37 = String1;
    v38 = 260;
    v39 = pszPath;
    do
    {
      if ( !v36 )
        break;
      if ( !*v37 )
        break;
      *v39++ = *v37++;
      --v36;
      --v38;
    }
    while ( v38 );
    v40 = v39 - 1;
    if ( v38 )
      v40 = v39;
    *v40 = 0;
    if ( !v38 || PathCchAppend(pszPath, 0x104u, StringSid) < 0 )
      goto LABEL_81;
    for ( j = wcsstr(pszPath, L"/"); j; j = wcsstr(j, L"/") )
      *j = 92;
    if ( PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0) < 0 )
      goto LABEL_81;
    v42 = -1;
    do
      ++v42;
    while ( String1[v42] );
    if ( v42 > 0xFFFFFFFF )
      goto LABEL_81;
    v43 = -1;
    do
      ++v43;
    while ( pszPathOut[v43] );
    if ( v43 > 0xFFFFFFFF
      || (unsigned int)v43 <= (unsigned int)v42
      || CompareStringOrdinal(String1, v42, pszPathOut, v42, 0) != 2
      || pszPathOut[(unsigned int)v42] != 92 )
    {
      goto LABEL_81;
    }
    v44 = 2147483646;
    v45 = pszPathOut;
    v46 = 260;
    v47 = String1;
    do
    {
      if ( !v44 )
        break;
      if ( !*v45 )
        break;
      *v47++ = *v45++;
      --v44;
      --v46;
    }
    while ( v46 );
    v48 = v47 - 1;
    if ( v46 )
      v48 = v47;
    *v48 = 0;
    if ( !v46 )
      goto LABEL_81;
    if ( a6 )
    {
      v100 = L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)";
      v101 = pszPathOut;
      v102 = 2147483646;
      v103 = 260;
      do
      {
        if ( !v102 )
          break;
        if ( !*v100 )
          break;
        *v101++ = *v100++;
        --v102;
        --v103;
      }
      while ( v103 );
      v104 = v101 - 1;
      v54 = -2147024774;
      if ( v103 )
      {
        v104 = v101;
        v54 = 0;
      }
      *v104 = 0;
      if ( v103 )
      {
        nLengthNeeded[0] = 0;
        if ( GetFileSecurityW(String1, 7u, 0, 0, nLengthNeeded) )
          goto LABEL_91;
        if ( (unsigned int)ResultFromKnownLastError() != -2147024774 )
          goto LABEL_91;
        v52 = CoTaskMemAlloc(nLengthNeeded[0]);
        v53 = v52;
        if ( !v52 )
          goto LABEL_91;
        v94 = 0;
        v95 = CTCoAllocPolicy::_CoTaskMemSize(v52);
        memset_0(v53, 0, v95);
        if ( GetFileSecurityW(String1, 7u, v53, nLengthNeeded[0], nLengthNeeded) )
        {
          StringSecurityDescriptor = 0;
          if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v53, 1u, 7u, &StringSecurityDescriptor, 0) )
          {
            v94 = CompareStringOrdinal(StringSecurityDescriptor, -1, pszPathOut, -1, 1) == 2;
            LocalFree(StringSecurityDescriptor);
          }
        }
        CoTaskMemFree(v53);
        if ( !v94 )
        {
LABEL_91:
          *(_QWORD *)nLengthNeeded = 0;
          if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                 pszPathOut,
                 1u,
                 (PSECURITY_DESCRIPTOR *)nLengthNeeded,
                 0)
            || (v54 = ResultFromKnownLastError(), v54 >= 0) )
          {
            if ( SetFileSecurityW(String1, 7u, *(PSECURITY_DESCRIPTOR *)nLengthNeeded) )
            {
              v54 = 0;
            }
            else
            {
              v54 = ResultFromKnownLastError();
              if ( v54 == -2147024894 )
              {
                SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)nLengthNeeded;
                *(_QWORD *)&SecurityAttributes.nLength = 24;
                *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
                if ( CreateDirectoryW(String1, &SecurityAttributes) )
                  v54 = 0;
                else
                  v54 = ResultFromKnownLastError();
              }
              else if ( v54 == -2147024891 )
              {
                v54 = 0;
              }
            }
            LocalFree(*(HLOCAL *)nLengthNeeded);
          }
        }
      }
      if ( v54 < 0 )
        goto LABEL_81;
    }
    v55 = 2147483646;
    v56 = String1;
    v57 = 260;
    v58 = pszPath;
    do
    {
      if ( !v55 )
        break;
      if ( !*v56 )
        break;
      *v58++ = *v56++;
      --v55;
      --v57;
    }
    while ( v57 );
    v59 = v58 - 1;
    if ( v57 )
      v59 = v58;
    *v59 = 0;
    if ( !v57 )
      goto LABEL_81;
    v60 = StringSid;
    v61 = 3LL * (int)v107;
    v62 = PathCchAppend(pszPath, 0x104u, (PCWSTR)qword_1800EE000[v61 + 1]);
    if ( v62 >= 0 )
    {
      v63 = wcsstr(pszPath, L"/");
      if ( v63 )
      {
        do
        {
          *v63 = 92;
          v63 = wcsstr(v63, L"/");
        }
        while ( v63 );
        v6 = v112;
      }
      v62 = PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0);
      if ( v62 >= 0 )
      {
        v64 = -1;
        v65 = -1;
        do
          ++v65;
        while ( String1[v65] );
        if ( v65 > 0xFFFFFFFF )
          goto LABEL_81;
        do
          ++v64;
        while ( pszPathOut[v64] );
        if ( v64 > 0xFFFFFFFF
          || (unsigned int)v64 <= (unsigned int)v65
          || CompareStringOrdinal(String1, v65, pszPathOut, v65, 0) != 2
          || pszPathOut[(unsigned int)v65] != 92 )
        {
          goto LABEL_81;
        }
        v66 = 2147483646;
        v67 = pszPathOut;
        v68 = 260;
        v69 = String1;
        do
        {
          if ( !v66 )
            break;
          if ( !*v67 )
            break;
          *v69++ = *v67++;
          --v66;
          --v68;
        }
        while ( v68 );
        v70 = v69 - 1;
        v62 = -2147024774;
        if ( v68 )
        {
          v70 = v69;
          v62 = 0;
        }
        *v70 = 0;
        if ( v68 )
        {
          if ( !a6 )
          {
LABEL_124:
            v71 = pszMore;
            if ( !pszMore || !*pszMore )
              goto LABEL_184;
            v72 = 2147483646;
            v73 = String1;
            v74 = 260;
            v75 = pszPath;
            do
            {
              if ( !v72 )
                break;
              if ( !*v73 )
                break;
              *v75++ = *v73++;
              --v72;
              --v74;
            }
            while ( v74 );
            v76 = v75 - 1;
            v77 = -2147024774;
            if ( v74 )
            {
              v76 = v75;
              v77 = 0;
            }
            *v76 = 0;
            if ( v74 )
            {
              v78 = StringSid;
              v77 = PathCchAppend(pszPath, 0x104u, v71);
              if ( v77 >= 0 )
              {
                v79 = wcsstr(pszPath, L"/");
                if ( v79 )
                {
                  do
                  {
                    *v79 = 92;
                    v79 = wcsstr(v79, L"/");
                  }
                  while ( v79 );
                  v6 = v112;
                }
                v77 = PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0);
                if ( v77 >= 0 )
                {
                  v80 = -1;
                  v81 = -1;
                  do
                    ++v81;
                  while ( String1[v81] );
                  if ( v81 > 0xFFFFFFFF )
                    goto LABEL_182;
                  do
                    ++v80;
                  while ( pszPathOut[v80] );
                  if ( v80 > 0xFFFFFFFF )
                  {
LABEL_182:
                    v77 = -2147024362;
                  }
                  else
                  {
                    v77 = -2147024809;
                    if ( (unsigned int)v80 > (unsigned int)v81
                      && CompareStringOrdinal(String1, v81, pszPathOut, v81, 0) == 2
                      && pszPathOut[(unsigned int)v81] == 92 )
                    {
                      v82 = 2147483646;
                      v83 = pszPathOut;
                      v84 = 260;
                      v85 = String1;
                      do
                      {
                        if ( !v82 )
                          break;
                        if ( !*v83 )
                          break;
                        *v85++ = *v83++;
                        --v82;
                        --v84;
                      }
                      while ( v84 );
                      v86 = v85 - 1;
                      v77 = -2147024774;
                      if ( v84 )
                      {
                        v86 = v85;
                        v77 = 0;
                      }
                      *v86 = 0;
                      if ( v84 && a6 )
                        v77 = _SetSecurityOnFileOrFolder(String1, v78, v107, 0);
                    }
                  }
                }
              }
            }
            if ( v77 >= 0 )
            {
LABEL_184:
              v98 = String1;
              do
              {
                if ( !v10 )
                  break;
                if ( !*v98 )
                  break;
                *v6++ = *v98++;
                --v10;
                --v12;
              }
              while ( v12 );
              v99 = v6 - 1;
              if ( v12 )
                v99 = v6;
              *v99 = 0;
            }
            goto LABEL_81;
          }
          if ( v107 )
          {
            v62 = StringCchPrintfW(pszPathOut, 0x104u, (const unsigned __int16 *)qword_1800EE000[v61 + 2], v60);
          }
          else
          {
            v87 = L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)";
            v88 = pszPathOut;
            v89 = 2147483646;
            v90 = 260;
            do
            {
              if ( !v89 )
                break;
              if ( !*v87 )
                break;
              *v88++ = *v87++;
              --v89;
              --v90;
            }
            while ( v90 );
            v91 = v88 - 1;
            v62 = -2147024774;
            if ( v90 )
            {
              v91 = v88;
              v62 = 0;
            }
            *v91 = 0;
          }
          if ( v62 < 0 )
            goto LABEL_81;
          nLengthNeeded[0] = 0;
          if ( GetFileSecurityW(String1, 7u, 0, 0, nLengthNeeded) )
            goto LABEL_166;
          if ( (unsigned int)ResultFromKnownLastError() != -2147024774 )
            goto LABEL_166;
          v92 = CoTaskMemAlloc(nLengthNeeded[0]);
          v93 = v92;
          if ( !v92 )
            goto LABEL_166;
          v96 = 0;
          v97 = CTCoAllocPolicy::_CoTaskMemSize(v92);
          memset_0(v93, 0, v97);
          if ( GetFileSecurityW(String1, 7u, v93, nLengthNeeded[0], nLengthNeeded) )
          {
            StringSecurityDescriptor = 0;
            if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v93, 1u, 7u, &StringSecurityDescriptor, 0) )
            {
              v96 = CompareStringOrdinal(StringSecurityDescriptor, -1, pszPathOut, -1, 1) == 2;
              LocalFree(StringSecurityDescriptor);
            }
          }
          CoTaskMemFree(v93);
          if ( !v96 )
          {
LABEL_166:
            *(_QWORD *)nLengthNeeded = 0;
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                   pszPathOut,
                   1u,
                   (PSECURITY_DESCRIPTOR *)nLengthNeeded,
                   0)
              || (v62 = ResultFromKnownLastError(), v62 >= 0) )
            {
              if ( SetFileSecurityW(String1, 7u, *(PSECURITY_DESCRIPTOR *)nLengthNeeded) )
              {
                v62 = 0;
              }
              else
              {
                v62 = ResultFromKnownLastError();
                if ( v62 == -2147024894 )
                {
                  SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)nLengthNeeded;
                  *(_QWORD *)&SecurityAttributes.nLength = 24;
                  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
                  if ( CreateDirectoryW(String1, &SecurityAttributes) )
                    v62 = 0;
                  else
                    v62 = ResultFromKnownLastError();
                }
                else if ( v62 == -2147024891 )
                {
                  v62 = 0;
                }
              }
              LocalFree(*(HLOCAL *)nLengthNeeded);
            }
          }
        }
      }
    }
    if ( v62 >= 0 )
      goto LABEL_124;
LABEL_81:
    LocalFree(StringSid);
    return v108;
  }
  result = ResultFromKnownLastError();
  v108 = result;
  if ( (int)result >= 0 )
    goto LABEL_3;
  return result;
}

```

## disassembly

```asm
0x1800053a0  push    rbp
0x1800053a2  push    r12
0x1800053a4  push    r13
0x1800053a6  push    r14
0x1800053a8  lea     rbp, [rsp-5E8h]
0x1800053b0  sub     rsp, 6E8h
0x1800053b7  mov     rax, cs:__security_cookie
0x1800053be  xor     rax, rsp
0x1800053c1  mov     [rbp+600h+var_50], rax
0x1800053c8  mov     [rsp+700h+pszMore], rdx
0x1800053cd  xor     r13d, r13d
0x1800053d0  lea     rdx, [rsp+700h+StringSid]; StringSid
0x1800053d5  mov     [r9], r13w
0x1800053d9  mov     [rsp+700h+StringSid], r13
0x1800053de  mov     r14, r9
0x1800053e1  mov     [rsp+700h+var_690], r9
0x1800053e6  mov     [rsp+700h+var_6C0], r8d
0x1800053eb  call    cs:__imp_ConvertSidToStringSidW
0x1800053f2  nop     dword ptr [rax+rax+00h]
0x1800053f7  test    eax, eax
0x1800053f9  jz      loc_18000630C
0x1800053ff  mov     [rsp+700h+var_6BC], r13d
0x180005404  lea     r9, [rsp+700h+ppszPath]; ppszPath
0x180005409  mov     [rsp+700h+ppszPath], r13
0x18000540e  xor     r8d, r8d; hToken
0x180005411  lea     rcx, FOLDERID_ProgramData; rfid
0x180005418  xor     edx, edx; dwFlags
0x18000541a  call    cs:__imp_SHGetKnownFolderPath
0x180005421  nop     dword ptr [rax+rax+00h]
0x180005426  test    eax, eax
0x180005428  js      loc_18000596D
0x18000542e  mov     rcx, [rsp+700h+ppszPath]; pv
0x180005433  lea     r9, [rbp+600h+String1]
0x180005437  mov     [rsp+700h+var_20], rbx
0x18000543f  mov     r8, rcx
0x180005442  mov     [rsp+700h+var_28], rsi
0x18000544a  mov     esi, 7FFFFFFEh
0x18000544f  mov     [rsp+700h+var_30], rdi
0x180005457  mov     edx, esi
0x180005459  mov     edi, 104h
0x18000545e  mov     ebx, edi
0x180005460  test    rdx, rdx
0x180005463  jz      short loc_180005483
0x180005465  movzx   eax, word ptr [r8]
0x180005469  test    ax, ax
0x18000546c  jz      short loc_180005483
0x18000546e  mov     [r9], ax
0x180005472  add     r8, 2
0x180005476  add     r9, 2
0x18000547a  dec     rdx
0x18000547d  sub     rbx, 1
0x180005481  jnz     short loc_180005460
0x180005483  lea     rdx, [r9-2]
0x180005487  test    rbx, rbx
0x18000548a  cmovnz  rdx, r9
0x18000548e  mov     [rdx], r13w
0x180005492  call    cs:__imp_CoTaskMemFree
0x180005499  nop     dword ptr [rax+rax+00h]
0x18000549e  mov     [rsp+700h+ppszPath], r13
0x1800054a3  test    rbx, rbx
0x1800054a6  jz      loc_180005955
0x1800054ac  mov     rcx, rsi
0x1800054af  lea     rdx, [rbp+600h+String1]
0x1800054b3  mov     r8, rdi
0x1800054b6  lea     r9, [rbp+600h+pszPath]
0x1800054bd  nop     dword ptr [rax]
0x1800054c0  test    rcx, rcx
0x1800054c3  jz      short loc_1800054E2
0x1800054c5  movzx   eax, word ptr [rdx]
0x1800054c8  test    ax, ax
0x1800054cb  jz      short loc_1800054E2
0x1800054cd  mov     [r9], ax
0x1800054d1  add     rdx, 2
0x1800054d5  add     r9, 2
0x1800054d9  dec     rcx
0x1800054dc  sub     r8, 1
0x1800054e0  jnz     short loc_1800054C0
0x1800054e2  test    r8, r8
0x1800054e5  lea     rcx, [r9-2]
0x1800054e9  cmovnz  rcx, r9
0x1800054ed  mov     [rcx], r13w
0x1800054f1  jz      loc_180005955
0x1800054f7  lea     r8, pszMore; "Microsoft\\Windows\\SystemData"
0x1800054fe  mov     rdx, rdi; cchPath
0x180005501  lea     rcx, [rbp+600h+pszPath]; pszPath
0x180005508  call    cs:__imp_PathCchAppend
0x18000550f  nop     dword ptr [rax+rax+00h]
0x180005514  test    eax, eax
0x180005516  js      loc_180005955
0x18000551c  lea     rdx, SubStr; "/"
0x180005523  lea     rcx, [rbp+600h+pszPath]; Str
0x18000552a  call    cs:__imp_wcsstr
0x180005531  nop     dword ptr [rax+rax+00h]
0x180005536  test    rax, rax
0x180005539  jnz     loc_180006322
0x18000553f  xor     r9d, r9d; dwFlags
0x180005542  lea     r8, [rbp+600h+pszPath]; pszPathIn
0x180005549  mov     rdx, rdi; cchPathOut
0x18000554c  lea     rcx, [rbp+600h+pszPathOut]; pszPathOut
0x180005553  call    cs:__imp_PathCchCanonicalizeEx
0x18000555a  nop     dword ptr [rax+rax+00h]
0x18000555f  test    eax, eax
0x180005561  js      loc_180005955
0x180005567  mov     [rsp+700h+var_38], r15
0x18000556f  lea     rax, [rbp+600h+String1]
0x180005573  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000557a  mov     rbx, r15
0x18000557d  nop     dword ptr [rax]
0x180005580  inc     rbx
0x180005583  cmp     [rax+rbx*2], r13w
0x180005588  jnz     short loc_180005580
0x18000558a  mov     r12d, 0FFFFFFFFh
0x180005590  cmp     rbx, r12
0x180005593  ja      loc_18000594D
0x180005599  lea     rcx, [rbp+600h+pszPathOut]
0x1800055a0  mov     rax, r15
0x1800055a3  inc     rax
0x1800055a6  cmp     [rcx+rax*2], r13w
0x1800055ab  jnz     short loc_1800055A3
0x1800055ad  cmp     rax, r12
0x1800055b0  ja      loc_18000594D
0x1800055b6  cmp     eax, ebx
0x1800055b8  jbe     loc_18000594D
0x1800055be  mov     r9d, ebx; cchCount2
0x1800055c1  mov     [rsp+700h+bIgnoreCase], r13d; bIgnoreCase
0x1800055c6  lea     r8, [rbp+600h+pszPathOut]; lpString2
0x1800055cd  mov     edx, ebx; cchCount1
0x1800055cf  lea     rcx, [rbp+600h+String1]; lpString1
0x1800055d3  call    cs:__imp_CompareStringOrdinal
0x1800055da  nop     dword ptr [rax+rax+00h]
0x1800055df  cmp     eax, 2
0x1800055e2  jnz     loc_18000594D
0x1800055e8  mov     eax, ebx
0x1800055ea  cmp     [rbp+rax*2+600h+pszPathOut], 5Ch ; '\'
0x1800055f3  jnz     loc_18000594D
0x1800055f9  mov     rcx, rsi
0x1800055fc  lea     r9, [rbp+600h+pszPathOut]
0x180005603  mov     rdx, rdi
0x180005606  lea     r8, [rbp+600h+String1]
0x18000560a  nop     word ptr [rax+rax+00h]
0x180005610  test    rcx, rcx
0x180005613  jz      short loc_180005633
0x180005615  movzx   eax, word ptr [r9]
0x180005619  test    ax, ax
0x18000561c  jz      short loc_180005633
0x18000561e  mov     [r8], ax
0x180005622  add     r9, 2
0x180005626  add     r8, 2
0x18000562a  dec     rcx
0x18000562d  sub     rdx, 1
0x180005631  jnz     short loc_180005610
0x180005633  test    rdx, rdx
0x180005636  lea     rcx, [r8-2]
0x18000563a  cmovnz  rcx, r8
0x18000563e  mov     [rcx], r13w
0x180005642  jz      loc_18000594D
0x180005648  movzx   r13d, [rbp+600h+arg_28]
0x180005650  test    r13b, r13b
0x180005653  jz      loc_1800057CC
0x180005659  mov     rdx, cs:off_1800EE010; "O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-"...
0x180005660  lea     r9, [rbp+600h+pszPathOut]
0x180005667  mov     rcx, rsi
0x18000566a  mov     r8, rdi
0x18000566d  nop     dword ptr [rax]
0x180005670  test    rcx, rcx
0x180005673  jz      short loc_180005692
0x180005675  movzx   eax, word ptr [rdx]
0x180005678  test    ax, ax
0x18000567b  jz      short loc_180005692
0x18000567d  mov     [r9], ax
0x180005681  add     rdx, 2
0x180005685  add     r9, 2
0x180005689  dec     rcx
0x18000568c  sub     r8, 1
0x180005690  jnz     short loc_180005670
0x180005692  test    r8, r8
0x180005695  lea     rcx, [r9-2]
0x180005699  mov     ebx, 8007007Ah
0x18000569e  cmovnz  rcx, r9
0x1800056a2  xor     eax, eax
0x1800056a4  test    r8, r8
0x1800056a7  cmovnz  ebx, eax
0x1800056aa  mov     [rcx], ax
0x1800056ad  jz      loc_1800057B7
0x1800056b3  mov     [rsp+700h+nLengthNeeded], eax
0x1800056b7  lea     rcx, [rbp+600h+String1]; lpFileName
0x1800056bb  lea     rax, [rsp+700h+nLengthNeeded]
0x1800056c0  xor     r9d, r9d; nLength
0x1800056c3  xor     r8d, r8d; pSecurityDescriptor
0x1800056c6  mov     qword ptr [rsp+700h+bIgnoreCase], rax; lpnLengthNeeded
0x1800056cb  mov     edx, 7; RequestedInformation
0x1800056d0  call    cs:__imp_GetFileSecurityW
0x1800056d7  nop     dword ptr [rax+rax+00h]
0x1800056dc  test    eax, eax
0x1800056de  jnz     short loc_180005708
0x1800056e0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800056e5  cmp     eax, 8007007Ah
0x1800056ea  jnz     short loc_180005708
0x1800056ec  mov     ecx, [rsp+700h+nLengthNeeded]; cb
0x1800056f0  call    cs:__imp_CoTaskMemAlloc
0x1800056f7  nop     dword ptr [rax+rax+00h]
0x1800056fc  mov     r15, rax
0x1800056ff  test    rax, rax
0x180005702  jnz     loc_1800059A1
0x180005708  xor     r9d, r9d; SecurityDescriptorSize
0x18000570b  mov     qword ptr [rsp+700h+nLengthNeeded], 0
0x180005714  lea     r8, [rsp+700h+nLengthNeeded]; SecurityDescriptor
0x180005719  mov     edx, 1; StringSDRevision
0x18000571e  lea     rcx, [rbp+600h+pszPathOut]; StringSecurityDescriptor
0x180005725  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000572c  nop     dword ptr [rax+rax+00h]
0x180005731  test    eax, eax
0x180005733  jz      loc_180006347
0x180005739  mov     r8, qword ptr [rsp+700h+nLengthNeeded]; pSecurityDescriptor
0x18000573e  lea     rcx, [rbp+600h+String1]; lpFileName
0x180005742  mov     edx, 7; SecurityInformation
0x180005747  call    cs:__imp_SetFileSecurityW
0x18000574e  nop     dword ptr [rax+rax+00h]
0x180005753  test    eax, eax
0x180005755  jnz     loc_18000635B
0x18000575b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005760  mov     ebx, eax
0x180005762  cmp     eax, 80070002h
0x180005767  jnz     loc_18000636E
0x18000576d  mov     rax, qword ptr [rsp+700h+nLengthNeeded]
0x180005772  lea     rdx, [rsp+700h+SecurityAttributes]; lpSecurityAttributes
0x180005777  mov     [rsp+700h+SecurityAttributes.lpSecurityDescriptor], rax
0x18000577c  lea     rcx, [rbp+600h+String1]; lpPathName
0x180005780  xor     eax, eax
0x180005782  mov     qword ptr [rsp+700h+SecurityAttributes.nLength], 18h
0x18000578b  mov     qword ptr [rsp+700h+SecurityAttributes.bInheritHandle], rax
0x180005790  call    cs:__imp_CreateDirectoryW
0x180005797  nop     dword ptr [rax+rax+00h]
0x18000579c  test    eax, eax
0x18000579e  jz      loc_180006362
0x1800057a4  xor     ebx, ebx
0x1800057a6  mov     rcx, qword ptr [rsp+700h+nLengthNeeded]; hMem
0x1800057ab  call    cs:__imp_LocalFree
0x1800057b2  nop     dword ptr [rax+rax+00h]
0x1800057b7  test    ebx, ebx
0x1800057b9  js      loc_18000594D
0x1800057bf  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800057c6  mov     r12d, 0FFFFFFFFh
0x1800057cc  mov     rcx, rsi
0x1800057cf  lea     rdx, [rbp+600h+String1]
0x1800057d3  mov     r8, rdi
0x1800057d6  lea     r9, [rbp+600h+pszPath]
0x1800057dd  nop     dword ptr [rax]
0x1800057e0  test    rcx, rcx
0x1800057e3  jz      short loc_180005802
0x1800057e5  movzx   eax, word ptr [rdx]
0x1800057e8  test    ax, ax
0x1800057eb  jz      short loc_180005802
0x1800057ed  mov     [r9], ax
0x1800057f1  add     rdx, 2
0x1800057f5  add     r9, 2
0x1800057f9  dec     rcx
0x1800057fc  sub     r8, 1
0x180005800  jnz     short loc_1800057E0
0x180005802  test    r8, r8
0x180005805  lea     rcx, [r9-2]
0x180005809  cmovnz  rcx, r9
0x18000580d  xor     eax, eax
0x18000580f  mov     [rcx], ax
0x180005812  test    r8, r8
0x180005815  jz      loc_18000594D
0x18000581b  mov     r8, [rsp+700h+StringSid]; pszMore
0x180005820  lea     rcx, [rbp+600h+pszPath]; pszPath
0x180005827  mov     rdx, rdi; cchPath
0x18000582a  call    cs:__imp_PathCchAppend
0x180005831  nop     dword ptr [rax+rax+00h]
0x180005836  test    eax, eax
0x180005838  js      loc_18000594D
0x18000583e  lea     rdx, SubStr; "/"
0x180005845  lea     rcx, [rbp+600h+pszPath]; Str
0x18000584c  call    cs:__imp_wcsstr
0x180005853  nop     dword ptr [rax+rax+00h]
0x180005858  test    rax, rax
0x18000585b  jnz     loc_18000637E
0x180005861  xor     r9d, r9d; dwFlags
0x180005864  lea     r8, [rbp+600h+pszPath]; pszPathIn
0x18000586b  mov     rdx, rdi; cchPathOut
0x18000586e  lea     rcx, [rbp+600h+pszPathOut]; pszPathOut
0x180005875  call    cs:__imp_PathCchCanonicalizeEx
0x18000587c  nop     dword ptr [rax+rax+00h]
0x180005881  test    eax, eax
0x180005883  js      loc_18000594D
0x180005889  lea     rax, [rbp+600h+String1]
0x18000588d  mov     rbx, r15
0x180005890  inc     rbx
0x180005893  cmp     word ptr [rax+rbx*2], 0
0x180005898  jnz     short loc_180005890
0x18000589a  cmp     rbx, r12
0x18000589d  ja      loc_18000594D
0x1800058a3  lea     rcx, [rbp+600h+pszPathOut]
0x1800058aa  mov     rax, r15
0x1800058ad  nop     dword ptr [rax]
0x1800058b0  inc     rax
0x1800058b3  cmp     word ptr [rcx+rax*2], 0
0x1800058b8  jnz     short loc_1800058B0
  ... truncated ...
```
