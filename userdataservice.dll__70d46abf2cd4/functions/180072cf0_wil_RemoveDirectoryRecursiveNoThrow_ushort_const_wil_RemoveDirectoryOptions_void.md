# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x180072cf0`
- end: `0x1800731ff`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1295`
- prototype: `__int64 __fastcall(wil *, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180072cf0`
- `0x1800a0b40`

## callees

- `0x180012988`
- `0x180072310`
- `0x180072cf0`
- `0x180073208`
- `0x1800732e0`
- `0x18007339c`
- `0x18009de6c`
- `0x18009eb60`
- `0x18009eb84`
- `0x1800a2ad0`
- `0x1800a369c`
- `0x1800a517c`
- `0x1800a5328`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072f55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007300c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007307a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072f55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007300c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007307a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180072f89`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180072f89`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180072f69`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180072f69`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180072f41`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180072f94`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180072f41`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180072f94`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180072f22`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180073116`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180072f22`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180073116`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180072e27`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180072e27`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180072ffe`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18007302e`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180072ffe`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18007302e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180072fb4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180072fb4`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180072ddf`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180072e91`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180072ddf`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180072e91`

## string_xrefs

- `0x180072da1`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180072df2`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180072eec`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180073048`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180073062`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800730d6`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180073164`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800731ab`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(wil *a1, const unsigned __int16 *a2, void *a3)
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
  unsigned int v22; // r8d
  const char *v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  DWORD v27; // eax
  unsigned int v28; // r8d
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // r9
  unsigned int LastError; // ebx
  unsigned int v34; // [rsp+20h] [rbp-E0h]
  PWSTR v35; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp-C8h] BYREF
  char *v37; // [rsp+40h] [rbp-C0h] BYREF
  char FileInformation[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  pszPathIn = 0;
  v4 = (int)a2;
  if ( wil::is_extended_length_path(a1, a2) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v37,
      a1,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPathIn,
      &v37);
    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v37);
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)v9,
        v34);
      goto LABEL_64;
    }
    v10 = 16;
  }
  else
  {
    v11 = wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
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
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v12 = PathAllocCombine(v6, L"*", v10, &ppszPathOut);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)(unsigned int)v12,
      v34);
    goto LABEL_63;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v37 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                  v14);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&ppszPathOut);
    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&pszPathIn);
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
    v35 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v35,
      0);
    v15 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, &v35);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v15,
        v34);
      goto LABEL_61;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    wil::TryCreateFileCanRecurseIntoDirectory(&hFile, v35, &FindFileData);
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        v27 = GetLastError();
        if ( !v27 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v35);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
          auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&ppszPathOut);
          v7 = 0;
          goto LABEL_64;
        }
        v26 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x136, v28, (const char *)v27, v34);
        goto LABEL_45;
      }
      if ( !RemoveDirectoryW(v35) )
      {
        v26 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                v17);
LABEL_45:
        v7 = v26;
        goto LABEL_22;
      }
    }
    else
    {
      v16 = wil::RemoveDirectoryRecursiveNoThrow(v35, v4 & 0xFFFFFFFE, hFile);
      v7 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
          (const char *)(unsigned int)v16,
          v34);
LABEL_22:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_61;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_33:
    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v35);
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
            v24 = 381;
            goto LABEL_42;
          }
LABEL_59:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
          auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&ppszPathOut);
          auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&pszPathIn);
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
            v24 = 369;
LABEL_42:
            v25 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v24,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                    v23);
LABEL_43:
            v7 = v25;
            goto LABEL_62;
          }
          goto LABEL_59;
        }
        v30 = 374;
        v31 = 5;
      }
      else
      {
        if ( !v21 )
          goto LABEL_59;
        v31 = v21;
        v30 = 348;
      }
      v25 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v30, v22, (const char *)v31, v34);
      goto LABEL_43;
    }
  }
  if ( DeleteFileW(v35) )
    goto LABEL_33;
  if ( (v4 & 2) != 0 && GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(v35);
    if ( (FileAttributesW & 1) == 0 )
    {
      v29 = 325;
      goto LABEL_50;
    }
    v20 = FileAttributesW & 0xFFFFFFFE;
    if ( !v20 )
      v20 = 128;
    SetFileAttributesW(v35, v20);
    if ( !DeleteFileW(v35) )
    {
      v29 = 336;
      goto LABEL_50;
    }
    goto LABEL_33;
  }
  v29 = 321;
LABEL_50:
  v7 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v29,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
         v18);
LABEL_61:
  auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v35);
LABEL_62:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
LABEL_63:
  auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&ppszPathOut);
