# SetupThemeForUser(void)

- ea: `0x180041a2c`
- end: `0x1800421dd`
- name: `?SetupThemeForUser@@YAJXZ`
- size: `1969`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800426c0`

## callees

- `0x180007d20`
- `0x180007e60`
- `0x1800082f0`
- `0x18000ab10`
- `0x18000c470`
- `0x180014e40`
- `0x180015660`
- `0x1800179e0`
- `0x18001a930`
- `0x18001d484`
- `0x18001ea1c`
- `0x18001f370`
- `0x1800211c4`
- `0x1800217fc`
- `0x180021cf0`
- `0x180030bb4`
- `0x180033524`
- `0x1800339d0`
- `0x180034e50`
- `0x1800358c0`
- `0x18003633c`
- `0x18003c1f4`
- `0x18003cf08`
- `0x1800406fc`
- `0x180040f10`
- `0x180040fcc`
- `0x1800415a4`
- `0x180041704`
- `0x180041a2c`
- `0x1800421e4`
- `0x1800423d0`
- `0x1800429e4`
- `0x180060058`
- `0x180060150`
- `0x18006ad80`

## import_xrefs

- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x180041bab`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x180041bab`
- `SHLWAPI!PathFileExistsW` at `0x180041c4d`
- `SHLWAPI!PathFileExistsW` at `0x180041c4d`
- `SHLWAPI!StrToIntExW` at `0x180041ad1`
- `SHLWAPI!StrToIntExW` at `0x180041b13`
- `SHLWAPI!StrToIntExW` at `0x180041ad1`
- `SHLWAPI!StrToIntExW` at `0x180041b13`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180041d04`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180041d04`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180041c8c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180041ca8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180041c8c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180041ca8`
- `USER32!SystemParametersInfoW` at `0x180041bd7`
- `USER32!SystemParametersInfoW` at `0x180041bd7`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180041b7b`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180041b7b`

## string_xrefs

