# DllInstall

- ea: `0x18029e210`
- end: `0x18029e548`
- name: `DllInstall`
- size: `824`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800c23f8`
- `0x1800ced54`
- `0x1800f5920`
- `0x18011611c`
- `0x18021181c`
- `0x180249490`
- `0x180299b08`
- `0x18029a300`
- `0x18029c128`
- `0x18029d2d8`
- `0x18029d558`
- `0x18029d844`
- `0x18029d970`
- `0x18029e210`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18029e490`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18029e490`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18029e4a9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18029e4a9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18029e472`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18029e472`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18029e39b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18029e455`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18029e39b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18029e455`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18029e32e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18029e32e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029e361`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029e361`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18029e266`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18029e266`
- `USER32!SystemParametersInfoW` at `0x18029e38b`
- `USER32!SystemParametersInfoW` at `0x18029e38b`
- `USER32!GetSystemMetrics` at `0x18029e282`
- `USER32!GetSystemMetrics` at `0x18029e282`
- `ntdll!RtlGetNtProductType` at `0x18029e247`
- `ntdll!RtlGetNtProductType` at `0x18029e247`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029e3d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029e3d7`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyA` at `0x18029e446`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyA` at `0x18029e446`
- `api-ms-win-storage-exports-internal-l1-1-0!SHPrepareKnownFoldersCommon` at `0x18029e519`
- `api-ms-win-storage-exports-internal-l1-1-0!SHPrepareKnownFoldersCommon` at `0x18029e519`
- `api-ms-win-storage-exports-internal-l1-1-0!SHPrepareKnownFoldersUser` at `0x18029e3a7`
- `api-ms-win-storage-exports-internal-l1-1-0!SHPrepareKnownFoldersUser` at `0x18029e3a7`
- `SHLWAPI!__imp_SKGetValueW` at `0x18029e2d8`
- `SHLWAPI!__imp_SKGetValueW` at `0x18029e2d8`
- `SHLWAPI!__imp_SHGetShellKeyEx` at `0x18029e42d`
- `SHLWAPI!__imp_SHGetShellKeyEx` at `0x18029e42d`
- `Windows.Storage!__imp_SHGetSetSettings` at `0x18029e306`
- `Windows.Storage!__imp_SHGetSetSettings` at `0x18029e306`

## string_xrefs

- `0x18029e4e2`: `Software\Microsoft\Windows\CurrentVersion\Explorer\Package Installation`
- `0x18029e4fc`: `Software\Microsoft\Windows\CurrentVersion\Explorer\Package Installation`
- `0x18029e46b`: `mydocs.dll`

## pseudocode

