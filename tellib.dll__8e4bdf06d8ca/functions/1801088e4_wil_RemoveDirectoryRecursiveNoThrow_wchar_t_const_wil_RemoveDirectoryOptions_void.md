# wil::RemoveDirectoryRecursiveNoThrow(wchar_t const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x1801088e4`
- end: `0x180108e65`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEB_WW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1409`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a9c80`
- `0x1801088e4`
- `0x180234ba0`

## callees

- `0x180026ecc`
- `0x180034d94`
- `0x18006dd98`
- `0x18006f66c`
- `0x18007fae8`
- `0x18008bd1c`
- `0x1801088e4`
- `0x180108e6c`
- `0x18012de40`
- `0x18012eb08`
- `0x1801796d4`
- `0x18017a9f8`
- `0x18017c0ac`
- `0x18017c828`
- `0x1801874d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108b6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108b6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108cc5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180108a21`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180108a21`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180108b84`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180108b84`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180108baa`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180108baa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180108b50`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180108bbb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180108b50`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180108bbb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180108be1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180108be1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180108c37`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180108c73`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180108c37`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180108c73`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180108b28`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180108d75`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180108b28`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180108d75`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801089d3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180108a91`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801089d3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180108a91`

## string_xrefs

- `0x180108995`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1801089ec`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180108af2`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180108c93`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180108cad`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180108cdc`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180108d2e`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180108d61`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180108dc9`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180108e10`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(wil *a1, const wchar_t *a2, void *a3)
{
  int v4; // r15d
  const WCHAR *v6; // rbx
  unsigned int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // r9
  ULONG v10; // edi
  int v11; // eax
  HRESULT v12; // eax
  char *FirstFileW; // rdi
  const char *v14; // r9
  HRESULT v15; // eax
  int v16; // eax
  const char *v17; // r9
  const char *v18; // r9
  DWORD FileAttributesW; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  const char *v22; // r9
  __int64 v23; // rdx
  unsigned int v24; // eax
  unsigned int v25; // eax
  DWORD v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 v29; // rdx
  unsigned int LastError; // ebx
  unsigned int v32; // [rsp+20h] [rbp-E0h]
  PWSTR v33; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp-C8h] BYREF
  char *v35; // [rsp+40h] [rbp-C0h] BYREF
  char FileInformation[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  pszPathIn = 0;
  v4 = (int)a2;
  if ( wil::is_extended_length_path(a1, a2) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
      &v35,
      a1,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      &pszPathIn,
      &v35);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v35);
    v6 = pszPathIn;
    if ( !pszPathIn )
    {
      v7 = -2147024882;
      v8 = 260;
      v9 = 2147942414LL;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)v9,
        v32);
      goto LABEL_64;
    }
    v10 = 16;
  }
  else
  {
    v11 = wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
            a1,
            &pszPathIn);
    v7 = v11;
    if ( v11 < 0 )
    {
      v9 = (unsigned int)v11;
      v8 = 268;
      goto LABEL_7;
    }
    v6 = pszPathIn;
    v10 = 1;
  }
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v12 = PathAllocCombine(v6, L"*", v10, &ppszPathOut);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
      (const char *)(unsigned int)v12,
      v32);
    goto LABEL_63;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v35 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                  v14);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppszPathOut);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pszPathIn);
    return LastError;
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_34;
    }
    v33 = 0;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      &v33,
      0);
    v15 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, &v33);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)(unsigned int)v15,
        v32);
      goto LABEL_61;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    wil::TryCreateFileCanRecurseIntoDirectory(&hFile, v33, &FindFileData);
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        v26 = GetLastError();
        if ( !v26 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v33);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppszPathOut);
          v7 = 0;
          goto LABEL_64;
        }
        v25 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x136,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)v26,
                v32);
        goto LABEL_45;
      }
      if ( !RemoveDirectoryW(v33) )
      {
        v25 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                v17);
LABEL_45:
        v7 = v25;
        goto LABEL_22;
      }
    }
    else
    {
      v16 = wil::RemoveDirectoryRecursiveNoThrow(v33, v4 & 0xFFFFFFFE);
      v7 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
          (const char *)(unsigned int)v16,
          v32);
LABEL_22:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_61;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v33);
LABEL_34:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v21 = GetLastError();
      if ( v21 == 18 )
      {
        if ( (v4 & 1) != 0 )
          goto LABEL_59;
        if ( a3 == (void *)-1LL )
        {
          if ( !RemoveDirectoryW(v6) )
          {
            v23 = 381;
            goto LABEL_42;
          }
LABEL_59:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppszPathOut);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pszPathIn);
          return 0;
        }
        LODWORD(hFile) = 3;
        if ( SetFileInformationByHandle(a3, FileRenameInfoEx|FileDispositionInfo, &hFile, 4u) )
          goto LABEL_59;
        if ( GetLastError() != 5 )
        {
          FileInformation[0] = 1;
          if ( !SetFileInformationByHandle(a3, FileDispositionInfo, FileInformation, 1u) )
          {
            v23 = 369;
LABEL_42:
            v24 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v23,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                    v22);
LABEL_43:
            v7 = v24;
            goto LABEL_62;
          }
          goto LABEL_59;
        }
        v28 = 5;
        v29 = 374;
      }
      else
      {
        if ( !v21 )
          goto LABEL_59;
        v28 = v21;
        v29 = 348;
      }
      v24 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v29,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
              (const char *)v28,
              v32);
      goto LABEL_43;
    }
  }
  if ( DeleteFileW(v33) )
    goto LABEL_33;
  if ( (v4 & 2) != 0 && GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(v33);
    if ( (FileAttributesW & 1) == 0 )
    {
      v27 = 325;
      goto LABEL_50;
    }
    v20 = FileAttributesW & 0xFFFFFFFE;
    if ( !v20 )
      v20 = 128;
    SetFileAttributesW(v33, v20);
    if ( !DeleteFileW(v33) )
    {
      v27 = 336;
      goto LABEL_50;
    }
    goto LABEL_33;
  }
  v27 = 321;
LABEL_50:
  v7 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v27,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
         v18);
LABEL_61:
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v33);
LABEL_62:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
LABEL_63:
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_64:
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pszPathIn);
  return v7;
}

```

