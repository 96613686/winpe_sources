# CCopyTree::InitializeFromPaths(HWND__ *,uint,ulong,ushort const *,ushort const *,CDPA<CPendingOperation,CTContainer_PolicyUnOwned<CPendingOperation>> *,bool)

- ea: `0x18019ec78`
- end: `0x18019f704`
- name: `?InitializeFromPaths@CCopyTree@@QEAAJPEAUHWND__@@IKPEBG1PEAV?$CDPA@VCPendingOperation@@V?$CTContainer_PolicyUnOwned@VCPendingOperation@@@@@@_N@Z`
- size: `2700`
- prototype: `__int64 __usercall@<rax>(CCopyTree *this@<rcx>, LPCWSTR lpsz, LPCWSTR, __int64, char)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180194b90`

## callees

- `0x180038f50`
- `0x18003e0a0`
- `0x180044320`
- `0x1800c72b0`
- `0x1800c8920`
- `0x1800d2c30`
- `0x1800d8a84`
- `0x1800f2ebc`
- `0x1801048a0`
- `0x180133f50`
- `0x180158c20`
- `0x1801591fc`
- `0x1801720d0`
- `0x180197ea0`
- `0x18019ce88`
- `0x18019decc`
- `0x18019e344`
- `0x18019ec78`
- `0x18019f70c`
- `0x18019f788`
- `0x18019f840`
- `0x18019f89c`
- `0x18019fac0`
- `0x1801feb8c`
- `0x1803b1f60`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x1805384a8`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18019f3d4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18019f3d4`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18019ed87`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18019f061`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18019f12f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18019ed87`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18019f061`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18019f12f`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18019f276`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18019f276`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18019f1a6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18019f1a6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18019eef1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18019eef1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18019efac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18019f21b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18019f258`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18019efac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18019f21b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18019f258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ed5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ef29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f0aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f390`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f5e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f5ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f68c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ed5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ef29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f0aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f390`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f5e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f5ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f68c`
- `SHCORE!__imp__CreateDirectoryHelper` at `0x18019f32a`
- `SHCORE!__imp__CreateDirectoryHelper` at `0x18019f32a`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x18019ef06`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x18019ef06`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18019f48e`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18019f48e`

## string_xrefs

- `0x18019ecf2`: `onecoreuap\shell\windows.storage\copy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCopyTree::InitializeFromPaths(
        CFileOperation **this,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int16 *lpsz,
        LPCWSTR a6,
        __int64 a7,
        char a8)
{
  unsigned int v8; // r15d
  unsigned __int16 *v11; // r14
  LPCWSTR v12; // r12
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // edi
  WCHAR *v16; // rbx
  __int64 v17; // rdx
  unsigned int v18; // eax
  BOOL IsDirectoryW; // eax
  int v21; // ecx
  int ProgressCancelled; // esi
  __int64 v23; // rbx
  WCHAR *v24; // rdi
  LPWSTR FileNameW; // rax
  __int64 v26; // rdx
  WCHAR *v27; // r8
  WCHAR v28; // cx
  WCHAR *v29; // rcx
  int v30; // r14d
  int IsWild; // eax
  CFileOperation *v32; // rcx
  WCHAR *v33; // rbx
  __int64 v34; // rdx
  HRESULT v35; // esi
  unsigned __int16 *v36; // r15
  const WCHAR *v37; // rbx
  size_t v38; // rdx
  const unsigned __int16 *v39; // rax
  __int64 v40; // rsi
  LPWSTR v41; // rax
  CFileOperation *v42; // rcx
  int v43; // eax
  int DirectoryHelper; // eax
  HRESULT v45; // esi
  int v46; // esi
  WCHAR *i; // rax
  unsigned int v48; // r14d
  CPendingOperation *v49; // rax
  CPendingOperation *v50; // r14
  CPendingOperation *v51; // r14
  void *v52; // rcx
  struct IShellItem *v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rax
  void *v56; // rcx
  struct IShellItem *v57; // rcx
  int v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+40h] [rbp-C0h]
  PWSTR pszPath; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v61; // [rsp+68h] [rbp-98h]
  PWSTR v62; // [rsp+70h] [rbp-90h] BYREF
  int v63; // [rsp+78h] [rbp-88h]
  unsigned int v64; // [rsp+7Ch] [rbp-84h]
  unsigned __int16 *v65; // [rsp+80h] [rbp-80h]
  int v66; // [rsp+88h] [rbp-78h]
  char v67[8]; // [rsp+90h] [rbp-70h] BYREF
  char v68[8]; // [rsp+98h] [rbp-68h] BYREF
  char v69[8]; // [rsp+A0h] [rbp-60h] BYREF
  PWSTR v70; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  struct IShellItem *v72; // [rsp+B8h] [rbp-48h] BYREF
  void *ppv; // [rsp+C0h] [rbp-40h] BYREF
  LPCITEMIDLIST v74; // [rsp+C8h] [rbp-38h]
  LPCITEMIDLIST pidl; // [rsp+D0h] [rbp-30h]
  WCHAR sz[256]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v77[256]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v8 = a4;
  v64 = a4;
  v61 = a3;
  v11 = lpsz;
  v65 = lpsz;
  v12 = a6;
  v58 = a4;
  LOBYTE(a4) = a8;
  v13 = CCopyTree::PromptDangerousOperation(this, a2, a7, a4);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2996,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\copy.cpp",
      (const char *)(unsigned int)v13,
      v58);
    return v14;
  }
  v63 = 0;
  v15 = CountFiles(lpsz);
  if ( a3 != 3 )
  {
    pszPath = 0;
    if ( a6 )
    {
      if ( *a6 )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &pv,
          a6,
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &pszPath,
          &pv);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
        v16 = pszPath;
        if ( !pszPath )
          goto LABEL_14;
      }
      else
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &pv,
          L".",
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &pszPath,
          &pv);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
        v16 = pszPath;
        if ( !pszPath )
          goto LABEL_14;
      }
    }
    else
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &pv,
        lpsz,
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &pszPath,
        &pv);
      if ( pv )
        CoTaskMemFree(pv);
      v16 = pszPath;
      if ( !pszPath )
        goto LABEL_14;
      v17 = -1;
      do
        ++v17;
      while ( pszPath[v17] );
      PathCchRemoveFileSpec(pszPath, v17 + 1);
    }
    if ( !(unsigned int)PathIsInvalidW(v16) )
    {
      if ( a3 == 4 )
      {
        if ( v15 != 1 && !(unsigned int)PathIsWild(v16) )
        {
          v18 = CFileOperation::PromptUserOrQueue(
                  this[2],
                  0,
                  0,
                  4u,
                  0,
                  0,
                  (const struct CONFIRM_CONSTANTS *)&off_1806F4220,
                  -2144927739,
                  0,
                  0,
                  0);
          goto LABEL_15;
        }
      }
      else if ( (v8 & 1) == 0 || !a6 || (unsigned int)CountFiles(a6) != v15 )
      {
        if ( v15 == 1 && !PathIsRootW(v16) )
        {
          IsDirectoryW = PathIsDirectoryW(v16);
          v21 = v63;
          if ( !IsDirectoryW )
            v21 = 1;
          v63 = v21;
        }
        goto LABEL_32;
      }
      v63 = 1;
LABEL_32:
      if ( v16 )
        CoTaskMemFree(v16);
      goto LABEL_34;
    }
