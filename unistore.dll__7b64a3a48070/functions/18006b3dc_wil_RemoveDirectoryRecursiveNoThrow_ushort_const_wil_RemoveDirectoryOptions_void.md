# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x18006b3dc`
- end: `0x18006b8eb`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1295`
- prototype: ``
- caller_count: `6`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016cc0`
- `0x180016d7c`
- `0x1800664d0`
- `0x18006b3dc`
- `0x18007dec0`
- `0x18007df9c`

## callees

- `0x180028ef4`
- `0x18005e5c8`
- `0x18005e69c`
- `0x18005e6d4`
- `0x18006a33c`
- `0x18006b3dc`
- `0x18006b8f4`
- `0x18006b91c`
- `0x18006b990`
- `0x18006b9b4`
- `0x18006b9d4`
- `0x18006bd68`
- `0x18007faac`
- `0x1800c50aa`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b6f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b6f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b766`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18006b4cb`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18006b57d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18006b4cb`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18006b57d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006b60e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006b802`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006b60e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006b802`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006b6a0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006b6a0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006b513`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006b513`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006b655`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006b655`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18006b675`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18006b675`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006b62d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006b680`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006b62d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006b680`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18006b6ea`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18006b71a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18006b6ea`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18006b71a`

## string_xrefs

- `0x18006b48d`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18006b4de`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18006b5d8`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18006b734`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18006b74e`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18006b7c2`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18006b850`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18006b897`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

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
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v37);
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
        v34);
      goto LABEL_64;
    }
    v10 = 16;
  }
  else
  {
    v11 = wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            (__int64)a1,
            (__int64)&pszPathIn);
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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                  v14);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&ppszPathOut);
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&pszPathIn);
    return LastError;
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || !FindFileData.cFileName[2] && FindFileData.cFileName[1] == 46) )
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
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
          auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v35);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
          auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&ppszPathOut);
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
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                v17);
LABEL_45:
        v7 = v26;
        goto LABEL_22;
      }
    }
    else
    {
      v16 = wil::RemoveDirectoryRecursiveNoThrow(v35, v4 & 0xFFFFFFFE);
      v7 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
          (const char *)(unsigned int)v16,
          v34);
LABEL_22:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_61;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_33:
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v35);
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
          auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&ppszPathOut);
          auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&pszPathIn);
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
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
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
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
         v18);
LABEL_61:
  auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v35);
LABEL_62:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v37);
LABEL_63:
  auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&ppszPathOut);
LABEL_64:
  auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&pszPathIn);
  return v7;
}

```

## disassembly

