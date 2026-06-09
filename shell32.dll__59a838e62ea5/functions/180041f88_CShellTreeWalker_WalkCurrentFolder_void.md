# CShellTreeWalker::_WalkCurrentFolder(void)

- ea: `0x180041f88`
- end: `0x180042681`
- name: `?_WalkCurrentFolder@CShellTreeWalker@@AEAAJXZ`
- size: `1785`
- prototype: `__int64 __fastcall(CShellTreeWalker *__hidden this)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180041ae8`
- `0x180041f88`
- `0x18039dd60`

## callees

- `0x1800181e0`
- `0x1800295b0`
- `0x18003eb50`
- `0x180041ae8`
- `0x180041f88`
- `0x180042688`
- `0x1800426e8`
- `0x180043380`
- `0x180043c88`
- `0x180054320`
- `0x180076fdc`
- `0x180080470`
- `0x1800ac89c`
- `0x1800c3454`
- `0x1800fae74`
- `0x180233280`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004257e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004257e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180042121`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180042121`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180042112`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180042112`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800420a5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800420a5`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180042545`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180042545`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x1800420fe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x1800420fe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800420b1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180042349`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18004245b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800420b1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180042349`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18004245b`
- `ntdll!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1800425ec`
- `ntdll!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1800425ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004206a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800424d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004206a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800424d4`
- `Windows.Storage!SHGetCompressedFileSizeW` at `0x180042673`
- `Windows.Storage!SHGetCompressedFileSizeW` at `0x180042673`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CShellTreeWalker::_WalkCurrentFolder(CShellTreeWalker *this)
{
  unsigned int v2; // ebx
  const WCHAR *v3; // rdx
  LPVOID *v4; // rsi
  __int64 v5; // r14
  int v6; // eax
  LPVOID v7; // r14
  union _ULARGE_INTEGER v8; // rdx
  int v9; // r14d
  HANDLE FirstFile; // r12
  int v11; // r14d
  const WCHAR *v12; // rdx
  struct _DSA *v13; // r12
  WCHAR *v14; // r15
  int v15; // r13d
  WCHAR *ItemPtr; // rax
  LPVOID v17; // r14
  int v18; // eax
  LPVOID v19; // rbx
  struct _DSA *v20; // r14
  union _ULARGE_INTEGER v21; // rdx
  int v22; // r14d
  int v23; // ecx
  unsigned int v24; // r14d
  int v25; // ecx
  __int64 v27; // rbx
  union _ULARGE_INTEGER v28; // r12
  LPVOID v29; // r14
  int v30; // eax
  PWSTR v31; // r14
  char v32; // r14
  union _ULARGE_INTEGER v33; // rdx
  int v34; // r14d
  unsigned __int64 v35; // r12
  __int64 v36; // rcx
  unsigned int v37; // r14d
  int lpSearchFilter; // [rsp+20h] [rbp-59h]
  int lpSearchFiltera; // [rsp+20h] [rbp-59h]
  LPVOID pv; // [rsp+30h] [rbp-49h] BYREF
  LPVOID v41; // [rsp+38h] [rbp-41h] BYREF
  char v42[8]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v43; // [rsp+48h] [rbp-31h]
  char v44[8]; // [rsp+50h] [rbp-29h] BYREF
  union _ULARGE_INTEGER v45; // [rsp+58h] [rbp-21h] BYREF
  PWSTR ppszPathOut; // [rsp+60h] [rbp-19h] BYREF
  int v47; // [rsp+68h] [rbp-11h] BYREF
  int v48; // [rsp+6Ch] [rbp-Dh]
  int v49; // [rsp+70h] [rbp-9h]
  int v50; // [rsp+74h] [rbp-5h]
  __int64 v51; // [rsp+78h] [rbp-1h]
  __int64 v52; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = 0;
  v3 = (const WCHAR *)*((_QWORD *)this + 8);
  if ( !v3 || *((_DWORD *)this + 5) != *((_DWORD *)this + 4) )
    v3 = L"*.*";
  v4 = (LPVOID *)((char *)this + 56);
  v5 = *((_QWORD *)this + 7);
  pv = 0;
  v6 = PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,260>(
         v5,
         (__int64)v3,
         (__int64)&pv);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"shell\\shell32\\treewalk.cpp",
      (const char *)(unsigned int)v6,
      lpSearchFilter);
    v45.QuadPart = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &ppszPathOut,
      v5,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v45,
      &ppszPathOut);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&ppszPathOut);
    v8 = v45;
    if ( v45.QuadPart )
    {
      v9 = 0;
      v45.QuadPart = 0;
      ((void (__fastcall *)(_QWORD, _QWORD))wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset)(
        v4,
        (union _ULARGE_INTEGER)v8.QuadPart);
    }
    else
    {
      v9 = -2147024882;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v45);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v9 < 0 )
      return v2;
  }
  else
  {
    v7 = pv;
    if ( *v4 )
      wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(*v4);
    *v4 = v7;
  }
  pv = 0;
  FirstFile = FindFirstFileExW(
                (LPCWSTR)*v4,
                FindExInfoBasic,
                (char *)this + 80,
                (FINDEX_SEARCH_OPS)((*((_DWORD *)this + 3) >> 2) & 1),
                0,
                2u);
  PathRemoveFileSpecW((LPWSTR)*v4);
  if ( FirstFile == (HANDLE)-1LL )
    return v2;
  while ( 1 )
  {
    if ( *((_WORD *)this + 62) == 46
      && (!*((_WORD *)this + 63) || *((_WORD *)this + 63) == 46 && !*((_WORD *)this + 64)) )
    {
      goto LABEL_20;
    }
    if ( (*((_BYTE *)this + 80) & 0x10) != 0 )
    {
      v11 = 1;
    }
    else
    {
      if ( (*((_BYTE *)this + 12) & 4) != 0 )
        goto LABEL_20;
      v11 = 0;
      v12 = (const WCHAR *)*((_QWORD *)this + 8);
      if ( v12 )
      {
        if ( *((_DWORD *)this + 5) < *((_DWORD *)this + 4) && !PathMatchSpecW((LPCWSTR)this + 62, v12) )
          goto LABEL_20;
      }
    }
    if ( v11 != (*((_DWORD *)this + 3) & 1) )
      break;
    v2 = CShellTreeWalker::_ProcessAndRecurse(this, (struct _WIN32_FIND_DATAW *)((char *)this + 80));
    if ( v2 )
      goto LABEL_21;
LABEL_20:
    if ( !FindNextFileW(FirstFile, (LPWIN32_FIND_DATAW)((char *)this + 80)) )
      goto LABEL_21;
  }
  v20 = (struct _DSA *)pv;
  if ( pv || (v20 = DSA_Create(592, 32), (pv = v20) != 0) )
  {
    DSA_InsertItem(v20, 0x7FFFFFFF, (char *)this + 80);
    goto LABEL_20;
  }
  v2 = -2147024882;
