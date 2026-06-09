# DllInstall

- ea: `0x180283d90`
- end: `0x18028405b`
- name: `DllInstall`
- size: `715`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180060798`
- `0x1800b8f00`
- `0x1800f188c`
- `0x180107838`
- `0x1801fa4c4`
- `0x180233280`
- `0x18027f9ec`
- `0x180280150`
- `0x180281e58`
- `0x180282e90`
- `0x1802830e8`
- `0x180283380`
- `0x180283494`
- `0x180283d90`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180283fc9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180283fc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180283fb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180283fb6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180283f9e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180283f9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180283e90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180283e90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180283eeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180283f87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180283eeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180283f87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180283ebd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180283ebd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180283de0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180283de0`
- `USER32!SystemParametersInfoW` at `0x180283ee1`
- `USER32!SystemParametersInfoW` at `0x180283ee1`
- `USER32!GetSystemMetrics` at `0x180283df6`
- `USER32!GetSystemMetrics` at `0x180283df6`
- `ntdll!RtlGetNtProductType` at `0x180283dc7`
- `ntdll!RtlGetNtProductType` at `0x180283dc7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180283f1b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180283f1b`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyA` at `0x180283f7e`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyA` at `0x180283f7e`
- `api-ms-win-storage-exports-internal-l1-1-0!SHPrepareKnownFoldersCommon` at `0x180284033`
- `api-ms-win-storage-exports-internal-l1-1-0!SHPrepareKnownFoldersCommon` at `0x180284033`
- `api-ms-win-storage-exports-internal-l1-1-0!SHPrepareKnownFoldersUser` at `0x180283ef1`
- `api-ms-win-storage-exports-internal-l1-1-0!SHPrepareKnownFoldersUser` at `0x180283ef1`
- `SHLWAPI!__imp_SKGetValueW` at `0x180283e46`
- `SHLWAPI!__imp_SKGetValueW` at `0x180283e46`
- `SHLWAPI!__imp_SHGetShellKeyEx` at `0x180283f6b`
- `SHLWAPI!__imp_SHGetShellKeyEx` at `0x180283f6b`
- `Windows.Storage!__imp_SHGetSetSettings` at `0x180283e6e`
- `Windows.Storage!__imp_SHGetSetSettings` at `0x180283e6e`

## string_xrefs

