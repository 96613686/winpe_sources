# CShellTreeWalker::_WalkCurrentFolder(void)

- ea: `0x18003da2c`
- end: `0x18003e17e`
- name: `?_WalkCurrentFolder@CShellTreeWalker@@AEAAJXZ`
- size: `1874`
- prototype: `__int64 __fastcall(CShellTreeWalker *__hidden this)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d554`
- `0x18003da2c`
- `0x1803c52e0`

## callees

- `0x180026890`
- `0x18003a480`
- `0x18003d554`
- `0x18003da2c`
- `0x18003e184`
- `0x18003e1e8`
- `0x18003ef10`
- `0x18003f824`
- `0x1800585dc`
- `0x180063e10`
- `0x180078a24`
- `0x18007c180`
- `0x18009d460`
- `0x1800d0b30`
- `0x180103384`
- `0x180249490`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e069`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e069`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003dbce`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003dbce`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003dbe3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003dbe3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18003db4f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18003db4f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18003e02a`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18003e02a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x18003dbb4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x18003dbb4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18003db61`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18003de17`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18003df30`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18003db61`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18003de17`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18003df30`
- `ntdll!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x18003e0dd`
- `ntdll!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x18003e0dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dd38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dfb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dd38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dfb3`
- `Windows.Storage!SHGetCompressedFileSizeW` at `0x18003e16a`
- `Windows.Storage!SHGetCompressedFileSizeW` at `0x18003e16a`

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
         v3,
         &pv);
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
                    v29,
                    ItemPtr + 22,
                    &ppszPathOut);
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
                    v17,
                    v14 + 22,
                    &v41);
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
0x18003da2c  push    rbp
0x18003da2e  push    rbx
0x18003da2f  push    rsi
0x18003da30  push    rdi
0x18003da31  push    r12
0x18003da33  push    r13
0x18003da35  push    r14
0x18003da37  push    r15
0x18003da39  lea     rbp, [rsp-1Fh]
0x18003da3e  sub     rsp, 98h
0x18003da45  mov     rax, cs:__security_cookie
0x18003da4c  xor     rax, rsp
0x18003da4f  mov     [rbp+57h+var_48], rax
0x18003da53  mov     rdi, rcx
0x18003da56  xor     r12d, r12d
0x18003da59  mov     ebx, r12d
0x18003da5c  mov     rdx, [rcx+40h]
0x18003da60  test    rdx, rdx
0x18003da63  jz      short loc_18003DA6D
0x18003da65  mov     eax, [rcx+10h]
0x18003da68  cmp     [rcx+14h], eax
0x18003da6b  jz      short loc_18003DA74
0x18003da6d  lea     rdx, c_szStarDotStar; "*.*"
0x18003da74  lea     rsi, [rcx+38h]
0x18003da78  mov     r14, [rsi]
0x18003da7b  mov     [rbp+57h+pv], r12
0x18003da7f  lea     r8, [rbp+57h+pv]
0x18003da83  mov     rcx, r14
0x18003da86  call    ??$Append@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAE@@PathAlloc@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,260>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003da8b  mov     rcx, [rbp+5Fh]; this
0x18003da8f  test    eax, eax
0x18003da91  js      short loc_18003DAAB
0x18003da93  mov     r14, [rbp+57h+pv]
0x18003da97  mov     rcx, [rsi]; pv
0x18003da9a  test    rcx, rcx
0x18003da9d  jnz     short loc_18003DAA4
0x18003da9f  mov     [rsi], r14
0x18003daa2  jmp     short loc_18003DB23
0x18003daa4  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZPEAG@details@wil@@SAXPEAG@Z; wil::details::close_invoke_helper<1,void (*)(void *),&CoTaskMemFree(void *),ushort *>::close_reset(ushort *)
0x18003daa9  jmp     short loc_18003DA9F
0x18003daab  mov     r9d, eax; char *
0x18003daae  lea     r8, aShellShell32Tr; "shell\\shell32\\treewalk.cpp"
0x18003dab5  mov     edx, 8Bh; void *
0x18003daba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003dabf  mov     qword ptr [rbp+57h+var_78], r12
0x18003dac3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003dac7  mov     rdx, r14
0x18003daca  lea     rcx, [rbp+57h+ppszPathOut]
0x18003dace  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003dad3  lea     rdx, [rbp+57h+ppszPathOut]
0x18003dad7  lea     rcx, [rbp+57h+var_78]
0x18003dadb  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003dae0  lea     rcx, [rbp+57h+ppszPathOut]; void *
0x18003dae4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18003dae9  mov     rdx, qword ptr [rbp+57h+var_78]
0x18003daed  test    rdx, rdx
0x18003daf0  jnz     loc_18003E0BC
0x18003daf6  mov     r14d, 8007000Eh
0x18003dafc  lea     rcx, [rbp+57h+var_78]; void *
0x18003db00  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18003db05  mov     rcx, [rbp+57h+pv]; pv
0x18003db09  test    rcx, rcx
0x18003db0c  jz      short loc_18003DB1A
0x18003db0e  call    cs:__imp_CoTaskMemFree
0x18003db15  nop     dword ptr [rax+rax+00h]
0x18003db1a  test    r14d, r14d
0x18003db1d  js      loc_18003DE55
0x18003db23  mov     [rbp+57h+pv], r12
0x18003db27  lea     r15, [rdi+50h]
0x18003db2b  mov     r9d, [rdi+0Ch]
0x18003db2f  shr     r9d, 2
0x18003db33  and     r9d, 1; fSearchOp
0x18003db37  mov     [rsp+0D0h+dwAdditionalFlags], 2; dwAdditionalFlags
0x18003db3f  mov     [rsp+0D0h+lpSearchFilter], r12; int
0x18003db44  mov     r8, r15; lpFindFileData
0x18003db47  mov     edx, 1; fInfoLevelId
0x18003db4c  mov     rcx, [rsi]; lpFileName
0x18003db4f  call    cs:__imp_FindFirstFileExW
0x18003db56  nop     dword ptr [rax+rax+00h]
0x18003db5b  mov     r12, rax
0x18003db5e  mov     rcx, [rsi]; pszPath
0x18003db61  call    cs:__imp_PathRemoveFileSpecW
0x18003db68  nop     dword ptr [rax+rax+00h]
0x18003db6d  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18003db71  jz      loc_18003DE55
0x18003db77  xor     ecx, ecx
0x18003db79  cmp     word ptr [rdi+7Ch], 2Eh ; '.'
0x18003db7e  jz      loc_18003DCAA
0x18003db84  test    byte ptr [r15], 10h
0x18003db88  jnz     loc_18003DC73
0x18003db8e  test    byte ptr [rdi+0Ch], 4
0x18003db92  jnz     short loc_18003DBC8
0x18003db94  mov     r14d, ecx
0x18003db97  mov     rdx, [rdi+40h]; pszSpec
0x18003db9b  test    rdx, rdx
0x18003db9e  jz      loc_18003DC79
0x18003dba4  mov     eax, [rdi+10h]
0x18003dba7  cmp     [rdi+14h], eax
0x18003dbaa  jnb     loc_18003DC79
0x18003dbb0  lea     rcx, [rdi+7Ch]; pszFile
0x18003dbb4  call    cs:__imp_PathMatchSpecW
0x18003dbbb  nop     dword ptr [rax+rax+00h]
0x18003dbc0  test    eax, eax
0x18003dbc2  jnz     loc_18003DC79
0x18003dbc8  mov     rdx, r15; lpFindFileData
0x18003dbcb  mov     rcx, r12; hFindFile
0x18003dbce  call    cs:__imp_FindNextFileW
0x18003dbd5  nop     dword ptr [rax+rax+00h]
0x18003dbda  xor     ecx, ecx
0x18003dbdc  test    eax, eax
0x18003dbde  jnz     short loc_18003DB79
0x18003dbe0  mov     rcx, r12; hFindFile
0x18003dbe3  call    cs:__imp_FindClose
0x18003dbea  nop     dword ptr [rax+rax+00h]
0x18003dbef  mov     r12, [rbp+57h+pv]
0x18003dbf3  xor     r15d, r15d
0x18003dbf6  test    r12, r12
0x18003dbf9  jz      loc_18003DE4E
0x18003dbff  test    ebx, ebx
0x18003dc01  jnz     loc_18003DE46
0x18003dc07  mov     r13d, r15d
0x18003dc0a  mov     dword ptr [rbp+57h+var_98], r15d
0x18003dc0e  cmp     [r12], r15d
0x18003dc12  jle     loc_18003DE46
0x18003dc18  mov     edx, r13d; i
0x18003dc1b  mov     rcx, r12; hdsa
0x18003dc1e  call    DSA_GetItemPtr
0x18003dc23  mov     r15, rax
0x18003dc26  test    byte ptr [rax], 10h
0x18003dc29  jz      loc_18003DEBB
0x18003dc2f  xor     ebx, ebx
0x18003dc31  inc     dword ptr [rdi+14h]
0x18003dc34  test    dword ptr [rax], 400h
0x18003dc3a  jnz     loc_18003E0D0
0x18003dc40  mov     r14, [rsi]
0x18003dc43  mov     [rbp+57h+var_98], rbx
0x18003dc47  lea     rdx, [r15+2Ch]
0x18003dc4b  lea     r8, [rbp+57h+var_98]
0x18003dc4f  mov     rcx, r14
0x18003dc52  call    ??$Append@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAE@@PathAlloc@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,260>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003dc57  test    eax, eax
0x18003dc59  js      short loc_18003DCD1
0x18003dc5b  mov     rbx, [rbp+57h+var_98]
0x18003dc5f  mov     rcx, [rsi]; pv
0x18003dc62  test    rcx, rcx
0x18003dc65  jnz     loc_18003E0A5
0x18003dc6b  mov     [rsi], rbx
0x18003dc6e  jmp     loc_18003DD4D
0x18003dc73  mov     r14d, 1
0x18003dc79  mov     eax, [rdi+0Ch]
0x18003dc7c  and     eax, 1
0x18003dc7f  cmp     r14d, eax
0x18003dc82  jz      loc_18003DEA1
0x18003dc88  mov     r14, [rbp+57h+pv]
0x18003dc8c  test    r14, r14
0x18003dc8f  jz      loc_18003DE78
0x18003dc95  mov     r8, r15; pitem
0x18003dc98  mov     edx, 7FFFFFFFh; i
0x18003dc9d  mov     rcx, r14; hdsa
0x18003dca0  call    DSA_InsertItem
0x18003dca5  jmp     loc_18003DBC8
0x18003dcaa  cmp     [rdi+7Eh], cx
0x18003dcae  jz      loc_18003DBC8
0x18003dcb4  cmp     word ptr [rdi+7Eh], 2Eh ; '.'
0x18003dcb9  jnz     loc_18003DB84
0x18003dcbf  cmp     [rdi+80h], cx
0x18003dcc6  jnz     loc_18003DB84
0x18003dccc  jmp     loc_18003DBC8
0x18003dcd1  mov     rcx, [rbp+5Fh]; this
0x18003dcd5  mov     r9d, eax; char *
0x18003dcd8  lea     r8, aShellShell32Tr; "shell\\shell32\\treewalk.cpp"
0x18003dcdf  mov     edx, 8Bh; void *
0x18003dce4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003dce9  mov     qword ptr [rbp+57h+var_78], rbx
0x18003dced  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003dcf1  mov     rdx, r14
0x18003dcf4  lea     rcx, [rbp+57h+var_90]
0x18003dcf8  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003dcfd  lea     rdx, [rbp+57h+var_90]
0x18003dd01  lea     rcx, [rbp+57h+var_78]
0x18003dd05  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003dd0a  lea     rcx, [rbp+57h+var_90]; void *
0x18003dd0e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18003dd13  mov     rdx, qword ptr [rbp+57h+var_78]
0x18003dd17  test    rdx, rdx
0x18003dd1a  jnz     loc_18003E0F2
0x18003dd20  mov     r14d, 8007000Eh
0x18003dd26  lea     rcx, [rbp+57h+var_78]; void *
0x18003dd2a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18003dd2f  mov     rcx, [rbp+57h+var_98]; pv
0x18003dd33  test    rcx, rcx
0x18003dd36  jz      short loc_18003DD44
0x18003dd38  call    cs:__imp_CoTaskMemFree
0x18003dd3f  nop     dword ptr [rax+rax+00h]
0x18003dd44  test    r14d, r14d
0x18003dd47  js      loc_18003E09D
0x18003dd4d  inc     dword ptr [rdi+1Ch]
0x18003dd50  mov     ecx, [rdi+1Ch]
0x18003dd53  xor     r14d, r14d
0x18003dd56  mov     eax, [rdi+18h]
0x18003dd59  mov     [rbp+57h+var_68], eax
0x18003dd5c  mov     [rbp+57h+var_64], ecx
0x18003dd5f  mov     eax, [rdi+14h]
0x18003dd62  mov     [rbp+57h+var_60], eax
0x18003dd65  mov     rax, [rdi+28h]
0x18003dd69  mov     [rbp+57h+var_58], rax
0x18003dd6d  mov     rax, [rdi+30h]
0x18003dd71  mov     [rbp+57h+var_50], rax
0x18003dd75  mov     eax, [rdi+20h]
0x18003dd78  mov     [rbp+57h+var_5C], eax
0x18003dd7b  mov     rcx, [rsi]; unsigned __int16 *
0x18003dd7e  call    PathGetClusterSize
0x18003dd83  mov     [rdi+20h], eax
0x18003dd86  test    byte ptr [rdi+0Ch], 8
0x18003dd8a  jz      short loc_18003DDB3
0x18003dd8c  cmp     [rdi+14h], r14d
0x18003dd90  jz      loc_18003E106
0x18003dd96  mov     rcx, [rdi+48h]
0x18003dd9a  mov     rax, [rcx]
0x18003dd9d  mov     r9, r15
0x18003dda0  lea     r8, [rbp+57h+var_68]
0x18003dda4  mov     rdx, [rsi]
0x18003dda7  mov     rax, [rax+20h]
0x18003ddab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddb0  mov     r14d, eax
0x18003ddb3  xor     r15d, r15d
0x18003ddb6  mov     ebx, r15d
0x18003ddb9  cmp     r14d, 80004001h
0x18003ddc0  cmovnz  ebx, r14d
0x18003ddc4  test    ebx, ebx
0x18003ddc6  jnz     loc_18003E091
0x18003ddcc  mov     eax, [rdi+10h]
0x18003ddcf  cmp     [rdi+14h], eax
0x18003ddd2  ja      loc_18003E091
0x18003ddd8  mov     rcx, rdi; this
0x18003dddb  call    ?_WalkCurrentFolder@CShellTreeWalker@@AEAAJXZ; CShellTreeWalker::_WalkCurrentFolder(void)
0x18003dde0  mov     ebx, eax
0x18003dde2  mov     eax, [rdi+18h]
0x18003dde5  mov     [rbp+57h+var_68], eax
0x18003dde8  mov     eax, [rdi+1Ch]
0x18003ddeb  mov     [rbp+57h+var_64], eax
0x18003ddee  mov     ecx, [rdi+14h]
0x18003ddf1  mov     [rbp+57h+var_60], ecx
0x18003ddf4  mov     rax, [rdi+28h]
0x18003ddf8  mov     [rbp+57h+var_58], rax
0x18003ddfc  mov     rax, [rdi+30h]
0x18003de00  mov     [rbp+57h+var_50], rax
0x18003de04  mov     eax, [rdi+20h]
0x18003de07  mov     [rbp+57h+var_5C], eax
0x18003de0a  test    byte ptr [rdi+0Ch], 10h
0x18003de0e  jnz     loc_18003E115
0x18003de14  mov     rcx, [rsi]; pszPath
0x18003de17  call    cs:__imp_PathRemoveFileSpecW
0x18003de1e  nop     dword ptr [rax+rax+00h]
0x18003de23  mov     rcx, [rsi]; unsigned __int16 *
0x18003de26  call    PathGetClusterSize
0x18003de2b  mov     [rdi+20h], eax
0x18003de2e  dec     dword ptr [rdi+14h]
0x18003de31  test    ebx, ebx
0x18003de33  jnz     short loc_18003DE46
0x18003de35  inc     r13d
0x18003de38  mov     dword ptr [rbp+57h+var_98], r13d
0x18003de3c  cmp     r13d, [r12]
0x18003de40  jl      loc_18003DC18
0x18003de46  mov     rcx, r12; hdsa
0x18003de49  call    DSA_Destroy
0x18003de4e  cmp     ebx, 1
0x18003de51  cmovz   ebx, r15d
0x18003de55  mov     eax, ebx
0x18003de57  mov     rcx, [rbp+57h+var_48]
0x18003de5b  xor     rcx, rsp; StackCookie
0x18003de5e  call    __security_check_cookie
0x18003de63  add     rsp, 98h
0x18003de6a  pop     r15
0x18003de6c  pop     r14
0x18003de6e  pop     r13
0x18003de70  pop     r12
0x18003de72  pop     rdi
0x18003de73  pop     rsi
0x18003de74  pop     rbx
0x18003de75  pop     rbp
0x18003de76  retn
0x18003de78  mov     edx, 20h ; ' '; cItemGrow
0x18003de7d  mov     ecx, 250h; cbItem
0x18003de82  call    DSA_Create
0x18003de87  mov     r14, rax
0x18003de8a  mov     [rbp+57h+pv], rax
0x18003de8e  test    rax, rax
0x18003de91  jnz     loc_18003DC95
0x18003de97  mov     ebx, 8007000Eh
0x18003de9c  jmp     loc_18003DBE0
0x18003dea1  mov     rdx, r15; struct _WIN32_FIND_DATAW *
0x18003dea4  mov     rcx, rdi; this
0x18003dea7  call    ?_ProcessAndRecurse@CShellTreeWalker@@AEAAJPEAU_WIN32_FIND_DATAW@@@Z; CShellTreeWalker::_ProcessAndRecurse(_WIN32_FIND_DATAW *)
0x18003deac  mov     ebx, eax
0x18003deae  test    eax, eax
0x18003deb0  jz      loc_18003DBC8
0x18003deb6  jmp     loc_18003DBE0
0x18003debb  inc     dword ptr [rdi+18h]
0x18003debe  mov     eax, [rax+20h]
  ... truncated ...
```