LABEL_21:
  FindClose(FirstFile);
  v13 = (struct _DSA *)pv;
  LODWORD(v14) = 0;
  if ( pv )
  {
    if ( !v2 )
    {
      v15 = 0;
      LODWORD(v41) = 0;
      if ( *(int *)pv > 0 )
      {
        while ( 1 )
        {
          ItemPtr = (WCHAR *)DSA_GetItemPtr(v13, v15);
          v14 = ItemPtr;
          if ( (*(_BYTE *)ItemPtr & 0x10) == 0 )
          {
            ++*((_DWORD *)this + 6);
            LODWORD(v43) = *((_DWORD *)ItemPtr + 8);
            HIDWORD(v43) = *((_DWORD *)ItemPtr + 7);
            v27 = v43;
            *((_QWORD *)this + 5) += v43;
            v28.QuadPart = 0;
            v29 = *v4;
            ppszPathOut = 0;
            v30 = PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,260>(
                    (__int64)v29,
                    (__int64)(ItemPtr + 22),
                    (__int64)&ppszPathOut);
            if ( v30 >= 0 )
            {
              v31 = ppszPathOut;
              if ( *v4 )
                wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(*v4);
              *v4 = v31;
              goto LABEL_68;
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8B,
              (unsigned int)"shell\\shell32\\treewalk.cpp",
              (const char *)(unsigned int)v30,
              lpSearchFiltera);
            v45.QuadPart = 0;
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              v44,
              v29,
              -1);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              &v45,
              v44);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v44);
            v33 = v45;
            if ( v45.QuadPart )
            {
              v34 = 0;
              v45.QuadPart = 0;
              ((void (__fastcall *)(_QWORD, _QWORD))wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset)(
                v4,
                (union _ULARGE_INTEGER)v33.QuadPart);
            }
            else
            {
              v34 = -2147024882;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v45);
            if ( ppszPathOut )
              CoTaskMemFree(ppszPathOut);
            if ( v34 < 0 )
            {
LABEL_77:
              v35 = *((unsigned int *)this + 8) + v27 - 1;
              v28.QuadPart = v35 - v35 % *((unsigned int *)this + 8);
              goto LABEL_78;
            }
LABEL_68:
            v45.QuadPart = 0;
            if ( GetFileAllStreamAllocationSize((const unsigned __int16 *)*v4, *((_DWORD *)this + 8), &v45) )
            {
LABEL_69:
              v32 = 0;
              v28 = v45;
            }
            else
            {
              v32 = 1;
              if ( (*(_DWORD *)v14 & 0xA00) != 0 )
              {
                v45.LowPart = SHGetCompressedFileSizeW(*v4, (char *)&v45.QuadPart + 4);
                goto LABEL_69;
              }
            }
            PathRemoveFileSpecW((LPWSTR)*v4);
            if ( v32 )
              goto LABEL_77;
LABEL_78:
            *((_QWORD *)this + 6) += v28.QuadPart;
            v36 = *((_QWORD *)this + 6);
            v37 = 0;
            v47 = *((_DWORD *)this + 6);
            v48 = *((_DWORD *)this + 7);
            v49 = *((_DWORD *)this + 5);
            v51 = *((_QWORD *)this + 5);
            v52 = v36;
            v50 = *((_DWORD *)this + 8);
            if ( v14 )
            {
              ppszPathOut = 0;
              if ( PathAllocCombine(*((PCWSTR *)this + 7), v14 + 22, 1u, &ppszPathOut) >= 0 )
              {
                lpSearchFiltera = v28.LowPart;
                v37 = (*(__int64 (__fastcall **)(_QWORD, PWSTR, int *, WCHAR *))(**((_QWORD **)this + 9) + 24LL))(
                        *((_QWORD *)this + 9),
                        ppszPathOut,
                        &v47,
                        v14);
              }
              LODWORD(v14) = 0;
              if ( ppszPathOut )
                LocalFree(ppszPathOut);
            }
            v2 = (unsigned int)v14;
            if ( v37 != -2147467263 )
              v2 = v37;
            v13 = (struct _DSA *)pv;
            v15 = (int)v41;
            goto LABEL_54;
          }
          v2 = 0;
          ++*((_DWORD *)this + 5);
          if ( (*(_DWORD *)ItemPtr & 0x400) == 0
            || (*((_BYTE *)this + 12) & 0x20) != 0
            || (unsigned __int8)RtlIsNonEmptyDirectoryReparsePointAllowed(*((unsigned int *)ItemPtr + 9)) )
          {
            v17 = *v4;
            v41 = 0;
            v18 = PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,260>(
                    (__int64)v17,
                    (__int64)(v14 + 22),
                    (__int64)&v41);
            if ( v18 >= 0 )
            {
              v19 = v41;
              if ( *v4 )
                wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(*v4);
              *v4 = v19;
LABEL_43:
              v23 = ++*((_DWORD *)this + 7);
              v24 = 0;
              v47 = *((_DWORD *)this + 6);
              v48 = v23;
              v49 = *((_DWORD *)this + 5);
              v51 = *((_QWORD *)this + 5);
              v52 = *((_QWORD *)this + 6);
              v50 = *((_DWORD *)this + 8);
              *((_DWORD *)this + 8) = PathGetClusterSize((unsigned __int16 *)*v4);
              if ( (*((_BYTE *)this + 12) & 8) != 0 && (*((_DWORD *)this + 5) || (*((_BYTE *)this + 12) & 0x40) == 0) )
                v24 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, int *, WCHAR *))(**((_QWORD **)this + 9) + 32LL))(
                        *((_QWORD *)this + 9),
                        *v4,
                        &v47,
                        v14);
              LODWORD(v14) = 0;
              v2 = 0;
              if ( v24 != -2147467263 )
                v2 = v24;
              if ( v2 || *((_DWORD *)this + 5) > *((_DWORD *)this + 4) )
              {
                if ( v2 == 1 )
                  v2 = 0;
              }
              else
              {
                v2 = CShellTreeWalker::_WalkCurrentFolder(this);
              }
              v47 = *((_DWORD *)this + 6);
              v48 = *((_DWORD *)this + 7);
              v25 = *((_DWORD *)this + 5);
              v49 = v25;
              v51 = *((_QWORD *)this + 5);
              v52 = *((_QWORD *)this + 6);
              v50 = *((_DWORD *)this + 8);
              if ( (*((_BYTE *)this + 12) & 0x10) != 0 && (v25 || (*((_BYTE *)this + 12) & 0x40) == 0) )
                (*(void (__fastcall **)(_QWORD, LPVOID, int *))(**((_QWORD **)this + 9) + 40LL))(
                  *((_QWORD *)this + 9),
                  *v4,
                  &v47);
              PathRemoveFileSpecW((LPWSTR)*v4);
              *((_DWORD *)this + 8) = PathGetClusterSize((unsigned __int16 *)*v4);
              goto LABEL_53;
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8B,
              (unsigned int)"shell\\shell32\\treewalk.cpp",
              (const char *)(unsigned int)v18,
              lpSearchFiltera);
            v45.QuadPart = 0;
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              v42,
              v17,
              -1);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              &v45,
              v42);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v42);
            v21 = v45;
            if ( v45.QuadPart )
            {
              v22 = 0;
              v45.QuadPart = 0;
              ((void (__fastcall *)(_QWORD, _QWORD))wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset)(
                v4,
                (union _ULARGE_INTEGER)v21.QuadPart);
            }
            else
            {
              v22 = -2147024882;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v45);
            if ( v41 )
              CoTaskMemFree(v41);
            if ( v22 >= 0 )
              goto LABEL_43;
          }
          LODWORD(v14) = 0;
