# CTemplateDownloader::CopyLocallyUpdateableFile(ushort const *)

- ea: `0x1801ab870`
- end: `0x1801abbc7`
- name: `?CopyLocallyUpdateableFile@CTemplateDownloader@@QEAAXPEBG@Z`
- size: `855`
- prototype: `void(CTemplateDownloader *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801ad168`

## callees

- `0x180027cc8`
- `0x180027ee4`
- `0x180038274`
- `0x180074b74`
- `0x1800887f8`
- `0x18013d330`
- `0x18013df8c`
- `0x1801ab870`
- `0x1801ac584`
- `0x1801ac678`
- `0x1801ad614`
- `0x1801ad6a8`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801ab98e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801aba59`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801abb00`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801ab98e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801aba59`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801abb00`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801abb66`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801abb66`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801abb53`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801abb53`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801aba99`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801aba99`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801ab967`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801ab967`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801abb11`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801abb11`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801ab9c8`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801ab9c8`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801aba0d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801aba0d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801abb1b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801abb1b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x1801ab8d4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x1801ab8d4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801abae3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801abae3`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1801ab958`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1801ab958`

## string_xrefs

- `0x1801aba1f`: `%s*.dll`
- `0x1801ababb`: `%s.dll`

## pseudocode

```c
void __fastcall CTemplateDownloader::CopyLocallyUpdateableFile(CTemplateDownloader *this, const unsigned __int16 *a2)
{
  unsigned __int64 i; // rbx
  __int64 v5; // r8
  const WCHAR *v6; // rcx
  unsigned __int16 **v7; // r8
  unsigned __int16 **v8; // rdx
  const WCHAR *v9; // rsi
  __int64 v10; // r8
  HANDLE FirstFile; // rax
  const unsigned __int16 *v12; // r8
  HANDLE hFindFile; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h]
  __int64 v16; // [rsp+48h] [rbp-B8h]
  LPCWSTR pszPath; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpExistingFileName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  _BYTE v23[8]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR pszStr2[3]; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR pszMore[4]; // [rsp+A0h] [rbp-60h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszPathOut[264]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR FileName[264]; // [rsp+520h] [rbp+420h] BYREF
  WCHAR v29[264]; // [rsp+730h] [rbp+630h] BYREF

  for ( i = 0; i < *((_QWORD *)this + 7); ++i )
  {
    v5 = -1;
    v6 = *(const WCHAR **)(*((_QWORD *)this + 6) + 8 * i);
    do
      ++v5;
    while ( v6[v5] );
    if ( !StrCmpNIW(v6, a2, v5) )
    {
      lpExistingFileName = 0;
      v21 = 0;
      v22 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpExistingFileName);
      v21 = -1;
      v22 = -1;
      if ( (int)TemplateDownloadHelpers::GetFilePathForDownloadedTemplate(
                  a2,
                  (const unsigned __int16 *)&lpExistingFileName,
                  v7) >= 0 )
      {
        pszPath = 0;
        v18 = 0;
        v19 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
        v18 = -1;
        v19 = -1;
        if ( (int)TemplateDownloadHelpers::GetLocalDirectoryPath((TemplateDownloadHelpers *)&pszPath, v8) >= 0 )
        {
          v9 = pszPath;
          if ( (PathIsDirectoryW(pszPath) || CreateDirectoryW(v9, 0))
            && PathCchCombine(pszPathOut, 0x104u, v9, *(PCWSTR *)(*((_QWORD *)this + 6) + 8 * i)) >= 0
            && StringCchCatW(pszPathOut, 0x104u, L".dll") >= 0
            && CopyFileW(lpExistingFileName, pszPathOut, 0) )
          {
            ppszPath = 0;
            v15 = 0;
            v16 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
            v15 = -1;
            v16 = -1;
            if ( SHGetKnownFolderPath(&FOLDERID_SearchTemplates, 0x8000u, 0, &ppszPath) >= 0 )
            {
              v10 = *((_QWORD *)this + 6);
              memset(pszMore, 0, 24);
              if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                          pszMore,
                          L"%s*.dll",
                          *(_QWORD *)(v10 + 8 * i)) >= 0
                && PathCchCombine(FileName, 0x104u, ppszPath, pszMore[0]) >= 0 )
              {
                memset_0(&FindFileData, 0, sizeof(FindFileData));
                hFindFile = 0;
                FirstFile = FindFirstFileExW(FileName, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
                if ( (int)ResultFromWin32Handle(FirstFile, &hFindFile) >= 0 )
                {
                  memset(pszStr2, 0, sizeof(pszStr2));
                  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                              pszStr2,
                              L"%s.dll",
                              a2) >= 0 )
                  {
                    do
                    {
                      if ( StrCmpICW(FindFileData.cFileName, pszStr2[0]) )
                      {
                        if ( PathCchCombine(v29, 0x104u, ppszPath, FindFileData.cFileName) >= 0 )
                        {
                          DeleteFileW(v29);
                          PathRemoveExtensionW(FindFileData.cFileName);
                          wil::AcquireSRWLockExclusive(v23, (char *)this + 168);
                          TemplateDownloadHelpers::RemoveTemplateFromArray(
                            (CTemplateDownloader *)((char *)this + 176),
                            (struct CSimpleCaseInsensitiveOrdinalStringArray *)FindFileData.cFileName,
                            v12);
                          Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v23);
                        }
                      }
                    }
                    while ( FindNextFileW(hFindFile, &FindFileData) );
                  }
                  FindClose(hFindFile);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszStr2);
                }
              }
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszMore);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
          }
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpExistingFileName);
      return;
    }
  }
}