LABEL_14:
    v18 = CFileOperation::PromptUserOrQueue(
            this[2],
            0,
            0,
            v61,
            0,
            0,
            (const struct CONFIRM_CONSTANTS *)&off_180699408,
            -2144927716,
            0,
            0,
            0);
LABEL_15:
    v14 = v18;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
    return v14;
  }
  v8 &= ~1u;
  v64 = v8;
LABEL_34:
  *((_DWORD *)this[2] + 50) = v15;
  v66 = v8 & 0x2000;
  ppv = 0;
  v72 = 0;
  ProgressCancelled = 0;
  while ( 1 )
  {
    if ( !*v11 )
      goto LABEL_144;
    ProgressCancelled = CFileOperation::QueryProgressCancelled(this[2]);
    if ( ProgressCancelled < 0 )
      goto LABEL_144;
    if ( (unsigned int)PathIsInvalidW(v11) )
    {
      ProgressCancelled = -2144927717;
      goto LABEL_144;
    }
    pszPath = 0;
    if ( (int)wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
                v11,
                &pszPath) < 0 )
      goto LABEL_141;
    v23 = 2147483646;
    v24 = pszPath;
    FileNameW = PathFindFileNameW(pszPath);
    v26 = 255;
    v27 = sz;
    do
    {
      if ( !v23 )
        break;
      v28 = *FileNameW;
      if ( !*FileNameW )
        break;
      ++FileNameW;
      *v27++ = v28;
      --v23;
      --v26;
    }
    while ( v26 );
    v29 = v27 - 1;
    if ( v26 )
      v29 = v27;
    *v29 = 0;
    if ( !v26 )
    {
LABEL_141:
      ProgressCancelled = -2144927717;
      goto LABEL_142;
    }
    v30 = 3;
    if ( (v8 & 0x80u) != 0 )
    {
      IsWild = PathIsWild(sz);
      v32 = this[2];
      if ( IsWild )
      {
        CFileOperation::SetOperationFlagsWithoutValidation(v32, v8);
        v30 = 1;
      }
      else
      {
        CFileOperation::SetOperationFlagsWithoutValidation(v32, v8 & 0xFFFFFF7F);
      }
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v62,
      v24,
      -1);
    v33 = v62;
    if ( !v62 )
    {
      ProgressCancelled = -2147024882;
      goto LABEL_140;
    }
    v34 = -1;
    do
      ++v34;
    while ( v62[v34] );
    PathCchRemoveFileSpec(v62, v34 + 1);
    pidl = 0;
    if ( (int)ILCreateFromPathEx(v33, 0) < 0 )
    {
      ProgressCancelled = -2144927717;
      goto LABEL_140;
    }
    v35 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    CoTaskMemFree((LPVOID)pidl);
    if ( v35 < 0 )
      break;
    ProgressCancelled = 0;
    if ( CCopyTree::DiskCheck((CCopyTree *)this, v33) < 0 )
    {
      ProgressCancelled = -2147023673;
LABEL_140:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v62);
LABEL_142:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
      goto LABEL_144;
    }
    v36 = 0;
    if ( v61 != 3 )
    {
      v70 = 0;
      if ( v12 )
      {
        if ( *v12 )
        {
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            v69,
            v12,
            -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v70,
            v69);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v69);
        }
        else
        {
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            v68,
            L".",
            -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v70,
            v68);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v68);
        }
        v37 = v70;
        if ( !v70 )
          goto LABEL_69;
      }
      else
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          v67,
          v65,
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v70,
          v67);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v67);
        v37 = v70;
        if ( !v70 )
          goto LABEL_69;
        v38 = -1;
        do
          ++v38;
        while ( v70[v38 + 1] );
        PathCchRemoveFileSpec(v70, v38);
      }
      if ( PathIsRelativeW(v37) || (unsigned int)PathContainsDotOrDotDot(v37) )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v62,
          0);
        if ( (int)wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
                    v37,
                    &v62) < 0 )
          goto LABEL_69;
        v33 = v62;
      }
      else
      {
        v70 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v62,
          v37);
        v33 = v62;
        if ( !v62 )
          goto LABEL_69;
      }
      if ( v63 )
      {
        v39 = PathFindFileNameW(v33);
        if ( (int)StringCchCopyW(v77, 0xFFu, v39) < 0 )
          goto LABEL_69;
        v36 = v77;
        v40 = -1;
        do
          ++v40;
        while ( v33[v40] );
        v41 = PathFindFileNameW(v33);
        if ( v41 > v33 )
        {
          *(v41 - 1) = 0;
          PathCchAddBackslash(v33, v40 + 1);
        }
        ProgressCancelled = 0;
      }
      v74 = 0;
      if ( (int)ILCreateFromPathEx(v33, 0) < 0 )
      {
        v42 = this[2];
        if ( (*((_DWORD *)v42 + 21) & 0x200) != 0 || (*((_DWORD *)v42 + 21) & 0x400) != 0 )
          goto LABEL_86;
        v43 = CFileOperation::PromptUserOrQueue(
                v42,
                0,
                0,
                v61,
                1,
                v33,
                (const struct CONFIRM_CONSTANTS *)&off_1806F4098,
                0,
                0,
                0,
                0);
        ProgressCancelled = v43;
        if ( v43 == 2555908 || v43 == 2555905 )
        {
          ProgressCancelled = 0;
LABEL_86:
          DirectoryHelper = _CreateDirectoryHelper(
                              *((_QWORD *)this[2] + 26),
                              v33,
                              0,
                              (*((_DWORD *)this[2] + 21) & 0x400) == 0);
          if ( DirectoryHelper > 0 )
          {
            ProgressCancelled = (unsigned __int16)DirectoryHelper | 0x80070000;
          }
          else if ( DirectoryHelper )
          {
            ProgressCancelled = DirectoryHelper;
          }
        }
        if ( ProgressCancelled < 0 )
          goto LABEL_70;
        if ( (int)ILCreateFromPathEx(v33, 0) < 0 )
        {
LABEL_69:
          ProgressCancelled = -2144927716;
          goto LABEL_70;
        }
      }
      v45 = SHCreateItemFromIDList(v74, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&v72);
      CoTaskMemFree((LPVOID)v74);
      if ( v45 < 0 )
      {
        ProgressCancelled = -2147024888;
LABEL_70:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v70);
        goto LABEL_140;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v70);
    }
    v46 = v66 != 0 ? 1 : 9;
    for ( i = sz; *i; i = CharNextW(i) )
    {
      if ( *i == 63 || *i == 42 )
      {
        pv = 0;
        v59 = v30;
        v48 = v61;
        ProgressCancelled = CCopyTree::EnumerateRootMatches(this, v61, ppv, v72, sz, 0, v36, v46, v59, &pv);
        if ( pv )
          CRecursiveFolderOperation::Release((CRecursiveFolderOperation *)pv);
        goto LABEL_112;
      }
    }
    ProgressCancelled = -2147024882;
    v49 = (CPendingOperation *)operator new(0x428u, (const struct std::nothrow_t *)&std::nothrow);
    v50 = v49;
    if ( v49 )
    {
      memset_0(v49, 0, 0x428u);
      v51 = CPendingOperation::CPendingOperation(v50);
      if ( v51 )
      {
        v70 = 0;
        ProgressCancelled = CreateBindCtx(0, (LPBC *)&v70);
        if ( ProgressCancelled >= 0 )
        {
          ProgressCancelled = SHAddSkipBindCtx((struct IBindCtx *)v70, 0);
          if ( ProgressCancelled >= 0 )
          {
            pv = 0;
            ProgressCancelled = SHCreateItemFromParsingName(
                                  v24,
                                  (IBindCtx *)v70,
                                  &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                  &pv);
            if ( ProgressCancelled >= 0 )
            {
              ProgressCancelled = CPendingOperation::InitPendingOperation(
                                    v51,
                                    v61,
                                    (struct IShellItem *)pv,
                                    v72,
                                    v36,
                                    0);
              if ( ProgressCancelled >= 0 )
                ProgressCancelled = (*(__int64 (__fastcall **)(CPendingOperation *, CFileOperation *, _QWORD))(*(_QWORD *)v51 + 8LL))(
                                      v51,
                                      this[2],
                                      0);
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
            }
            (*(void (__fastcall **)(PWSTR))(*(_QWORD *)v70 + 16LL))(v70);
          }
        }
        (**(void (__fastcall ***)(CPendingOperation *, __int64))v51)(v51, 1);
      }
    }
    v48 = v61;