## disassembly

```asm
0x1801088e4  push    rbp
0x1801088e6  push    rbx
0x1801088e7  push    rsi
0x1801088e8  push    rdi
0x1801088e9  push    r12
0x1801088eb  push    r14
0x1801088ed  push    r15
0x1801088ef  lea     rbp, [rsp-1C0h]
0x1801088f7  sub     rsp, 2C0h
0x1801088fe  mov     rax, cs:__security_cookie
0x180108905  xor     rax, rsp
0x180108908  mov     [rbp+1F0h+var_40], rax
0x18010890f  xor     r12d, r12d
0x180108912  mov     r14, r8
0x180108915  mov     [rsp+2F0h+pszPathIn], r12
0x18010891a  mov     r15d, edx
0x18010891d  mov     rbx, rcx
0x180108920  call    ?is_extended_length_path@wil@@YA_NPEB_W@Z; wil::is_extended_length_path(wchar_t const *)
0x180108925  test    al, al
0x180108927  jz      short loc_180108973
0x180108929  or      r8, 0FFFFFFFFFFFFFFFFh
0x18010892d  lea     rcx, [rsp+2F0h+var_2B0]
0x180108932  mov     rdx, rbx
0x180108935  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18010893a  lea     rdx, [rsp+2F0h+var_2B0]
0x18010893f  lea     rcx, [rsp+2F0h+pszPathIn]
0x180108944  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x180108949  lea     rcx, [rsp+2F0h+var_2B0]
0x18010894e  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180108953  mov     rbx, [rsp+2F0h+pszPathIn]
0x180108958  test    rbx, rbx
0x18010895b  jnz     short loc_18010896C
0x18010895d  mov     esi, 8007000Eh
0x180108962  mov     edx, 104h
0x180108967  mov     r9d, esi
0x18010896a  jmp     short loc_18010898E
0x18010896c  mov     edi, 10h
0x180108971  jmp     short loc_1801089B0
0x180108973  lea     rdx, [rsp+2F0h+pszPathIn]
0x180108978  mov     rcx, rbx
0x18010897b  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAPEB_W@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const * *)
0x180108980  mov     esi, eax
0x180108982  test    eax, eax
0x180108984  jns     short loc_1801089A6
0x180108986  mov     r9d, eax; char *
0x180108989  mov     edx, 10Ch; void *
0x18010898e  mov     rcx, [rbp+1F8h]; this
0x180108995  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18010899c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801089a1  jmp     loc_180108DFB
0x1801089a6  mov     rbx, [rsp+2F0h+pszPathIn]
0x1801089ab  mov     edi, 1
0x1801089b0  xor     edx, edx
0x1801089b2  mov     [rsp+2F0h+ppszPathOut], r12
0x1801089b7  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1801089bc  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x1801089c1  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x1801089c6  mov     r8d, edi; dwFlags
0x1801089c9  lea     rdx, pszMore; "*"
0x1801089d0  mov     rcx, rbx; pszPathIn
0x1801089d3  call    cs:__imp_PathAllocCombine
0x1801089da  nop     dword ptr [rax+rax+00h]
0x1801089df  mov     esi, eax
0x1801089e1  test    eax, eax
0x1801089e3  jns     short loc_180108A05
0x1801089e5  mov     rcx, [rbp+1F8h]; this
0x1801089ec  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801089f3  mov     r9d, eax; char *
0x1801089f6  mov     edx, 111h; void *
0x1801089fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108a00  jmp     loc_180108DF1
0x180108a05  xor     edx, edx; Val
0x180108a07  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x180108a0c  mov     r8d, 250h; Size
0x180108a12  call    memset_0
0x180108a17  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x180108a1c  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x180108a21  call    cs:__imp_FindFirstFileW
0x180108a28  nop     dword ptr [rax+rax+00h]
0x180108a2d  mov     rdi, rax
0x180108a30  mov     [rsp+2F0h+var_2B0], rax
0x180108a35  dec     rax
0x180108a38  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180108a3c  ja      loc_180108E09
0x180108a42  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x180108a47  jz      short loc_180108A6E
0x180108a49  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x180108a4e  jnz     short loc_180108A6E
0x180108a50  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x180108a54  test    ax, ax
0x180108a57  jz      loc_180108BD9
0x180108a5d  cmp     ax, 2Eh ; '.'
0x180108a61  jnz     short loc_180108A6E
0x180108a63  cmp     [rbp+1F0h+FindFileData.cFileName+4], r12w
0x180108a68  jz      loc_180108BD9
0x180108a6e  xor     edx, edx
0x180108a70  mov     [rsp+2F0h+var_2C0], r12
0x180108a75  lea     rcx, [rsp+2F0h+var_2C0]
0x180108a7a  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x180108a7f  lea     r9, [rsp+2F0h+var_2C0]; ppszPathOut
0x180108a84  mov     r8d, 18h; dwFlags
0x180108a8a  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x180108a8e  mov     rcx, rbx; pszPathIn
0x180108a91  call    cs:__imp_PathAllocCombine
0x180108a98  nop     dword ptr [rax+rax+00h]
0x180108a9d  mov     esi, eax
0x180108a9f  test    eax, eax
0x180108aa1  js      loc_180108DC2
0x180108aa7  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x180108aac  jz      loc_180108B4B
0x180108ab2  mov     rdx, [rsp+2F0h+var_2C0]
0x180108ab7  lea     r8, [rsp+2F0h+FindFileData]
0x180108abc  lea     rcx, [rsp+2F0h+hFile]
0x180108ac1  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEB_WPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(wchar_t const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x180108ac6  mov     r8, [rsp+2F0h+hFile]
0x180108acb  lea     rax, [r8-1]
0x180108acf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180108ad3  ja      short loc_180108B15
0x180108ad5  mov     rcx, [rsp+2F0h+var_2C0]
0x180108ada  mov     edx, r15d
0x180108add  and     edx, 0FFFFFFFEh
0x180108ae0  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEB_WW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(wchar_t const *,wil::RemoveDirectoryOptions,void *)
0x180108ae5  mov     esi, eax
0x180108ae7  test    eax, eax
0x180108ae9  jns     short loc_180108B3C
0x180108aeb  mov     rcx, [rbp+1F8h]; this
0x180108af2  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180108af9  mov     r9d, eax; char *
0x180108afc  mov     edx, 12Ch; void *
0x180108b01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108b06  lea     rcx, [rsp+2F0h+hFile]
0x180108b0b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180108b10  jmp     loc_180108DDD
0x180108b15  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x180108b1d  jz      loc_180108CC5
0x180108b23  mov     rcx, [rsp+2F0h+var_2C0]; lpPathName
0x180108b28  call    cs:__imp_RemoveDirectoryW
0x180108b2f  nop     dword ptr [rax+rax+00h]
0x180108b34  test    eax, eax
0x180108b36  jz      loc_180108CA6
0x180108b3c  lea     rcx, [rsp+2F0h+hFile]
0x180108b41  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180108b46  jmp     loc_180108BCF
0x180108b4b  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180108b50  call    cs:__imp_DeleteFileW
0x180108b57  nop     dword ptr [rax+rax+00h]
0x180108b5c  test    eax, eax
0x180108b5e  jnz     short loc_180108BCF
0x180108b60  test    r15b, 2
0x180108b64  jz      loc_180108D48
0x180108b6a  call    cs:__imp_GetLastError
0x180108b71  nop     dword ptr [rax+rax+00h]
0x180108b76  cmp     eax, 5
0x180108b79  jnz     loc_180108D48
0x180108b7f  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180108b84  call    cs:__imp_GetFileAttributesW
0x180108b8b  nop     dword ptr [rax+rax+00h]
0x180108b90  test    al, 1
0x180108b92  jz      loc_180108D41
0x180108b98  and     eax, 0FFFFFFFEh
0x180108b9b  mov     ecx, 80h
0x180108ba0  cmovz   eax, ecx
0x180108ba3  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180108ba8  mov     edx, eax; dwFileAttributes
0x180108baa  call    cs:__imp_SetFileAttributesW
0x180108bb1  nop     dword ptr [rax+rax+00h]
0x180108bb6  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180108bbb  call    cs:__imp_DeleteFileW
0x180108bc2  nop     dword ptr [rax+rax+00h]
0x180108bc7  test    eax, eax
0x180108bc9  jz      loc_180108D22
0x180108bcf  lea     rcx, [rsp+2F0h+var_2C0]
0x180108bd4  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180108bd9  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x180108bde  mov     rcx, rdi; hFindFile
0x180108be1  call    cs:__imp_FindNextFileW
0x180108be8  nop     dword ptr [rax+rax+00h]
0x180108bed  test    eax, eax
0x180108bef  jnz     loc_180108A42
0x180108bf5  call    cs:__imp_GetLastError
0x180108bfc  nop     dword ptr [rax+rax+00h]
0x180108c01  cmp     eax, 12h
0x180108c04  jnz     loc_180108D8F
0x180108c0a  test    r15b, 1
0x180108c0e  jnz     loc_180108D9D
0x180108c14  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180108c18  jz      loc_180108D72
0x180108c1e  lea     ebx, [rax-0Eh]
0x180108c21  mov     dword ptr [rsp+2F0h+hFile], 3
0x180108c29  mov     r9d, ebx; dwBufferSize
0x180108c2c  lea     r8, [rsp+2F0h+hFile]; lpFileInformation
0x180108c31  lea     edx, [rax+3]; FileInformationClass
0x180108c34  mov     rcx, r14; hFile
0x180108c37  call    cs:__imp_SetFileInformationByHandle
0x180108c3e  nop     dword ptr [rax+rax+00h]
0x180108c43  test    eax, eax
0x180108c45  jnz     loc_180108D9D
0x180108c4b  call    cs:__imp_GetLastError
0x180108c52  nop     dword ptr [rax+rax+00h]
0x180108c57  cmp     eax, 5
0x180108c5a  jz      loc_180108D4F
0x180108c60  lea     r9d, [rbx-3]; dwBufferSize
0x180108c64  mov     [rsp+2F0h+FileInformation], 1
0x180108c69  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x180108c6e  mov     edx, ebx; FileInformationClass
0x180108c70  mov     rcx, r14; hFile
0x180108c73  call    cs:__imp_SetFileInformationByHandle
0x180108c7a  nop     dword ptr [rax+rax+00h]
0x180108c7f  test    eax, eax
0x180108c81  jnz     loc_180108D9D
0x180108c87  mov     edx, 171h; void *
0x180108c8c  mov     rcx, [rbp+1F8h]; this
0x180108c93  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180108c9a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180108c9f  mov     esi, eax
0x180108ca1  jmp     loc_180108DE7
0x180108ca6  mov     rcx, [rbp+1F8h]; this
0x180108cad  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180108cb4  mov     edx, 131h; void *
0x180108cb9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180108cbe  mov     esi, eax
0x180108cc0  jmp     loc_180108B06
0x180108cc5  call    cs:__imp_GetLastError
0x180108ccc  nop     dword ptr [rax+rax+00h]
0x180108cd1  test    eax, eax
0x180108cd3  jz      short loc_180108CF2
0x180108cd5  mov     rcx, [rbp+1F8h]; this
0x180108cdc  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180108ce3  mov     r9d, eax; char *
0x180108ce6  mov     edx, 136h; void *
0x180108ceb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180108cf0  jmp     short loc_180108CBE
0x180108cf2  lea     rcx, [rsp+2F0h+hFile]
0x180108cf7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180108cfc  lea     rcx, [rsp+2F0h+var_2C0]
0x180108d01  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180108d06  lea     rcx, [rsp+2F0h+var_2B0]
0x180108d0b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180108d10  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180108d15  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180108d1a  mov     esi, r12d
0x180108d1d  jmp     loc_180108DFB
0x180108d22  mov     edx, 150h; void *
0x180108d27  mov     rcx, [rbp+1F8h]; this
0x180108d2e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180108d35  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180108d3a  mov     esi, eax
0x180108d3c  jmp     loc_180108DDD
0x180108d41  mov     edx, 145h
0x180108d46  jmp     short loc_180108D27
0x180108d48  mov     edx, 141h
0x180108d4d  jmp     short loc_180108D27
0x180108d4f  mov     r9d, 5; char *
0x180108d55  mov     edx, 176h; void *
0x180108d5a  mov     rcx, [rbp+1F8h]; this
0x180108d61  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180108d68  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180108d6d  jmp     loc_180108C9F
0x180108d72  mov     rcx, rbx; lpPathName
0x180108d75  call    cs:__imp_RemoveDirectoryW
0x180108d7c  nop     dword ptr [rax+rax+00h]
0x180108d81  test    eax, eax
0x180108d83  jnz     short loc_180108D9D
0x180108d85  mov     edx, 17Dh
0x180108d8a  jmp     loc_180108C8C
0x180108d8f  test    eax, eax
0x180108d91  jz      short loc_180108D9D
0x180108d93  mov     r9d, eax
0x180108d96  mov     edx, 15Ch
0x180108d9b  jmp     short loc_180108D5A
0x180108d9d  lea     rcx, [rsp+2F0h+var_2B0]
0x180108da2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180108da7  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180108dac  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180108db1  lea     rcx, [rsp+2F0h+pszPathIn]
0x180108db6  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180108dbb  xor     eax, eax
0x180108dbd  jmp     loc_180108E43
0x180108dc2  mov     rcx, [rbp+1F8h]; this
0x180108dc9  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180108dd0  mov     r9d, eax; char *
0x180108dd3  mov     edx, 120h; void *
0x180108dd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108ddd  lea     rcx, [rsp+2F0h+var_2C0]
0x180108de2  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180108de7  lea     rcx, [rsp+2F0h+var_2B0]
0x180108dec  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180108df1  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180108df6  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180108dfb  lea     rcx, [rsp+2F0h+pszPathIn]
0x180108e00  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180108e05  mov     eax, esi
0x180108e07  jmp     short loc_180108E43
0x180108e09  mov     rcx, [rbp+1F8h]; this
0x180108e10  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180108e17  mov     edx, 115h; void *
0x180108e1c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180108e21  lea     rcx, [rsp+2F0h+var_2B0]
0x180108e26  mov     ebx, eax
0x180108e28  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
  ... truncated ...
```
