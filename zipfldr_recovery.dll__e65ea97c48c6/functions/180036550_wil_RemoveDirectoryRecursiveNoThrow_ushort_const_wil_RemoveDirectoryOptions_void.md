# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x180036550`
- end: `0x180036a67`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1303`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036550`
- `0x180046ec0`

## callees

- `0x180031e94`
- `0x180033aa8`
- `0x18003534c`
- `0x180036550`
- `0x180036a70`
- `0x180036f50`
- `0x180037958`
- `0x180046aa0`
- `0x180046b88`
- `0x180046c98`
- `0x180046cbc`
- `0x180046cdc`
- `0x180046ee0`
- `0x180047030`
- `0x18004709c`
- `0x1800470c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800367ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800367ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368d0`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180036645`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800366e7`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180036645`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800366e7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180036797`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800367ea`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180036797`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800367ea`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003668d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003668d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003680a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003680a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800367bf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800367bf`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180036778`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180036979`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180036778`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180036979`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800367df`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800367df`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180036854`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180036884`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180036854`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180036884`

## string_xrefs

- `0x180036603`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180036658`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180036742`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18003689e`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800368b8`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800368e1`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180036932`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180036965`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800369c7`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180036a0e`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(wil *a1, const unsigned __int16 *a2, void *a3)
{
  int v4; // r15d
  const WCHAR *v6; // rbx
  ULONG v7; // edi
  unsigned int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  HRESULT v12; // eax
  const unsigned __int16 *v13; // rdx
  char *FirstFileW; // rdi
  const char *v15; // r9
  HRESULT v16; // eax
  int v17; // eax
  const char *v18; // r9
  const char *v19; // r9
  DWORD FileAttributesW; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  const char *v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  DWORD v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rdx
  unsigned int LastError; // ebx
  unsigned int v33; // [rsp+20h] [rbp-E0h]
  char *v34; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszPathIn; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR v36; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPathOut; // [rsp+48h] [rbp-B8h] BYREF
  char FileInformation[8]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-A8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  pszPathIn = 0;
  v4 = (int)a2;
  if ( wil::is_extended_length_path(a1, a2) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v34,
      a1,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPathIn,
      &v34);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
    v6 = pszPathIn;
    if ( pszPathIn )
    {
      v7 = 16;
      goto LABEL_9;
    }
    v8 = -2147024882;
    v9 = 260;
    v10 = 2147942414LL;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)v10);
    goto LABEL_61;
  }
  v11 = wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
          a1,
          &pszPathIn);
  v8 = v11;
  if ( v11 < 0 )
  {
    v10 = (unsigned int)v11;
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
  v12 = PathAllocCombine(v6, L"*", v7, &ppszPathOut);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)(unsigned int)v12);
    goto LABEL_60;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v34 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                  v15);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v34);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
    return LastError;
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 && wil::path_is_dot_or_dotdot((wil *)FindFileData.cFileName, v13) )
      goto LABEL_31;
    v36 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v36,
      0);
    v16 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, &v36);
    v8 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v16);
      goto LABEL_58;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    wil::TryCreateFileCanRecurseIntoDirectory(&hFile, v36, &FindFileData);
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        v27 = GetLastError();
        if ( !v27 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v34);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          v8 = 0;
          goto LABEL_61;
        }
        v26 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x136,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                (const char *)v27,
                v33);
        goto LABEL_42;
      }
      if ( !RemoveDirectoryW(v36) )
      {
        v26 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                v18);
LABEL_42:
        v8 = v26;
        goto LABEL_19;
      }
    }
    else
    {
      v17 = wil::RemoveDirectoryRecursiveNoThrow(v36, v4 & 0xFFFFFFFE);
      v8 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
          (const char *)(unsigned int)v17);
LABEL_19:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_58;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_30:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
LABEL_31:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v22 = GetLastError();
      if ( v22 == 18 )
      {
        if ( (v4 & 1) != 0 )
          goto LABEL_56;
        if ( a3 == (void *)-1LL )
        {
          if ( !RemoveDirectoryW(v6) )
          {
            v24 = 381;
            goto LABEL_39;
          }
LABEL_56:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v34);
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
            v24 = 369;
LABEL_39:
            v25 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v24,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                    v23);
LABEL_40:
            v8 = v25;
            goto LABEL_59;
          }
          goto LABEL_56;
        }
        v29 = 5;
        v30 = 374;
      }
      else
      {
        if ( !v22 )
          goto LABEL_56;
        v29 = v22;
        v30 = 348;
      }
      v25 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v30,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)v29,
              v33);
      goto LABEL_40;
    }
  }
  if ( DeleteFileW(v36) )
    goto LABEL_30;
  if ( (v4 & 2) != 0 && GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(v36);
    if ( (FileAttributesW & 1) == 0 )
    {
      v28 = 325;
      goto LABEL_47;
    }
    v21 = FileAttributesW & 0xFFFFFFFE;
    if ( !v21 )
      v21 = 128;
    SetFileAttributesW(v36, v21);
    if ( !DeleteFileW(v36) )
    {
      v28 = 336;
      goto LABEL_47;
    }
    goto LABEL_30;
  }
  v28 = 321;
LABEL_47:
  v8 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v28,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
         v19);
LABEL_58:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
LABEL_59:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v34);
LABEL_60:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_61:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return v8;
}

```