LABEL_112:
    v52 = ppv;
    ppv = 0;
    if ( v52 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v52 + 16LL))(v52);
    v53 = v72;
    v72 = 0;
    if ( v53 )
      ((void (__fastcall *)(struct IShellItem *))v53->lpVtbl->Release)(v53);
    if ( ProgressCancelled < 0 )
    {
      if ( !v33 )
        goto LABEL_136;
      goto LABEL_135;
    }
    if ( ProgressCancelled == 1 )
    {
      ProgressCancelled = CFileOperation::PromptUserOrQueue(
                            this[2],
                            0,
                            0,
                            v48,
                            0,
                            v65,
                            (const struct CONFIRM_CONSTANTS *)&off_1806F4108,
                            -2147024894,
                            0,
                            0,
                            0);
      goto LABEL_140;
    }
    v54 = -1;
    do
      ++v54;
    while ( v65[v54] );
    v11 = &v65[v54 + 1];
    v65 = v11;
    v8 = v64;
    if ( (v64 & 1) != 0 && v12 )
    {
      v55 = -1;
      do
        ++v55;
      while ( v12[v55] );
      v12 += v55 + 1;
    }
    if ( v33 )
      CoTaskMemFree(v33);
    if ( v24 )
      CoTaskMemFree(v24);
  }
  ProgressCancelled = -2147024888;
