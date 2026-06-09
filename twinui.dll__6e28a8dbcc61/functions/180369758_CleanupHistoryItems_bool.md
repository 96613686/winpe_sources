# CleanupHistoryItems(bool)

- ea: `0x180369758`
- end: `0x1803699c7`
- name: `?CleanupHistoryItems@@YAJ_N@Z`
- size: `623`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18036ace0`

## callees

- `0x18000b7e8`
- `0x18001f3c0`
- `0x180027ee4`
- `0x18013d330`
- `0x18013df8c`
- `0x1801bc5f8`
- `0x18036935c`
- `0x1803694c8`
- `0x180369758`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x180369943`
- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x180369943`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1803697f2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18036991e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1803697f2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18036991e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1803698da`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1803698da`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1803698cd`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1803698cd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180369846`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180369846`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180369954`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180369954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180369994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180369994`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1803697ca`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1803697ca`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180369861`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180369861`

## pseudocode

```c
__int64 __fastcall CleanupHistoryItems()
{
  HRESULT v0; // ebx
  _QWORD *v1; // rsi
  unsigned __int64 v2; // r14
  HANDLE FirstFile; // rdi
  __int64 v4; // rdx
  __int32 v5; // edi
  unsigned __int64 v6; // r15
  const unsigned __int16 *v7; // r12
  const struct _GUID *v8; // rcx
  unsigned __int64 i; // rdi
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR ppszPath; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+68h] [rbp-98h]
  __int64 v19; // [rsp+70h] [rbp-90h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  ppszPath = 0;
  v14 = 0;
  v15 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  v14 = -1;
  v15 = -1;
  v0 = SHGetKnownFolderPath(&FOLDERID_SearchHistory, 0x8000u, 0, &ppszPath);
  if ( v0 < 0 )
    goto LABEL_22;
  v0 = PathCchCombine(pszPathOut, 0x104u, ppszPath, L"*.lnk");
  if ( v0 < 0 )
    goto LABEL_22;
  v1 = 0;
  v2 = 0;
  pv = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFile = FindFirstFileExW(pszPathOut, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  if ( FirstFile == (HANDLE)-1LL )
    goto LABEL_9;
  do
  {
    v11 = 0;
    PathRemoveExtensionW(FindFileData.cFileName);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v11);
    v0 = Microsoft::WRL::Details::MakeAndInitialize<CHistoryItem,CHistoryItem,unsigned short (&)[260],_FILETIME &>(
           &v11,
           FindFileData.cFileName,
           &FindFileData.ftCreationTime);
    if ( v0 >= 0 )
    {
      v12 = v11;
      Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v12);
      v0 = CTSimpleArray<Microsoft::WRL::ComPtr<CHistoryItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<CHistoryItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CHistoryItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CHistoryItem>>>::_AddSortedEx<CCompareHistoryItems,Microsoft::WRL::ComPtr<CHistoryItem> &&>(
             &pv,
             v4,
             &v12);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v12);
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v11);
  }
  while ( v0 >= 0 && FindNextFileW(FirstFile, &FindFileData) );
  FindClose(FirstFile);
  v2 = v17;
  v1 = pv;
  if ( v0 >= 0 )
  {
LABEL_9:
    v5 = v2;
    v6 = 950;
    if ( v2 <= 0x3B6 )
    {
      if ( v2 < 0x3B6 )
      {
LABEL_17:
        _InterlockedExchange(&dword_1804B69D0, v5);
        goto LABEL_18;
      }
    }
    else
    {
      do
      {
        v7 = *(const unsigned __int16 **)(v1[v6] + 24LL);
        if ( PathCchCombine(pszPathOut, 0x104u, ppszPath, v7) >= 0 )
        {
          UADeleteEntry(v8, v7);
          if ( PathCchAddExtension(pszPathOut, 0x104u, L".lnk") >= 0 )
            DeleteFileW(pszPathOut);
        }
        ++v6;
      }
      while ( v6 < v2 );
    }
    v5 = 950;
    goto LABEL_17;
  }
LABEL_18:
  if ( v1 )
  {
    for ( i = 0; i < v2; ++i )
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v1[i]);
    CoTaskMemFree(v1);
  }
LABEL_22:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180369758  push    rbp
0x18036975a  push    rbx
0x18036975b  push    rsi
0x18036975c  push    rdi
0x18036975d  push    r12
0x18036975f  push    r14
0x180369761  push    r15
0x180369763  lea     rbp, [rsp-3F0h]
0x18036976b  sub     rsp, 4F0h
0x180369772  mov     rax, cs:__security_cookie
0x180369779  xor     rax, rsp
0x18036977c  mov     [rbp+420h+var_40], rax
0x180369783  lea     rcx, [rsp+520h+ppszPath]
0x180369788  mov     [rsp+520h+ppszPath], 0
0x180369791  mov     [rsp+520h+var_4D8], 0
0x18036979a  mov     [rsp+520h+var_4D0], 0
0x1803697a3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1803697a8  or      r15, 0FFFFFFFFFFFFFFFFh
0x1803697ac  lea     r9, [rsp+520h+ppszPath]; ppszPath
0x1803697b1  xor     r8d, r8d; hToken
0x1803697b4  mov     [rsp+520h+var_4D8], r15
0x1803697b9  mov     edx, 8000h; dwFlags
0x1803697be  mov     [rsp+520h+var_4D0], r15
0x1803697c3  lea     rcx, FOLDERID_SearchHistory; rfid
0x1803697ca  call    cs:__imp_SHGetKnownFolderPath
0x1803697d0  mov     ebx, eax
0x1803697d2  test    eax, eax
0x1803697d4  js      loc_18036999A
0x1803697da  mov     r8, [rsp+520h+ppszPath]; pszPathIn
0x1803697df  lea     r9, aLnk; "*.lnk"
0x1803697e6  mov     edx, 104h; cchPathOut
0x1803697eb  lea     rcx, [rbp+420h+pszPathOut]; pszPathOut
0x1803697f2  call    cs:__imp_PathCchCombine
0x1803697f8  mov     ebx, eax
0x1803697fa  test    eax, eax
0x1803697fc  js      loc_18036999A
0x180369802  xor     esi, esi
0x180369804  lea     rcx, [rbp+420h+FindFileData]; void *
0x180369808  xor     r14d, r14d
0x18036980b  mov     [rsp+520h+pv], rsi
0x180369810  xor     edx, edx; Val
0x180369812  mov     [rsp+520h+var_4C0], r14
0x180369817  mov     r8d, 250h; Size
0x18036981d  mov     [rsp+520h+var_4B8], rsi
0x180369822  mov     [rsp+520h+var_4B0], rsi
0x180369827  call    memset_0
0x18036982c  xor     r9d, r9d; fSearchOp
0x18036982f  mov     [rsp+520h+dwAdditionalFlags], esi; dwAdditionalFlags
0x180369833  lea     r8, [rbp+420h+FindFileData]; lpFindFileData
0x180369837  mov     [rsp+520h+lpSearchFilter], rsi; lpSearchFilter
0x18036983c  lea     edx, [rsi+1]; fInfoLevelId
0x18036983f  lea     rcx, [rbp+420h+pszPathOut]; lpFileName
0x180369846  call    cs:__imp_FindFirstFileExW
0x18036984c  mov     rdi, rax
0x18036984f  cmp     rax, r15
0x180369852  jz      loc_1803698F2
0x180369858  lea     rcx, [rbp+420h+pszPath]; pszPath
0x18036985c  mov     [rsp+520h+var_4F0], rsi
0x180369861  call    cs:__imp_PathRemoveExtensionW
0x180369867  lea     rcx, [rsp+520h+var_4F0]
0x18036986c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180369871  lea     r8, [rbp+420h+var_49C]
0x180369875  lea     rdx, [rbp+420h+pszPath]
0x180369879  lea     rcx, [rsp+520h+var_4F0]
0x18036987e  call    ??$MakeAndInitialize@VCHistoryItem@@V1@AEAY0BAE@GAEAU_FILETIME@@@Details@WRL@Microsoft@@YAJPEAPEAVCHistoryItem@@AEAY0BAE@GAEAU_FILETIME@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CHistoryItem,CHistoryItem,ushort (&)[260],_FILETIME &>(CHistoryItem * *,ushort (&)[260],_FILETIME &)
0x180369883  mov     ebx, eax
0x180369885  test    eax, eax
0x180369887  js      short loc_1803698B8
0x180369889  mov     rax, [rsp+520h+var_4F0]
0x18036988e  lea     rcx, [rsp+520h+var_4E8]
0x180369893  mov     [rsp+520h+var_4E8], rax
0x180369898  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x18036989d  lea     r8, [rsp+520h+var_4E8]
0x1803698a2  lea     rcx, [rsp+520h+pv]
0x1803698a7  call    ??$_AddSortedEx@VCCompareHistoryItems@@$$QEAV?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@@?$CTSimpleArray@V?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@@@@@QEAAJAEBVCCompareHistoryItems@@$$QEAV?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@PEA_K@Z; CTSimpleArray<Microsoft::WRL::ComPtr<CHistoryItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<CHistoryItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CHistoryItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CHistoryItem>>>::_AddSortedEx<CCompareHistoryItems,Microsoft::WRL::ComPtr<CHistoryItem> &&>(CCompareHistoryItems const &,Microsoft::WRL::ComPtr<CHistoryItem> &&,unsigned __int64 *)
0x1803698ac  lea     rcx, [rsp+520h+var_4E8]
0x1803698b1  mov     ebx, eax
0x1803698b3  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803698b8  lea     rcx, [rsp+520h+var_4F0]
0x1803698bd  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803698c2  test    ebx, ebx
0x1803698c4  js      short loc_1803698D7
0x1803698c6  lea     rdx, [rbp+420h+FindFileData]; lpFindFileData
0x1803698ca  mov     rcx, rdi; hFindFile
0x1803698cd  call    cs:__imp_FindNextFileW
0x1803698d3  test    eax, eax
0x1803698d5  jnz     short loc_180369858
0x1803698d7  mov     rcx, rdi; hFindFile
0x1803698da  call    cs:__imp_FindClose
0x1803698e0  mov     r14, [rsp+520h+var_4C0]
0x1803698e5  mov     rsi, [rsp+520h+pv]
0x1803698ea  test    ebx, ebx
0x1803698ec  js      loc_180369974
0x1803698f2  mov     eax, 3B6h
0x1803698f7  mov     rdi, r14
0x1803698fa  mov     r15d, eax
0x1803698fd  cmp     r14, rax
0x180369900  jbe     short loc_180369969
0x180369902  mov     rax, [rsi+r15*8]
0x180369906  lea     rcx, [rbp+420h+pszPathOut]; pszPathOut
0x18036990d  mov     r8, [rsp+520h+ppszPath]; pszPathIn
0x180369912  mov     edx, 104h; cchPathOut
0x180369917  mov     r12, [rax+18h]
0x18036991b  mov     r9, r12; pszMore
0x18036991e  call    cs:__imp_PathCchCombine
0x180369924  test    eax, eax
0x180369926  js      short loc_18036995A
0x180369928  mov     rdx, r12; unsigned __int16 *
0x18036992b  call    ?UADeleteEntry@@YAJPEBU_GUID@@PEBG@Z; UADeleteEntry(_GUID const *,ushort const *)
0x180369930  lea     r8, aLnk_0; ".lnk"
0x180369937  mov     edx, 104h; cchPath
0x18036993c  lea     rcx, [rbp+420h+pszPathOut]; pszPath
0x180369943  call    cs:__imp_PathCchAddExtension
0x180369949  test    eax, eax
0x18036994b  js      short loc_18036995A
0x18036994d  lea     rcx, [rbp+420h+pszPathOut]; lpFileName
0x180369954  call    cs:__imp_DeleteFileW
0x18036995a  inc     r15
0x18036995d  cmp     r15, r14
0x180369960  jb      short loc_180369902
0x180369962  mov     eax, 3B6h
0x180369967  jmp     short loc_18036996B
0x180369969  jb      short loc_18036996E
0x18036996b  mov     rdi, rax
0x18036996e  xchg    edi, cs:dword_1804B69D0
0x180369974  test    rsi, rsi
0x180369977  jz      short loc_18036999A
0x180369979  xor     edi, edi
0x18036997b  test    r14, r14
0x18036997e  jz      short loc_180369991
0x180369980  lea     rcx, [rsi+rdi*8]
0x180369984  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180369989  inc     rdi
0x18036998c  cmp     rdi, r14
0x18036998f  jb      short loc_180369980
0x180369991  mov     rcx, rsi; pv
0x180369994  call    cs:__imp_CoTaskMemFree
0x18036999a  lea     rcx, [rsp+520h+ppszPath]
0x18036999f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1803699a4  mov     eax, ebx
0x1803699a6  mov     rcx, [rbp+420h+var_40]
0x1803699ad  xor     rcx, rsp; StackCookie
0x1803699b0  call    __security_check_cookie
0x1803699b5  add     rsp, 4F0h
0x1803699bc  pop     r15
0x1803699be  pop     r14
0x1803699c0  pop     r12
0x1803699c2  pop     rdi
0x1803699c3  pop     rsi
0x1803699c4  pop     rbx
0x1803699c5  pop     rbp
0x1803699c6  retn
```