- `0x180041cc4`: `%SystemRoot%\Resources\Ease of Access Themes\hc2.theme`
- `0x180041cd0`: `%SystemRoot%\Resources\Ease of Access Themes\hcblack.theme`
- `0x180041cb8`: `%SystemRoot%\Resources\Ease of Access Themes\hc1.theme`
- `0x180041cdb`: `%SystemRoot%\Resources\Ease of Access Themes\hcwhite.theme`
- `0x180041ea1`: `InstallTheme`
- `0x180041ba1`: `NoThemeInstall`
- `0x180041ee0`: `InstallVisualStyle`
- `0x180041f04`: `InstallVisualStyle`
- `0x180041f1d`: `InstallVisualStyleColor`
- `0x180041f3a`: `InstallVisualStyleColor`
- `0x180041f53`: `InstallVisualStyleSize`
- `0x180041f72`: `InstallVisualStyleSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SetupThemeForUser(void)
{
  int Path; // ebx
  const unsigned __int16 *v1; // rdx
  HKEY v2; // rcx
  unsigned int v3; // esi
  char v4; // r15
  unsigned int v5; // edx
  int v6; // edx
  int v7; // eax
  HKEY v8; // rcx
  int v9; // r9d
  int v10; // edx
  int v11; // edx
  __int64 v12; // rdx
  unsigned __int16 *v13; // rcx
  __int64 v14; // r8
  char v15; // di
  unsigned __int16 *v16; // rcx
  unsigned int v17; // edx
  int v18; // edx
  HKEY v19; // rcx
  int v20; // r8d
  unsigned int v21; // r9d
  HKEY v22; // rcx
  __int64 v23; // rcx
  int AllRegSoundEvents; // r14d
  unsigned int v25; // ebx
  const unsigned __int16 *Ptr; // rax
  unsigned int v27; // r9d
  const unsigned __int16 *v28; // rdi
  unsigned int v29; // r9d
  unsigned __int16 *v30; // rax
  int v31; // ecx
  int v32; // edx
  unsigned int v34; // [rsp+20h] [rbp-E0h]
  unsigned int v35; // [rsp+20h] [rbp-E0h]
  unsigned int v36; // [rsp+20h] [rbp-E0h]
  unsigned int v37; // [rsp+20h] [rbp-E0h]
  unsigned int v38; // [rsp+20h] [rbp-E0h]
  unsigned int v39; // [rsp+20h] [rbp-E0h]
  unsigned int v40; // [rsp+20h] [rbp-E0h]
  unsigned int v41; // [rsp+20h] [rbp-E0h]
  bool v42; // [rsp+40h] [rbp-C0h] BYREF
  bool v43; // [rsp+41h] [rbp-BFh] BYREF
  HDPA hdpa; // [rsp+48h] [rbp-B8h] BYREF
  int piRet; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v47; // [rsp+58h] [rbp-A8h] BYREF
  __int128 pvParam; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v49; // [rsp+70h] [rbp-90h]
  const wchar_t *v50; // [rsp+78h] [rbp-88h]
  const wchar_t *v51; // [rsp+80h] [rbp-80h]
  const wchar_t *v52; // [rsp+88h] [rbp-78h]
  WCHAR pszPath[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v54; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v55[526]; // [rsp+2A2h] [rbp+1A2h] BYREF
  WCHAR v56[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR Buffer[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  WCHAR pszString[264]; // [rsp+8D0h] [rbp+7D0h] BYREF
  unsigned __int16 v59[264]; // [rsp+AE0h] [rbp+9E0h] BYREF
  unsigned __int16 v60[264]; // [rsp+CF0h] [rbp+BF0h] BYREF
  unsigned __int16 v61[264]; // [rsp+F00h] [rbp+E00h] BYREF

  v42 = 0;
  v43 = 0;
  Path = MapOldTheme(&v42, &v43);
  ValidateCursorSchemes(v2, v1);
  v3 = 0;
  LODWORD(hdpa) = 0;
  piRet = 0;
  if ( (int)HrRegGetValueString(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
              L"SetupVersion",
              pszString,
              0x104u) >= 0 )
    StrToIntExW(pszString, 0, &piRet);
  v46 = 0;
  if ( (int)HrRegGetValueString(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
              L"SetupVersion",
              pszString,
              0x104u) >= 0
    && StrToIntExW(pszString, 0, &v46) )
  {
    v4 = 0;
    v54 = 0;
    memset_0(v55, 0, 0x206u);
    if ( (int)HrRegGetValueString(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                L"SetVisualStyle",
                &v54,
                0x104u) >= 0
      && (piRet == v46 || !piRet) )
    {
      v4 = 1;
    }
    if ( (unsigned int)ClassicGetSystemMetrics(67) )
    {
LABEL_86:
      if ( v4 )
        ApplySetVisualStylePolicy(&v54);
      return (unsigned int)Path;
    }
    pszPath[0] = 0;
    v56[0] = 0;
    Buffer[0] = 0;
    if ( SHRegGetBoolValueFromHKCUHKLM(L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes", L"NoThemeInstall", 0) )
      goto LABEL_56;
    pvParam = 0;
    LODWORD(pvParam) = 16;
    if ( SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) && (BYTE4(pvParam) & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_db16c1876f9a307062c8a47e08f10cfd_Traceguids);
      Path = HrRegGetPath(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
               L"CurrentTheme",
               pszPath,
               v34);
      if ( Path >= 0 )
      {
        Path = ValidateOrFixThemeLocation(pszPath, v6);
        if ( Path >= 0 )
        {
          if ( PathFileExistsW(pszPath) )
            goto LABEL_56;
        }
      }
      pszPath[0] = 0;
      StringCchCopyW(&v54, 0x104u, L"%ResourceDir%\\themes\\Aero\\AeroLite.msstyles");
      LoadStringW(g_hinst, 0x7EBu, Buffer, 260);
      LoadStringW(g_hinst, 0x7ECu, v56, 260);
      v7 = HighContrastNumberFromSchemeName(*((const unsigned __int16 **)&pvParam + 1));
      v49 = L"%SystemRoot%\\Resources\\Ease of Access Themes\\hc1.theme";
      v50 = L"%SystemRoot%\\Resources\\Ease of Access Themes\\hc2.theme";
      v51 = L"%SystemRoot%\\Resources\\Ease of Access Themes\\hcblack.theme";
      v52 = L"%SystemRoot%\\Resources\\Ease of Access Themes\\hcwhite.theme";
      if ( v7 > 0 && (unsigned int)(v7 - 1) < 4 )
      {
        if ( !(unsigned int)SHExpandEnvironmentStringsW(*((_QWORD *)&pvParam + v7 + 1), v59, 260) )
          goto LABEL_56;
        goto LABEL_22;
      }
      Path = HrRegGetPath(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
               L"LastHighContrastTheme",
               v59,
               v35);
      if ( Path >= 0 )
      {
LABEL_22:
        Path = HrRegSetPath(v8, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes", L"CurrentTheme", v9, v59);
        goto LABEL_56;
      }
      goto LABEL_56;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_db16c1876f9a307062c8a47e08f10cfd_Traceguids);
    if ( (int)HrRegGetPath(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                L"CurrentTheme",
                pszPath,
                v34) < 0
      || (Path = ValidateOrFixThemeLocation(pszPath, v10), Path < 0) )
    {
      if ( (int)HrRegGetPath(
                  HKEY_CURRENT_USER,
                  L"Software\\Policies\\Microsoft\\Windows\\Personalization",
                  L"ThemeFile",
                  pszPath,
                  v36) >= 0
        || (int)HrRegGetPath(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Policies\\Microsoft\\Windows\\Personalization",
                  L"ThemeFile",
                  pszPath,
                  v37) >= 0 )
      {
        Path = ValidateOrFixThemeLocation(pszPath, v11);
        if ( Path >= 0 )
          goto LABEL_56;
      }
      if ( IsDesktopSpotlightAllowedByPolicy()
        && (v47 = 0,
            (int)SHRegGetDWORD(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DesktopOptimization",
                   L"WindowsSpotlightTheme",
                   &v47) >= 0)
        && v47 == 1
        && (Path = GetWindowsSpotlightTheme(v13, v12), Path >= 0) )
      {
        v15 = 1;
      }
      else
      {
        v15 = 0;
        Path = GetOEMTheme(pszPath, v12);
        if ( Path >= 0 )
          Path = ValidateOrFixThemeLocation(pszPath, v12);
      }
      LOBYTE(v14) = 3;
      LOBYTE(v12) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl'::`2'::impl,
        v12,
        v14);
      if ( v15 )
        goto LABEL_43;
      if ( Path >= 0 )
        goto LABEL_56;
      Path = GetWindowsSpotlightTheme(v16, v5);
      if ( Path >= 0 )
      {
LABEL_43:
        if ( Path >= 0 )
        {
LABEL_56:
          ExpandResourceDir(pszPath, v5);
          ExpandResourceDir(&v54, v17);
          if ( pszPath[0] || v54 )
          {
            LODWORD(hdpa) = 0;
            if ( (int)SHRegGetBOOLWithREGSAM(
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                        L"WallpaperSetFromTheme",
                        v21,
                        (int *)&hdpa) >= 0
              && (_DWORD)hdpa )
            {
              if ( !v43 )
                v3 |= 1u;
            }
            else
            {
              SHRegSetBOOL(v22, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes", L"WallpaperSetFromTheme", 1);
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_db16c1876f9a307062c8a47e08f10cfd_Traceguids, v3);
            hdpa = 0;
            if ( (unsigned int)CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::Create(&hdpa) )
            {
              AllRegSoundEvents = GetAllRegSoundEvents(&hdpa);
              v25 = 0;
              if ( AllRegSoundEvents > 0 )
              {
                while ( 1 )
                {
                  Ptr = (const unsigned __int16 *)g_pfn_DPA_GetPtr(hdpa, v25);
                  v28 = Ptr;
                  if ( Ptr )
                  {
                    if ( GetSystemSoundSchemeSetting(Ptr, L".Current", v60, v27) >= 0
                      && GetSystemSoundSchemeSetting(v28, L".Default", v61, v29) >= 0 )
                    {
                      v30 = v60;
                      do
                      {
                        v31 = v30[264];
                        v32 = *v30 - v31;
                        if ( v32 )
                          break;
                        ++v30;
                      }
                      while ( v31 );
                      if ( v32 )
                        break;
                    }
                  }
                  if ( (int)++v25 >= AllRegSoundEvents )
                    goto LABEL_78;
                }
                v3 |= 0x10u;
              }
LABEL_78:
              CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::Destroy(&hdpa);
            }
            Path = InstallThemeAndDoNotStompBackground(v23, pszPath, &v54, Buffer, v56, v4, v3);
            v4 = 0;
            CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::~CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>(&hdpa);
          }
          if ( Path >= 0 )
            Path = HrRegSetValueString(
                     v19,
                     L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                     L"SetupVersion",
                     pszString);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SSSSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v18,
              v20,
              (unsigned int)pszPath,
              (__int64)&v54,
              (__int64)Buffer,
              (__int64)v56,
              Path);
          ThemesTelemetry::SetupThemeForUser();
          goto LABEL_86;
        }
      }
      Path = HrRegGetPath(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
               L"InstallTheme",
               pszPath,
               v37);
      if ( Path < 0 )
      {
        Path = GetSystemDefaultTheme(pszPath, v5);
        if ( Path < 0 && !v4 )
        {
          if ( (int)HrRegGetPath(
                      HKEY_CURRENT_USER,
                      L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                      L"InstallVisualStyle",
                      &v54,
                      v38) < 0 )
            HrRegGetPath(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
              L"InstallVisualStyle",
              &v54,
              v39);
          if ( (int)HrRegGetPath(
                      HKEY_CURRENT_USER,
                      L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                      L"InstallVisualStyleColor",
                      Buffer,
                      v39) < 0 )
            HrRegGetPath(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
              L"InstallVisualStyleColor",
              Buffer,
              v40);
          Path = HrRegGetPath(
                   HKEY_CURRENT_USER,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                   L"InstallVisualStyleSize",
                   v56,
                   v40);
          if ( Path < 0 )
            Path = HrRegGetPath(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                     L"InstallVisualStyleSize",
                     v56,
                     v41);
        }
      }
    }
    if ( piRet > 0 && !v42 )
    {
      EnsureValidSettings((enum THEME_APPLY_FLAGS *)&hdpa);
      v3 = (unsigned int)hdpa;
    }
    goto LABEL_56;
  }
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x180041a2c  push    rbp
0x180041a2e  push    rbx
0x180041a2f  push    rsi
0x180041a30  push    rdi
0x180041a31  push    r12
0x180041a33  push    r13
0x180041a35  push    r14
0x180041a37  push    r15
0x180041a39  lea     rbp, [rsp-1028h]
0x180041a41  mov     eax, 1128h
0x180041a46  call    _alloca_probe
0x180041a4b  sub     rsp, rax
0x180041a4e  mov     rax, cs:__security_cookie
0x180041a55  xor     rax, rsp
0x180041a58  mov     [rbp+1060h+var_50], rax
0x180041a5f  xor     r12d, r12d
0x180041a62  mov     [rsp+1160h+var_1120], r12b
0x180041a67  mov     [rsp+1160h+var_111F], r12b
0x180041a6c  lea     rdx, [rsp+1160h+var_111F]; bool *
0x180041a71  lea     rcx, [rsp+1160h+var_1120]; bool *
0x180041a76  call    ?MapOldTheme@@YAJPEA_N0@Z; MapOldTheme(bool *,bool *)
0x180041a7b  mov     ebx, eax
0x180041a7d  call    ?ValidateCursorSchemes@@YAJPEAUHKEY__@@PEBG@Z; ValidateCursorSchemes(HKEY__ *,ushort const *)
0x180041a82  mov     esi, r12d
0x180041a85  mov     dword ptr [rsp+1160h+hdpa], r12d
0x180041a8a  mov     [rsp+1160h+piRet], r12d
0x180041a8f  mov     edi, 104h
0x180041a94  mov     dword ptr [rsp+1160h+var_1140], edi; unsigned int
0x180041a98  lea     r9, [rbp+1060h+pszString]; unsigned __int16 *
0x180041a9f  lea     r8, aSetupversion; "SetupVersion"
0x180041aa6  lea     r13, pszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180041aad  mov     rdx, r13; unsigned __int16 *
0x180041ab0  mov     r14, 0FFFFFFFF80000001h
0x180041ab7  mov     rcx, r14; HKEY
0x180041aba  call    ?HrRegGetValueString@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetValueString(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041abf  test    eax, eax
0x180041ac1  js      short loc_180041AD7
0x180041ac3  lea     r8, [rsp+1160h+piRet]; piRet
0x180041ac8  xor     edx, edx; dwFlags
0x180041aca  lea     rcx, [rbp+1060h+pszString]; pszString
0x180041ad1  call    cs:__imp_StrToIntExW
0x180041ad7  mov     [rsp+1160h+var_110C], r12d
0x180041adc  mov     dword ptr [rsp+1160h+var_1140], edi; unsigned int
0x180041ae0  lea     r9, [rbp+1060h+pszString]; unsigned __int16 *
0x180041ae7  lea     r8, aSetupversion; "SetupVersion"
0x180041aee  mov     rdx, r13; unsigned __int16 *
0x180041af1  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180041af8  call    ?HrRegGetValueString@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetValueString(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041afd  test    eax, eax
0x180041aff  js      loc_1800421B8
0x180041b05  lea     r8, [rsp+1160h+var_110C]; piRet
0x180041b0a  xor     edx, edx; dwFlags
0x180041b0c  lea     rcx, [rbp+1060h+pszString]; pszString
0x180041b13  call    cs:__imp_StrToIntExW
0x180041b19  test    eax, eax
0x180041b1b  jz      loc_1800421B8
0x180041b21  mov     r15b, r12b
0x180041b24  mov     [rbp+1060h+var_EC0], r12w
0x180041b2c  xor     edx, edx; Val
0x180041b2e  mov     r8d, 206h; Size
0x180041b34  lea     rcx, [rbp+1060h+var_EBE]; void *
0x180041b3b  call    memset_0
0x180041b40  mov     dword ptr [rsp+1160h+var_1140], edi; unsigned int
0x180041b44  lea     r9, [rbp+1060h+var_EC0]; unsigned __int16 *
0x180041b4b  lea     r8, aSetvisualstyle; "SetVisualStyle"
0x180041b52  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180041b59  mov     rcx, r14; HKEY
0x180041b5c  call    ?HrRegGetValueString@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetValueString(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041b61  test    eax, eax
0x180041b63  js      short loc_180041B76
0x180041b65  mov     eax, [rsp+1160h+piRet]
0x180041b69  cmp     eax, [rsp+1160h+var_110C]
0x180041b6d  jz      short loc_180041B73
0x180041b6f  test    eax, eax
0x180041b71  jnz     short loc_180041B76
0x180041b73  mov     r15b, 1
0x180041b76  mov     ecx, 43h ; 'C'
0x180041b7b  call    cs:__imp_ClassicGetSystemMetrics
0x180041b81  test    eax, eax
0x180041b83  jnz     loc_1800421A7
0x180041b89  mov     [rbp+1060h+pszPath], r12w
0x180041b8e  mov     [rbp+1060h+var_CB0], r12w
0x180041b96  mov     [rbp+1060h+Buffer], r12w
0x180041b9e  xor     r8d, r8d; fDefault
0x180041ba1  lea     rdx, aNothemeinstall; "NoThemeInstall"
0x180041ba8  mov     rcx, r13; pszKey
0x180041bab  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x180041bb1  mov     ecx, 10h
0x180041bb6  test    eax, eax
0x180041bb8  jnz     loc_180041FA2
0x180041bbe  xorps   xmm0, xmm0
0x180041bc1  movups  [rsp+1160h+pvParam], xmm0
0x180041bc6  mov     dword ptr [rsp+1160h+pvParam], ecx
0x180041bca  xor     r9d, r9d; fWinIni
0x180041bcd  lea     r8, [rsp+1160h+pvParam]; pvParam
0x180041bd2  mov     edx, ecx; uiParam
0x180041bd4  lea     ecx, [rdx+32h]; uiAction
0x180041bd7  call    cs:__imp_SystemParametersInfoW
0x180041bdd  test    eax, eax
0x180041bdf  jz      loc_180041D59
0x180041be5  test    byte ptr [rsp+1160h+pvParam+4], 1
0x180041bea  jz      loc_180041D59
0x180041bf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180041bf7  lea     rax, WPP_GLOBAL_Control
0x180041bfe  cmp     rcx, rax
0x180041c01  jz      short loc_180041C1E
0x180041c03  test    byte ptr [rcx+1Ch], 8
0x180041c07  jz      short loc_180041C1E
0x180041c09  mov     edx, 10h
0x180041c0e  lea     r8, WPP_db16c1876f9a307062c8a47e08f10cfd_Traceguids
0x180041c15  mov     rcx, [rcx+10h]
0x180041c19  call    WPP_SF_
0x180041c1e  lea     r9, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041c22  lea     r8, aCurrenttheme; "CurrentTheme"
0x180041c29  mov     rdx, r13; pszSubKey
0x180041c2c  mov     rcx, r14; hkey
0x180041c2f  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041c34  mov     ebx, eax
0x180041c36  test    eax, eax
0x180041c38  js      short loc_180041C5B
0x180041c3a  lea     rcx, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041c3e  call    ?ValidateOrFixThemeLocation@@YAJPEAGH@Z; ValidateOrFixThemeLocation(ushort *,int)
0x180041c43  mov     ebx, eax
0x180041c45  test    eax, eax
0x180041c47  js      short loc_180041C5B
0x180041c49  lea     rcx, [rbp+1060h+pszPath]; pszPath
0x180041c4d  call    cs:__imp_PathFileExistsW
0x180041c53  test    eax, eax
0x180041c55  jnz     loc_180041FA2
0x180041c5b  mov     [rbp+1060h+pszPath], r12w
0x180041c60  lea     r8, aResourcedirThe_0; "%ResourceDir%\\themes\\Aero\\AeroLite.m"...
0x180041c67  mov     rdx, rdi; unsigned __int64
0x180041c6a  lea     rcx, [rbp+1060h+var_EC0]; unsigned __int16 *
0x180041c71  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041c76  mov     r9d, edi; cchBufferMax
0x180041c79  lea     r8, [rbp+1060h+Buffer]; lpBuffer
0x180041c80  mov     edx, 7EBh; uID
0x180041c85  mov     rcx, cs:g_hinst; hInstance
0x180041c8c  call    cs:__imp_LoadStringW
0x180041c92  mov     r9d, edi; cchBufferMax
0x180041c95  lea     r8, [rbp+1060h+var_CB0]; lpBuffer
0x180041c9c  mov     edx, 7ECh; uID
0x180041ca1  mov     rcx, cs:g_hinst; hInstance
0x180041ca8  call    cs:__imp_LoadStringW
0x180041cae  mov     rcx, qword ptr [rsp+1160h+pvParam+8]; unsigned __int16 *
0x180041cb3  call    ?HighContrastNumberFromSchemeName@@YAHPEBG@Z; HighContrastNumberFromSchemeName(ushort const *)
0x180041cb8  lea     rcx, aSystemrootReso_4; "%SystemRoot%\\Resources\\Ease of Access"...
0x180041cbf  mov     [rsp+1160h+var_10F0], rcx
0x180041cc4  lea     rcx, aSystemrootReso_3; "%SystemRoot%\\Resources\\Ease of Access"...
0x180041ccb  mov     [rsp+1160h+var_10E8], rcx
0x180041cd0  lea     rcx, aSystemrootReso_5; "%SystemRoot%\\Resources\\Ease of Access"...
0x180041cd7  mov     [rbp+1060h+var_10E0], rcx
0x180041cdb  lea     rcx, aSystemrootReso_1; "%SystemRoot%\\Resources\\Ease of Access"...
0x180041ce2  mov     [rbp+1060h+var_10D8], rcx
0x180041ce6  test    eax, eax
0x180041ce8  jle     short loc_180041D34
0x180041cea  lea     ecx, [rax-1]
0x180041ced  cmp     ecx, 4
0x180041cf0  jnb     short loc_180041D34
0x180041cf2  movsxd  rcx, eax
0x180041cf5  mov     r8d, edi
0x180041cf8  lea     rdx, [rbp+1060h+var_680]
0x180041cff  mov     rcx, qword ptr [rsp+rcx*8+1160h+pvParam+8]
0x180041d04  call    cs:__imp_SHExpandEnvironmentStringsW
0x180041d0a  test    eax, eax
0x180041d0c  jz      loc_180041FA2
0x180041d12  lea     rax, [rbp+1060h+var_680]
0x180041d19  mov     [rsp+1160h+var_1140], rax; unsigned __int16 *
0x180041d1e  lea     r8, aCurrenttheme; "CurrentTheme"
0x180041d25  mov     rdx, r13; unsigned __int16 *
0x180041d28  call    ?HrRegSetPath@@YAJPEAUHKEY__@@PEBG1H1@Z; HrRegSetPath(HKEY__ *,ushort const *,ushort const *,int,ushort const *)
0x180041d2d  mov     ebx, eax
0x180041d2f  jmp     loc_180041FA2
0x180041d34  lea     r9, [rbp+1060h+var_680]; unsigned __int16 *
0x180041d3b  lea     r8, aLasthighcontra; "LastHighContrastTheme"
0x180041d42  mov     rdx, r13; pszSubKey
0x180041d45  mov     rcx, r14; hkey
0x180041d48  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041d4d  mov     ebx, eax
0x180041d4f  test    eax, eax
0x180041d51  js      loc_180041FA2
0x180041d57  jmp     short loc_180041D12
0x180041d59  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d60  lea     rax, WPP_GLOBAL_Control
0x180041d67  cmp     rcx, rax
0x180041d6a  jz      short loc_180041D87
0x180041d6c  test    byte ptr [rcx+1Ch], 8
0x180041d70  jz      short loc_180041D87
0x180041d72  mov     edx, 0Fh
0x180041d77  lea     r8, WPP_db16c1876f9a307062c8a47e08f10cfd_Traceguids
0x180041d7e  mov     rcx, [rcx+10h]
0x180041d82  call    WPP_SF_
0x180041d87  lea     r9, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041d8b  lea     r8, aCurrenttheme; "CurrentTheme"
0x180041d92  mov     rdx, r13; pszSubKey
0x180041d95  mov     rcx, r14; hkey
0x180041d98  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041d9d  test    eax, eax
0x180041d9f  js      short loc_180041DB4
0x180041da1  lea     rcx, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041da5  call    ?ValidateOrFixThemeLocation@@YAJPEAGH@Z; ValidateOrFixThemeLocation(ushort *,int)
0x180041daa  mov     ebx, eax
0x180041dac  test    eax, eax
0x180041dae  jns     loc_180041F86
0x180041db4  lea     r9, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041db8  lea     r8, aThemefile; "ThemeFile"
0x180041dbf  lea     rdx, aSoftwarePolici_2; "Software\\Policies\\Microsoft\\Windows"...
0x180041dc6  mov     rcx, r14; hkey
0x180041dc9  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041dce  test    eax, eax
0x180041dd0  jns     short loc_180041DF4
0x180041dd2  lea     r9, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041dd6  lea     r8, aThemefile; "ThemeFile"
0x180041ddd  lea     rdx, aSoftwarePolici_2; "Software\\Policies\\Microsoft\\Windows"...
0x180041de4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180041deb  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041df0  test    eax, eax
0x180041df2  js      short loc_180041E07
0x180041df4  lea     rcx, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041df8  call    ?ValidateOrFixThemeLocation@@YAJPEAGH@Z; ValidateOrFixThemeLocation(ushort *,int)
0x180041dfd  mov     ebx, eax
0x180041dff  test    eax, eax
0x180041e01  jns     loc_180041FA2
0x180041e07  call    ?IsDesktopSpotlightAllowedByPolicy@@YA_NXZ; IsDesktopSpotlightAllowedByPolicy(void)
0x180041e0c  test    al, al
0x180041e0e  jz      short loc_180041E4F
0x180041e10  mov     [rsp+1160h+var_1108], r12d
0x180041e15  lea     r9, [rsp+1160h+var_1108]; unsigned int *
0x180041e1a  lea     r8, aWindowsspotlig_0; "WindowsSpotlightTheme"
0x180041e21  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180041e28  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180041e2f  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180041e34  test    eax, eax
0x180041e36  js      short loc_180041E4F
0x180041e38  cmp     [rsp+1160h+var_1108], 1
0x180041e3d  jnz     short loc_180041E4F
0x180041e3f  call    ?GetWindowsSpotlightTheme@@YAJPEAGI@Z; GetWindowsSpotlightTheme(ushort *,uint)
0x180041e44  mov     ebx, eax
0x180041e46  test    eax, eax
0x180041e48  js      short loc_180041E4F
0x180041e4a  mov     dil, 1
0x180041e4d  jmp     short loc_180041E6C
0x180041e4f  mov     dil, r12b
0x180041e52  lea     rcx, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041e56  call    ?GetOEMTheme@@YAJPEAGI@Z; GetOEMTheme(ushort *,uint)
0x180041e5b  mov     ebx, eax
0x180041e5d  test    eax, eax
0x180041e5f  js      short loc_180041E6C
0x180041e61  lea     rcx, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041e65  call    ?ValidateOrFixThemeLocation@@YAJPEAGH@Z; ValidateOrFixThemeLocation(ushort *,int)
0x180041e6a  mov     ebx, eax
0x180041e6c  mov     r8b, 3
0x180041e6f  mov     dl, 1
0x180041e71  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl(void)'::`2'::impl
0x180041e78  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180041e7d  test    dil, dil
0x180041e80  jnz     short loc_180041E95
0x180041e82  test    ebx, ebx
0x180041e84  jns     loc_180041FA2
0x180041e8a  call    ?GetWindowsSpotlightTheme@@YAJPEAGI@Z; GetWindowsSpotlightTheme(ushort *,uint)
0x180041e8f  mov     ebx, eax
0x180041e91  test    eax, eax
0x180041e93  js      short loc_180041E9D
0x180041e95  test    ebx, ebx
0x180041e97  jns     loc_180041FA2
0x180041e9d  lea     r9, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041ea1  lea     r8, aInstalltheme; "InstallTheme"
0x180041ea8  mov     rdx, r13; pszSubKey
0x180041eab  mov     rcx, r14; hkey
0x180041eae  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041eb3  mov     ebx, eax
0x180041eb5  test    eax, eax
0x180041eb7  jns     loc_180041F86
0x180041ebd  lea     rcx, [rbp+1060h+pszPath]; unsigned __int16 *
0x180041ec1  call    ?GetSystemDefaultTheme@@YAJPEAGK@Z; GetSystemDefaultTheme(ushort *,ulong)
0x180041ec6  mov     ebx, eax
0x180041ec8  test    eax, eax
0x180041eca  jns     loc_180041F86
0x180041ed0  test    r15b, r15b
0x180041ed3  jnz     loc_180041F86
0x180041ed9  lea     r9, [rbp+1060h+var_EC0]; unsigned __int16 *
0x180041ee0  lea     r8, aInstallvisuals; "InstallVisualStyle"
0x180041ee7  mov     rdx, r13; pszSubKey
0x180041eea  mov     rcx, r14; hkey
0x180041eed  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041ef2  mov     rdi, 0FFFFFFFF80000002h
0x180041ef9  test    eax, eax
0x180041efb  jns     short loc_180041F16
0x180041efd  lea     r9, [rbp+1060h+var_EC0]; unsigned __int16 *
0x180041f04  lea     r8, aInstallvisuals; "InstallVisualStyle"
0x180041f0b  mov     rdx, r13; pszSubKey
0x180041f0e  mov     rcx, rdi; hkey
0x180041f11  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041f16  lea     r9, [rbp+1060h+Buffer]; unsigned __int16 *
0x180041f1d  lea     r8, aInstallvisuals_1; "InstallVisualStyleColor"
0x180041f24  mov     rdx, r13; pszSubKey
0x180041f27  mov     rcx, r14; hkey
0x180041f2a  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041f2f  test    eax, eax
0x180041f31  jns     short loc_180041F4C
  ... truncated ...
```