LABEL_135:
  CoTaskMemFree(v33);
LABEL_136:
  if ( v24 )
    CoTaskMemFree(v24);
LABEL_144:
  v56 = ppv;
  ppv = 0;
  if ( v56 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v56 + 16LL))(v56);
  v57 = v72;
  v72 = 0;
  if ( v57 )
    ((void (__fastcall *)(struct IShellItem *))v57->lpVtbl->Release)(v57);
  return (unsigned int)ProgressCancelled;
}

```

## disassembly

```asm
0x18019ec78  push    rbp
0x18019ec7a  push    rbx
0x18019ec7b  push    rsi
0x18019ec7c  push    rdi
0x18019ec7d  push    r12
0x18019ec7f  push    r13
0x18019ec81  push    r14
0x18019ec83  push    r15
0x18019ec85  lea     rbp, [rsp-3F8h]
0x18019ec8d  sub     rsp, 4F8h
0x18019ec94  mov     rax, cs:__security_cookie
0x18019ec9b  xor     rax, rsp
0x18019ec9e  mov     [rbp+430h+var_50], rax
0x18019eca5  mov     r15d, r9d
0x18019eca8  mov     [rsp+530h+var_4B4], r9d
0x18019ecad  mov     esi, r8d
0x18019ecb0  mov     [rsp+530h+var_4C8], r8d
0x18019ecb5  mov     r13, rcx
0x18019ecb8  mov     r14, [rbp+430h+lpsz]
0x18019ecbf  mov     [rbp+430h+var_4B0], r14
0x18019ecc3  mov     r12, [rbp+430h+arg_28]
0x18019ecca  mov     r8, [rbp+430h+arg_30]
0x18019ecd1  mov     dword ptr [rsp+530h+var_510], r9d; int
0x18019ecd6  mov     r9b, [rbp+430h+arg_38]
0x18019ecdd  call    ?PromptDangerousOperation@CCopyTree@@AEAAJPEAUHWND__@@PEBV?$CDPA@VCPendingOperation@@V?$CTContainer_PolicyUnOwned@VCPendingOperation@@@@@@_NK@Z; CCopyTree::PromptDangerousOperation(HWND__ *,CDPA<CPendingOperation,CTContainer_PolicyUnOwned<CPendingOperation>> const *,bool,ulong)
0x18019ece2  mov     ebx, eax
0x18019ece4  test    eax, eax
0x18019ece6  jns     short loc_18019ED08
0x18019ece8  mov     rcx, [rbp+438h]; this
0x18019ecef  mov     r9d, eax; char *
0x18019ecf2  lea     r8, aOnecoreuapShel_88; "onecoreuap\\shell\\windows.storage\\cop"...
0x18019ecf9  mov     edx, 2996h; void *
0x18019ecfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019ed03  jmp     loc_18019EE26
0x18019ed08  xor     ebx, ebx
0x18019ed0a  mov     [rsp+530h+var_4B8], ebx
0x18019ed0e  mov     rcx, r14; lpsz
0x18019ed11  call    CountFiles
0x18019ed16  mov     edi, eax
0x18019ed18  or      r8, 0FFFFFFFFFFFFFFFFh
0x18019ed1c  cmp     esi, 3
0x18019ed1f  jnz     short loc_18019ED2F
0x18019ed21  and     r15d, 0FFFFFFFEh
0x18019ed25  mov     [rsp+530h+var_4B4], r15d
0x18019ed2a  jmp     loc_18019EF35
0x18019ed2f  mov     [rsp+530h+pszPath], rbx
0x18019ed34  lea     rcx, [rbp+430h+pv]
0x18019ed38  test    r12, r12
0x18019ed3b  jnz     short loc_18019ED98
0x18019ed3d  mov     rdx, r14
0x18019ed40  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18019ed45  lea     rdx, [rbp+430h+pv]
0x18019ed49  lea     rcx, [rsp+530h+pszPath]
0x18019ed4e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18019ed53  mov     rcx, [rbp+430h+pv]; pv
0x18019ed57  test    rcx, rcx
0x18019ed5a  jz      short loc_18019ED68
0x18019ed5c  call    cs:__imp_CoTaskMemFree
0x18019ed63  nop     dword ptr [rax+rax+00h]
0x18019ed68  mov     rbx, [rsp+530h+pszPath]
0x18019ed6d  xor     ecx, ecx
0x18019ed6f  test    rbx, rbx
0x18019ed72  jz      short loc_18019EDDB
0x18019ed74  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18019ed78  inc     rdx
0x18019ed7b  cmp     [rbx+rdx*2], cx
0x18019ed7f  jnz     short loc_18019ED78
0x18019ed81  inc     rdx; cchPath
0x18019ed84  mov     rcx, rbx; pszPath
0x18019ed87  call    cs:__imp_PathCchRemoveFileSpec
0x18019ed8e  nop     dword ptr [rax+rax+00h]
0x18019ed93  jmp     loc_18019EE7B
0x18019ed98  cmp     [r12], bx
0x18019ed9d  jnz     loc_18019EE4C
0x18019eda3  lea     rdx, pszExt; "."
0x18019edaa  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18019edaf  lea     rdx, [rbp+430h+pv]
0x18019edb3  lea     rcx, [rsp+530h+pszPath]
0x18019edb8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18019edbd  lea     rcx, [rbp+430h+pv]; void *
0x18019edc1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18019edc6  mov     rbx, [rsp+530h+pszPath]
0x18019edcb  xor     ecx, ecx
0x18019edcd  test    rbx, rbx
0x18019edd0  setnz   al
0x18019edd3  test    al, al
0x18019edd5  jnz     loc_18019EE7B
0x18019eddb  mov     [rsp+530h+var_4E0], rcx; struct IAutoRetry *
0x18019ede0  mov     [rsp+530h+var_4E8], rcx; struct CCopyWorkItem *
0x18019ede5  mov     [rsp+530h+var_4F0], rcx; struct CRecursiveFolderOperation *
0x18019edea  mov     r9d, [rsp+530h+var_4C8]; unsigned int
0x18019edef  lea     rax, off_180699408
0x18019edf6  mov     [rsp+530h+var_4F8], 8027001Ch; int
0x18019edfe  mov     [rsp+530h+var_500], rax; struct CONFIRM_CONSTANTS *
0x18019ee03  mov     [rsp+530h+var_508], rcx; unsigned __int16 *
0x18019ee08  mov     dword ptr [rsp+530h+var_510], ecx; int
0x18019ee0c  xor     r8d, r8d; struct IShellItem *
0x18019ee0f  xor     edx, edx; struct IShellItem *
0x18019ee11  mov     rcx, [r13+10h]; this
0x18019ee15  call    ?PromptUserOrQueue@CFileOperation@@QEAAJPEAUIShellItem@@0IHPEBGPEBUCONFIRM_CONSTANTS@@JPEAVCRecursiveFolderOperation@@PEAVCCopyWorkItem@@PEAUIAutoRetry@@@Z; CFileOperation::PromptUserOrQueue(IShellItem *,IShellItem *,uint,int,ushort const *,CONFIRM_CONSTANTS const *,long,CRecursiveFolderOperation *,CCopyWorkItem *,IAutoRetry *)
0x18019ee1a  mov     ebx, eax
0x18019ee1c  lea     rcx, [rsp+530h+pszPath]; void *
0x18019ee21  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18019ee26  mov     eax, ebx
0x18019ee28  mov     rcx, [rbp+430h+var_50]
0x18019ee2f  xor     rcx, rsp; StackCookie
0x18019ee32  call    __security_check_cookie
0x18019ee37  add     rsp, 4F8h
0x18019ee3e  pop     r15
0x18019ee40  pop     r14
0x18019ee42  pop     r13
0x18019ee44  pop     r12
0x18019ee46  pop     rdi
0x18019ee47  pop     rsi
0x18019ee48  pop     rbx
0x18019ee49  pop     rbp
0x18019ee4a  retn
0x18019ee4c  mov     rdx, r12
0x18019ee4f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18019ee54  lea     rdx, [rbp+430h+pv]
0x18019ee58  lea     rcx, [rsp+530h+pszPath]
0x18019ee5d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18019ee62  lea     rcx, [rbp+430h+pv]; void *
0x18019ee66  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18019ee6b  mov     rbx, [rsp+530h+pszPath]
0x18019ee70  xor     ecx, ecx
0x18019ee72  test    rbx, rbx
0x18019ee75  jz      loc_18019EDDB
0x18019ee7b  mov     rcx, rbx; unsigned __int16 *
0x18019ee7e  call    PathIsInvalidW
0x18019ee83  xor     ecx, ecx
0x18019ee85  test    eax, eax
0x18019ee87  jnz     loc_18019EDDB
0x18019ee8d  cmp     esi, 4
0x18019ee90  lea     esi, [rcx+1]
0x18019ee93  jnz     short loc_18019EED4
0x18019ee95  cmp     edi, esi
0x18019ee97  jz      short loc_18019EECE
0x18019ee99  mov     rcx, rbx; lpsz
0x18019ee9c  call    PathIsWild
0x18019eea1  xor     ecx, ecx
0x18019eea3  test    eax, eax
0x18019eea5  jnz     short loc_18019EECE
0x18019eea7  mov     [rsp+530h+var_4E0], rcx
0x18019eeac  mov     [rsp+530h+var_4E8], rcx
0x18019eeb1  mov     [rsp+530h+var_4F0], rcx
0x18019eeb6  mov     [rsp+530h+var_4F8], 80270005h
0x18019eebe  lea     rax, off_1806F4220
0x18019eec5  lea     r9d, [rsi+3]
0x18019eec9  jmp     loc_18019EDFE
0x18019eece  mov     [rsp+530h+var_4B8], esi
0x18019eed2  jmp     short loc_18019EF1F
0x18019eed4  test    sil, r15b
0x18019eed7  jz      short loc_18019EEEA
0x18019eed9  test    r12, r12
0x18019eedc  jz      short loc_18019EEEA
0x18019eede  mov     rcx, r12; lpsz
0x18019eee1  call    CountFiles
0x18019eee6  cmp     eax, edi
0x18019eee8  jz      short loc_18019EECE
0x18019eeea  cmp     edi, esi
0x18019eeec  jnz     short loc_18019EF1F
0x18019eeee  mov     rcx, rbx; pszPath
0x18019eef1  call    cs:__imp_PathIsRootW
0x18019eef8  nop     dword ptr [rax+rax+00h]
0x18019eefd  xor     ecx, ecx
0x18019eeff  test    eax, eax
0x18019ef01  jnz     short loc_18019EF21
0x18019ef03  mov     rcx, rbx; pszPath
0x18019ef06  call    cs:__imp_PathIsDirectoryW
0x18019ef0d  nop     dword ptr [rax+rax+00h]
0x18019ef12  mov     ecx, [rsp+530h+var_4B8]
0x18019ef16  test    eax, eax
0x18019ef18  cmovz   ecx, esi
0x18019ef1b  mov     [rsp+530h+var_4B8], ecx
0x18019ef1f  xor     ecx, ecx
0x18019ef21  test    rbx, rbx
0x18019ef24  jz      short loc_18019EF37
0x18019ef26  mov     rcx, rbx; pv
0x18019ef29  call    cs:__imp_CoTaskMemFree
0x18019ef30  nop     dword ptr [rax+rax+00h]
0x18019ef35  xor     ecx, ecx
0x18019ef37  mov     rax, [r13+10h]
0x18019ef3b  mov     [rax+0C8h], edi
0x18019ef41  mov     eax, r15d
0x18019ef44  and     eax, 2000h
0x18019ef49  mov     [rbp+430h+var_4A8], eax
0x18019ef4c  mov     [rbp+430h+ppv], rcx
0x18019ef50  mov     [rbp+430h+var_478], rcx
0x18019ef54  mov     esi, ecx
0x18019ef56  cmp     [r14], cx
0x18019ef5a  jz      loc_18019F6C8
0x18019ef60  mov     rcx, [r13+10h]; this
0x18019ef64  call    ?QueryProgressCancelled@CFileOperation@@QEAAJXZ; CFileOperation::QueryProgressCancelled(void)
0x18019ef69  mov     esi, eax
0x18019ef6b  test    eax, eax
0x18019ef6d  js      loc_18019F6C8
0x18019ef73  mov     rcx, r14; unsigned __int16 *
0x18019ef76  call    PathIsInvalidW
0x18019ef7b  xor     esi, esi
0x18019ef7d  test    eax, eax
0x18019ef7f  jnz     loc_18019F6C3
0x18019ef85  mov     [rsp+530h+pszPath], rsi
0x18019ef8a  lea     rdx, [rsp+530h+pszPath]
0x18019ef8f  mov     rcx, r14
0x18019ef92  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x18019ef97  test    eax, eax
0x18019ef99  js      loc_18019F6B2
0x18019ef9f  mov     ebx, 7FFFFFFEh
0x18019efa4  mov     rdi, [rsp+530h+pszPath]
0x18019efa9  mov     rcx, rdi; pszPath
0x18019efac  call    cs:__imp_PathFindFileNameW
0x18019efb3  nop     dword ptr [rax+rax+00h]
0x18019efb8  mov     edx, 0FFh
0x18019efbd  lea     r8, [rbp+430h+sz]
0x18019efc1  test    rbx, rbx
0x18019efc4  jz      short loc_18019EFE3
0x18019efc6  movzx   ecx, word ptr [rax]
0x18019efc9  test    cx, cx
0x18019efcc  jz      short loc_18019EFE3
0x18019efce  add     rax, 2
0x18019efd2  mov     [r8], cx
0x18019efd6  add     r8, 2
0x18019efda  dec     rbx
0x18019efdd  sub     rdx, 1
0x18019efe1  jnz     short loc_18019EFC1
0x18019efe3  lea     rcx, [r8-2]
0x18019efe7  test    rdx, rdx
0x18019efea  cmovnz  rcx, r8
0x18019efee  mov     [rcx], si
0x18019eff1  jz      loc_18019F6B2
0x18019eff7  mov     r14d, 3
0x18019effd  test    r15b, r15b
0x18019f000  jns     short loc_18019F02C
0x18019f002  lea     rcx, [rbp+430h+sz]; lpsz
0x18019f006  call    PathIsWild
0x18019f00b  mov     rcx, [r13+10h]; this
0x18019f00f  mov     edx, r15d; unsigned int
0x18019f012  test    eax, eax
0x18019f014  jz      short loc_18019F023
0x18019f016  call    ?SetOperationFlagsWithoutValidation@CFileOperation@@QEAAJK@Z; CFileOperation::SetOperationFlagsWithoutValidation(ulong)
0x18019f01b  mov     r14d, 1
0x18019f021  jmp     short loc_18019F02C
0x18019f023  btr     edx, 7; unsigned int
0x18019f027  call    ?SetOperationFlagsWithoutValidation@CFileOperation@@QEAAJK@Z; CFileOperation::SetOperationFlagsWithoutValidation(ulong)
0x18019f02c  or      r15, 0FFFFFFFFFFFFFFFFh
0x18019f030  mov     r8, r15
0x18019f033  mov     rdx, rdi
0x18019f036  lea     rcx, [rsp+530h+var_4C0]
0x18019f03b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18019f040  nop
0x18019f041  mov     rbx, [rsp+530h+var_4C0]
0x18019f046  test    rbx, rbx
0x18019f049  jz      loc_18019F6A1
0x18019f04f  mov     rdx, r15
0x18019f052  inc     rdx
0x18019f055  cmp     [rbx+rdx*2], si
0x18019f059  jnz     short loc_18019F052
0x18019f05b  inc     rdx; cchPath
0x18019f05e  mov     rcx, rbx; pszPath
0x18019f061  call    cs:__imp_PathCchRemoveFileSpec
0x18019f068  nop     dword ptr [rax+rax+00h]
0x18019f06d  mov     [rbp+430h+pidl], rsi
0x18019f071  mov     [rsp+530h+var_510], rsi; SFGAOF *
0x18019f076  lea     r9, [rbp+430h+pidl]
0x18019f07a  xor     edx, edx
0x18019f07c  lea     r8d, [rdx+1]
0x18019f080  mov     rcx, rbx; pszName
0x18019f083  call    ILCreateFromPathEx
0x18019f088  test    eax, eax
0x18019f08a  js      loc_18019F69A
0x18019f090  lea     r8, [rbp+430h+ppv]; ppv
0x18019f094  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18019f09b  mov     rcx, [rbp+430h+pidl]; pidl
0x18019f09f  call    SHCreateItemFromIDList
0x18019f0a4  mov     esi, eax
0x18019f0a6  mov     rcx, [rbp+430h+pidl]; pv
0x18019f0aa  call    cs:__imp_CoTaskMemFree
0x18019f0b1  nop     dword ptr [rax+rax+00h]
0x18019f0b6  test    esi, esi
0x18019f0b8  js      loc_18019F66F
0x18019f0be  mov     rdx, rbx; unsigned __int16 *
0x18019f0c1  mov     rcx, r13; this
0x18019f0c4  call    ?DiskCheck@CCopyTree@@QEAAJPEBG@Z; CCopyTree::DiskCheck(ushort const *)
0x18019f0c9  xor     esi, esi
0x18019f0cb  test    eax, eax
0x18019f0cd  js      loc_18019F668
0x18019f0d3  mov     r15d, esi
0x18019f0d6  cmp     [rsp+530h+var_4C8], 3
0x18019f0db  jz      loc_18019F3AD
0x18019f0e1  mov     [rbp+430h+var_488], rsi
0x18019f0e5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18019f0e9  test    r12, r12
0x18019f0ec  jnz     short loc_18019F13D
0x18019f0ee  mov     rdx, [rbp+430h+var_4B0]
0x18019f0f2  lea     rcx, [rbp+430h+var_4A0]
0x18019f0f6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18019f0fb  lea     rdx, [rbp+430h+var_4A0]
0x18019f0ff  lea     rcx, [rbp+430h+var_488]
0x18019f103  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
  ... truncated ...
```