LABEL_53:
          --*((_DWORD *)this + 5);
LABEL_54:
          if ( !v2 )
          {
            LODWORD(v41) = ++v15;
            if ( v15 < *(_DWORD *)v13 )
              continue;
          }
          break;
        }
      }
    }
    DSA_Destroy(v13);
  }
  if ( v2 == 1 )
    return (unsigned int)v14;
  return v2;
}

```

## disassembly

```asm
0x180041f88  push    rbp
0x180041f8a  push    rbx
0x180041f8b  push    rsi
0x180041f8c  push    rdi
0x180041f8d  push    r12
0x180041f8f  push    r13
0x180041f91  push    r14
0x180041f93  push    r15
0x180041f95  lea     rbp, [rsp-1Fh]
0x180041f9a  sub     rsp, 98h
0x180041fa1  mov     rax, cs:__security_cookie
0x180041fa8  xor     rax, rsp
0x180041fab  mov     [rbp+57h+var_48], rax
0x180041faf  mov     rdi, rcx
0x180041fb2  xor     r12d, r12d
0x180041fb5  mov     ebx, r12d
0x180041fb8  mov     rdx, [rcx+40h]
0x180041fbc  test    rdx, rdx
0x180041fbf  jz      short loc_180041FC9
0x180041fc1  mov     eax, [rcx+10h]
0x180041fc4  cmp     [rcx+14h], eax
0x180041fc7  jz      short loc_180041FD0
0x180041fc9  lea     rdx, c_szStarDotStar; "*.*"
0x180041fd0  lea     rsi, [rcx+38h]
0x180041fd4  mov     r14, [rsi]
0x180041fd7  mov     [rbp+57h+pv], r12
0x180041fdb  lea     r8, [rbp+57h+pv]
0x180041fdf  mov     rcx, r14
0x180041fe2  call    ??$Append@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAE@@PathAlloc@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,260>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180041fe7  mov     rcx, [rbp+5Fh]; this
0x180041feb  test    eax, eax
0x180041fed  js      short loc_180042007
0x180041fef  mov     r14, [rbp+57h+pv]
0x180041ff3  mov     rcx, [rsi]; pv
0x180041ff6  test    rcx, rcx
0x180041ff9  jnz     short loc_180042000
0x180041ffb  mov     [rsi], r14
0x180041ffe  jmp     short loc_180042079
0x180042000  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZPEAG@details@wil@@SAXPEAG@Z; wil::details::close_invoke_helper<1,void (*)(void *),&CoTaskMemFree(void *),ushort *>::close_reset(ushort *)
0x180042005  jmp     short loc_180041FFB
0x180042007  mov     r9d, eax; char *
0x18004200a  lea     r8, aShellShell32Tr; "shell\\shell32\\treewalk.cpp"
0x180042011  mov     edx, 8Bh; void *
0x180042016  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004201b  mov     qword ptr [rbp+57h+var_78], r12
0x18004201f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180042023  mov     rdx, r14
0x180042026  lea     rcx, [rbp+57h+ppszPathOut]
0x18004202a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004202f  lea     rdx, [rbp+57h+ppszPathOut]
0x180042033  lea     rcx, [rbp+57h+var_78]
0x180042037  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004203c  lea     rcx, [rbp+57h+ppszPathOut]; void *
0x180042040  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180042045  mov     rdx, qword ptr [rbp+57h+var_78]
0x180042049  test    rdx, rdx
0x18004204c  jnz     loc_1800425CB
0x180042052  mov     r14d, 8007000Eh
0x180042058  lea     rcx, [rbp+57h+var_78]; void *
0x18004205c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180042061  mov     rcx, [rbp+57h+pv]; pv
0x180042065  test    rcx, rcx
0x180042068  jz      short loc_180042070
0x18004206a  call    cs:__imp_CoTaskMemFree
0x180042070  test    r14d, r14d
0x180042073  js      loc_180042381
0x180042079  mov     [rbp+57h+pv], r12
0x18004207d  lea     r15, [rdi+50h]
0x180042081  mov     r9d, [rdi+0Ch]
0x180042085  shr     r9d, 2
0x180042089  and     r9d, 1; fSearchOp
0x18004208d  mov     [rsp+0D0h+dwAdditionalFlags], 2; dwAdditionalFlags
0x180042095  mov     [rsp+0D0h+lpSearchFilter], r12; int
0x18004209a  mov     r8, r15; lpFindFileData
0x18004209d  mov     edx, 1; fInfoLevelId
0x1800420a2  mov     rcx, [rsi]; lpFileName
0x1800420a5  call    cs:__imp_FindFirstFileExW
0x1800420ab  mov     r12, rax
0x1800420ae  mov     rcx, [rsi]; pszPath
0x1800420b1  call    cs:__imp_PathRemoveFileSpecW
0x1800420b7  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1800420bb  jz      loc_180042381
0x1800420c1  xor     ecx, ecx
0x1800420c3  cmp     word ptr [rdi+7Ch], 2Eh ; '.'
0x1800420c8  jz      loc_1800421E2
0x1800420ce  test    byte ptr [r15], 10h
0x1800420d2  jnz     loc_1800421AB
0x1800420d8  test    byte ptr [rdi+0Ch], 4
0x1800420dc  jnz     short loc_18004210C
0x1800420de  mov     r14d, ecx
0x1800420e1  mov     rdx, [rdi+40h]; pszSpec
0x1800420e5  test    rdx, rdx
0x1800420e8  jz      loc_1800421B1
0x1800420ee  mov     eax, [rdi+10h]
0x1800420f1  cmp     [rdi+14h], eax
0x1800420f4  jnb     loc_1800421B1
0x1800420fa  lea     rcx, [rdi+7Ch]; pszFile
0x1800420fe  call    cs:__imp_PathMatchSpecW
0x180042104  test    eax, eax
0x180042106  jnz     loc_1800421B1
0x18004210c  mov     rdx, r15; lpFindFileData
0x18004210f  mov     rcx, r12; hFindFile
0x180042112  call    cs:__imp_FindNextFileW
0x180042118  xor     ecx, ecx
0x18004211a  test    eax, eax
0x18004211c  jnz     short loc_1800420C3
0x18004211e  mov     rcx, r12; hFindFile
0x180042121  call    cs:__imp_FindClose
0x180042127  mov     r12, [rbp+57h+pv]
0x18004212b  xor     r15d, r15d
0x18004212e  test    r12, r12
0x180042131  jz      loc_18004237A
0x180042137  test    ebx, ebx
0x180042139  jnz     loc_180042372
0x18004213f  mov     r13d, r15d
0x180042142  mov     dword ptr [rbp+57h+var_98], r15d
0x180042146  cmp     [r12], r15d
0x18004214a  jle     loc_180042372
0x180042150  mov     edx, r13d; i
0x180042153  mov     rcx, r12; hdsa
0x180042156  call    DSA_GetItemPtr
0x18004215b  mov     r15, rax
0x18004215e  test    byte ptr [rax], 10h
0x180042161  jz      loc_1800423E6
0x180042167  xor     ebx, ebx
0x180042169  inc     dword ptr [rdi+14h]
0x18004216c  test    dword ptr [rax], 400h
0x180042172  jnz     loc_1800425DF
0x180042178  mov     r14, [rsi]
0x18004217b  mov     [rbp+57h+var_98], rbx
0x18004217f  lea     rdx, [r15+2Ch]
0x180042183  lea     r8, [rbp+57h+var_98]
0x180042187  mov     rcx, r14
0x18004218a  call    ??$Append@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAE@@PathAlloc@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,260>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004218f  test    eax, eax
0x180042191  js      short loc_180042209
0x180042193  mov     rbx, [rbp+57h+var_98]
0x180042197  mov     rcx, [rsi]; pv
0x18004219a  test    rcx, rcx
0x18004219d  jnz     loc_1800425B4
0x1800421a3  mov     [rsi], rbx
0x1800421a6  jmp     loc_18004227F
0x1800421ab  mov     r14d, 1
0x1800421b1  mov     eax, [rdi+0Ch]
0x1800421b4  and     eax, 1
0x1800421b7  cmp     r14d, eax
0x1800421ba  jz      loc_1800423CC
0x1800421c0  mov     r14, [rbp+57h+pv]
0x1800421c4  test    r14, r14
0x1800421c7  jz      loc_1800423A3
0x1800421cd  mov     r8, r15; pitem
0x1800421d0  mov     edx, 7FFFFFFFh; i
0x1800421d5  mov     rcx, r14; hdsa
0x1800421d8  call    DSA_InsertItem
0x1800421dd  jmp     loc_18004210C
0x1800421e2  cmp     [rdi+7Eh], cx
0x1800421e6  jz      loc_18004210C
0x1800421ec  cmp     word ptr [rdi+7Eh], 2Eh ; '.'
0x1800421f1  jnz     loc_1800420CE
0x1800421f7  cmp     [rdi+80h], cx
0x1800421fe  jnz     loc_1800420CE
0x180042204  jmp     loc_18004210C
0x180042209  mov     rcx, [rbp+5Fh]; this
0x18004220d  mov     r9d, eax; char *
0x180042210  lea     r8, aShellShell32Tr; "shell\\shell32\\treewalk.cpp"
0x180042217  mov     edx, 8Bh; void *
0x18004221c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042221  mov     qword ptr [rbp+57h+var_78], rbx
0x180042225  or      r8, 0FFFFFFFFFFFFFFFFh
0x180042229  mov     rdx, r14
0x18004222c  lea     rcx, [rbp+57h+var_90]
0x180042230  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180042235  lea     rdx, [rbp+57h+var_90]
0x180042239  lea     rcx, [rbp+57h+var_78]
0x18004223d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180042242  lea     rcx, [rbp+57h+var_90]; void *
0x180042246  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004224b  mov     rdx, qword ptr [rbp+57h+var_78]
0x18004224f  test    rdx, rdx
0x180042252  jnz     loc_1800425FB
0x180042258  mov     r14d, 8007000Eh
0x18004225e  lea     rcx, [rbp+57h+var_78]; void *
0x180042262  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180042267  mov     rcx, [rbp+57h+var_98]; pv
0x18004226b  test    rcx, rcx
0x18004226e  jz      short loc_180042276
0x180042270  call    cs:__imp_CoTaskMemFree
0x180042276  test    r14d, r14d
0x180042279  js      loc_1800425AC
0x18004227f  inc     dword ptr [rdi+1Ch]
0x180042282  mov     ecx, [rdi+1Ch]
0x180042285  xor     r14d, r14d
0x180042288  mov     eax, [rdi+18h]
0x18004228b  mov     [rbp+57h+var_68], eax
0x18004228e  mov     [rbp+57h+var_64], ecx
0x180042291  mov     eax, [rdi+14h]
0x180042294  mov     [rbp+57h+var_60], eax
0x180042297  mov     rax, [rdi+28h]
0x18004229b  mov     [rbp+57h+var_58], rax
0x18004229f  mov     rax, [rdi+30h]
0x1800422a3  mov     [rbp+57h+var_50], rax
0x1800422a7  mov     eax, [rdi+20h]
0x1800422aa  mov     [rbp+57h+var_5C], eax
0x1800422ad  mov     rcx, [rsi]; unsigned __int16 *
0x1800422b0  call    PathGetClusterSize
0x1800422b5  mov     [rdi+20h], eax
0x1800422b8  test    byte ptr [rdi+0Ch], 8
0x1800422bc  jz      short loc_1800422E5
0x1800422be  cmp     [rdi+14h], r14d
0x1800422c2  jz      loc_18004260F
0x1800422c8  mov     rcx, [rdi+48h]
0x1800422cc  mov     rax, [rcx]
0x1800422cf  mov     r9, r15
0x1800422d2  lea     r8, [rbp+57h+var_68]
0x1800422d6  mov     rdx, [rsi]
0x1800422d9  mov     rax, [rax+20h]
0x1800422dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422e2  mov     r14d, eax
0x1800422e5  xor     r15d, r15d
0x1800422e8  mov     ebx, r15d
0x1800422eb  cmp     r14d, 80004001h
0x1800422f2  cmovnz  ebx, r14d
0x1800422f6  test    ebx, ebx
0x1800422f8  jnz     loc_1800425A0
0x1800422fe  mov     eax, [rdi+10h]
0x180042301  cmp     [rdi+14h], eax
0x180042304  ja      loc_1800425A0
0x18004230a  mov     rcx, rdi; this
0x18004230d  call    ?_WalkCurrentFolder@CShellTreeWalker@@AEAAJXZ; CShellTreeWalker::_WalkCurrentFolder(void)
0x180042312  mov     ebx, eax
0x180042314  mov     eax, [rdi+18h]
0x180042317  mov     [rbp+57h+var_68], eax
0x18004231a  mov     eax, [rdi+1Ch]
0x18004231d  mov     [rbp+57h+var_64], eax
0x180042320  mov     ecx, [rdi+14h]
0x180042323  mov     [rbp+57h+var_60], ecx
0x180042326  mov     rax, [rdi+28h]
0x18004232a  mov     [rbp+57h+var_58], rax
0x18004232e  mov     rax, [rdi+30h]
0x180042332  mov     [rbp+57h+var_50], rax
0x180042336  mov     eax, [rdi+20h]
0x180042339  mov     [rbp+57h+var_5C], eax
0x18004233c  test    byte ptr [rdi+0Ch], 10h
0x180042340  jnz     loc_18004261E
0x180042346  mov     rcx, [rsi]; pszPath
0x180042349  call    cs:__imp_PathRemoveFileSpecW
0x18004234f  mov     rcx, [rsi]; unsigned __int16 *
0x180042352  call    PathGetClusterSize
0x180042357  mov     [rdi+20h], eax
0x18004235a  dec     dword ptr [rdi+14h]
0x18004235d  test    ebx, ebx
0x18004235f  jnz     short loc_180042372
0x180042361  inc     r13d
0x180042364  mov     dword ptr [rbp+57h+var_98], r13d
0x180042368  cmp     r13d, [r12]
0x18004236c  jl      loc_180042150
0x180042372  mov     rcx, r12; hdsa
0x180042375  call    DSA_Destroy
0x18004237a  cmp     ebx, 1
0x18004237d  cmovz   ebx, r15d
0x180042381  mov     eax, ebx
0x180042383  mov     rcx, [rbp+57h+var_48]
0x180042387  xor     rcx, rsp; StackCookie
0x18004238a  call    __security_check_cookie
0x18004238f  add     rsp, 98h
0x180042396  pop     r15
0x180042398  pop     r14
0x18004239a  pop     r13
0x18004239c  pop     r12
0x18004239e  pop     rdi
0x18004239f  pop     rsi
0x1800423a0  pop     rbx
0x1800423a1  pop     rbp
0x1800423a2  retn
0x1800423a3  mov     edx, 20h ; ' '; cItemGrow
0x1800423a8  mov     ecx, 250h; cbItem
0x1800423ad  call    DSA_Create
0x1800423b2  mov     r14, rax
0x1800423b5  mov     [rbp+57h+pv], rax
0x1800423b9  test    rax, rax
0x1800423bc  jnz     loc_1800421CD
0x1800423c2  mov     ebx, 8007000Eh
0x1800423c7  jmp     loc_18004211E
0x1800423cc  mov     rdx, r15; struct _WIN32_FIND_DATAW *
0x1800423cf  mov     rcx, rdi; this
0x1800423d2  call    ?_ProcessAndRecurse@CShellTreeWalker@@AEAAJPEAU_WIN32_FIND_DATAW@@@Z; CShellTreeWalker::_ProcessAndRecurse(_WIN32_FIND_DATAW *)
0x1800423d7  mov     ebx, eax
0x1800423d9  test    eax, eax
0x1800423db  jz      loc_18004210C
0x1800423e1  jmp     loc_18004211E
0x1800423e6  inc     dword ptr [rdi+18h]
0x1800423e9  mov     eax, [rax+20h]
0x1800423ec  mov     dword ptr [rbp+57h+var_88], eax
0x1800423ef  mov     eax, [r15+1Ch]
0x1800423f3  mov     dword ptr [rbp+57h+var_88+4], eax
0x1800423f6  mov     rbx, [rbp+57h+var_88]
0x1800423fa  add     [rdi+28h], rbx
0x1800423fe  xor     r12d, r12d
0x180042401  mov     r14, [rsi]
0x180042404  mov     [rbp+57h+ppszPathOut], r12
  ... truncated ...
```