```c
HRESULT __stdcall DllInstall(BOOL bInstall, PCWSTR pszCmdLine)
{
  unsigned __int16 *v3; // rcx
  int v4; // eax
  int AutolistShortcutsInLinksDir; // ebx
  HKEY v6; // rax
  HKEY v7; // rdi
  HMODULE LibraryW; // rax
  HMODULE v9; // rdi
  void (*ProcAddress)(void); // rax
  int v11; // eax
  HKEY hKey; // [rsp+30h] [rbp-19h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-11h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+40h] [rbp-9h] BYREF
  int v16; // [rsp+44h] [rbp-5h] BYREF
  int v17; // [rsp+48h] [rbp-1h] BYREF
  unsigned int v18; // [rsp+4Ch] [rbp+3h] BYREF
  struct $D321FDA48A4D82B6F6ABB6499405B63E v19; // [rsp+50h] [rbp+7h] BYREF

  if ( !bInstall )
    return -2147467263;
  ProductType = NtProductWinNt;
  RtlGetNtProductType(&ProductType);
  if ( !pszCmdLine || StrCmpICW(pszCmdLine, L"U") )
  {
    AutolistShortcutsInLinksDir = 0;
    v11 = Shell32RegTypeLib();
    if ( v11 < 0 )
      AutolistShortcutsInLinksDir = v11;
    SHPrepareKnownFoldersCommon();
  }
  else
  {
    _UpdateSIDsOnLibraries();
    if ( GetSystemMetrics(86) )
    {
      hKey = 0;
      v17 = 0;
      v16 = 4;
      if ( (unsigned int)SKGetValueW(1, L"Advanced", L"AutoCheckSelect", 0, &v17, &v16) )
      {
        *(_OWORD *)&v19.iSortDirection = 0;
        *((_DWORD *)&v19 + 7) = 8;
        *(_OWORD *)&v19 = 0;
        SHGetSetSettings(&v19, 0x800000u, 1);
      }
      if ( !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows",
              0,
              0x20019u,
              &hKey) )
      {
        if ( RegQueryValueExW(hKey, L"MenuDropAlignment", 0, 0, 0, 0) == 2 )
        {
          v4 = IsBiDiLocalizedSystemEx(v3);
          SystemParametersInfoW(0x1Cu, v4 == 0, 0, 3u);
        }
        RegCloseKey(hKey);
      }
    }
    SHPrepareKnownFoldersUser();
    ppv = 0;
    AutolistShortcutsInLinksDir = CoCreateInstance(
                                    &GUID_f235ce7d_b143_4d4f_ad93_64e48d53a5fb,
                                    0,
                                    1u,
                                    &GUID_a768a74d_ae70_45d6_9997_ea0c0bd5513e,
                                    &ppv);
    if ( AutolistShortcutsInLinksDir >= 0 )
    {
      AutolistShortcutsInLinksDir = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( AutolistShortcutsInLinksDir >= 0 )
        AutolistShortcutsInLinksDir = CreateAutolistShortcutsInLinksDir();
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( AutolistShortcutsInLinksDir >= 0 )
      AutolistShortcutsInLinksDir = 0;
    LODWORD(v6) = SHGetShellKeyEx((LPCWSTR)0x5021);
    v7 = v6;
    if ( v6 )
    {
      SHDeleteKeyA(v6, 0);
      RegCloseKey(v7);
    }
    _ApplyPassiveFTP();
    _DeleteOldRemovableLinks();
    LibraryW = LoadLibraryW(L"mydocs.dll");
    v9 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = (void (*)(void))GetProcAddress(LibraryW, "PerUserInit");
      if ( ProcAddress )
        ProcAddress();
      FreeLibrary(v9);
    }
    _DefaultVisualEffects();
    if ( !(unsigned int)IsOS_OS_ANYSERVER() )
      _NoDriveAutorunTweak();
    MigrateFavoriteLinks();
    v18 = 0;
    if ( (int)SHRegGetDWORD(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Package Installation",
                L"PackageListVersion",
                &v18) < 0 )
      SHRegSetDWORD(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Package Installation",
        L"PackageListVersion",
        0);
  }
  return AutolistShortcutsInLinksDir;
}

```

## disassembly