## disassembly

```asm
0x180036550  mov     [rsp-8+arg_18], rbx
0x180036555  push    rbp
0x180036556  push    rsi
0x180036557  push    rdi
0x180036558  push    r14
0x18003655a  push    r15
0x18003655c  lea     rbp, [rsp-1C0h]
0x180036564  sub     rsp, 2C0h
0x18003656b  mov     rax, cs:__security_cookie
0x180036572  xor     rax, rsp
0x180036575  mov     [rbp+1E0h+var_30], rax
0x18003657c  mov     r14, r8
0x18003657f  mov     [rsp+2E0h+pszPathIn], 0
0x180036588  mov     r15d, edx
0x18003658b  mov     rbx, rcx
0x18003658e  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180036593  test    al, al
0x180036595  jz      short loc_1800365E1
0x180036597  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003659b  lea     rcx, [rsp+2E0h+var_2B0]
0x1800365a0  mov     rdx, rbx
0x1800365a3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800365a8  lea     rdx, [rsp+2E0h+var_2B0]
0x1800365ad  lea     rcx, [rsp+2E0h+pszPathIn]
0x1800365b2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800365b7  lea     rcx, [rsp+2E0h+var_2B0]
0x1800365bc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800365c1  mov     rbx, [rsp+2E0h+pszPathIn]
0x1800365c6  test    rbx, rbx
0x1800365c9  jz      short loc_1800365D2
0x1800365cb  mov     edi, 10h
0x1800365d0  jmp     short loc_18003661E
0x1800365d2  mov     esi, 8007000Eh
0x1800365d7  mov     edx, 104h
0x1800365dc  mov     r9d, esi
0x1800365df  jmp     short loc_1800365FC
0x1800365e1  lea     rdx, [rsp+2E0h+pszPathIn]
0x1800365e6  mov     rcx, rbx
0x1800365e9  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x1800365ee  mov     esi, eax
0x1800365f0  test    eax, eax
0x1800365f2  jns     short loc_180036614
0x1800365f4  mov     r9d, eax
0x1800365f7  mov     edx, 10Ch
0x1800365fc  mov     rcx, [rbp+1E8h]
0x180036603  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003660a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003660f  jmp     loc_1800369F9
0x180036614  mov     rbx, [rsp+2E0h+pszPathIn]
0x180036619  mov     edi, 1
0x18003661e  xor     edx, edx
0x180036620  mov     [rsp+2E0h+ppszPathOut], 0
0x180036629  lea     rcx, [rsp+2E0h+ppszPathOut]
0x18003662e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180036633  lea     r9, [rsp+2E0h+ppszPathOut]; ppszPathOut
0x180036638  mov     r8d, edi; dwFlags
0x18003663b  lea     rdx, asc_18007AB58; "*"
0x180036642  mov     rcx, rbx; pszPathIn
0x180036645  call    cs:__imp_PathAllocCombine
0x18003664b  mov     esi, eax
0x18003664d  test    eax, eax
0x18003664f  jns     short loc_180036671
0x180036651  mov     rcx, [rbp+1E8h]
0x180036658  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003665f  mov     r9d, eax
0x180036662  mov     edx, 111h
0x180036667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003666c  jmp     loc_1800369EF
0x180036671  xor     edx, edx; Val
0x180036673  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x180036678  mov     r8d, 250h; Size
0x18003667e  call    memset_0
0x180036683  mov     rcx, [rsp+2E0h+ppszPathOut]; lpFileName
0x180036688  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18003668d  call    cs:__imp_FindFirstFileW
0x180036693  mov     rdi, rax
0x180036696  mov     [rsp+2E0h+var_2B0], rax
0x18003669b  dec     rax
0x18003669e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800366a2  ja      loc_180036A07
0x1800366a8  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x1800366ad  jz      short loc_1800366C0
0x1800366af  lea     rcx, [rbp+1E0h+FindFileData.cFileName]; this
0x1800366b3  call    ?path_is_dot_or_dotdot@wil@@YA_NPEBG@Z; wil::path_is_dot_or_dotdot(ushort const *)
0x1800366b8  test    al, al
0x1800366ba  jnz     loc_180036802
0x1800366c0  xor     edx, edx
0x1800366c2  mov     [rsp+2E0h+var_2A0], 0
0x1800366cb  lea     rcx, [rsp+2E0h+var_2A0]
0x1800366d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800366d5  lea     r9, [rsp+2E0h+var_2A0]; ppszPathOut
0x1800366da  mov     r8d, 18h; dwFlags
0x1800366e0  lea     rdx, [rbp+1E0h+FindFileData.cFileName]; pszMore
0x1800366e4  mov     rcx, rbx; pszPathIn
0x1800366e7  call    cs:__imp_PathAllocCombine
0x1800366ed  mov     esi, eax
0x1800366ef  test    eax, eax
0x1800366f1  js      loc_1800369C0
0x1800366f7  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x1800366fc  jz      loc_180036792
0x180036702  mov     rdx, [rsp+2E0h+var_2A0]
0x180036707  lea     r8, [rsp+2E0h+FindFileData]
0x18003670c  lea     rcx, [rsp+2E0h+hFile]
0x180036711  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x180036716  mov     r8, [rsp+2E0h+hFile]
0x18003671b  lea     rax, [r8-1]
0x18003671f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180036723  ja      short loc_180036765
0x180036725  mov     rcx, [rsp+2E0h+var_2A0]
0x18003672a  mov     edx, r15d
0x18003672d  and     edx, 0FFFFFFFEh
0x180036730  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180036735  mov     esi, eax
0x180036737  test    eax, eax
0x180036739  jns     short loc_180036786
0x18003673b  mov     rcx, [rbp+1E8h]
0x180036742  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180036749  mov     r9d, eax
0x18003674c  mov     edx, 12Ch
0x180036751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036756  lea     rcx, [rsp+2E0h+hFile]
0x18003675b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180036760  jmp     loc_1800369DB
0x180036765  test    [rsp+2E0h+FindFileData.dwFileAttributes], 400h
0x18003676d  jz      loc_1800368D0
0x180036773  mov     rcx, [rsp+2E0h+var_2A0]; lpPathName
0x180036778  call    cs:__imp_RemoveDirectoryW
0x18003677e  test    eax, eax
0x180036780  jz      loc_1800368B1
0x180036786  lea     rcx, [rsp+2E0h+hFile]
0x18003678b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180036790  jmp     short loc_1800367F8
0x180036792  mov     rcx, [rsp+2E0h+var_2A0]; lpFileName
0x180036797  call    cs:__imp_DeleteFileW
0x18003679d  test    eax, eax
0x18003679f  jnz     short loc_1800367F8
0x1800367a1  test    r15b, 2
0x1800367a5  jz      loc_18003694C
0x1800367ab  call    cs:__imp_GetLastError
0x1800367b1  cmp     eax, 5
0x1800367b4  jnz     loc_18003694C
0x1800367ba  mov     rcx, [rsp+2E0h+var_2A0]; lpFileName
0x1800367bf  call    cs:__imp_GetFileAttributesW
0x1800367c5  test    al, 1
0x1800367c7  jz      loc_180036945
0x1800367cd  and     eax, 0FFFFFFFEh
0x1800367d0  mov     ecx, 80h
0x1800367d5  cmovz   eax, ecx
0x1800367d8  mov     rcx, [rsp+2E0h+var_2A0]; lpFileName
0x1800367dd  mov     edx, eax; dwFileAttributes
0x1800367df  call    cs:__imp_SetFileAttributesW
0x1800367e5  mov     rcx, [rsp+2E0h+var_2A0]; lpFileName
0x1800367ea  call    cs:__imp_DeleteFileW
0x1800367f0  test    eax, eax
0x1800367f2  jz      loc_180036926
0x1800367f8  lea     rcx, [rsp+2E0h+var_2A0]
0x1800367fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180036802  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x180036807  mov     rcx, rdi; hFindFile
0x18003680a  call    cs:__imp_FindNextFileW
0x180036810  test    eax, eax
0x180036812  jnz     loc_1800366A8
0x180036818  call    cs:__imp_GetLastError
0x18003681e  cmp     eax, 12h
0x180036821  jnz     loc_18003698D
0x180036827  test    r15b, 1
0x18003682b  jnz     loc_18003699B
0x180036831  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180036835  jz      loc_180036976
0x18003683b  lea     ebx, [rax-0Eh]
0x18003683e  mov     dword ptr [rsp+2E0h+hFile], 3
0x180036846  mov     r9d, ebx; dwBufferSize
0x180036849  lea     r8, [rsp+2E0h+hFile]; lpFileInformation
0x18003684e  lea     edx, [rax+3]; FileInformationClass
0x180036851  mov     rcx, r14; hFile
0x180036854  call    cs:__imp_SetFileInformationByHandle
0x18003685a  test    eax, eax
0x18003685c  jnz     loc_18003699B
0x180036862  call    cs:__imp_GetLastError
0x180036868  cmp     eax, 5
0x18003686b  jz      loc_180036953
0x180036871  lea     r9d, [rbx-3]; dwBufferSize
0x180036875  mov     [rsp+2E0h+FileInformation], 1
0x18003687a  lea     r8, [rsp+2E0h+FileInformation]; lpFileInformation
0x18003687f  mov     edx, ebx; FileInformationClass
0x180036881  mov     rcx, r14; hFile
0x180036884  call    cs:__imp_SetFileInformationByHandle
0x18003688a  test    eax, eax
0x18003688c  jnz     loc_18003699B
0x180036892  mov     edx, 171h; void *
0x180036897  mov     rcx, [rbp+1E8h]; this
0x18003689e  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800368a5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800368aa  mov     esi, eax
0x1800368ac  jmp     loc_1800369E5
0x1800368b1  mov     rcx, [rbp+1E8h]; this
0x1800368b8  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800368bf  mov     edx, 131h; void *
0x1800368c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800368c9  mov     esi, eax
0x1800368cb  jmp     loc_180036756
0x1800368d0  call    cs:__imp_GetLastError
0x1800368d6  test    eax, eax
0x1800368d8  jz      short loc_1800368F7
0x1800368da  mov     rcx, [rbp+1E8h]; this
0x1800368e1  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800368e8  mov     r9d, eax; char *
0x1800368eb  mov     edx, 136h; void *
0x1800368f0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800368f5  jmp     short loc_1800368C9
0x1800368f7  lea     rcx, [rsp+2E0h+hFile]
0x1800368fc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180036901  lea     rcx, [rsp+2E0h+var_2A0]
0x180036906  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003690b  lea     rcx, [rsp+2E0h+var_2B0]
0x180036910  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180036915  lea     rcx, [rsp+2E0h+ppszPathOut]
0x18003691a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003691f  xor     esi, esi
0x180036921  jmp     loc_1800369F9
0x180036926  mov     edx, 150h; void *
0x18003692b  mov     rcx, [rbp+1E8h]; this
0x180036932  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180036939  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003693e  mov     esi, eax
0x180036940  jmp     loc_1800369DB
0x180036945  mov     edx, 145h
0x18003694a  jmp     short loc_18003692B
0x18003694c  mov     edx, 141h
0x180036951  jmp     short loc_18003692B
0x180036953  mov     r9d, 5; char *
0x180036959  mov     edx, 176h; void *
0x18003695e  mov     rcx, [rbp+1E8h]; this
0x180036965  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003696c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036971  jmp     loc_1800368AA
0x180036976  mov     rcx, rbx; lpPathName
0x180036979  call    cs:__imp_RemoveDirectoryW
0x18003697f  test    eax, eax
0x180036981  jnz     short loc_18003699B
0x180036983  mov     edx, 17Dh
0x180036988  jmp     loc_180036897
0x18003698d  test    eax, eax
0x18003698f  jz      short loc_18003699B
0x180036991  mov     r9d, eax
0x180036994  mov     edx, 15Ch
0x180036999  jmp     short loc_18003695E
0x18003699b  lea     rcx, [rsp+2E0h+var_2B0]
0x1800369a0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800369a5  lea     rcx, [rsp+2E0h+ppszPathOut]
0x1800369aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800369af  lea     rcx, [rsp+2E0h+pszPathIn]
0x1800369b4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800369b9  xor     eax, eax
0x1800369bb  jmp     loc_180036A41
0x1800369c0  mov     rcx, [rbp+1E8h]
0x1800369c7  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800369ce  mov     r9d, eax
0x1800369d1  mov     edx, 120h
0x1800369d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800369db  lea     rcx, [rsp+2E0h+var_2A0]
0x1800369e0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800369e5  lea     rcx, [rsp+2E0h+var_2B0]
0x1800369ea  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800369ef  lea     rcx, [rsp+2E0h+ppszPathOut]
0x1800369f4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800369f9  lea     rcx, [rsp+2E0h+pszPathIn]
0x1800369fe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180036a03  mov     eax, esi
0x180036a05  jmp     short loc_180036A41
0x180036a07  mov     rcx, [rbp+1E8h]; this
0x180036a0e  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180036a15  mov     edx, 115h; void *
0x180036a1a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036a1f  lea     rcx, [rsp+2E0h+var_2B0]
0x180036a24  mov     ebx, eax
0x180036a26  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180036a2b  lea     rcx, [rsp+2E0h+ppszPathOut]
0x180036a30  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180036a35  lea     rcx, [rsp+2E0h+pszPathIn]
0x180036a3a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180036a3f  mov     eax, ebx
0x180036a41  mov     rcx, [rbp+1E0h+var_30]
0x180036a48  xor     rcx, rsp; StackCookie
0x180036a4b  call    __security_check_cookie
0x180036a50  mov     rbx, [rsp+2E0h+arg_18]
0x180036a58  add     rsp, 2C0h
0x180036a5f  pop     r15
0x180036a61  pop     r14
0x180036a63  pop     rdi
0x180036a64  pop     rsi
0x180036a65  pop     rbp
0x180036a66  retn
```