- `0x180283ffc`: `Software\Microsoft\Windows\CurrentVersion\Explorer\Package Installation`
- `0x180284016`: `Software\Microsoft\Windows\CurrentVersion\Explorer\Package Installation`
- `0x180283f97`: `mydocs.dll`

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
0x180283d90  push    rbp
0x180283d92  push    rbx
0x180283d93  push    rdi
0x180283d94  push    r14
0x180283d96  lea     rbp, [rsp-3Fh]
0x180283d9b  sub     rsp, 88h
0x180283da2  mov     rax, cs:__security_cookie
0x180283da9  xor     rax, rsp
0x180283dac  mov     [rbp+57h+var_30], rax
0x180283db0  mov     rbx, rdx
0x180283db3  test    ecx, ecx
0x180283db5  jz      loc_18028403B
0x180283dbb  mov     edi, 1
0x180283dc0  lea     rcx, [rbp+57h+ProductType]; ProductType
0x180283dc4  mov     [rbp+57h+ProductType], edi
0x180283dc7  call    cs:__imp_RtlGetNtProductType
0x180283dcd  test    rbx, rbx
0x180283dd0  jz      loc_180284027
0x180283dd6  lea     rdx, aU_1; "U"
0x180283ddd  mov     rcx, rbx; pszStr1
0x180283de0  call    cs:__imp_StrCmpICW
0x180283de6  test    eax, eax
0x180283de8  jnz     loc_180284027
0x180283dee  call    ?_UpdateSIDsOnLibraries@@YAXXZ; _UpdateSIDsOnLibraries(void)
0x180283df3  lea     ecx, [rdi+55h]; nIndex
0x180283df6  call    cs:__imp_GetSystemMetrics
0x180283dfc  mov     r14, 0FFFFFFFF80000001h
0x180283e03  test    eax, eax
0x180283e05  jz      loc_180283EF1
0x180283e0b  lea     rax, [rbp+57h+var_5C]
0x180283e0f  mov     [rbp+57h+hKey], 0
0x180283e17  mov     [rsp+0A0h+lpcbData], rax
0x180283e1c  lea     r8, aAutocheckselec; "AutoCheckSelect"
0x180283e23  lea     rax, [rbp+57h+var_58]
0x180283e27  mov     [rbp+57h+var_58], 0
0x180283e2e  xor     r9d, r9d
0x180283e31  mov     [rsp+0A0h+phkResult], rax
0x180283e36  lea     rdx, aAdvanced_0; "Advanced"
0x180283e3d  mov     [rbp+57h+var_5C], 4
0x180283e44  mov     ecx, edi
0x180283e46  call    cs:__imp_SKGetValueW
0x180283e4c  test    eax, eax
0x180283e4e  jz      short loc_180283E74
0x180283e50  xorps   xmm0, xmm0
0x180283e53  lea     rcx, [rbp+57h+var_50]; lpss
0x180283e57  movups  xmmword ptr [rbp+57h+var_50.iSortDirection], xmm0
0x180283e5b  mov     r8d, edi; bSet
0x180283e5e  mov     dword ptr [rbp+57h+var_50.fSepProcess], 8
0x180283e65  mov     edx, 800000h; dwMask
0x180283e6a  movups  xmmword ptr [rbp+57h+var_50.fShowAllObjects], xmm0
0x180283e6e  call    cs:__imp_SHGetSetSettings
0x180283e74  lea     rax, [rbp+57h+hKey]
0x180283e78  mov     r9d, 20019h; samDesired
0x180283e7e  xor     r8d, r8d; ulOptions
0x180283e81  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180283e86  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x180283e8d  mov     rcx, r14; hKey
0x180283e90  call    cs:__imp_RegOpenKeyExW
0x180283e96  test    eax, eax
0x180283e98  jnz     short loc_180283EF1
0x180283e9a  mov     rcx, [rbp+57h+hKey]; hKey
0x180283e9e  lea     rdx, aMenudropalignm; "MenuDropAlignment"
0x180283ea5  mov     [rsp+0A0h+lpcbData], 0; lpcbData
0x180283eae  xor     r9d, r9d; lpType
0x180283eb1  xor     r8d, r8d; lpReserved
0x180283eb4  mov     [rsp+0A0h+phkResult], 0; lpData
0x180283ebd  call    cs:__imp_RegQueryValueExW
0x180283ec3  cmp     eax, 2
0x180283ec6  jnz     short loc_180283EE7
0x180283ec8  call    ?IsBiDiLocalizedSystemEx@@YAHPEAG@Z; IsBiDiLocalizedSystemEx(ushort *)
0x180283ecd  xor     edx, edx
0x180283ecf  mov     r9d, 3; fWinIni
0x180283ed5  test    eax, eax
0x180283ed7  setz    dl; uiParam
0x180283eda  xor     r8d, r8d; pvParam
0x180283edd  lea     ecx, [r9+19h]; uiAction
0x180283ee1  call    cs:__imp_SystemParametersInfoW
0x180283ee7  mov     rcx, [rbp+57h+hKey]; hKey
0x180283eeb  call    cs:__imp_RegCloseKey
0x180283ef1  call    cs:__imp_SHPrepareKnownFoldersUser
0x180283ef7  lea     rax, [rbp+57h+ppv]
0x180283efb  mov     [rbp+57h+ppv], 0
0x180283f03  lea     r9, _GUID_a768a74d_ae70_45d6_9997_ea0c0bd5513e; riid
0x180283f0a  mov     [rsp+0A0h+phkResult], rax; ppv
0x180283f0f  mov     r8d, edi; dwClsContext
0x180283f12  lea     rcx, _GUID_f235ce7d_b143_4d4f_ad93_64e48d53a5fb; rclsid
0x180283f19  xor     edx, edx; pUnkOuter
0x180283f1b  call    cs:__imp_CoCreateInstance
0x180283f21  mov     ebx, eax
0x180283f23  test    eax, eax
0x180283f25  js      short loc_180283F54
0x180283f27  mov     rcx, [rbp+57h+ppv]
0x180283f2b  mov     rax, [rcx]
0x180283f2e  mov     rax, [rax+20h]
0x180283f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180283f37  mov     ebx, eax
0x180283f39  test    eax, eax
0x180283f3b  js      short loc_180283F44
0x180283f3d  call    ?CreateAutolistShortcutsInLinksDir@@YAJXZ; CreateAutolistShortcutsInLinksDir(void)
0x180283f42  mov     ebx, eax
0x180283f44  mov     rcx, [rbp+57h+ppv]
0x180283f48  mov     rax, [rcx]
0x180283f4b  mov     rax, [rax+10h]
0x180283f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180283f54  xor     eax, eax
0x180283f56  mov     r9d, 3001Fh
0x180283f5c  test    ebx, ebx
0x180283f5e  mov     ecx, 5021h; pszPath
0x180283f63  cmovns  ebx, eax
0x180283f66  xor     r8d, r8d
0x180283f69  xor     edx, edx
0x180283f6b  call    cs:__imp_SHGetShellKeyEx
0x180283f71  mov     rdi, rax
0x180283f74  test    rax, rax
0x180283f77  jz      short loc_180283F8D
0x180283f79  xor     edx, edx; pszSubKey
0x180283f7b  mov     rcx, rax; hkey
0x180283f7e  call    cs:__imp_SHDeleteKeyA
0x180283f84  mov     rcx, rdi; hKey
0x180283f87  call    cs:__imp_RegCloseKey
0x180283f8d  call    ?_ApplyPassiveFTP@@YAXXZ; _ApplyPassiveFTP(void)
0x180283f92  call    ?_DeleteOldRemovableLinks@@YAXXZ; _DeleteOldRemovableLinks(void)
0x180283f97  lea     rcx, aMydocsDll; "mydocs.dll"
0x180283f9e  call    cs:__imp_LoadLibraryW
0x180283fa4  mov     rdi, rax
0x180283fa7  test    rax, rax
0x180283faa  jz      short loc_180283FCF
0x180283fac  lea     rdx, aPeruserinit; "PerUserInit"
0x180283fb3  mov     rcx, rax; hModule
0x180283fb6  call    cs:__imp_GetProcAddress
0x180283fbc  test    rax, rax
0x180283fbf  jz      short loc_180283FC6
0x180283fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180283fc6  mov     rcx, rdi; hLibModule
0x180283fc9  call    cs:__imp_FreeLibrary
0x180283fcf  call    ?_DefaultVisualEffects@@YAXXZ; _DefaultVisualEffects(void)
0x180283fd4  call    ?IsOS_OS_ANYSERVER@@YAHXZ; IsOS_OS_ANYSERVER(void)
0x180283fd9  test    eax, eax
0x180283fdb  jnz     short loc_180283FE2
0x180283fdd  call    ?_NoDriveAutorunTweak@@YAXXZ; _NoDriveAutorunTweak(void)
0x180283fe2  call    ?MigrateFavoriteLinks@@YAXXZ; MigrateFavoriteLinks(void)
0x180283fe7  lea     r9, [rbp+57h+var_54]; unsigned int *
0x180283feb  mov     [rbp+57h+var_54], 0
0x180283ff2  lea     r8, aPackagelistver; "PackageListVersion"
0x180283ff9  mov     rcx, r14; HKEY
0x180283ffc  lea     rdx, aSoftwareMicros_31; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180284003  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180284008  test    eax, eax
0x18028400a  jns     short loc_180284040
0x18028400c  xor     r9d, r9d; unsigned int
0x18028400f  lea     r8, aPackagelistver; "PackageListVersion"
0x180284016  lea     rdx, aSoftwareMicros_31; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18028401d  mov     rcx, r14; HKEY
0x180284020  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180284025  jmp     short loc_180284040
0x180284027  xor     ebx, ebx
0x180284029  call    ?Shell32RegTypeLib@@YAJXZ; Shell32RegTypeLib(void)
0x18028402e  test    eax, eax
0x180284030  cmovs   ebx, eax
0x180284033  call    cs:__imp_SHPrepareKnownFoldersCommon
0x180284039  jmp     short loc_180284040
0x18028403b  mov     ebx, 80004001h
0x180284040  mov     eax, ebx
0x180284042  mov     rcx, [rbp+57h+var_30]
0x180284046  xor     rcx, rsp; StackCookie
0x180284049  call    __security_check_cookie
0x18028404e  add     rsp, 88h
0x180284055  pop     r14
0x180284057  pop     rdi
0x180284058  pop     rbx
0x180284059  pop     rbp
0x18028405a  retn
```