```

## disassembly

```asm
0x1801ab870  mov     [rsp-8+arg_10], rbx
0x1801ab875  mov     [rsp-8+arg_18], rsi
0x1801ab87a  push    rbp
0x1801ab87b  push    rdi
0x1801ab87c  push    r12
0x1801ab87e  push    r14
0x1801ab880  push    r15
0x1801ab882  lea     rbp, [rsp-850h]
0x1801ab88a  sub     rsp, 950h
0x1801ab891  mov     rax, cs:__security_cookie
0x1801ab898  xor     rax, rsp
0x1801ab89b  mov     [rbp+870h+var_30], rax
0x1801ab8a2  xor     r15d, r15d
0x1801ab8a5  mov     r14, rdx
0x1801ab8a8  mov     ebx, r15d
0x1801ab8ab  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801ab8af  mov     rdi, rcx
0x1801ab8b2  cmp     rbx, [rdi+38h]
0x1801ab8b6  jnb     loc_1801ABB9C
0x1801ab8bc  mov     rax, [rdi+30h]
0x1801ab8c0  mov     r8, r12
0x1801ab8c3  mov     rcx, [rax+rbx*8]; psz1
0x1801ab8c7  inc     r8; nChar
0x1801ab8ca  cmp     [rcx+r8*2], r15w
0x1801ab8cf  jnz     short loc_1801AB8C7
0x1801ab8d1  mov     rdx, r14; psz2
0x1801ab8d4  call    cs:__imp_StrCmpNIW
0x1801ab8da  test    eax, eax
0x1801ab8dc  jz      short loc_1801AB8E3
0x1801ab8de  inc     rbx
0x1801ab8e1  jmp     short loc_1801AB8B2
0x1801ab8e3  lea     rcx, [rsp+970h+lpExistingFileName]
0x1801ab8e8  mov     [rsp+970h+lpExistingFileName], r15
0x1801ab8ed  mov     [rsp+970h+var_900], r15
0x1801ab8f2  mov     [rsp+970h+var_8F8], r15
0x1801ab8f7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801ab8fc  lea     rdx, [rsp+970h+lpExistingFileName]; unsigned __int16 *
0x1801ab901  mov     [rsp+970h+var_900], r12
0x1801ab906  mov     rcx, r14; pszMore
0x1801ab909  mov     [rsp+970h+var_8F8], r12
0x1801ab90e  call    ?GetFilePathForDownloadedTemplate@TemplateDownloadHelpers@@YAJPEBGPEAPEAG@Z; TemplateDownloadHelpers::GetFilePathForDownloadedTemplate(ushort const *,ushort * *)
0x1801ab913  test    eax, eax
0x1801ab915  js      loc_1801ABB92
0x1801ab91b  lea     rcx, [rsp+970h+pszPath]
0x1801ab920  mov     [rsp+970h+pszPath], r15
0x1801ab925  mov     [rsp+970h+var_918], r15
0x1801ab92a  mov     [rsp+970h+var_910], r15
0x1801ab92f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801ab934  lea     rcx, [rsp+970h+pszPath]; this
0x1801ab939  mov     [rsp+970h+var_918], r12
0x1801ab93e  mov     [rsp+970h+var_910], r12
0x1801ab943  call    ?GetLocalDirectoryPath@TemplateDownloadHelpers@@YAJPEAPEAG@Z; TemplateDownloadHelpers::GetLocalDirectoryPath(ushort * *)
0x1801ab948  test    eax, eax
0x1801ab94a  js      loc_1801ABB88
0x1801ab950  mov     rsi, [rsp+970h+pszPath]
0x1801ab955  mov     rcx, rsi; pszPath
0x1801ab958  call    cs:__imp_PathIsDirectoryW
0x1801ab95e  test    eax, eax
0x1801ab960  jnz     short loc_1801AB975
0x1801ab962  xor     edx, edx; lpSecurityAttributes
0x1801ab964  mov     rcx, rsi; lpPathName
0x1801ab967  call    cs:__imp_CreateDirectoryW
0x1801ab96d  test    eax, eax
0x1801ab96f  jz      loc_1801ABB88
0x1801ab975  mov     r9, [rdi+30h]
0x1801ab979  lea     rcx, [rbp+870h+pszPathOut]; pszPathOut
0x1801ab980  mov     r8, rsi; pszPathIn
0x1801ab983  mov     esi, 104h
0x1801ab988  mov     edx, esi; cchPathOut
0x1801ab98a  mov     r9, [r9+rbx*8]; pszMore
0x1801ab98e  call    cs:__imp_PathCchCombine
0x1801ab994  test    eax, eax
0x1801ab996  js      loc_1801ABB88
0x1801ab99c  lea     r8, aDll_0; ".dll"
0x1801ab9a3  mov     edx, esi; unsigned __int64
0x1801ab9a5  lea     rcx, [rbp+870h+pszPathOut]; unsigned __int16 *
0x1801ab9ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801ab9b1  test    eax, eax
0x1801ab9b3  js      loc_1801ABB88
0x1801ab9b9  mov     rcx, [rsp+970h+lpExistingFileName]; lpExistingFileName
0x1801ab9be  lea     rdx, [rbp+870h+pszPathOut]; lpNewFileName
0x1801ab9c5  xor     r8d, r8d; bFailIfExists
0x1801ab9c8  call    cs:__imp_CopyFileW
0x1801ab9ce  test    eax, eax
0x1801ab9d0  jz      loc_1801ABB88
0x1801ab9d6  lea     rcx, [rsp+970h+ppszPath]
0x1801ab9db  mov     [rsp+970h+ppszPath], r15
0x1801ab9e0  mov     [rsp+970h+var_930], r15
0x1801ab9e5  mov     [rsp+970h+var_928], r15
0x1801ab9ea  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801ab9ef  lea     r9, [rsp+970h+ppszPath]; ppszPath
0x1801ab9f4  mov     [rsp+970h+var_930], r12
0x1801ab9f9  xor     r8d, r8d; hToken
0x1801ab9fc  mov     [rsp+970h+var_928], r12
0x1801aba01  mov     edx, 8000h; dwFlags
0x1801aba06  lea     rcx, FOLDERID_SearchTemplates; rfid
0x1801aba0d  call    cs:__imp_SHGetKnownFolderPath
0x1801aba13  test    eax, eax
0x1801aba15  js      loc_1801ABB7E
0x1801aba1b  mov     r8, [rdi+30h]
0x1801aba1f  lea     rdx, aSDll; "%s*.dll"
0x1801aba26  lea     rcx, [rbp+870h+pszMore]
0x1801aba2a  mov     [rbp+870h+pszMore], r15
0x1801aba2e  mov     [rbp+870h+var_8C8], r15
0x1801aba32  mov     [rbp+870h+var_8C0], r15
0x1801aba36  mov     r8, [r8+rbx*8]
0x1801aba3a  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801aba3f  test    eax, eax
0x1801aba41  js      loc_1801ABB75
0x1801aba47  mov     r9, [rbp+870h+pszMore]; pszMore
0x1801aba4b  lea     rcx, [rbp+870h+FileName]; pszPathOut
0x1801aba52  mov     r8, [rsp+970h+ppszPath]; pszPathIn
0x1801aba57  mov     edx, esi; cchPathOut
0x1801aba59  call    cs:__imp_PathCchCombine
0x1801aba5f  test    eax, eax
0x1801aba61  js      loc_1801ABB75
0x1801aba67  xor     edx, edx; Val
0x1801aba69  lea     rcx, [rbp+870h+FindFileData]; void *
0x1801aba6d  mov     r8d, 250h; Size
0x1801aba73  call    memset_0
0x1801aba78  xor     r9d, r9d; fSearchOp
0x1801aba7b  mov     [rsp+970h+dwAdditionalFlags], r15d; dwAdditionalFlags
0x1801aba80  lea     r8, [rbp+870h+FindFileData]; lpFindFileData
0x1801aba84  mov     [rsp+970h+hFindFile], r15
0x1801aba89  lea     rcx, [rbp+870h+FileName]; lpFileName
0x1801aba90  mov     [rsp+970h+lpSearchFilter], r15; lpSearchFilter
0x1801aba95  lea     edx, [r9+1]; fInfoLevelId
0x1801aba99  call    cs:__imp_FindFirstFileExW
0x1801aba9f  mov     rcx, rax; void *
0x1801abaa2  lea     rdx, [rsp+970h+hFindFile]; void **
0x1801abaa7  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x1801abaac  test    eax, eax
0x1801abaae  js      loc_1801ABB75
0x1801abab4  mov     r8, r14
0x1801abab7  mov     [rbp+870h+pszStr2], r15
0x1801ababb  lea     rdx, aSDll_0; "%s.dll"
0x1801abac2  mov     [rbp+870h+var_8E0], r15
0x1801abac6  lea     rcx, [rbp+870h+pszStr2]
0x1801abaca  mov     [rbp+870h+var_8D8], r15
0x1801abace  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801abad3  test    eax, eax
0x1801abad5  js      loc_1801ABB61
0x1801abadb  mov     rdx, [rbp+870h+pszStr2]; pszStr2
0x1801abadf  lea     rcx, [rbp+870h+pszStr1]; pszStr1
0x1801abae3  call    cs:__imp_StrCmpICW
0x1801abae9  test    eax, eax
0x1801abaeb  jz      short loc_1801ABB4A
0x1801abaed  mov     r8, [rsp+970h+ppszPath]; pszPathIn
0x1801abaf2  lea     r9, [rbp+870h+pszStr1]; pszMore
0x1801abaf6  mov     rdx, rsi; cchPathOut
0x1801abaf9  lea     rcx, [rbp+870h+var_240]; pszPathOut
0x1801abb00  call    cs:__imp_PathCchCombine
0x1801abb06  test    eax, eax
0x1801abb08  js      short loc_1801ABB4A
0x1801abb0a  lea     rcx, [rbp+870h+var_240]; lpFileName
0x1801abb11  call    cs:__imp_DeleteFileW
0x1801abb17  lea     rcx, [rbp+870h+pszStr1]; pszPath
0x1801abb1b  call    cs:__imp_PathRemoveExtensionW
0x1801abb21  lea     rdx, [rdi+0A8h]
0x1801abb28  lea     rcx, [rbp+870h+var_8F0]
0x1801abb2c  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801abb31  lea     rcx, [rdi+0B0h]; this
0x1801abb38  lea     rdx, [rbp+870h+pszStr1]; struct CSimpleCaseInsensitiveOrdinalStringArray *
0x1801abb3c  call    ?RemoveTemplateFromArray@TemplateDownloadHelpers@@YAJAEAVCSimpleCaseInsensitiveOrdinalStringArray@@PEBG@Z; TemplateDownloadHelpers::RemoveTemplateFromArray(CSimpleCaseInsensitiveOrdinalStringArray &,ushort const *)
0x1801abb41  lea     rcx, [rbp+870h+var_8F0]; this
0x1801abb45  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801abb4a  mov     rcx, [rsp+970h+hFindFile]; hFindFile
0x1801abb4f  lea     rdx, [rbp+870h+FindFileData]; lpFindFileData
0x1801abb53  call    cs:__imp_FindNextFileW
0x1801abb59  test    eax, eax
0x1801abb5b  jnz     loc_1801ABADB
0x1801abb61  mov     rcx, [rsp+970h+hFindFile]; hFindFile
0x1801abb66  call    cs:__imp_FindClose
0x1801abb6c  lea     rcx, [rbp+870h+pszStr2]
0x1801abb70  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abb75  lea     rcx, [rbp+870h+pszMore]
0x1801abb79  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abb7e  lea     rcx, [rsp+970h+ppszPath]
0x1801abb83  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abb88  lea     rcx, [rsp+970h+pszPath]
0x1801abb8d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abb92  lea     rcx, [rsp+970h+lpExistingFileName]
0x1801abb97  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801abb9c  mov     rcx, [rbp+870h+var_30]
0x1801abba3  xor     rcx, rsp; StackCookie
0x1801abba6  call    __security_check_cookie
0x1801abbab  lea     r11, [rsp+970h+var_20]
0x1801abbb3  mov     rbx, [r11+40h]
0x1801abbb7  mov     rsi, [r11+48h]
0x1801abbbb  mov     rsp, r11
0x1801abbbe  pop     r15
0x1801abbc0  pop     r14
0x1801abbc2  pop     r12
0x1801abbc4  pop     rdi
0x1801abbc5  pop     rbp
0x1801abbc6  retn
```