LABEL_64:
  auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&pszPathIn);
  return v7;
}

```

## disassembly

```asm
0x180072cf0  push    rbp
0x180072cf2  push    rbx
0x180072cf3  push    rsi
0x180072cf4  push    rdi
0x180072cf5  push    r12
0x180072cf7  push    r14
0x180072cf9  push    r15
0x180072cfb  lea     rbp, [rsp-1C0h]
0x180072d03  sub     rsp, 2C0h
0x180072d0a  mov     rax, cs:__security_cookie
0x180072d11  xor     rax, rsp
0x180072d14  mov     [rbp+1F0h+var_40], rax
0x180072d1b  xor     r12d, r12d
0x180072d1e  mov     r14, r8
0x180072d21  mov     [rsp+2F0h+pszPathIn], r12
0x180072d26  mov     r15d, edx
0x180072d29  mov     rbx, rcx
0x180072d2c  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180072d31  test    al, al
0x180072d33  jz      short loc_180072D7F
0x180072d35  or      r8, 0FFFFFFFFFFFFFFFFh
0x180072d39  lea     rcx, [rsp+2F0h+var_2B0]
0x180072d3e  mov     rdx, rbx
0x180072d41  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180072d46  lea     rdx, [rsp+2F0h+var_2B0]
0x180072d4b  lea     rcx, [rsp+2F0h+pszPathIn]
0x180072d50  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180072d55  lea     rcx, [rsp+2F0h+var_2B0]
0x180072d5a  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x180072d5f  mov     rbx, [rsp+2F0h+pszPathIn]
0x180072d64  test    rbx, rbx
0x180072d67  jnz     short loc_180072D78
0x180072d69  mov     esi, 8007000Eh
0x180072d6e  mov     edx, 104h
0x180072d73  mov     r9d, esi
0x180072d76  jmp     short loc_180072D9A
0x180072d78  mov     edi, 10h
0x180072d7d  jmp     short loc_180072DBC
0x180072d7f  lea     rdx, [rsp+2F0h+pszPathIn]
0x180072d84  mov     rcx, rbx
0x180072d87  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x180072d8c  mov     esi, eax
0x180072d8e  test    eax, eax
0x180072d90  jns     short loc_180072DB2
0x180072d92  mov     r9d, eax; char *
0x180072d95  mov     edx, 10Ch; void *
0x180072d9a  mov     rcx, [rbp+1F8h]; this
0x180072da1  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180072da8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072dad  jmp     loc_180073196
0x180072db2  mov     rbx, [rsp+2F0h+pszPathIn]
0x180072db7  mov     edi, 1
0x180072dbc  xor     edx, edx
0x180072dbe  mov     [rsp+2F0h+ppszPathOut], r12
0x180072dc3  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180072dc8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180072dcd  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x180072dd2  mov     r8d, edi; dwFlags
0x180072dd5  lea     rdx, pszMore; "*"
0x180072ddc  mov     rcx, rbx; pszPathIn
0x180072ddf  call    cs:__imp_PathAllocCombine
0x180072de5  mov     esi, eax
0x180072de7  test    eax, eax
0x180072de9  jns     short loc_180072E0B
0x180072deb  mov     rcx, [rbp+1F8h]; this
0x180072df2  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180072df9  mov     r9d, eax; char *
0x180072dfc  mov     edx, 111h; void *
0x180072e01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072e06  jmp     loc_18007318C
0x180072e0b  xor     edx, edx; Val
0x180072e0d  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x180072e12  mov     r8d, 250h; Size
0x180072e18  call    memset_0
0x180072e1d  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x180072e22  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x180072e27  call    cs:__imp_FindFirstFileW
0x180072e2d  mov     rdi, rax
0x180072e30  mov     [rsp+2F0h+var_2B0], rax
0x180072e35  dec     rax
0x180072e38  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180072e3c  ja      loc_1800731A4
0x180072e42  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x180072e47  jz      short loc_180072E6E
0x180072e49  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x180072e4e  jnz     short loc_180072E6E
0x180072e50  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x180072e54  test    ax, ax
0x180072e57  jz      loc_180072FAC
0x180072e5d  cmp     ax, 2Eh ; '.'
0x180072e61  jnz     short loc_180072E6E
0x180072e63  cmp     [rbp+1F0h+FindFileData.cFileName+4], r12w
0x180072e68  jz      loc_180072FAC
0x180072e6e  xor     edx, edx
0x180072e70  mov     [rsp+2F0h+var_2C0], r12
0x180072e75  lea     rcx, [rsp+2F0h+var_2C0]
0x180072e7a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180072e7f  lea     r9, [rsp+2F0h+var_2C0]; ppszPathOut
0x180072e84  mov     r8d, 18h; dwFlags
0x180072e8a  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x180072e8e  mov     rcx, rbx; pszPathIn
0x180072e91  call    cs:__imp_PathAllocCombine
0x180072e97  mov     esi, eax
0x180072e99  test    eax, eax
0x180072e9b  js      loc_18007315D
0x180072ea1  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x180072ea6  jz      loc_180072F3C
0x180072eac  mov     rdx, [rsp+2F0h+var_2C0]
0x180072eb1  lea     r8, [rsp+2F0h+FindFileData]
0x180072eb6  lea     rcx, [rsp+2F0h+hFile]
0x180072ebb  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x180072ec0  mov     r8, [rsp+2F0h+hFile]
0x180072ec5  lea     rax, [r8-1]
0x180072ec9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180072ecd  ja      short loc_180072F0F
0x180072ecf  mov     rcx, [rsp+2F0h+var_2C0]
0x180072ed4  mov     edx, r15d
0x180072ed7  and     edx, 0FFFFFFFEh
0x180072eda  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180072edf  mov     esi, eax
0x180072ee1  test    eax, eax
0x180072ee3  jns     short loc_180072F30
0x180072ee5  mov     rcx, [rbp+1F8h]; this
0x180072eec  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180072ef3  mov     r9d, eax; char *
0x180072ef6  mov     edx, 12Ch; void *
0x180072efb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072f00  lea     rcx, [rsp+2F0h+hFile]
0x180072f05  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180072f0a  jmp     loc_180073178
0x180072f0f  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x180072f17  jz      loc_18007307A
0x180072f1d  mov     rcx, [rsp+2F0h+var_2C0]; lpPathName
0x180072f22  call    cs:__imp_RemoveDirectoryW
0x180072f28  test    eax, eax
0x180072f2a  jz      loc_18007305B
0x180072f30  lea     rcx, [rsp+2F0h+hFile]
0x180072f35  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180072f3a  jmp     short loc_180072FA2
0x180072f3c  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180072f41  call    cs:__imp_DeleteFileW
0x180072f47  test    eax, eax
0x180072f49  jnz     short loc_180072FA2
0x180072f4b  test    r15b, 2
0x180072f4f  jz      loc_1800730F0
0x180072f55  call    cs:__imp_GetLastError
0x180072f5b  cmp     eax, 5
0x180072f5e  jnz     loc_1800730F0
0x180072f64  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180072f69  call    cs:__imp_GetFileAttributesW
0x180072f6f  test    al, 1
0x180072f71  jz      loc_1800730E9
0x180072f77  and     eax, 0FFFFFFFEh
0x180072f7a  mov     ecx, 80h
0x180072f7f  cmovz   eax, ecx
0x180072f82  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180072f87  mov     edx, eax; dwFileAttributes
0x180072f89  call    cs:__imp_SetFileAttributesW
0x180072f8f  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x180072f94  call    cs:__imp_DeleteFileW
0x180072f9a  test    eax, eax
0x180072f9c  jz      loc_1800730CA
0x180072fa2  lea     rcx, [rsp+2F0h+var_2C0]
0x180072fa7  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x180072fac  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x180072fb1  mov     rcx, rdi; hFindFile
0x180072fb4  call    cs:__imp_FindNextFileW
0x180072fba  test    eax, eax
0x180072fbc  jnz     loc_180072E42
0x180072fc2  call    cs:__imp_GetLastError
0x180072fc8  cmp     eax, 12h
0x180072fcb  jnz     loc_18007312A
0x180072fd1  test    r15b, 1
0x180072fd5  jnz     loc_180073138
0x180072fdb  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180072fdf  jz      loc_180073113
0x180072fe5  lea     ebx, [rax-0Eh]
0x180072fe8  mov     dword ptr [rsp+2F0h+hFile], 3
0x180072ff0  mov     r9d, ebx; dwBufferSize
0x180072ff3  lea     r8, [rsp+2F0h+hFile]; lpFileInformation
0x180072ff8  lea     edx, [rax+3]; FileInformationClass
0x180072ffb  mov     rcx, r14; hFile
0x180072ffe  call    cs:__imp_SetFileInformationByHandle
0x180073004  test    eax, eax
0x180073006  jnz     loc_180073138
0x18007300c  call    cs:__imp_GetLastError
0x180073012  cmp     eax, 5
0x180073015  jz      loc_1800730F7
0x18007301b  lea     r9d, [rbx-3]; dwBufferSize
0x18007301f  mov     [rsp+2F0h+FileInformation], 1
0x180073024  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x180073029  mov     edx, ebx; FileInformationClass
0x18007302b  mov     rcx, r14; hFile
0x18007302e  call    cs:__imp_SetFileInformationByHandle
0x180073034  test    eax, eax
0x180073036  jnz     loc_180073138
0x18007303c  mov     edx, 171h; void *
0x180073041  mov     rcx, [rbp+1F8h]; this
0x180073048  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007304f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180073054  mov     esi, eax
0x180073056  jmp     loc_180073182
0x18007305b  mov     rcx, [rbp+1F8h]; this
0x180073062  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180073069  mov     edx, 131h; void *
0x18007306e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180073073  mov     esi, eax
0x180073075  jmp     loc_180072F00
0x18007307a  call    cs:__imp_GetLastError
0x180073080  test    eax, eax
0x180073082  jz      short loc_18007309A
0x180073084  mov     rcx, [rbp+1F8h]; this
0x18007308b  mov     r9d, eax; char *
0x18007308e  mov     edx, 136h; void *
0x180073093  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180073098  jmp     short loc_180073073
0x18007309a  lea     rcx, [rsp+2F0h+hFile]
0x18007309f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800730a4  lea     rcx, [rsp+2F0h+var_2C0]
0x1800730a9  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800730ae  lea     rcx, [rsp+2F0h+var_2B0]
0x1800730b3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800730b8  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800730bd  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800730c2  mov     esi, r12d
0x1800730c5  jmp     loc_180073196
0x1800730ca  mov     edx, 150h; void *
0x1800730cf  mov     rcx, [rbp+1F8h]; this
0x1800730d6  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800730dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800730e2  mov     esi, eax
0x1800730e4  jmp     loc_180073178
0x1800730e9  mov     edx, 145h
0x1800730ee  jmp     short loc_1800730CF
0x1800730f0  mov     edx, 141h
0x1800730f5  jmp     short loc_1800730CF
0x1800730f7  mov     edx, 176h; void *
0x1800730fc  mov     r9d, 5; char *
0x180073102  mov     rcx, [rbp+1F8h]; this
0x180073109  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007310e  jmp     loc_180073054
0x180073113  mov     rcx, rbx; lpPathName
0x180073116  call    cs:__imp_RemoveDirectoryW
0x18007311c  test    eax, eax
0x18007311e  jnz     short loc_180073138
0x180073120  mov     edx, 17Dh
0x180073125  jmp     loc_180073041
0x18007312a  test    eax, eax
0x18007312c  jz      short loc_180073138
0x18007312e  mov     r9d, eax
0x180073131  mov     edx, 15Ch
0x180073136  jmp     short loc_180073102
0x180073138  lea     rcx, [rsp+2F0h+var_2B0]
0x18007313d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180073142  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180073147  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x18007314c  lea     rcx, [rsp+2F0h+pszPathIn]
0x180073151  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x180073156  xor     eax, eax
0x180073158  jmp     loc_1800731DE
0x18007315d  mov     rcx, [rbp+1F8h]; this
0x180073164  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007316b  mov     r9d, eax; char *
0x18007316e  mov     edx, 120h; void *
0x180073173  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073178  lea     rcx, [rsp+2F0h+var_2C0]
0x18007317d  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x180073182  lea     rcx, [rsp+2F0h+var_2B0]
0x180073187  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18007318c  lea     rcx, [rsp+2F0h+ppszPathOut]
0x180073191  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x180073196  lea     rcx, [rsp+2F0h+pszPathIn]
0x18007319b  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800731a0  mov     eax, esi
0x1800731a2  jmp     short loc_1800731DE
0x1800731a4  mov     rcx, [rbp+1F8h]; this
0x1800731ab  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800731b2  mov     edx, 115h; void *
0x1800731b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800731bc  lea     rcx, [rsp+2F0h+var_2B0]
0x1800731c1  mov     ebx, eax
0x1800731c3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800731c8  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800731cd  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800731d2  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800731d7  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800731dc  mov     eax, ebx
0x1800731de  mov     rcx, [rbp+1F0h+var_40]
0x1800731e5  xor     rcx, rsp; StackCookie
0x1800731e8  call    __security_check_cookie
0x1800731ed  add     rsp, 2C0h
0x1800731f4  pop     r15
0x1800731f6  pop     r14
0x1800731f8  pop     r12
0x1800731fa  pop     rdi
0x1800731fb  pop     rsi
0x1800731fc  pop     rbx
0x1800731fd  pop     rbp
0x1800731fe  retn
```
