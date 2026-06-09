# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x18003f130`
- end: `0x18003f67a`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1354`
- prototype: `__int64 __fastcall(const wchar_t *, int, void *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003f0f8`
- `0x18003f130`

## callees

- `0x180003110`
- `0x180003c88`
- `0x18000e5ac`
- `0x180014d60`
- `0x18001b624`
- `0x18001e06c`
- `0x18003c6fc`
- `0x18003cbfc`
- `0x18003d52c`
- `0x18003d550`
- `0x18003d620`
- `0x18003f130`
- `0x18003f70c`
- `0x18003f7dc`
- `0x1800403e0`
- `0x180040504`
- `0x1800546b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f42b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f4e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f42b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f4e3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003f3d3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003f3d3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003f3f3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003f3f3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003f41d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003f41d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003f3ab`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003f3fe`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003f3ab`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003f3fe`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18003f38c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18003f58c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18003f38c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18003f58c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003f2a5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003f2a5`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003f467`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003f497`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003f467`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003f497`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18003f25f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18003f2fe`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18003f25f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18003f2fe`

## string_xrefs

- `0x18003f21a`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003f272`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003f357`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003f4b1`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003f4cb`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003f4f4`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003f545`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003f578`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003f5da`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18003f621`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(const wchar_t *a1, int a2, void *a3)
{
  const WCHAR *v6; // rbx
  ULONG v7; // edi
  int v8; // esi
  __int64 v9; // rdx
  HRESULT v10; // eax
  const unsigned __int16 *v11; // rdx
  wchar_t *FirstFileW; // rdi
  const char *v13; // r9
  HRESULT v14; // eax
  int v15; // eax
  const char *v16; // r9
  const char *v17; // r9
  DWORD FileAttributesW; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  const char *v21; // r9
  __int64 v22; // rdx
  int v23; // eax
  int v24; // eax
  DWORD v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // rdx
  unsigned int LastError; // ebx
  unsigned int v31; // [rsp+20h] [rbp-E0h]
  const wchar_t *v32; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR v33; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR ppszPathOut; // [rsp+40h] [rbp-C0h] BYREF
  char FileInformation[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  char v38[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v39[15]; // [rsp+68h] [rbp-98h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  pszPathIn = 0;
  if ( !wcsncmp_0(a1, L"\\\\?\\", 4u) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v32,
      a1,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPathIn,
      &v32);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
    v6 = pszPathIn;
    if ( pszPathIn )
    {
      v7 = 16;
      goto LABEL_9;
    }
    v8 = -2147024882;
    v9 = 260;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
      (const char *)(unsigned int)v8,
      v31);
    goto LABEL_61;
  }
  v32 = a1;
  v39[0] = &wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v39[1] = &v32;
  v39[13] = v39;
  v8 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         &pszPathIn,
         v38);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v38);
  if ( v8 < 0 )
  {
    v9 = 268;
    goto LABEL_7;
  }
  v6 = pszPathIn;
  v7 = 1;
LABEL_9:
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v10 = PathAllocCombine(v6, L"*", v7, &ppszPathOut);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
      (const char *)(unsigned int)v10,
      v31);
    goto LABEL_60;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (wchar_t *)FindFirstFileW(ppszPathOut, &FindFileData);
  v32 = FirstFileW;
  if ( (unsigned __int64)FirstFileW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                  v13);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
    return LastError;
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 && wil::path_is_dot_or_dotdot((wil *)FindFileData.cFileName, v11) )
      goto LABEL_31;
    v33 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v33,
      0);
    v14 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, &v33);
    v8 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)(unsigned int)v14,
        v31);
      goto LABEL_58;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    wil::TryCreateFileCanRecurseIntoDirectory(&hFile, v33, &FindFileData);
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        v25 = GetLastError();
        if ( !v25 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          v8 = 0;
          goto LABEL_61;
        }
        v24 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x136,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)v25,
                v31);
        goto LABEL_42;
      }
      if ( !RemoveDirectoryW(v33) )
      {
        v24 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                v16);
LABEL_42:
        v8 = v24;
        goto LABEL_19;
      }
    }
    else
    {
      v15 = wil::RemoveDirectoryRecursiveNoThrow(v33, a2 & 0xFFFFFFFE, hFile);
      v8 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
          (const char *)(unsigned int)v15,
          v31);
