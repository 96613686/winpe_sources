# CSettingsManager::DeleteLocalHistory(void)

- ea: `0x1801bb248`
- end: `0x1801bb4fd`
- name: `?DeleteLocalHistory@CSettingsManager@@QEAAJXZ`
- size: `693`
- prototype: `__int64 __fastcall(CSettingsManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801a2160`

## callees

- `0x18000b7e8`
- `0x1800149d8`
- `0x1800150c0`
- `0x180027ee4`
- `0x180047224`
- `0x18013d330`
- `0x18013df8c`
- `0x1801ad6a8`
- `0x1801bb248`
- `0x1801bb8f0`
- `0x1801bc5f8`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801bb30b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801bb38d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801bb30b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801bb38d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801bb3d6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801bb3d6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801bb3c5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801bb3c5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801bb35c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801bb35c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801bb39e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801bb39e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801bb420`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801bb420`
- `WININET!DeleteUrlCacheGroup` at `0x1801bb490`
- `WININET!DeleteUrlCacheGroup` at `0x1801bb490`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x1801bb451`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x1801bb451`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801bb2e3`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801bb2e3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801bb3a9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801bb3a9`

## pseudocode

```c
__int64 __fastcall CSettingsManager::DeleteLocalHistory(CSettingsManager *this, __int64 a2, __int64 a3)
{
  HRESULT Instance; // ebx
  HANDLE FirstFile; // rax
  int v5; // eax
  const struct _GUID *v6; // rcx
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h]
  __int64 v10; // [rsp+40h] [rbp-C0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFindFile[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_TWINUI_PUBLISHER_Context,
      ConnectedSearch_DeleteLocalHistorySettingEntry,
      a3,
      1,
      hFindFile);
  ppszPath = 0;
  v9 = 0;
  v10 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  v9 = -1;
  v10 = -1;
  Instance = SHGetKnownFolderPath(&FOLDERID_SearchHistory, 0x8000u, 0, &ppszPath);
  if ( Instance >= 0 )
  {
    Instance = PathCchCombine(pszPathOut, 0x104u, ppszPath, L"*.lnk");
    if ( Instance >= 0 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      hFindFile[0] = 0;
      FirstFile = FindFirstFileExW(pszPathOut, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
      v5 = ResultFromWin32Handle(FirstFile, hFindFile);
      Instance = v5;
      if ( v5 < 0 )
      {
        if ( v5 != -2147024894 )
        {
          hFindFile[0] = 0;
          goto LABEL_20;
        }
      }
      else
      {
        do
        {
          if ( PathCchCombine(pszPathOut, 0x104u, ppszPath, FindFileData.cFileName) >= 0 )
            DeleteFileW(pszPathOut);
          PathRemoveExtensionW(FindFileData.cFileName);
          UADeleteEntry(v6, FindFileData.cFileName);
        }
        while ( FindNextFileW(hFindFile[0], &FindFileData) );
        FindClose(hFindFile[0]);
      }
      hFindFile[0] = 0;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(hFindFile);
      Instance = CoCreateInstance(
                   &CLSID_TypeAheadSearchHistorySettings,
                   0,
                   1u,
                   &GUID_1d90776b_4df7_442b_b4e5_f4bd8ba98c39,
                   hFindFile);
      if ( Instance >= 0 )
        Instance = (*(__int64 (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)hFindFile[0] + 40LL))(hFindFile[0], 0);
      SHDeleteKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\RunMRU");
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(hFindFile);
    }
  }
  hFindFile[0] = 0;
  if ( Instance >= 0 && FindSearchVisitedGroupId((__int64 *)hFindFile) )
  {
    if ( DeleteUrlCacheGroup((GROUPID)hFindFile[0], 2u, 0) )
      Instance = 0;
    else
      Instance = ResultFromKnownLastError();
  }
LABEL_20:
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McTemplateU0q_EventWriteTransfer(
      &MICROSOFT_TWINUI_PUBLISHER_Context,
      ConnectedSearch_DeleteLocalHistory,
      (unsigned int)Instance);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801bb248  mov     [rsp-8+arg_0], rbx
0x1801bb24d  push    rbp
0x1801bb24e  lea     rbp, [rsp-3D0h]
0x1801bb256  sub     rsp, 4D0h
0x1801bb25d  mov     rax, cs:__security_cookie
0x1801bb264  xor     rax, rsp
0x1801bb267  mov     [rbp+3D0h+var_10], rax
0x1801bb26e  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x1801bb275  jz      short loc_1801BB29C
0x1801bb277  lea     rax, [rbp+3D0h+hFindFile]
0x1801bb27e  mov     r9d, 1
0x1801bb284  lea     rdx, ConnectedSearch_DeleteLocalHistorySettingEntry
0x1801bb28b  mov     [rsp+4D0h+lpSearchFilter], rax
0x1801bb290  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x1801bb297  call    McGenEventWrite_EventWriteTransfer
0x1801bb29c  lea     rcx, [rsp+4D0h+ppszPath]
0x1801bb2a1  mov     [rsp+4D0h+ppszPath], 0
0x1801bb2aa  mov     [rsp+4D0h+var_498], 0
0x1801bb2b3  mov     [rsp+4D0h+var_490], 0
0x1801bb2bc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801bb2c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801bb2c5  lea     r9, [rsp+4D0h+ppszPath]; ppszPath
0x1801bb2ca  xor     r8d, r8d; hToken
0x1801bb2cd  mov     [rsp+4D0h+var_498], rax
0x1801bb2d2  mov     edx, 8000h; dwFlags
0x1801bb2d7  mov     [rsp+4D0h+var_490], rax
0x1801bb2dc  lea     rcx, FOLDERID_SearchHistory; rfid
0x1801bb2e3  call    cs:__imp_SHGetKnownFolderPath
0x1801bb2e9  mov     ebx, eax
0x1801bb2eb  test    eax, eax
0x1801bb2ed  js      loc_1801BB463
0x1801bb2f3  mov     r8, [rsp+4D0h+ppszPath]; pszPathIn
0x1801bb2f8  lea     r9, aLnk; "*.lnk"
0x1801bb2ff  mov     edx, 104h; cchPathOut
0x1801bb304  lea     rcx, [rbp+3D0h+pszPathOut]; pszPathOut
0x1801bb30b  call    cs:__imp_PathCchCombine
0x1801bb311  mov     ebx, eax
0x1801bb313  test    eax, eax
0x1801bb315  js      loc_1801BB463
0x1801bb31b  xor     edx, edx; Val
0x1801bb31d  lea     rcx, [rsp+4D0h+FindFileData]; void *
0x1801bb322  mov     r8d, 250h; Size
0x1801bb328  call    memset_0
0x1801bb32d  xor     r9d, r9d; fSearchOp
0x1801bb330  mov     [rsp+4D0h+dwAdditionalFlags], 0; dwAdditionalFlags
0x1801bb338  lea     r8, [rsp+4D0h+FindFileData]; lpFindFileData
0x1801bb33d  mov     [rbp+3D0h+hFindFile], 0
0x1801bb348  lea     rcx, [rbp+3D0h+pszPathOut]; lpFileName
0x1801bb34f  mov     [rsp+4D0h+lpSearchFilter], 0; lpSearchFilter
0x1801bb358  lea     edx, [r9+1]; fInfoLevelId
0x1801bb35c  call    cs:__imp_FindFirstFileExW
0x1801bb362  mov     rcx, rax; void *
0x1801bb365  lea     rdx, [rbp+3D0h+hFindFile]; void **
0x1801bb36c  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x1801bb371  mov     ebx, eax
0x1801bb373  test    eax, eax
0x1801bb375  js      short loc_1801BB3DE
0x1801bb377  mov     r8, [rsp+4D0h+ppszPath]; pszPathIn
0x1801bb37c  lea     r9, [rsp+4D0h+pszMore]; pszMore
0x1801bb381  mov     edx, 104h; cchPathOut
0x1801bb386  lea     rcx, [rbp+3D0h+pszPathOut]; pszPathOut
0x1801bb38d  call    cs:__imp_PathCchCombine
0x1801bb393  test    eax, eax
0x1801bb395  js      short loc_1801BB3A4
0x1801bb397  lea     rcx, [rbp+3D0h+pszPathOut]; lpFileName
0x1801bb39e  call    cs:__imp_DeleteFileW
0x1801bb3a4  lea     rcx, [rsp+4D0h+pszMore]; pszPath
0x1801bb3a9  call    cs:__imp_PathRemoveExtensionW
0x1801bb3af  lea     rdx, [rsp+4D0h+pszMore]; unsigned __int16 *
0x1801bb3b4  call    ?UADeleteEntry@@YAJPEBU_GUID@@PEBG@Z; UADeleteEntry(_GUID const *,ushort const *)
0x1801bb3b9  mov     rcx, [rbp+3D0h+hFindFile]; hFindFile
0x1801bb3c0  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x1801bb3c5  call    cs:__imp_FindNextFileW
0x1801bb3cb  test    eax, eax
0x1801bb3cd  jnz     short loc_1801BB377
0x1801bb3cf  mov     rcx, [rbp+3D0h+hFindFile]; hFindFile
0x1801bb3d6  call    cs:__imp_FindClose
0x1801bb3dc  jmp     short loc_1801BB3E9
0x1801bb3de  cmp     eax, 80070002h
0x1801bb3e3  jnz     loc_1801BB49E
0x1801bb3e9  lea     rcx, [rbp+3D0h+hFindFile]
0x1801bb3f0  mov     [rbp+3D0h+hFindFile], 0
0x1801bb3fb  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801bb400  xor     edx, edx; pUnkOuter
0x1801bb402  lea     rax, [rbp+3D0h+hFindFile]
0x1801bb409  lea     r9, _GUID_1d90776b_4df7_442b_b4e5_f4bd8ba98c39; riid
0x1801bb410  mov     [rsp+4D0h+lpSearchFilter], rax; ppv
0x1801bb415  lea     rcx, CLSID_TypeAheadSearchHistorySettings; rclsid
0x1801bb41c  lea     r8d, [rdx+1]; dwClsContext
0x1801bb420  call    cs:__imp_CoCreateInstance
0x1801bb426  mov     ebx, eax
0x1801bb428  test    eax, eax
0x1801bb42a  js      short loc_1801BB443
0x1801bb42c  mov     rcx, [rbp+3D0h+hFindFile]
0x1801bb433  xor     edx, edx
0x1801bb435  mov     rax, [rcx]
0x1801bb438  mov     rax, [rax+28h]
0x1801bb43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb441  mov     ebx, eax
0x1801bb443  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801bb44a  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1801bb451  call    cs:__imp_SHDeleteKeyW
0x1801bb457  lea     rcx, [rbp+3D0h+hFindFile]
0x1801bb45e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801bb463  mov     [rbp+3D0h+hFindFile], 0
0x1801bb46e  test    ebx, ebx
0x1801bb470  js      short loc_1801BB4B2
0x1801bb472  lea     rcx, [rbp+3D0h+hFindFile]; __int64 *
0x1801bb479  call    ?FindSearchVisitedGroupId@@YA_NPEA_J@Z; FindSearchVisitedGroupId(__int64 *)
0x1801bb47e  test    al, al
0x1801bb480  jz      short loc_1801BB4B2
0x1801bb482  mov     rcx, [rbp+3D0h+hFindFile]; GroupId
0x1801bb489  xor     r8d, r8d; lpReserved
0x1801bb48c  lea     edx, [r8+2]; dwFlags
0x1801bb490  call    cs:__imp_DeleteUrlCacheGroup
0x1801bb496  test    eax, eax
0x1801bb498  jz      short loc_1801BB4AB
0x1801bb49a  xor     ebx, ebx
0x1801bb49c  jmp     short loc_1801BB4B2
0x1801bb49e  mov     [rbp+3D0h+hFindFile], 0
0x1801bb4a9  jmp     short loc_1801BB4B2
0x1801bb4ab  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801bb4b0  mov     ebx, eax
0x1801bb4b2  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x1801bb4b9  jz      short loc_1801BB4D1
0x1801bb4bb  mov     r8d, ebx
0x1801bb4be  lea     rdx, ConnectedSearch_DeleteLocalHistory
0x1801bb4c5  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x1801bb4cc  call    McTemplateU0q_EventWriteTransfer
0x1801bb4d1  lea     rcx, [rsp+4D0h+ppszPath]
0x1801bb4d6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801bb4db  mov     eax, ebx
0x1801bb4dd  mov     rcx, [rbp+3D0h+var_10]
0x1801bb4e4  xor     rcx, rsp; StackCookie
0x1801bb4e7  call    __security_check_cookie
0x1801bb4ec  mov     rbx, [rsp+4D0h+arg_0]
0x1801bb4f4  add     rsp, 4D0h
0x1801bb4fb  pop     rbp
0x1801bb4fc  retn
```