```asm
0x18006b3dc  push    rbp
0x18006b3de  push    rbx
0x18006b3df  push    rsi
0x18006b3e0  push    rdi
0x18006b3e1  push    r12
0x18006b3e3  push    r14
0x18006b3e5  push    r15
0x18006b3e7  lea     rbp, [rsp-1C0h]
0x18006b3ef  sub     rsp, 2C0h
0x18006b3f6  mov     rax, cs:__security_cookie
0x18006b3fd  xor     rax, rsp
0x18006b400  mov     [rbp+1F0h+var_40], rax
0x18006b407  xor     r12d, r12d
0x18006b40a  mov     r14, r8
0x18006b40d  mov     [rsp+2F0h+pszPathIn], r12
0x18006b412  mov     r15d, edx
0x18006b415  mov     rbx, rcx
0x18006b418  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x18006b41d  test    al, al
0x18006b41f  jz      short loc_18006B46B
0x18006b421  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006b425  lea     rcx, [rsp+2F0h+var_2B0]
0x18006b42a  mov     rdx, rbx
0x18006b42d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18006b432  lea     rdx, [rsp+2F0h+var_2B0]
0x18006b437  lea     rcx, [rsp+2F0h+pszPathIn]
0x18006b43c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18006b441  lea     rcx, [rsp+2F0h+var_2B0]
0x18006b446  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b44b  mov     rbx, [rsp+2F0h+pszPathIn]
0x18006b450  test    rbx, rbx
0x18006b453  jnz     short loc_18006B464
0x18006b455  mov     esi, 8007000Eh
0x18006b45a  mov     edx, 104h
0x18006b45f  mov     r9d, esi
0x18006b462  jmp     short loc_18006B486
0x18006b464  mov     edi, 10h
0x18006b469  jmp     short loc_18006B4A8
0x18006b46b  lea     rdx, [rsp+2F0h+pszPathIn]
0x18006b470  mov     rcx, rbx
0x18006b473  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x18006b478  mov     esi, eax
0x18006b47a  test    eax, eax
0x18006b47c  jns     short loc_18006B49E
0x18006b47e  mov     r9d, eax; char *
0x18006b481  mov     edx, 10Ch; void *
0x18006b486  mov     rcx, [rbp+1F8h]; this
0x18006b48d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006b494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b499  jmp     loc_18006B882
0x18006b49e  mov     rbx, [rsp+2F0h+pszPathIn]
0x18006b4a3  mov     edi, 1
0x18006b4a8  xor     edx, edx
0x18006b4aa  mov     [rsp+2F0h+ppszPathOut], r12
0x18006b4af  lea     rcx, [rsp+2F0h+ppszPathOut]
0x18006b4b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006b4b9  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x18006b4be  mov     r8d, edi; dwFlags
0x18006b4c1  lea     rdx, pszMore; "*"
0x18006b4c8  mov     rcx, rbx; pszPathIn
0x18006b4cb  call    cs:__imp_PathAllocCombine
0x18006b4d1  mov     esi, eax
0x18006b4d3  test    eax, eax
0x18006b4d5  jns     short loc_18006B4F7
0x18006b4d7  mov     rcx, [rbp+1F8h]; this
0x18006b4de  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006b4e5  mov     r9d, eax; char *
0x18006b4e8  mov     edx, 111h; void *
0x18006b4ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b4f2  jmp     loc_18006B878
0x18006b4f7  xor     edx, edx; Val
0x18006b4f9  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x18006b4fe  mov     r8d, 250h; Size
0x18006b504  call    memset_0
0x18006b509  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x18006b50e  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18006b513  call    cs:__imp_FindFirstFileW
0x18006b519  mov     rdi, rax
0x18006b51c  mov     [rsp+2F0h+var_2B0], rax
0x18006b521  dec     rax
0x18006b524  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006b528  ja      loc_18006B890
0x18006b52e  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x18006b533  jz      short loc_18006B55A
0x18006b535  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x18006b53a  jnz     short loc_18006B55A
0x18006b53c  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x18006b540  test    ax, ax
0x18006b543  jz      loc_18006B698
0x18006b549  cmp     [rbp+1F0h+FindFileData.cFileName+4], r12w
0x18006b54e  jnz     short loc_18006B55A
0x18006b550  cmp     ax, 2Eh ; '.'
0x18006b554  jz      loc_18006B698
0x18006b55a  xor     edx, edx
0x18006b55c  mov     [rsp+2F0h+var_2C0], r12
0x18006b561  lea     rcx, [rsp+2F0h+var_2C0]
0x18006b566  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006b56b  lea     r9, [rsp+2F0h+var_2C0]; ppszPathOut
0x18006b570  mov     r8d, 18h; dwFlags
0x18006b576  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x18006b57a  mov     rcx, rbx; pszPathIn
0x18006b57d  call    cs:__imp_PathAllocCombine
0x18006b583  mov     esi, eax
0x18006b585  test    eax, eax
0x18006b587  js      loc_18006B849
0x18006b58d  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x18006b592  jz      loc_18006B628
0x18006b598  mov     rdx, [rsp+2F0h+var_2C0]
0x18006b59d  lea     r8, [rsp+2F0h+FindFileData]
0x18006b5a2  lea     rcx, [rsp+2F0h+hFile]
0x18006b5a7  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x18006b5ac  mov     r8, [rsp+2F0h+hFile]
0x18006b5b1  lea     rax, [r8-1]
0x18006b5b5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006b5b9  ja      short loc_18006B5FB
0x18006b5bb  mov     rcx, [rsp+2F0h+var_2C0]
0x18006b5c0  mov     edx, r15d
0x18006b5c3  and     edx, 0FFFFFFFEh
0x18006b5c6  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18006b5cb  mov     esi, eax
0x18006b5cd  test    eax, eax
0x18006b5cf  jns     short loc_18006B61C
0x18006b5d1  mov     rcx, [rbp+1F8h]; this
0x18006b5d8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006b5df  mov     r9d, eax; char *
0x18006b5e2  mov     edx, 12Ch; void *
0x18006b5e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b5ec  lea     rcx, [rsp+2F0h+hFile]
0x18006b5f1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b5f6  jmp     loc_18006B864
0x18006b5fb  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x18006b603  jz      loc_18006B766
0x18006b609  mov     rcx, [rsp+2F0h+var_2C0]; lpPathName
0x18006b60e  call    cs:__imp_RemoveDirectoryW
0x18006b614  test    eax, eax
0x18006b616  jz      loc_18006B747
0x18006b61c  lea     rcx, [rsp+2F0h+hFile]
0x18006b621  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b626  jmp     short loc_18006B68E
0x18006b628  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x18006b62d  call    cs:__imp_DeleteFileW
0x18006b633  test    eax, eax
0x18006b635  jnz     short loc_18006B68E
0x18006b637  test    r15b, 2
0x18006b63b  jz      loc_18006B7DC
0x18006b641  call    cs:__imp_GetLastError
0x18006b647  cmp     eax, 5
0x18006b64a  jnz     loc_18006B7DC
0x18006b650  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x18006b655  call    cs:__imp_GetFileAttributesW
0x18006b65b  test    al, 1
0x18006b65d  jz      loc_18006B7D5
0x18006b663  and     eax, 0FFFFFFFEh
0x18006b666  mov     ecx, 80h
0x18006b66b  cmovz   eax, ecx
0x18006b66e  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x18006b673  mov     edx, eax; dwFileAttributes
0x18006b675  call    cs:__imp_SetFileAttributesW
0x18006b67b  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x18006b680  call    cs:__imp_DeleteFileW
0x18006b686  test    eax, eax
0x18006b688  jz      loc_18006B7B6
0x18006b68e  lea     rcx, [rsp+2F0h+var_2C0]
0x18006b693  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b698  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18006b69d  mov     rcx, rdi; hFindFile
0x18006b6a0  call    cs:__imp_FindNextFileW
0x18006b6a6  test    eax, eax
0x18006b6a8  jnz     loc_18006B52E
0x18006b6ae  call    cs:__imp_GetLastError
0x18006b6b4  cmp     eax, 12h
0x18006b6b7  jnz     loc_18006B816
0x18006b6bd  test    r15b, 1
0x18006b6c1  jnz     loc_18006B824
0x18006b6c7  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18006b6cb  jz      loc_18006B7FF
0x18006b6d1  lea     ebx, [rax-0Eh]
0x18006b6d4  mov     dword ptr [rsp+2F0h+hFile], 3
0x18006b6dc  mov     r9d, ebx; dwBufferSize
0x18006b6df  lea     r8, [rsp+2F0h+hFile]; lpFileInformation
0x18006b6e4  lea     edx, [rax+3]; FileInformationClass
0x18006b6e7  mov     rcx, r14; hFile
0x18006b6ea  call    cs:__imp_SetFileInformationByHandle
0x18006b6f0  test    eax, eax
0x18006b6f2  jnz     loc_18006B824
0x18006b6f8  call    cs:__imp_GetLastError
0x18006b6fe  cmp     eax, 5
0x18006b701  jz      loc_18006B7E3
0x18006b707  lea     r9d, [rbx-3]; dwBufferSize
0x18006b70b  mov     [rsp+2F0h+FileInformation], 1
0x18006b710  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x18006b715  mov     edx, ebx; FileInformationClass
0x18006b717  mov     rcx, r14; hFile
0x18006b71a  call    cs:__imp_SetFileInformationByHandle
0x18006b720  test    eax, eax
0x18006b722  jnz     loc_18006B824
0x18006b728  mov     edx, 171h; void *
0x18006b72d  mov     rcx, [rbp+1F8h]; this
0x18006b734  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006b73b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006b740  mov     esi, eax
0x18006b742  jmp     loc_18006B86E
0x18006b747  mov     rcx, [rbp+1F8h]; this
0x18006b74e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006b755  mov     edx, 131h; void *
0x18006b75a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006b75f  mov     esi, eax
0x18006b761  jmp     loc_18006B5EC
0x18006b766  call    cs:__imp_GetLastError
0x18006b76c  test    eax, eax
0x18006b76e  jz      short loc_18006B786
0x18006b770  mov     rcx, [rbp+1F8h]; this
0x18006b777  mov     r9d, eax; char *
0x18006b77a  mov     edx, 136h; void *
0x18006b77f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006b784  jmp     short loc_18006B75F
0x18006b786  lea     rcx, [rsp+2F0h+hFile]
0x18006b78b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b790  lea     rcx, [rsp+2F0h+var_2C0]
0x18006b795  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b79a  lea     rcx, [rsp+2F0h+var_2B0]
0x18006b79f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18006b7a4  lea     rcx, [rsp+2F0h+ppszPathOut]
0x18006b7a9  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b7ae  mov     esi, r12d
0x18006b7b1  jmp     loc_18006B882
0x18006b7b6  mov     edx, 150h; void *
0x18006b7bb  mov     rcx, [rbp+1F8h]; this
0x18006b7c2  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006b7c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006b7ce  mov     esi, eax
0x18006b7d0  jmp     loc_18006B864
0x18006b7d5  mov     edx, 145h
0x18006b7da  jmp     short loc_18006B7BB
0x18006b7dc  mov     edx, 141h
0x18006b7e1  jmp     short loc_18006B7BB
0x18006b7e3  mov     edx, 176h; void *
0x18006b7e8  mov     r9d, 5; char *
0x18006b7ee  mov     rcx, [rbp+1F8h]; this
0x18006b7f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006b7fa  jmp     loc_18006B740
0x18006b7ff  mov     rcx, rbx; lpPathName
0x18006b802  call    cs:__imp_RemoveDirectoryW
0x18006b808  test    eax, eax
0x18006b80a  jnz     short loc_18006B824
0x18006b80c  mov     edx, 17Dh
0x18006b811  jmp     loc_18006B72D
0x18006b816  test    eax, eax
0x18006b818  jz      short loc_18006B824
0x18006b81a  mov     r9d, eax
0x18006b81d  mov     edx, 15Ch
0x18006b822  jmp     short loc_18006B7EE
0x18006b824  lea     rcx, [rsp+2F0h+var_2B0]
0x18006b829  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18006b82e  lea     rcx, [rsp+2F0h+ppszPathOut]
0x18006b833  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b838  lea     rcx, [rsp+2F0h+pszPathIn]
0x18006b83d  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b842  xor     eax, eax
0x18006b844  jmp     loc_18006B8CA
0x18006b849  mov     rcx, [rbp+1F8h]; this
0x18006b850  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006b857  mov     r9d, eax; char *
0x18006b85a  mov     edx, 120h; void *
0x18006b85f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b864  lea     rcx, [rsp+2F0h+var_2C0]
0x18006b869  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b86e  lea     rcx, [rsp+2F0h+var_2B0]
0x18006b873  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18006b878  lea     rcx, [rsp+2F0h+ppszPathOut]
0x18006b87d  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b882  lea     rcx, [rsp+2F0h+pszPathIn]
0x18006b887  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b88c  mov     eax, esi
0x18006b88e  jmp     short loc_18006B8CA
0x18006b890  mov     rcx, [rbp+1F8h]; this
0x18006b897  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006b89e  mov     edx, 115h; void *
0x18006b8a3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006b8a8  lea     rcx, [rsp+2F0h+var_2B0]
0x18006b8ad  mov     ebx, eax
0x18006b8af  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18006b8b4  lea     rcx, [rsp+2F0h+ppszPathOut]
0x18006b8b9  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b8be  lea     rcx, [rsp+2F0h+pszPathIn]
0x18006b8c3  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18006b8c8  mov     eax, ebx
0x18006b8ca  mov     rcx, [rbp+1F0h+var_40]
0x18006b8d1  xor     rcx, rsp; StackCookie
0x18006b8d4  call    __security_check_cookie
0x18006b8d9  add     rsp, 2C0h
0x18006b8e0  pop     r15
0x18006b8e2  pop     r14
0x18006b8e4  pop     r12
0x18006b8e6  pop     rdi
0x18006b8e7  pop     rsi
0x18006b8e8  pop     rbx
0x18006b8e9  pop     rbp
0x18006b8ea  retn
```