```asm
0x18029e210  push    rbp
0x18029e212  push    rbx
0x18029e213  push    rdi
0x18029e214  push    r14
0x18029e216  lea     rbp, [rsp-3Fh]
0x18029e21b  sub     rsp, 88h
0x18029e222  mov     rax, cs:__security_cookie
0x18029e229  xor     rax, rsp
0x18029e22c  mov     [rbp+57h+var_30], rax
0x18029e230  mov     rbx, rdx
0x18029e233  test    ecx, ecx
0x18029e235  jz      loc_18029E527
0x18029e23b  mov     edi, 1
0x18029e240  lea     rcx, [rbp+57h+ProductType]; ProductType
0x18029e244  mov     [rbp+57h+ProductType], edi
0x18029e247  call    cs:__imp_RtlGetNtProductType
0x18029e24e  nop     dword ptr [rax+rax+00h]
0x18029e253  test    rbx, rbx
0x18029e256  jz      loc_18029E50D
0x18029e25c  lea     rdx, aU_1; "U"
0x18029e263  mov     rcx, rbx; pszStr1
0x18029e266  call    cs:__imp_StrCmpICW
0x18029e26d  nop     dword ptr [rax+rax+00h]
0x18029e272  test    eax, eax
0x18029e274  jnz     loc_18029E50D
0x18029e27a  call    ?_UpdateSIDsOnLibraries@@YAXXZ; _UpdateSIDsOnLibraries(void)
0x18029e27f  lea     ecx, [rdi+55h]; nIndex
0x18029e282  call    cs:__imp_GetSystemMetrics
0x18029e289  nop     dword ptr [rax+rax+00h]
0x18029e28e  mov     r14, 0FFFFFFFF80000001h
0x18029e295  test    eax, eax
0x18029e297  jz      loc_18029E3A7
0x18029e29d  lea     rax, [rbp+57h+var_5C]
0x18029e2a1  mov     [rbp+57h+hKey], 0
0x18029e2a9  mov     [rsp+0A0h+lpcbData], rax
0x18029e2ae  lea     r8, aAutocheckselec; "AutoCheckSelect"
0x18029e2b5  lea     rax, [rbp+57h+var_58]
0x18029e2b9  mov     [rbp+57h+var_58], 0
0x18029e2c0  xor     r9d, r9d
0x18029e2c3  mov     [rsp+0A0h+phkResult], rax
0x18029e2c8  lea     rdx, aAdvanced_0; "Advanced"
0x18029e2cf  mov     [rbp+57h+var_5C], 4
0x18029e2d6  mov     ecx, edi
0x18029e2d8  call    cs:__imp_SKGetValueW
0x18029e2df  nop     dword ptr [rax+rax+00h]
0x18029e2e4  test    eax, eax
0x18029e2e6  jz      short loc_18029E312
0x18029e2e8  xorps   xmm0, xmm0
0x18029e2eb  lea     rcx, [rbp+57h+var_50]; lpss
0x18029e2ef  movups  xmmword ptr [rbp+57h+var_50.iSortDirection], xmm0
0x18029e2f3  mov     r8d, edi; bSet
0x18029e2f6  mov     dword ptr [rbp+57h+var_50.fSepProcess], 8
0x18029e2fd  mov     edx, 800000h; dwMask
0x18029e302  movups  xmmword ptr [rbp+57h+var_50.fShowAllObjects], xmm0
0x18029e306  call    cs:__imp_SHGetSetSettings
0x18029e30d  nop     dword ptr [rax+rax+00h]
0x18029e312  lea     rax, [rbp+57h+hKey]
0x18029e316  mov     r9d, 20019h; samDesired
0x18029e31c  xor     r8d, r8d; ulOptions
0x18029e31f  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18029e324  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x18029e32b  mov     rcx, r14; hKey
0x18029e32e  call    cs:__imp_RegOpenKeyExW
0x18029e335  nop     dword ptr [rax+rax+00h]
0x18029e33a  test    eax, eax
0x18029e33c  jnz     short loc_18029E3A7
0x18029e33e  mov     rcx, [rbp+57h+hKey]; hKey
0x18029e342  lea     rdx, aMenudropalignm; "MenuDropAlignment"
0x18029e349  mov     [rsp+0A0h+lpcbData], 0; lpcbData
0x18029e352  xor     r9d, r9d; lpType
0x18029e355  xor     r8d, r8d; lpReserved
0x18029e358  mov     [rsp+0A0h+phkResult], 0; lpData
0x18029e361  call    cs:__imp_RegQueryValueExW
0x18029e368  nop     dword ptr [rax+rax+00h]
0x18029e36d  cmp     eax, 2
0x18029e370  jnz     short loc_18029E397
0x18029e372  call    ?IsBiDiLocalizedSystemEx@@YAHPEAG@Z; IsBiDiLocalizedSystemEx(ushort *)
0x18029e377  xor     edx, edx
0x18029e379  mov     r9d, 3; fWinIni
0x18029e37f  test    eax, eax
0x18029e381  setz    dl; uiParam
0x18029e384  xor     r8d, r8d; pvParam
0x18029e387  lea     ecx, [r9+19h]; uiAction
0x18029e38b  call    cs:__imp_SystemParametersInfoW
0x18029e392  nop     dword ptr [rax+rax+00h]
0x18029e397  mov     rcx, [rbp+57h+hKey]; hKey
0x18029e39b  call    cs:__imp_RegCloseKey
0x18029e3a2  nop     dword ptr [rax+rax+00h]
0x18029e3a7  call    cs:__imp_SHPrepareKnownFoldersUser
0x18029e3ae  nop     dword ptr [rax+rax+00h]
0x18029e3b3  lea     rax, [rbp+57h+ppv]
0x18029e3b7  mov     [rbp+57h+ppv], 0
0x18029e3bf  lea     r9, _GUID_a768a74d_ae70_45d6_9997_ea0c0bd5513e; riid
0x18029e3c6  mov     [rsp+0A0h+phkResult], rax; ppv
0x18029e3cb  mov     r8d, edi; dwClsContext
0x18029e3ce  lea     rcx, _GUID_f235ce7d_b143_4d4f_ad93_64e48d53a5fb; rclsid
0x18029e3d5  xor     edx, edx; pUnkOuter
0x18029e3d7  call    cs:__imp_CoCreateInstance
0x18029e3de  nop     dword ptr [rax+rax+00h]
0x18029e3e3  mov     ebx, eax
0x18029e3e5  test    eax, eax
0x18029e3e7  js      short loc_18029E416
0x18029e3e9  mov     rcx, [rbp+57h+ppv]
0x18029e3ed  mov     rax, [rcx]
0x18029e3f0  mov     rax, [rax+20h]
0x18029e3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e3f9  mov     ebx, eax
0x18029e3fb  test    eax, eax
0x18029e3fd  js      short loc_18029E406
0x18029e3ff  call    ?CreateAutolistShortcutsInLinksDir@@YAJXZ; CreateAutolistShortcutsInLinksDir(void)
0x18029e404  mov     ebx, eax
0x18029e406  mov     rcx, [rbp+57h+ppv]
0x18029e40a  mov     rax, [rcx]
0x18029e40d  mov     rax, [rax+10h]
0x18029e411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e416  xor     eax, eax
0x18029e418  mov     r9d, 3001Fh
0x18029e41e  test    ebx, ebx
0x18029e420  mov     ecx, 5021h; pszPath
0x18029e425  cmovns  ebx, eax
0x18029e428  xor     r8d, r8d
0x18029e42b  xor     edx, edx
0x18029e42d  call    cs:__imp_SHGetShellKeyEx
0x18029e434  nop     dword ptr [rax+rax+00h]
0x18029e439  mov     rdi, rax
0x18029e43c  test    rax, rax
0x18029e43f  jz      short loc_18029E461
0x18029e441  xor     edx, edx; pszSubKey
0x18029e443  mov     rcx, rax; hkey
0x18029e446  call    cs:__imp_SHDeleteKeyA
0x18029e44d  nop     dword ptr [rax+rax+00h]
0x18029e452  mov     rcx, rdi; hKey
0x18029e455  call    cs:__imp_RegCloseKey
0x18029e45c  nop     dword ptr [rax+rax+00h]
0x18029e461  call    ?_ApplyPassiveFTP@@YAXXZ; _ApplyPassiveFTP(void)
0x18029e466  call    ?_DeleteOldRemovableLinks@@YAXXZ; _DeleteOldRemovableLinks(void)
0x18029e46b  lea     rcx, aMydocsDll; "mydocs.dll"
0x18029e472  call    cs:__imp_LoadLibraryW
0x18029e479  nop     dword ptr [rax+rax+00h]
0x18029e47e  mov     rdi, rax
0x18029e481  test    rax, rax
0x18029e484  jz      short loc_18029E4B5
0x18029e486  lea     rdx, aPeruserinit; "PerUserInit"
0x18029e48d  mov     rcx, rax; hModule
0x18029e490  call    cs:__imp_GetProcAddress
0x18029e497  nop     dword ptr [rax+rax+00h]
0x18029e49c  test    rax, rax
0x18029e49f  jz      short loc_18029E4A6
0x18029e4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e4a6  mov     rcx, rdi; hLibModule
0x18029e4a9  call    cs:__imp_FreeLibrary
0x18029e4b0  nop     dword ptr [rax+rax+00h]
0x18029e4b5  call    ?_DefaultVisualEffects@@YAXXZ; _DefaultVisualEffects(void)
0x18029e4ba  call    ?IsOS_OS_ANYSERVER@@YAHXZ; IsOS_OS_ANYSERVER(void)
0x18029e4bf  test    eax, eax
0x18029e4c1  jnz     short loc_18029E4C8
0x18029e4c3  call    ?_NoDriveAutorunTweak@@YAXXZ; _NoDriveAutorunTweak(void)
0x18029e4c8  call    ?MigrateFavoriteLinks@@YAXXZ; MigrateFavoriteLinks(void)
0x18029e4cd  lea     r9, [rbp+57h+var_54]; unsigned int *
0x18029e4d1  mov     [rbp+57h+var_54], 0
0x18029e4d8  lea     r8, aPackagelistver; "PackageListVersion"
0x18029e4df  mov     rcx, r14; HKEY
0x18029e4e2  lea     rdx, aSoftwareMicros_31; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18029e4e9  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18029e4ee  test    eax, eax
0x18029e4f0  jns     short loc_18029E52C
0x18029e4f2  xor     r9d, r9d; unsigned int
0x18029e4f5  lea     r8, aPackagelistver; "PackageListVersion"
0x18029e4fc  lea     rdx, aSoftwareMicros_31; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18029e503  mov     rcx, r14; HKEY
0x18029e506  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18029e50b  jmp     short loc_18029E52C
0x18029e50d  xor     ebx, ebx
0x18029e50f  call    ?Shell32RegTypeLib@@YAJXZ; Shell32RegTypeLib(void)
0x18029e514  test    eax, eax
0x18029e516  cmovs   ebx, eax
0x18029e519  call    cs:__imp_SHPrepareKnownFoldersCommon
0x18029e520  nop     dword ptr [rax+rax+00h]
0x18029e525  jmp     short loc_18029E52C
0x18029e527  mov     ebx, 80004001h
0x18029e52c  mov     eax, ebx
0x18029e52e  mov     rcx, [rbp+57h+var_30]
0x18029e532  xor     rcx, rsp; StackCookie
0x18029e535  call    __security_check_cookie
0x18029e53a  add     rsp, 88h
0x18029e541  pop     r14
0x18029e543  pop     rdi
0x18029e544  pop     rbx
0x18029e545  pop     rbp
0x18029e546  retn
```