LABEL_19:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_58;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_30:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
LABEL_31:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v20 = GetLastError();
      if ( v20 == 18 )
      {
        if ( (a2 & 1) != 0 )
          goto LABEL_56;
        if ( a3 == (void *)-1LL )
        {
          if ( !RemoveDirectoryW(v6) )
          {
            v22 = 381;
            goto LABEL_39;
          }
LABEL_56:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
          return 0;
        }
        LODWORD(hFile) = 3;
        if ( SetFileInformationByHandle(a3, FileRenameInfoEx|FileDispositionInfo, &hFile, 4u) )
          goto LABEL_56;
        if ( GetLastError() != 5 )
        {
          FileInformation[0] = 1;
          if ( !SetFileInformationByHandle(a3, FileDispositionInfo, FileInformation, 1u) )
          {
            v22 = 369;
LABEL_39:
            v23 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v22,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                    v21);
LABEL_40:
            v8 = v23;
            goto LABEL_59;
          }
          goto LABEL_56;
        }
        v27 = 5;
        v28 = 374;
      }
      else
      {
        if ( !v20 )
          goto LABEL_56;
        v27 = v20;
        v28 = 348;
      }
      v23 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v28,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
              (const char *)v27,
              v31);
      goto LABEL_40;
    }
  }
  if ( DeleteFileW(v33) )
    goto LABEL_30;
  if ( (a2 & 2) != 0 && GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(v33);
    if ( (FileAttributesW & 1) == 0 )
    {
      v26 = 325;
      goto LABEL_47;
    }
    v19 = FileAttributesW & 0xFFFFFFFE;
    if ( !v19 )
      v19 = 128;
    SetFileAttributesW(v33, v19);
    if ( !DeleteFileW(v33) )
    {
      v26 = 336;
      goto LABEL_47;
    }
    goto LABEL_30;
  }
  v26 = 321;
LABEL_47:
  v8 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v26,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
         v17);
