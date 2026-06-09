# CThemeManager2::_ApplyVisualStyle(THEME_APPLY_FLAGS,THEMEPACK_FLAGS,bool *)

- ea: `0x18004fb2c`
- end: `0x180050348`
- name: `?_ApplyVisualStyle@CThemeManager2@@AEAAJW4THEME_APPLY_FLAGS@@W4THEMEPACK_FLAGS@@PEA_N@Z`
- size: `2076`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004f044`

## callees

- `0x180003690`
- `0x18000ab10`
- `0x1800154d8`
- `0x180015ad0`
- `0x18001987c`
- `0x180019a28`
- `0x18001edb4`
- `0x1800358c0`
- `0x18003d58c`
- `0x18003d67c`
- `0x18003e95c`
- `0x180042664`
- `0x18004b794`
- `0x18004b7e8`
- `0x18004b9b8`
- `0x18004fb2c`
- `0x18005fa88`
- `0x18005fb24`
- `0x180060058`
- `0x18006ac64`
- `0x18006d010`

## import_xrefs

- `SHELL32!__imp_SHRestricted` at `0x18004fd23`
- `SHELL32!__imp_SHRestricted` at `0x18004fd62`
- `SHELL32!__imp_SHRestricted` at `0x18004fd23`
- `SHELL32!__imp_SHRestricted` at `0x18004fd62`
- `SHLWAPI!PathFileExistsW` at `0x18004fc82`
- `SHLWAPI!PathFileExistsW` at `0x18004fcd7`
- `SHLWAPI!PathFileExistsW` at `0x180050058`
- `SHLWAPI!PathFileExistsW` at `0x180050281`
- `SHLWAPI!PathFileExistsW` at `0x18004fc82`
- `SHLWAPI!PathFileExistsW` at `0x18004fcd7`
- `SHLWAPI!PathFileExistsW` at `0x180050058`
- `SHLWAPI!PathFileExistsW` at `0x180050281`
- `SHLWAPI!StrRStrIW` at `0x18004fda0`
- `SHLWAPI!StrRStrIW` at `0x18004fdb7`
- `SHLWAPI!StrRStrIW` at `0x18004fda0`
- `SHLWAPI!StrRStrIW` at `0x18004fdb7`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004fc71`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004fcc9`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180050273`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004fc71`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004fcc9`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180050273`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004fd85`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004fe81`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004fea6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004fecb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004fd85`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004fe81`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004fea6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004fecb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004fc37`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004fc37`
- `api-ms-win-core-privateprofile-l1-1-1!WritePrivateProfileSectionW` at `0x180050257`
- `api-ms-win-core-privateprofile-l1-1-1!WritePrivateProfileSectionW` at `0x180050257`
- `UxTheme!IsThemeActive` at `0x1800501f8`
- `UxTheme!IsThemeActive` at `0x1800501f8`
- `UxTheme!GetCurrentThemeName` at `0x18004fb99`
- `UxTheme!GetCurrentThemeName` at `0x18004fb99`
- `OLEAUT32!__imp_SysFreeString` at `0x1800501db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800502dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800502e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800502f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800502ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800501db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800502dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800502e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800502f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800502ff`
- `OLEAUT32!__imp_VariantClear` at `0x1800500ab`
- `OLEAUT32!__imp_VariantClear` at `0x1800501e6`
- `OLEAUT32!__imp_VariantClear` at `0x1800500ab`
- `OLEAUT32!__imp_VariantClear` at `0x1800501e6`

## string_xrefs

- `0x18004ff73`: `DllName`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CThemeManager2::_ApplyVisualStyle(__int64 a1, __int16 a2, char a3, _BYTE *a4)
{
  PWSTR v7; // rdi
  char v8; // r12
  WCHAR *v9; // rbx
  signed int v10; // esi
  LSTATUS ValueW; // eax
  WCHAR *v12; // rdx
  unsigned int v13; // r10d
  PWSTR v14; // rax
  HINSTANCE v15; // rdx
  HINSTANCE v16; // rdx
  HINSTANCE v17; // rdx
  int v18; // eax
  wil::details::in1diag3 *v19; // rcx
  __int64 v20; // rdx
  bool updated; // al
  HKEY v22; // rcx
  int v23; // r9d
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // rdx
  WCHAR *v26; // rcx
  OLECHAR *v27; // rax
  HINSTANCE v28; // rdx
  bool v29; // r8
  CDimmedWindow *v30; // rax
  int v31; // eax
  int pszSizeBuff; // [rsp+20h] [rbp-E0h]
  bool v34; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  LPCWCH v36; // [rsp+48h] [rbp-B8h] BYREF
  LPCWCH lpString2; // [rsp+50h] [rbp-B0h] BYREF
  LPCWCH v38; // [rsp+58h] [rbp-A8h] BYREF
  struct IThemeScheme *v39; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH lpString1; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h] BYREF
  _BYTE *v43; // [rsp+80h] [rbp-80h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  WCHAR v45[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 pvData[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszThemeFileName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR String1[264]; // [rsp+6D0h] [rbp+5D0h] BYREF
  WCHAR pszColorBuff[264]; // [rsp+8E0h] [rbp+7E0h] BYREF
  WCHAR pszPath[264]; // [rsp+AF0h] [rbp+9F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D48h] [rbp+C48h]

  v43 = a4;
  LOBYTE(v7) = 0;
  *a4 = 0;
  if ( GetCurrentThemeName(pszThemeFileName, 260, pszColorBuff, 260, String1, 260) < 0 )
  {
    pszThemeFileName[0] = 0;
    pszColorBuff[0] = 0;
    String1[0] = 0;
  }
  v8 = 0;
  v9 = 0;
  lpString2 = 0;
  v36 = 0;
  v38 = 0;
  lpString1 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, LPCWCH *))(**(_QWORD **)(a1 + 2128) + 40LL))(
          *(_QWORD *)(a1 + 2128),
          &lpString1);
  if ( v10 < 0 )
    goto LABEL_76;
  v8 = 1;
  pcbData = 520;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
             L"SetVisualStyle",
             2u,
             0,
             pvData,
             &pcbData);
  v10 = ValueW;
  if ( ValueW )
  {
    pvData[0] = 0;
    if ( ValueW > 0 )
      v10 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( v10 < 0 )
  {
    if ( !SHRestricted(REST_NOVISUALSTYLECHOICE) || *(_BYTE *)(a1 + 2145) )
      ATL::CComBSTR::operator=(&lpString2, &lpString1);
    else
      ATL::CComBSTR::operator=(&lpString2, pszThemeFileName);
    v9 = (WCHAR *)lpString2;
  }
  else
  {
    if ( (unsigned int)SHExpandEnvironmentStringsW(pvData, pszPath, 260) && PathFileExistsW(pszPath) )
    {
      v12 = pszPath;
      goto LABEL_15;
    }
    v10 = StringCchCopyW(pvData, 0x104u, L"%SystemRoot%\\Resources\\Themes\\Aero\\AeroLite.msstyles");
    if ( v10 >= 0 )
    {
      if ( !(unsigned int)SHExpandEnvironmentStringsW(pvData, v45, v13) || !PathFileExistsW(v45) )
      {
        v10 = -2147467259;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6DC,
          (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
          (const char *)0x80004005LL,
          pszSizeBuff);
LABEL_17:
        if ( v10 >= 0 )
          goto LABEL_25;
        goto LABEL_24;
      }
      v12 = v45;
LABEL_15:
      ATL::CComBSTR::operator=(&lpString2, v12);
      v9 = (WCHAR *)lpString2;
      goto LABEL_17;
    }
  }
LABEL_24:
  if ( !SHRestricted(REST_NOVISUALSTYLECHOICE) )
  {
LABEL_31:
    v10 = (*(__int64 (__fastcall **)(_QWORD, LPCWCH *))(**(_QWORD **)(a1 + 2128) + 56LL))(*(_QWORD *)(a1 + 2128), &v36);
    if ( v10 < 0 )
      goto LABEL_76;
    v10 = (*(__int64 (__fastcall **)(_QWORD, LPCWCH *))(**(_QWORD **)(a1 + 2128) + 72LL))(*(_QWORD *)(a1 + 2128), &v38);
LABEL_33:
    if ( v10 < 0 )
      goto LABEL_76;
    goto LABEL_34;
  }
LABEL_25:
  if ( CompareStringOrdinal(lpString1, -1, v9, -1, 1) == 2 )
    goto LABEL_31;
  v7 = StrRStrIW(v9, 0, L"aero.msstyles");
  v14 = StrRStrIW(lpString1, 0, L"aero.msstyles");
  if ( v7 )
  {
    ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&v36, v15, 0x7EBu);
    v10 = !ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&v38, v17, 0x7ECu) ? 0x80004005 : 0;
    LOBYTE(v7) = 0;
    goto LABEL_33;
  }
  if ( !v14 )
    goto LABEL_33;
  ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&v36, v15, 0x7EBu);
  if ( !ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&v38, v16, 0x7ECu) )
  {
    v10 = -2147467259;
    goto LABEL_33;
  }
LABEL_34:
  if ( CompareStringOrdinal(pszThemeFileName, -1, v9, -1, 1) != 2
    || CompareStringOrdinal(pszColorBuff, -1, v36, -1, 1) != 2
    || CompareStringOrdinal(String1, -1, v38, -1, 1) != 2 )
  {
    if ( !*(_BYTE *)(a1 + 2145) && !*(_QWORD *)(a1 + 2136) )
    {
      v27 = (OLECHAR *)operator new(0x50u);
      bstrString = v27;
      if ( v27 )
      {
        if ( (a3 & 3) != 0 || (v29 = 1, (a2 & 0x100) == 0) )
          v29 = 0;
        v30 = CDimmedWindow::CDimmedWindow((CDimmedWindow *)v27, v28, v29);
        *(_QWORD *)(a1 + 2136) = v30;
        if ( v30 )
          CDimmedWindow::Create(v30);
      }
      else
      {
        *(_QWORD *)(a1 + 2136) = 0;
      }
    }
    v18 = CThemeManager2::_ApplyWindowColorsAndMetrics((CThemeManager2 *)a1, (a2 & 0x40) == 0, 0);
    v10 = v18;
    v19 = retaddr;
    if ( v18 < 0 )
    {
      v20 = 1844;
      goto LABEL_39;
    }
    v39 = 0;
    if ( PathFileExistsW(v9) )
      v10 = CSkinScheme_CreateInstance(v9, &v39);
    else
      v10 = -2147024894;
    if ( v10 >= 0 )
    {
      pvarg.vt = 0;
      VariantClear(&pvarg);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)ATL::CComBSTR::Copy((ATL::CComBSTR *)&v36);
      if ( !pvarg.llVal && v36 )
      {
        pvarg.vt = 10;
        pvarg.lVal = -2147024882;
        ATL::AtlThrowImpl(-2147024882);
      }
      v42 = 0;
      if ( (*(int (__fastcall **)(struct IThemeScheme *, VARIANTARG *, __int64 *))(*(_QWORD *)v39 + 64LL))(
             v39,
             &pvarg,
             &v42) >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(struct IThemeScheme *, __int64))(*(_QWORD *)v39 + 80LL))(v39, v42);
        if ( v10 >= 0 )
        {
          pcbData = 0;
          v10 = (*(__int64 (__fastcall **)(_QWORD, DWORD *))(**(_QWORD **)(a1 + 2128) + 464LL))(
                  *(_QWORD *)(a1 + 2128),
                  &pcbData);
          UpdateHighContrastSetting(pcbData);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      bstrString = 0;
      if ( (*(int (__fastcall **)(struct IThemeScheme *, BSTR *))(*(_QWORD *)v39 + 40LL))(v39, &bstrString) >= 0
        && (int)CanLoadVisualStyle(bstrString) >= 0 )
      {
        v31 = ApplyVisualStyle(v9, v36, v38);
        v10 = v31;
        if ( v31 >= 0 )
          LOBYTE(v7) = 1;
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x75B,
            (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
            (const char *)(unsigned int)v31,
            pszSizeBuff);
      }
      (*(void (__fastcall **)(struct IThemeScheme *))(*(_QWORD *)v39 + 16LL))(v39);
      SysFreeString(bstrString);
      VariantClear(&pvarg);
      *v43 = (_BYTE)v7;
      if ( (_BYTE)v7 )
        goto LABEL_76;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x742,
        (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
        (const char *)(unsigned int)v10,
        pszSizeBuff);
      *v43 = 0;
    }
    if ( !IsThemeActive() )
      goto LABEL_76;
    v24 = String1;
    v25 = pszColorBuff;
    v26 = pszThemeFileName;
    goto LABEL_75;
  }
  v34 = 0;
  v18 = CThemeManager2::_ApplyWindowColorsAndMetrics((CThemeManager2 *)a1, (a2 & 0x40) == 0, &v34);
  v10 = v18;
  v19 = retaddr;
  if ( v18 < 0 )
  {
    v20 = 1907;
LABEL_39:
    wil::details::in1diag3::_Log_Hr(
      v19,
      (void *)v20,
      (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
      (const char *)(unsigned int)v18,
      pszSizeBuff);
    goto LABEL_76;
  }
  pcbData = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, DWORD *))(**(_QWORD **)(a1 + 2128) + 464LL))(
          *(_QWORD *)(a1 + 2128),
          &pcbData);
  updated = UpdateHighContrastSetting(pcbData);
  if ( v10 >= 0 )
  {
    if ( !updated || !v34 )
    {
      HrRegSetPath(v22, L"Software\\Microsoft\\Windows\\CurrentVersion\\ThemeManager", L"DllName", v23, v9);
      SHRegSetString(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\ThemeManager",
        L"ColorName",
        v36);
      SHRegSetString(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\ThemeManager", L"SizeName", v38);
      goto LABEL_76;
    }
    v24 = v38;
    v25 = v36;
    v26 = v9;
LABEL_75:
    v10 = ApplyVisualStyle(v26, v25, v24);
  }
LABEL_76:
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x798,
      (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
      (const char *)(unsigned int)v10,
      pszSizeBuff);
    if ( v10 == -2147467259 && !v8 )
    {
      WritePrivateProfileSectionW(L"Control Panel\\Colors", 0, (LPCWSTR)(a1 + 12));
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( (unsigned int)SHExpandEnvironmentStringsW(L"%SystemRoot%\\Resources\\Themes\\Aero\\Aero.msstyles", v45, 260)
      && PathFileExistsW(v45) )
    {
      v10 = ApplyVisualStyle(v45, L"NormalColor", L"NormalSize");
    }
  }
  if ( v10 >= 0 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 192LL))(a1);
  else
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7AE,
      (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
      (const char *)(unsigned int)v10,
      pszSizeBuff);
  SysFreeString((BSTR)lpString1);
  SysFreeString((BSTR)v38);
  SysFreeString((BSTR)v36);
  SysFreeString(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004fb2c  mov     [rsp-8+arg_8], rbx
0x18004fb31  push    rbp
0x18004fb32  push    rsi
0x18004fb33  push    rdi
0x18004fb34  push    r12
0x18004fb36  push    r13
0x18004fb38  push    r14
0x18004fb3a  push    r15
0x18004fb3c  lea     rbp, [rsp-0C10h]
0x18004fb44  sub     rsp, 0D10h
0x18004fb4b  mov     rax, cs:__security_cookie
0x18004fb52  xor     rax, rsp
0x18004fb55  mov     [rbp+0C40h+var_40], rax
0x18004fb5c  mov     [rbp+0C40h+var_CC0], r9
0x18004fb60  mov     r13d, r8d
0x18004fb63  mov     r15d, edx
0x18004fb66  mov     r14, rcx
0x18004fb69  xor     edi, edi
0x18004fb6b  mov     [r9], dil
0x18004fb6e  mov     [rsp+0D40h+cchMaxSizeChars], 104h; cchMaxSizeChars
0x18004fb76  lea     rax, [rbp+0C40h+String1]
0x18004fb7d  mov     [rsp+0D40h+pszSizeBuff], rax; pszSizeBuff
0x18004fb82  mov     r9d, 104h; cchMaxColorChars
0x18004fb88  lea     r8, [rbp+0C40h+pszColorBuff]; pszColorBuff
0x18004fb8f  mov     edx, r9d; cchMaxNameChars
0x18004fb92  lea     rcx, [rbp+0C40h+pszThemeFileName]; pszThemeFileName
0x18004fb99  call    cs:__imp_GetCurrentThemeName
0x18004fb9f  test    eax, eax
0x18004fba1  jns     short loc_18004FBB8
0x18004fba3  mov     [rbp+0C40h+pszThemeFileName], di
0x18004fbaa  mov     [rbp+0C40h+pszColorBuff], di
0x18004fbb1  mov     [rbp+0C40h+String1], di
0x18004fbb8  mov     r12b, dil
0x18004fbbb  mov     rbx, rdi
0x18004fbbe  mov     [rsp+0D40h+lpString2], rbx
0x18004fbc3  mov     [rsp+0D40h+var_CF8], rdi
0x18004fbc8  mov     [rsp+0D40h+var_CE8], rdi
0x18004fbcd  mov     [rsp+0D40h+lpString1], rdi
0x18004fbd2  mov     rcx, [r14+850h]
0x18004fbd9  mov     rax, [rcx]
0x18004fbdc  lea     rdx, [rsp+0D40h+lpString1]
0x18004fbe1  mov     rax, [rax+28h]
0x18004fbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbea  mov     esi, eax
0x18004fbec  test    eax, eax
0x18004fbee  js      loc_18005021E
0x18004fbf4  mov     r12d, 1
0x18004fbfa  mov     [rsp+0D40h+var_CFC], 208h
0x18004fc02  lea     rax, [rsp+0D40h+var_CFC]
0x18004fc07  mov     [rsp+0D40h+pcbData], rax; pcbData
0x18004fc0c  lea     rax, [rbp+0C40h+pvData]
0x18004fc13  mov     qword ptr [rsp+0D40h+cchMaxSizeChars], rax; pvData
0x18004fc18  mov     [rsp+0D40h+pszSizeBuff], rdi; int
0x18004fc1d  lea     r9d, [r12+1]; dwFlags
0x18004fc22  lea     r8, aSetvisualstyle; "SetVisualStyle"
0x18004fc29  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004fc30  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18004fc37  call    cs:__imp_RegGetValueW
0x18004fc3d  mov     esi, eax
0x18004fc3f  test    eax, eax
0x18004fc41  jz      short loc_18004FC55
0x18004fc43  mov     [rbp+0C40h+pvData], di
0x18004fc4a  jle     short loc_18004FC55
0x18004fc4c  movzx   esi, ax
0x18004fc4f  or      esi, 80070000h
0x18004fc55  test    esi, esi
0x18004fc57  js      loc_18004FD1E
0x18004fc5d  mov     r8d, 104h
0x18004fc63  lea     rdx, [rbp+0C40h+pszPath]
0x18004fc6a  lea     rcx, [rbp+0C40h+pvData]
0x18004fc71  call    cs:__imp_SHExpandEnvironmentStringsW
0x18004fc77  test    eax, eax
0x18004fc79  jz      short loc_18004FC95
0x18004fc7b  lea     rcx, [rbp+0C40h+pszPath]; pszPath
0x18004fc82  call    cs:__imp_PathFileExistsW
0x18004fc88  test    eax, eax
0x18004fc8a  jz      short loc_18004FC95
0x18004fc8c  lea     rdx, [rbp+0C40h+pszPath]
0x18004fc93  jmp     short loc_18004FCE5
0x18004fc95  lea     r8, aSystemrootReso; "%SystemRoot%\\Resources\\Themes\\Aero\\"...
0x18004fc9c  mov     r10d, 104h
0x18004fca2  mov     edx, r10d; unsigned __int64
0x18004fca5  lea     rcx, [rbp+0C40h+pvData]; unsigned __int16 *
0x18004fcac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004fcb1  mov     esi, eax
0x18004fcb3  test    eax, eax
0x18004fcb5  js      loc_18004FD5D
0x18004fcbb  mov     r8d, r10d
0x18004fcbe  lea     rdx, [rbp+0C40h+var_CA0]
0x18004fcc2  lea     rcx, [rbp+0C40h+pvData]
0x18004fcc9  call    cs:__imp_SHExpandEnvironmentStringsW
0x18004fccf  test    eax, eax
0x18004fcd1  jz      short loc_18004FCF6
0x18004fcd3  lea     rcx, [rbp+0C40h+var_CA0]; pszPath
0x18004fcd7  call    cs:__imp_PathFileExistsW
0x18004fcdd  test    eax, eax
0x18004fcdf  jz      short loc_18004FCF6
0x18004fce1  lea     rdx, [rbp+0C40h+var_CA0]
0x18004fce5  lea     rcx, [rsp+0D40h+lpString2]
0x18004fcea  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18004fcef  mov     rbx, [rsp+0D40h+lpString2]
0x18004fcf4  jmp     short loc_18004FD18
0x18004fcf6  mov     eax, 80004005h
0x18004fcfb  mov     esi, eax
0x18004fcfd  mov     rcx, [rbp+0C48h]; this
0x18004fd04  mov     r9d, eax; char *
0x18004fd07  lea     r8, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004fd0e  mov     edx, 6DCh; void *
0x18004fd13  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004fd18  test    esi, esi
0x18004fd1a  jns     short loc_18004FD70
0x18004fd1c  jmp     short loc_18004FD5D
0x18004fd1e  mov     ecx, 4000005Dh; rest
0x18004fd23  call    cs:__imp_SHRestricted
0x18004fd29  test    eax, eax
0x18004fd2b  jz      short loc_18004FD49
0x18004fd2d  cmp     [r14+861h], dil
0x18004fd34  jnz     short loc_18004FD49
0x18004fd36  lea     rdx, [rbp+0C40h+pszThemeFileName]
0x18004fd3d  lea     rcx, [rsp+0D40h+lpString2]
0x18004fd42  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18004fd47  jmp     short loc_18004FD58
0x18004fd49  lea     rdx, [rsp+0D40h+lpString1]
0x18004fd4e  lea     rcx, [rsp+0D40h+lpString2]
0x18004fd53  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18004fd58  mov     rbx, [rsp+0D40h+lpString2]
0x18004fd5d  mov     ecx, 4000005Dh; rest
0x18004fd62  call    cs:__imp_SHRestricted
0x18004fd68  test    eax, eax
0x18004fd6a  jz      loc_18004FE26
0x18004fd70  mov     dword ptr [rsp+0D40h+pszSizeBuff], r12d; bIgnoreCase
0x18004fd75  or      eax, 0FFFFFFFFh
0x18004fd78  mov     r9d, eax; cchCount2
0x18004fd7b  mov     r8, rbx; lpString2
0x18004fd7e  mov     edx, eax; cchCount1
0x18004fd80  mov     rcx, [rsp+0D40h+lpString1]; lpString1
0x18004fd85  call    cs:__imp_CompareStringOrdinal
0x18004fd8b  cmp     eax, 2
0x18004fd8e  jz      loc_18004FE26
0x18004fd94  lea     r8, aAeroMsstyles; "aero.msstyles"
0x18004fd9b  xor     edx, edx; pszLast
0x18004fd9d  mov     rcx, rbx; pszSource
0x18004fda0  call    cs:__imp_StrRStrIW
0x18004fda6  mov     rdi, rax
0x18004fda9  lea     r8, aAeroMsstyles; "aero.msstyles"
0x18004fdb0  xor     edx, edx; pszLast
0x18004fdb2  mov     rcx, [rsp+0D40h+lpString1]; pszSource
0x18004fdb7  call    cs:__imp_StrRStrIW
0x18004fdbd  test    rdi, rdi
0x18004fdc0  jnz     short loc_18004FDF6
0x18004fdc2  test    rax, rax
0x18004fdc5  jz      loc_18004FE62
0x18004fdcb  mov     r8d, 7EBh; unsigned int
0x18004fdd1  lea     rcx, [rsp+0D40h+var_CF8]; this
0x18004fdd6  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18004fddb  mov     r8d, 7ECh; unsigned int
0x18004fde1  lea     rcx, [rsp+0D40h+var_CE8]; this
0x18004fde6  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18004fdeb  test    al, al
0x18004fded  jnz     short loc_18004FE6A
0x18004fdef  mov     esi, 80004005h
0x18004fdf4  jmp     short loc_18004FE62
0x18004fdf6  mov     r8d, 7EBh; unsigned int
0x18004fdfc  lea     rcx, [rsp+0D40h+var_CF8]; this
0x18004fe01  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18004fe06  mov     r8d, 7ECh; unsigned int
0x18004fe0c  lea     rcx, [rsp+0D40h+var_CE8]; this
0x18004fe11  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18004fe16  neg     al
0x18004fe18  sbb     esi, esi
0x18004fe1a  not     esi
0x18004fe1c  and     esi, 80004005h
0x18004fe22  xor     edi, edi
0x18004fe24  jmp     short loc_18004FE62
0x18004fe26  mov     rcx, [r14+850h]
0x18004fe2d  mov     rax, [rcx]
0x18004fe30  lea     rdx, [rsp+0D40h+var_CF8]
0x18004fe35  mov     rax, [rax+38h]
0x18004fe39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe3e  mov     esi, eax
0x18004fe40  test    eax, eax
0x18004fe42  js      loc_18005021E
0x18004fe48  mov     rcx, [r14+850h]
0x18004fe4f  mov     rax, [rcx]
0x18004fe52  lea     rdx, [rsp+0D40h+var_CE8]
0x18004fe57  mov     rax, [rax+48h]
0x18004fe5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe60  mov     esi, eax
0x18004fe62  test    esi, esi
0x18004fe64  js      loc_18005021E
0x18004fe6a  mov     dword ptr [rsp+0D40h+pszSizeBuff], r12d; int
0x18004fe6f  or      esi, 0FFFFFFFFh
0x18004fe72  mov     r9d, esi; cchCount2
0x18004fe75  mov     r8, rbx; lpString2
0x18004fe78  mov     edx, esi; cchCount1
0x18004fe7a  lea     rcx, [rbp+0C40h+pszThemeFileName]; lpString1
0x18004fe81  call    cs:__imp_CompareStringOrdinal
0x18004fe87  cmp     eax, 2
0x18004fe8a  jnz     loc_18004FFC3
0x18004fe90  mov     dword ptr [rsp+0D40h+pszSizeBuff], r12d; bIgnoreCase
0x18004fe95  mov     r9d, esi; cchCount2
0x18004fe98  mov     r8, [rsp+0D40h+var_CF8]; lpString2
0x18004fe9d  mov     edx, esi; cchCount1
0x18004fe9f  lea     rcx, [rbp+0C40h+pszColorBuff]; lpString1
0x18004fea6  call    cs:__imp_CompareStringOrdinal
0x18004feac  cmp     eax, 2
0x18004feaf  jnz     loc_18004FFC3
0x18004feb5  mov     dword ptr [rsp+0D40h+pszSizeBuff], r12d; int
0x18004feba  mov     r9d, esi; cchCount2
0x18004febd  mov     r8, [rsp+0D40h+var_CE8]; lpString2
0x18004fec2  mov     edx, esi; cchCount1
0x18004fec4  lea     rcx, [rbp+0C40h+String1]; lpString1
0x18004fecb  call    cs:__imp_CompareStringOrdinal
0x18004fed1  cmp     eax, 2
0x18004fed4  jnz     loc_18004FFC3
0x18004feda  mov     [rsp+0D40h+var_D00], dil
0x18004fedf  shr     r15d, 6
0x18004fee3  not     r15b
0x18004fee6  and     r15b, r12b
0x18004fee9  lea     r8, [rsp+0D40h+var_D00]; bool *
0x18004feee  mov     dl, r15b; bool
0x18004fef1  mov     rcx, r14; this
0x18004fef4  call    ?_ApplyWindowColorsAndMetrics@CThemeManager2@@AEAAJ_NPEA_N@Z; CThemeManager2::_ApplyWindowColorsAndMetrics(bool,bool *)
0x18004fef9  mov     esi, eax
0x18004fefb  mov     rcx, [rbp+0C48h]; this
0x18004ff02  test    eax, eax
0x18004ff04  jns     short loc_18004FF1F
0x18004ff06  mov     edx, 773h; void *
0x18004ff0b  lea     r8, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004ff12  mov     r9d, eax; char *
0x18004ff15  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ff1a  jmp     loc_18005021E
0x18004ff1f  mov     [rsp+0D40h+var_CFC], edi
0x18004ff23  mov     rcx, [r14+850h]
0x18004ff2a  mov     rax, [rcx]
0x18004ff2d  lea     rdx, [rsp+0D40h+var_CFC]
0x18004ff32  mov     rax, [rax+1D0h]
0x18004ff39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff3e  mov     esi, eax
0x18004ff40  mov     ecx, [rsp+0D40h+var_CFC]; unsigned int
0x18004ff44  call    ?UpdateHighContrastSetting@@YA_NH@Z; UpdateHighContrastSetting(int)
0x18004ff49  test    esi, esi
0x18004ff4b  js      loc_18005021E
0x18004ff51  test    al, al
0x18004ff53  jz      short loc_18004FF6E
0x18004ff55  cmp     [rsp+0D40h+var_D00], dil
0x18004ff5a  jz      short loc_18004FF6E
0x18004ff5c  mov     r8, [rsp+0D40h+var_CE8]
0x18004ff61  mov     rdx, [rsp+0D40h+var_CF8]
0x18004ff66  mov     rcx, rbx
0x18004ff69  jmp     loc_180050217
0x18004ff6e  mov     [rsp+0D40h+pszSizeBuff], rbx; unsigned __int16 *
0x18004ff73  lea     r8, aDllname; "DllName"
0x18004ff7a  lea     rdi, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004ff81  mov     rdx, rdi; unsigned __int16 *
0x18004ff84  call    ?HrRegSetPath@@YAJPEAUHKEY__@@PEBG1H1@Z; HrRegSetPath(HKEY__ *,ushort const *,ushort const *,int,ushort const *)
0x18004ff89  mov     r9, [rsp+0D40h+var_CF8]; unsigned __int16 *
0x18004ff8e  lea     r8, aColorname; "ColorName"
0x18004ff95  mov     rdx, rdi; unsigned __int16 *
0x18004ff98  mov     r15, 0FFFFFFFF80000001h
0x18004ff9f  mov     rcx, r15; HKEY
0x18004ffa2  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004ffa7  mov     r9, [rsp+0D40h+var_CE8]; unsigned __int16 *
0x18004ffac  lea     r8, aSizename; "SizeName"
0x18004ffb3  mov     rdx, rdi; unsigned __int16 *
0x18004ffb6  mov     rcx, r15; HKEY
0x18004ffb9  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004ffbe  jmp     loc_18005021E
0x18004ffc3  cmp     [r14+861h], dil
0x18004ffca  jnz     short loc_180050021
0x18004ffcc  cmp     [r14+858h], rdi
0x18004ffd3  jnz     short loc_180050021
0x18004ffd5  mov     ecx, 50h ; 'P'; unsigned __int64
0x18004ffda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ffdf  mov     [rsp+0D40h+bstrString], rax
0x18004ffe4  test    rax, rax
0x18004ffe7  jz      short loc_18005001A
0x18004ffe9  test    r13b, 3
0x18004ffed  jnz     short loc_18004FFF9
0x18004ffef  bt      r15d, 8
0x18004fff4  mov     r8b, r12b
0x18004fff7  jb      short loc_18004FFFC
0x18004fff9  mov     r8b, dil; bool
0x18004fffc  mov     rcx, rax; this
0x18004ffff  call    ??0CDimmedWindow@@QEAA@PEAUHINSTANCE__@@_N@Z; CDimmedWindow::CDimmedWindow(HINSTANCE__ *,bool)
0x180050004  mov     [r14+858h], rax
0x18005000b  test    rax, rax
0x18005000e  jz      short loc_180050021
0x180050010  mov     rcx, rax; this
0x180050013  call    ?Create@CDimmedWindow@@QEAAJXZ; CDimmedWindow::Create(void)
0x180050018  jmp     short loc_180050021
0x18005001a  mov     [r14+858h], rdi
0x180050021  shr     r15d, 6
0x180050025  not     r15b
0x180050028  and     r15b, r12b
0x18005002b  xor     r8d, r8d; bool *
0x18005002e  mov     dl, r15b; bool
0x180050031  mov     rcx, r14; this
0x180050034  call    ?_ApplyWindowColorsAndMetrics@CThemeManager2@@AEAAJ_NPEA_N@Z; CThemeManager2::_ApplyWindowColorsAndMetrics(bool,bool *)
0x180050039  mov     esi, eax
  ... truncated ...
```