LABEL_58:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
LABEL_59:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
LABEL_60:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_61:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003f130  mov     [rsp-8+arg_18], rbx
0x18003f135  push    rbp
0x18003f136  push    rsi
0x18003f137  push    rdi
0x18003f138  push    r14
0x18003f13a  push    r15
0x18003f13c  lea     rbp, [rsp-240h]
0x18003f144  sub     rsp, 340h
0x18003f14b  mov     rax, cs:__security_cookie
0x18003f152  xor     rax, rsp
0x18003f155  mov     [rbp+260h+var_30], rax
0x18003f15c  mov     r14, r8
0x18003f15f  mov     [rsp+360h+pszPathIn], 0
0x18003f168  mov     r15d, edx
0x18003f16b  mov     r8d, 4; MaxCount
0x18003f171  lea     rdx, String2; "\\\\?\\"
0x18003f178  mov     rbx, rcx
0x18003f17b  call    wcsncmp_0
0x18003f180  test    eax, eax
0x18003f182  jnz     short loc_18003F1CB
0x18003f184  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003f188  lea     rcx, [rsp+360h+var_330]
0x18003f18d  mov     rdx, rbx
0x18003f190  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003f195  lea     rdx, [rsp+360h+var_330]
0x18003f19a  lea     rcx, [rsp+360h+pszPathIn]
0x18003f19f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003f1a4  lea     rcx, [rsp+360h+var_330]
0x18003f1a9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f1ae  mov     rbx, [rsp+360h+pszPathIn]
0x18003f1b3  test    rbx, rbx
0x18003f1b6  jz      short loc_18003F1BF
0x18003f1b8  mov     edi, 10h
0x18003f1bd  jmp     short loc_18003F238
0x18003f1bf  mov     esi, 8007000Eh
0x18003f1c4  mov     edx, 104h
0x18003f1c9  jmp     short loc_18003F213
0x18003f1cb  lea     rax, ??_7?$__func@V_lambda_8b91c585b7835484d8ed00982d386965_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18003f1d2  mov     [rsp+360h+var_330], rbx
0x18003f1d7  mov     [rsp+360h+var_2F8], rax
0x18003f1dc  lea     rdx, [rsp+360h+var_300]
0x18003f1e1  lea     rax, [rsp+360h+var_330]
0x18003f1e6  mov     [rsp+360h+var_2F0], rax
0x18003f1eb  lea     rcx, [rsp+360h+pszPathIn]
0x18003f1f0  lea     rax, [rsp+360h+var_2F8]
0x18003f1f5  mov     [rbp+260h+var_290], rax
0x18003f1f9  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x18003f1fe  lea     rcx, [rsp+360h+var_300]
0x18003f203  mov     esi, eax
0x18003f205  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x18003f20a  test    esi, esi
0x18003f20c  jns     short loc_18003F22E
0x18003f20e  mov     edx, 10Ch; void *
0x18003f213  mov     rcx, [rbp+268h]; this
0x18003f21a  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f221  mov     r9d, esi; char *
0x18003f224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f229  jmp     loc_18003F60C
0x18003f22e  mov     rbx, [rsp+360h+pszPathIn]
0x18003f233  mov     edi, 1
0x18003f238  xor     edx, edx
0x18003f23a  mov     [rsp+360h+ppszPathOut], 0
0x18003f243  lea     rcx, [rsp+360h+ppszPathOut]
0x18003f248  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003f24d  lea     r9, [rsp+360h+ppszPathOut]; ppszPathOut
0x18003f252  mov     r8d, edi; dwFlags
0x18003f255  lea     rdx, pszMore; "*"
0x18003f25c  mov     rcx, rbx; pszPathIn
0x18003f25f  call    cs:__imp_PathAllocCombine
0x18003f265  mov     esi, eax
0x18003f267  test    eax, eax
0x18003f269  jns     short loc_18003F28B
0x18003f26b  mov     rcx, [rbp+268h]; this
0x18003f272  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f279  mov     r9d, eax; char *
0x18003f27c  mov     edx, 111h; void *
0x18003f281  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f286  jmp     loc_18003F602
0x18003f28b  xor     edx, edx; Val
0x18003f28d  lea     rcx, [rbp+260h+FindFileData]; void *
0x18003f291  mov     r8d, 250h; Size
0x18003f297  call    memset_0
0x18003f29c  mov     rcx, [rsp+360h+ppszPathOut]; lpFileName
0x18003f2a1  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x18003f2a5  call    cs:__imp_FindFirstFileW
0x18003f2ab  mov     rdi, rax
0x18003f2ae  mov     [rsp+360h+var_330], rax
0x18003f2b3  dec     rax
0x18003f2b6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f2ba  ja      loc_18003F61A
0x18003f2c0  test    byte ptr [rbp+260h+FindFileData.dwFileAttributes], 10h
0x18003f2c4  jz      short loc_18003F2D7
0x18003f2c6  lea     rcx, [rbp+260h+FindFileData.cFileName]; this
0x18003f2ca  call    ?path_is_dot_or_dotdot@wil@@YA_NPEBG@Z; wil::path_is_dot_or_dotdot(ushort const *)
0x18003f2cf  test    al, al
0x18003f2d1  jnz     loc_18003F416
0x18003f2d7  xor     edx, edx
0x18003f2d9  mov     [rsp+360h+var_328], 0
0x18003f2e2  lea     rcx, [rsp+360h+var_328]
0x18003f2e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003f2ec  lea     r9, [rsp+360h+var_328]; ppszPathOut
0x18003f2f1  mov     r8d, 18h; dwFlags
0x18003f2f7  lea     rdx, [rbp+260h+FindFileData.cFileName]; pszMore
0x18003f2fb  mov     rcx, rbx; pszPathIn
0x18003f2fe  call    cs:__imp_PathAllocCombine
0x18003f304  mov     esi, eax
0x18003f306  test    eax, eax
0x18003f308  js      loc_18003F5D3
0x18003f30e  test    byte ptr [rbp+260h+FindFileData.dwFileAttributes], 10h
0x18003f312  jz      loc_18003F3A6
0x18003f318  mov     rdx, [rsp+360h+var_328]
0x18003f31d  lea     r8, [rbp+260h+FindFileData]
0x18003f321  lea     rcx, [rsp+360h+hFile]
0x18003f326  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x18003f32b  mov     r8, [rsp+360h+hFile]
0x18003f330  lea     rax, [r8-1]
0x18003f334  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f338  ja      short loc_18003F37A
0x18003f33a  mov     rcx, [rsp+360h+var_328]
0x18003f33f  mov     edx, r15d
0x18003f342  and     edx, 0FFFFFFFEh
0x18003f345  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18003f34a  mov     esi, eax
0x18003f34c  test    eax, eax
0x18003f34e  jns     short loc_18003F39A
0x18003f350  mov     rcx, [rbp+268h]; this
0x18003f357  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f35e  mov     r9d, eax; char *
0x18003f361  mov     edx, 12Ch; void *
0x18003f366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f36b  lea     rcx, [rsp+360h+hFile]
0x18003f370  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f375  jmp     loc_18003F5EE
0x18003f37a  test    [rbp+260h+FindFileData.dwFileAttributes], 400h
0x18003f381  jz      loc_18003F4E3
0x18003f387  mov     rcx, [rsp+360h+var_328]; lpPathName
0x18003f38c  call    cs:__imp_RemoveDirectoryW
0x18003f392  test    eax, eax
0x18003f394  jz      loc_18003F4C4
0x18003f39a  lea     rcx, [rsp+360h+hFile]
0x18003f39f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f3a4  jmp     short loc_18003F40C
0x18003f3a6  mov     rcx, [rsp+360h+var_328]; lpFileName
0x18003f3ab  call    cs:__imp_DeleteFileW
0x18003f3b1  test    eax, eax
0x18003f3b3  jnz     short loc_18003F40C
0x18003f3b5  test    r15b, 2
0x18003f3b9  jz      loc_18003F55F
0x18003f3bf  call    cs:__imp_GetLastError
0x18003f3c5  cmp     eax, 5
0x18003f3c8  jnz     loc_18003F55F
0x18003f3ce  mov     rcx, [rsp+360h+var_328]; lpFileName
0x18003f3d3  call    cs:__imp_GetFileAttributesW
0x18003f3d9  test    al, 1
0x18003f3db  jz      loc_18003F558
0x18003f3e1  and     eax, 0FFFFFFFEh
0x18003f3e4  mov     ecx, 80h
0x18003f3e9  cmovz   eax, ecx
0x18003f3ec  mov     rcx, [rsp+360h+var_328]; lpFileName
0x18003f3f1  mov     edx, eax; dwFileAttributes
0x18003f3f3  call    cs:__imp_SetFileAttributesW
0x18003f3f9  mov     rcx, [rsp+360h+var_328]; lpFileName
0x18003f3fe  call    cs:__imp_DeleteFileW
0x18003f404  test    eax, eax
0x18003f406  jz      loc_18003F539
0x18003f40c  lea     rcx, [rsp+360h+var_328]
0x18003f411  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f416  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x18003f41a  mov     rcx, rdi; hFindFile
0x18003f41d  call    cs:__imp_FindNextFileW
0x18003f423  test    eax, eax
0x18003f425  jnz     loc_18003F2C0
0x18003f42b  call    cs:__imp_GetLastError
0x18003f431  cmp     eax, 12h
0x18003f434  jnz     loc_18003F5A0
0x18003f43a  test    r15b, 1
0x18003f43e  jnz     loc_18003F5AE
0x18003f444  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18003f448  jz      loc_18003F589
0x18003f44e  lea     ebx, [rax-0Eh]
0x18003f451  mov     dword ptr [rsp+360h+hFile], 3
0x18003f459  mov     r9d, ebx; dwBufferSize
0x18003f45c  lea     r8, [rsp+360h+hFile]; lpFileInformation
0x18003f461  lea     edx, [rax+3]; FileInformationClass
0x18003f464  mov     rcx, r14; hFile
0x18003f467  call    cs:__imp_SetFileInformationByHandle
0x18003f46d  test    eax, eax
0x18003f46f  jnz     loc_18003F5AE
0x18003f475  call    cs:__imp_GetLastError
0x18003f47b  cmp     eax, 5
0x18003f47e  jz      loc_18003F566
0x18003f484  lea     r9d, [rbx-3]; dwBufferSize
0x18003f488  mov     [rsp+360h+FileInformation], 1
0x18003f48d  lea     r8, [rsp+360h+FileInformation]; lpFileInformation
0x18003f492  mov     edx, ebx; FileInformationClass
0x18003f494  mov     rcx, r14; hFile
0x18003f497  call    cs:__imp_SetFileInformationByHandle
0x18003f49d  test    eax, eax
0x18003f49f  jnz     loc_18003F5AE
0x18003f4a5  mov     edx, 171h; void *
0x18003f4aa  mov     rcx, [rbp+268h]; this
0x18003f4b1  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f4b8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f4bd  mov     esi, eax
0x18003f4bf  jmp     loc_18003F5F8
0x18003f4c4  mov     rcx, [rbp+268h]; this
0x18003f4cb  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f4d2  mov     edx, 131h; void *
0x18003f4d7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f4dc  mov     esi, eax
0x18003f4de  jmp     loc_18003F36B
0x18003f4e3  call    cs:__imp_GetLastError
0x18003f4e9  test    eax, eax
0x18003f4eb  jz      short loc_18003F50A
0x18003f4ed  mov     rcx, [rbp+268h]; this
0x18003f4f4  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f4fb  mov     r9d, eax; char *
0x18003f4fe  mov     edx, 136h; void *
0x18003f503  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003f508  jmp     short loc_18003F4DC
0x18003f50a  lea     rcx, [rsp+360h+hFile]
0x18003f50f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f514  lea     rcx, [rsp+360h+var_328]
0x18003f519  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f51e  lea     rcx, [rsp+360h+var_330]
0x18003f523  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003f528  lea     rcx, [rsp+360h+ppszPathOut]
0x18003f52d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f532  xor     esi, esi
0x18003f534  jmp     loc_18003F60C
0x18003f539  mov     edx, 150h; void *
0x18003f53e  mov     rcx, [rbp+268h]; this
0x18003f545  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f54c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f551  mov     esi, eax
0x18003f553  jmp     loc_18003F5EE
0x18003f558  mov     edx, 145h
0x18003f55d  jmp     short loc_18003F53E
0x18003f55f  mov     edx, 141h
0x18003f564  jmp     short loc_18003F53E
0x18003f566  mov     r9d, 5; char *
0x18003f56c  mov     edx, 176h; void *
0x18003f571  mov     rcx, [rbp+268h]; this
0x18003f578  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f57f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003f584  jmp     loc_18003F4BD
0x18003f589  mov     rcx, rbx; lpPathName
0x18003f58c  call    cs:__imp_RemoveDirectoryW
0x18003f592  test    eax, eax
0x18003f594  jnz     short loc_18003F5AE
0x18003f596  mov     edx, 17Dh
0x18003f59b  jmp     loc_18003F4AA
0x18003f5a0  test    eax, eax
0x18003f5a2  jz      short loc_18003F5AE
0x18003f5a4  mov     r9d, eax
0x18003f5a7  mov     edx, 15Ch
0x18003f5ac  jmp     short loc_18003F571
0x18003f5ae  lea     rcx, [rsp+360h+var_330]
0x18003f5b3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003f5b8  lea     rcx, [rsp+360h+ppszPathOut]
0x18003f5bd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f5c2  lea     rcx, [rsp+360h+pszPathIn]
0x18003f5c7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f5cc  xor     eax, eax
0x18003f5ce  jmp     loc_18003F654
0x18003f5d3  mov     rcx, [rbp+268h]; this
0x18003f5da  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f5e1  mov     r9d, eax; char *
0x18003f5e4  mov     edx, 120h; void *
0x18003f5e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f5ee  lea     rcx, [rsp+360h+var_328]
0x18003f5f3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f5f8  lea     rcx, [rsp+360h+var_330]
0x18003f5fd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003f602  lea     rcx, [rsp+360h+ppszPathOut]
0x18003f607  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f60c  lea     rcx, [rsp+360h+pszPathIn]
0x18003f611  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f616  mov     eax, esi
0x18003f618  jmp     short loc_18003F654
0x18003f61a  mov     rcx, [rbp+268h]; this
0x18003f621  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f628  mov     edx, 115h; void *
0x18003f62d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f632  lea     rcx, [rsp+360h+var_330]
0x18003f637  mov     ebx, eax
0x18003f639  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003f63e  lea     rcx, [rsp+360h+ppszPathOut]
0x18003f643  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f648  lea     rcx, [rsp+360h+pszPathIn]
0x18003f64d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003f652  mov     eax, ebx
0x18003f654  mov     rcx, [rbp+260h+var_30]
0x18003f65b  xor     rcx, rsp; StackCookie
0x18003f65e  call    __security_check_cookie
0x18003f663  mov     rbx, [rsp+360h+arg_18]
0x18003f66b  add     rsp, 340h
0x18003f672  pop     r15
0x18003f674  pop     r14
0x18003f676  pop     rdi
  ... truncated ...
```
