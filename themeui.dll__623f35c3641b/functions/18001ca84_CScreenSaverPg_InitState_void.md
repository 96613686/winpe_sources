# CScreenSaverPg::_InitState(void)

- ea: `0x18001ca84`
- end: `0x18001d0a4`
- name: `?_InitState@CScreenSaverPg@@AEAAJXZ`
- size: `1568`
- prototype: `__int64 __fastcall(CScreenSaverPg *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046704`

## callees

- `0x18000ab10`
- `0x180014e40`
- `0x18001ca84`
- `0x18001f370`
- `0x1800331c4`
- `0x1800358c0`
- `0x18003c1f4`

## import_xrefs

- `SHLWAPI!StrToIntW` at `0x18001cc65`
- `SHLWAPI!StrToIntW` at `0x18001cd2c`
- `SHLWAPI!StrToIntW` at `0x18001cd93`
- `SHLWAPI!StrToIntW` at `0x18001cf33`
- `SHLWAPI!StrToIntW` at `0x18001cf43`
- `SHLWAPI!StrToIntW` at `0x18001cf57`
- `SHLWAPI!StrToIntW` at `0x18001cf6c`
- `SHLWAPI!StrToIntW` at `0x18001cc65`
- `SHLWAPI!StrToIntW` at `0x18001cd2c`
- `SHLWAPI!StrToIntW` at `0x18001cd93`
- `SHLWAPI!StrToIntW` at `0x18001cf33`
- `SHLWAPI!StrToIntW` at `0x18001cf43`
- `SHLWAPI!StrToIntW` at `0x18001cf57`
- `SHLWAPI!StrToIntW` at `0x18001cf6c`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001ce6e`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001ce6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cfb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cfb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d071`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cb8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cb8b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cc43`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cc43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cbd7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ccca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ceb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cbd7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ccca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ceb8`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001cff2`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001cff2`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18001ce47`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18001ce47`
- `GDI32!CreateCompatibleDC` at `0x18001cae4`
- `GDI32!CreateCompatibleDC` at `0x18001cae4`
- `USER32!ReleaseDC` at `0x18001caf6`
- `USER32!ReleaseDC` at `0x18001caf6`
- `USER32!GetDC` at `0x18001cad8`
- `USER32!GetDC` at `0x18001cad8`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001cb10`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001cb64`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001d009`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001d026`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001d051`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001cb10`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001cb64`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001d009`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001d026`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001d051`

## pseudocode

```c
__int64 __fastcall CScreenSaverPg::_InitState(CScreenSaverPg *this)
{
  HDC DC; // rbx
  int v3; // ecx
  int v4; // eax
  LSTATUS ValueW; // eax
  bool v6; // sf
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  int v10; // ecx
  __int16 v11; // ax
  __int16 *v12; // rdx
  bool v13; // zf
  DWORD v14; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-ACh] BYREF
  int v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 pvData[20]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v26[264]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  v23 = 0;
  v20 = 1;
  if ( !g_hdcMem )
  {
    DC = GetDC(0);
    g_hdcMem = CreateCompatibleDC(DC);
    ReleaseDC(0, DC);
  }
  *((_DWORD *)this + 17) = 0;
  *((_DWORD *)this + 18) = 1;
  ClassicSystemParametersInfoW(14, 0, &v20, 0);
  v3 = v20;
  v4 = 1;
  if ( v20 > 1 )
    v4 = v20;
  if ( v4 >= 60 * *((_DWORD *)this + 20) )
  {
    v3 = 60 * *((_DWORD *)this + 20);
  }
  else if ( v20 <= 1 )
  {
    v3 = 1;
  }
  v20 = (v3 + 59) / 60;
  g_Timeout = v20;
  ClassicSystemParametersInfoW(16, 0, &v23, 1);
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Policies\\Microsoft\\Windows\\Control Panel\\Desktop",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"SCRNSAVE.EXE", 0, 0, &g_szSaverName, &cbData) )
    {
      g_fScreenSaverExecutablePolicy = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3a85b4cb2b973e23e694840dc466c662_Traceguids);
    }
    pcbData = 40;
    ValueW = RegGetValueW(hKey, &Default, L"ScreenSaverIsSecure", 2u, 0, pvData, &pcbData);
    v6 = ValueW < 0;
    if ( ValueW )
    {
      pvData[0] = 0;
      if ( ValueW > 0 )
        v6 = 1;
    }
    if ( !v6 )
    {
      *((_DWORD *)this + 15) = StrToIntW(pvData);
      g_fPasswordBoxDeterminedByPolicy = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_3a85b4cb2b973e23e694840dc466c662_Traceguids);
    }
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"ScreenSaverSettingsButton", 0, 0, Data, &cbData) )
    {
      g_fSettingsButtonOffByPolicy = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_3a85b4cb2b973e23e694840dc466c662_Traceguids);
    }
    if ( (int)HrRegGetValueString(hKey, 0, L"ScreenSaveTimeOut", pvData, 0x14u) >= 0 )
    {
      if ( pvData[0] )
      {
        *((_DWORD *)this + 19) = StrToIntW(pvData);
        g_fTimeoutDeterminedByPolicy = 1;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_3a85b4cb2b973e23e694840dc466c662_Traceguids);
      }
    }
    if ( (int)HrRegGetValueString(hKey, 0, L"ScreenSaveActive", pvData, 0x14u) >= 0 )
    {
      if ( pvData[0] )
      {
        *((_DWORD *)this + 17) = 1;
        *((_DWORD *)this + 18) = StrToIntW(pvData);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3a85b4cb2b973e23e694840dc466c662_Traceguids);
      }
    }
    RegCloseKey(hKey);
  }
  if ( !g_fScreenSaverExecutablePolicy
    && (int)HrRegGetPath(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ScreenSavers",
              L"SCRNSAVE.EXE",
              (unsigned __int16 *)&g_szSaverName,
              phkResult) < 0
    && (int)HrRegGetPath(
              HKEY_CURRENT_USER,
              L"Control Panel\\Desktop",
              L"SCRNSAVE.EXE",
              (unsigned __int16 *)&g_szSaverName,
              phkResulta) < 0
    && GetPrivateProfileStringW(L"boot", L"SCRNSAVE.EXE", &Default, (LPWSTR)&g_szSaverName, 0x104u, L"system.ini")
    && (int)StringCchCopyW(v26, 0x104u, (const unsigned __int16 *)&g_szSaverName) >= 0 )
  {
    SHExpandEnvironmentStringsW(v26, &g_szSaverName, 260);
  }
  if ( (unsigned int)RegOpenScreenSaverKeyForQuery(&hKey) )
  {
    cbData = 0;
    *(_DWORD *)Data = 4;
    if ( !RegQueryValueExW(hKey, L"ScanSystemDirOnly", 0, 0, (LPBYTE)&cbData, (LPDWORD)Data) )
    {
      g_fScanSystemDirOnly = cbData != 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_3a85b4cb2b973e23e694840dc466c662_Traceguids);
    }
    if ( (int)HrRegGetValueString(hKey, 0, L"ScreenSaveMaxTimeOut", pvData, 0xAu) >= 0 && pvData[0] )
    {
      if ( StrToIntW(pvData) < 1 || (v7 = StrToIntW(pvData), v8 = 9999, v7 < 9999) )
      {
        if ( StrToIntW(pvData) >= 1 )
          v8 = StrToIntW(pvData);
        else
          v8 = 1;
      }
      v9 = *((_DWORD *)this + 19);
      *((_DWORD *)this + 20) = v8;
      v10 = 60 * v8;
      if ( v9 >= v10 )
        v9 = v10;
      *((_DWORD *)this + 19) = v9;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3a85b4cb2b973e23e694840dc466c662_Traceguids);
    }
    RegCloseKey(hKey);
  }
  if ( *(_WORD *)&g_szSaverName == 34 )
  {
    v11 = word_18008A742;
    v12 = &word_18008A742;
    while ( v11 && v11 != 34 )
      v11 = *++v12;
    *v12 = 0;
  }
  GetLongPathNameW((LPCWSTR)&g_szSaverName, (LPWSTR)&g_szSaverName, 0x104u);
  v22 = 0;
  dword_18008B3B4 = ClassicSystemParametersInfoW(83, 0, &v22, 0);
  if ( !dword_18008B3B4 )
    dword_18008B3B4 = ClassicSystemParametersInfoW(84, 0, &v22, 0);
  if ( (unsigned int)RegOpenScreenSaverKeyForQuery(&hKey) )
  {
    cbData = 0;
    v13 = (unsigned int)ClassicSystemParametersInfoW(118, 0, &cbData, 0) == 0;
    v14 = 0;
    if ( !v13 )
      v14 = cbData;
    if ( v14 )
      g_fPasswordWasPreviouslyEnabled = 1;
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ca84  mov     [rsp-8+arg_8], rbx
0x18001ca89  mov     [rsp-8+arg_10], rsi
0x18001ca8e  push    rbp
0x18001ca8f  push    rdi
0x18001ca90  push    r13
0x18001ca92  push    r14
0x18001ca94  push    r15
0x18001ca96  lea     rbp, [rsp-1B0h]
0x18001ca9e  sub     rsp, 2B0h
0x18001caa5  mov     rax, cs:__security_cookie
0x18001caac  xor     rax, rsp
0x18001caaf  mov     [rbp+1D0h+var_30], rax
0x18001cab6  xor     esi, esi
0x18001cab8  mov     rdi, rcx
0x18001cabb  cmp     cs:?g_hdcMem@@3PEAUHDC__@@EA, rsi; HDC__ * g_hdcMem
0x18001cac2  mov     [rsp+2D0h+hKey], rsi
0x18001cac7  mov     [rsp+2D0h+var_274], esi
0x18001cacb  lea     r14d, [rsi+1]
0x18001cacf  mov     [rsp+2D0h+var_280], r14d
0x18001cad4  jnz     short loc_18001CAFC
0x18001cad6  xor     ecx, ecx; hWnd
0x18001cad8  call    cs:__imp_GetDC
0x18001cade  mov     rcx, rax; hdc
0x18001cae1  mov     rbx, rax
0x18001cae4  call    cs:__imp_CreateCompatibleDC
0x18001caea  mov     rdx, rbx; hDC
0x18001caed  xor     ecx, ecx; hWnd
0x18001caef  mov     cs:?g_hdcMem@@3PEAUHDC__@@EA, rax; HDC__ * g_hdcMem
0x18001caf6  call    cs:__imp_ReleaseDC
0x18001cafc  xor     edx, edx
0x18001cafe  mov     [rdi+44h], esi
0x18001cb01  xor     r9d, r9d
0x18001cb04  mov     [rdi+48h], r14d
0x18001cb08  lea     r8, [rsp+2D0h+var_280]
0x18001cb0d  lea     ecx, [rdx+0Eh]
0x18001cb10  call    cs:__imp_ClassicSystemParametersInfoW
0x18001cb16  mov     ecx, [rsp+2D0h+var_280]
0x18001cb1a  mov     eax, r14d
0x18001cb1d  cmp     ecx, r14d
0x18001cb20  cmovg   eax, ecx
0x18001cb23  imul    edx, [rdi+50h], 3Ch ; '<'
0x18001cb27  cmp     eax, edx
0x18001cb29  jge     short loc_18001CB35
0x18001cb2b  cmp     ecx, r14d
0x18001cb2e  jg      short loc_18001CB37
0x18001cb30  mov     ecx, r14d
0x18001cb33  jmp     short loc_18001CB37
0x18001cb35  mov     ecx, edx
0x18001cb37  add     ecx, 3Bh ; ';'
0x18001cb3a  lea     r8, [rsp+2D0h+var_274]
0x18001cb3f  mov     eax, 88888889h
0x18001cb44  mov     r9d, r14d
0x18001cb47  imul    ecx
0x18001cb49  add     edx, ecx
0x18001cb4b  sar     edx, 5
0x18001cb4e  mov     eax, edx
0x18001cb50  shr     eax, 1Fh
0x18001cb53  add     edx, eax
0x18001cb55  mov     [rsp+2D0h+var_280], edx
0x18001cb59  mov     cs:?g_Timeout@@3PAHA, edx; int near * g_Timeout
0x18001cb5f  xor     edx, edx
0x18001cb61  lea     ecx, [rdx+10h]
0x18001cb64  call    cs:__imp_ClassicSystemParametersInfoW
0x18001cb6a  lea     rax, [rsp+2D0h+hKey]
0x18001cb6f  mov     r9d, 20019h; samDesired
0x18001cb75  xor     r8d, r8d; ulOptions
0x18001cb78  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18001cb7d  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18001cb84  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001cb8b  call    cs:__imp_RegOpenKeyExW
0x18001cb91  lea     rbx, ?g_szSaverName@@3PAGA; ushort near * g_szSaverName
0x18001cb98  lea     r15, WPP_GLOBAL_Control
0x18001cb9f  lea     r13, WPP_3a85b4cb2b973e23e694840dc466c662_Traceguids
0x18001cba6  test    eax, eax
0x18001cba8  jnz     loc_18001CDCA
0x18001cbae  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18001cbb3  lea     rax, [rsp+2D0h+cbData]
0x18001cbb8  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x18001cbbd  lea     rdx, aScrnsaveExe; "SCRNSAVE.EXE"
0x18001cbc4  xor     r9d, r9d; lpType
0x18001cbc7  mov     [rsp+2D0h+phkResult], rbx; lpData
0x18001cbcc  xor     r8d, r8d; lpReserved
0x18001cbcf  mov     [rsp+2D0h+cbData], 208h
0x18001cbd7  call    cs:__imp_RegQueryValueExW
0x18001cbdd  test    eax, eax
0x18001cbdf  jnz     short loc_18001CC09
0x18001cbe1  mov     cs:?g_fScreenSaverExecutablePolicy@@3HA, r14d; int g_fScreenSaverExecutablePolicy
0x18001cbe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbef  cmp     rcx, r15
0x18001cbf2  jz      short loc_18001CC09
0x18001cbf4  test    byte ptr [rcx+1Ch], 8
0x18001cbf8  jz      short loc_18001CC09
0x18001cbfa  mov     rcx, [rcx+10h]
0x18001cbfe  lea     edx, [rax+0Ah]
0x18001cc01  mov     r8, r13
0x18001cc04  call    WPP_SF_
0x18001cc09  mov     rcx, [rsp+2D0h+hKey]; hkey
0x18001cc0e  lea     rax, [rsp+2D0h+var_270]
0x18001cc13  mov     [rsp+2D0h+pcbData], rax; pcbData
0x18001cc18  lea     r8, aScreensaveriss; "ScreenSaverIsSecure"
0x18001cc1f  lea     rax, [rsp+2D0h+pvData]
0x18001cc24  mov     [rsp+2D0h+var_270], 28h ; '('
0x18001cc2c  mov     [rsp+2D0h+lpcbData], rax; pvData
0x18001cc31  lea     rdx, Default; lpSubKey
0x18001cc38  mov     r9d, 2; dwFlags
0x18001cc3e  mov     [rsp+2D0h+phkResult], rsi; pdwType
0x18001cc43  call    cs:__imp_RegGetValueW
0x18001cc49  test    eax, eax
0x18001cc4b  jz      short loc_18001CC5E
0x18001cc4d  mov     [rsp+2D0h+pvData], si
0x18001cc52  jle     short loc_18001CC5E
0x18001cc54  movzx   eax, ax
0x18001cc57  or      eax, 80070000h
0x18001cc5c  test    eax, eax
0x18001cc5e  js      short loc_18001CC98
0x18001cc60  lea     rcx, [rsp+2D0h+pvData]; pszSrc
0x18001cc65  call    cs:__imp_StrToIntW
0x18001cc6b  mov     [rdi+3Ch], eax
0x18001cc6e  mov     cs:?g_fPasswordBoxDeterminedByPolicy@@3HA, r14d; int g_fPasswordBoxDeterminedByPolicy
0x18001cc75  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc7c  cmp     rcx, r15
0x18001cc7f  jz      short loc_18001CC98
0x18001cc81  test    byte ptr [rcx+1Ch], 8
0x18001cc85  jz      short loc_18001CC98
0x18001cc87  mov     rcx, [rcx+10h]
0x18001cc8b  mov     edx, 0Bh
0x18001cc90  mov     r8, r13
0x18001cc93  call    WPP_SF_
0x18001cc98  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18001cc9d  lea     rax, [rsp+2D0h+cbData]
0x18001cca2  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x18001cca7  lea     rdx, aScreensaverset; "ScreenSaverSettingsButton"
0x18001ccae  lea     rax, [rsp+2D0h+Data]
0x18001ccb3  mov     dword ptr [rsp+2D0h+Data], esi
0x18001ccb7  xor     r9d, r9d; lpType
0x18001ccba  mov     [rsp+2D0h+phkResult], rax; lpData
0x18001ccbf  xor     r8d, r8d; lpReserved
0x18001ccc2  mov     [rsp+2D0h+cbData], 4
0x18001ccca  call    cs:__imp_RegQueryValueExW
0x18001ccd0  test    eax, eax
0x18001ccd2  jnz     short loc_18001CCFC
0x18001ccd4  mov     cs:?g_fSettingsButtonOffByPolicy@@3HA, r14d; int g_fSettingsButtonOffByPolicy
0x18001ccdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cce2  cmp     rcx, r15
0x18001cce5  jz      short loc_18001CCFC
0x18001cce7  test    byte ptr [rcx+1Ch], 8
0x18001cceb  jz      short loc_18001CCFC
0x18001cced  mov     rcx, [rcx+10h]
0x18001ccf1  lea     edx, [rax+0Ch]
0x18001ccf4  mov     r8, r13
0x18001ccf7  call    WPP_SF_
0x18001ccfc  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x18001cd01  lea     r9, [rsp+2D0h+pvData]; unsigned __int16 *
0x18001cd06  lea     r8, aScreensavetime; "ScreenSaveTimeOut"
0x18001cd0d  mov     dword ptr [rsp+2D0h+phkResult], 14h; unsigned int
0x18001cd15  xor     edx, edx; unsigned __int16 *
0x18001cd17  call    ?HrRegGetValueString@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetValueString(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x18001cd1c  test    eax, eax
0x18001cd1e  js      short loc_18001CD5F
0x18001cd20  cmp     [rsp+2D0h+pvData], si
0x18001cd25  jz      short loc_18001CD5F
0x18001cd27  lea     rcx, [rsp+2D0h+pvData]; pszSrc
0x18001cd2c  call    cs:__imp_StrToIntW
0x18001cd32  mov     [rdi+4Ch], eax
0x18001cd35  mov     cs:?g_fTimeoutDeterminedByPolicy@@3HA, r14d; int g_fTimeoutDeterminedByPolicy
0x18001cd3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd43  cmp     rcx, r15
0x18001cd46  jz      short loc_18001CD5F
0x18001cd48  test    byte ptr [rcx+1Ch], 8
0x18001cd4c  jz      short loc_18001CD5F
0x18001cd4e  mov     rcx, [rcx+10h]
0x18001cd52  mov     edx, 0Dh
0x18001cd57  mov     r8, r13
0x18001cd5a  call    WPP_SF_
0x18001cd5f  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x18001cd64  lea     r9, [rsp+2D0h+pvData]; unsigned __int16 *
0x18001cd69  lea     r8, aScreensaveacti; "ScreenSaveActive"
0x18001cd70  mov     dword ptr [rsp+2D0h+phkResult], 14h; unsigned int
0x18001cd78  xor     edx, edx; unsigned __int16 *
0x18001cd7a  call    ?HrRegGetValueString@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetValueString(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x18001cd7f  test    eax, eax
0x18001cd81  js      short loc_18001CDBF
0x18001cd83  cmp     [rsp+2D0h+pvData], si
0x18001cd88  jz      short loc_18001CDBF
0x18001cd8a  lea     rcx, [rsp+2D0h+pvData]; pszSrc
0x18001cd8f  mov     [rdi+44h], r14d
0x18001cd93  call    cs:__imp_StrToIntW
0x18001cd99  mov     [rdi+48h], eax
0x18001cd9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cda3  cmp     rcx, r15
0x18001cda6  jz      short loc_18001CDBF
0x18001cda8  test    byte ptr [rcx+1Ch], 8
0x18001cdac  jz      short loc_18001CDBF
0x18001cdae  mov     rcx, [rcx+10h]
0x18001cdb2  mov     edx, 0Eh
0x18001cdb7  mov     r8, r13
0x18001cdba  call    WPP_SF_
0x18001cdbf  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18001cdc4  call    cs:__imp_RegCloseKey
0x18001cdca  cmp     cs:?g_fScreenSaverExecutablePolicy@@3HA, esi; int g_fScreenSaverExecutablePolicy
0x18001cdd0  mov     r15d, 104h
0x18001cdd6  jnz     loc_18001CE74
0x18001cddc  mov     r9, rbx; unsigned __int16 *
0x18001cddf  lea     r8, aScrnsaveExe; "SCRNSAVE.EXE"
0x18001cde6  lea     rdx, aSoftwareMicros_28; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001cded  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001cdf4  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x18001cdf9  test    eax, eax
0x18001cdfb  jns     short loc_18001CE74
0x18001cdfd  mov     r9, rbx; unsigned __int16 *
0x18001ce00  lea     r8, aScrnsaveExe; "SCRNSAVE.EXE"
0x18001ce07  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop"
0x18001ce0e  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001ce15  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x18001ce1a  test    eax, eax
0x18001ce1c  jns     short loc_18001CE74
0x18001ce1e  lea     rax, FileName; "system.ini"
0x18001ce25  mov     r9, rbx; lpReturnedString
0x18001ce28  mov     [rsp+2D0h+lpcbData], rax; lpFileName
0x18001ce2d  lea     r8, Default; lpDefault
0x18001ce34  lea     rdx, aScrnsaveExe; "SCRNSAVE.EXE"
0x18001ce3b  mov     dword ptr [rsp+2D0h+phkResult], r15d; nSize
0x18001ce40  lea     rcx, aBoot; "boot"
0x18001ce47  call    cs:__imp_GetPrivateProfileStringW
0x18001ce4d  test    eax, eax
0x18001ce4f  jz      short loc_18001CE74
0x18001ce51  mov     r8, rbx; unsigned __int16 *
0x18001ce54  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x18001ce58  mov     edx, r15d; unsigned __int64
0x18001ce5b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ce60  test    eax, eax
0x18001ce62  js      short loc_18001CE74
0x18001ce64  mov     r8d, r15d
0x18001ce67  lea     rcx, [rbp+1D0h+var_240]
0x18001ce6b  mov     rdx, rbx
0x18001ce6e  call    cs:__imp_SHExpandEnvironmentStringsW
0x18001ce74  lea     rcx, [rsp+2D0h+hKey]; HKEY *
0x18001ce79  call    ?RegOpenScreenSaverKeyForQuery@@YAHPEAPEAUHKEY__@@@Z; RegOpenScreenSaverKeyForQuery(HKEY__ * *)
0x18001ce7e  test    eax, eax
0x18001ce80  jz      loc_18001CFBA
0x18001ce86  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18001ce8b  lea     rax, [rsp+2D0h+Data]
0x18001ce90  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x18001ce95  lea     rdx, aScansystemdiro; "ScanSystemDirOnly"
0x18001ce9c  lea     rax, [rsp+2D0h+cbData]
0x18001cea1  mov     [rsp+2D0h+cbData], esi
0x18001cea5  xor     r9d, r9d; lpType
0x18001cea8  mov     [rsp+2D0h+phkResult], rax; lpData
0x18001cead  xor     r8d, r8d; lpReserved
0x18001ceb0  mov     dword ptr [rsp+2D0h+Data], 4
0x18001ceb8  call    cs:__imp_RegQueryValueExW
0x18001cebe  test    eax, eax
0x18001cec0  jnz     short loc_18001CEFB
0x18001cec2  cmp     [rsp+2D0h+cbData], esi
0x18001cec6  mov     eax, esi
0x18001cec8  setnz   al
0x18001cecb  mov     cs:?g_fScanSystemDirOnly@@3HA, eax; int g_fScanSystemDirOnly
0x18001ced1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ced8  lea     rax, WPP_GLOBAL_Control
0x18001cedf  cmp     rcx, rax
0x18001cee2  jz      short loc_18001CEFB
0x18001cee4  test    byte ptr [rcx+1Ch], 8
0x18001cee8  jz      short loc_18001CEFB
0x18001ceea  mov     rcx, [rcx+10h]
0x18001ceee  mov     edx, 0Fh
0x18001cef3  mov     r8, r13
0x18001cef6  call    WPP_SF_
0x18001cefb  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x18001cf00  lea     r9, [rsp+2D0h+pvData]; unsigned __int16 *
0x18001cf05  lea     r8, aScreensavemaxt; "ScreenSaveMaxTimeOut"
0x18001cf0c  mov     dword ptr [rsp+2D0h+phkResult], 0Ah; unsigned int
0x18001cf14  xor     edx, edx; unsigned __int16 *
0x18001cf16  call    ?HrRegGetValueString@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetValueString(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x18001cf1b  test    eax, eax
0x18001cf1d  js      loc_18001CFAF
0x18001cf23  cmp     [rsp+2D0h+pvData], si
0x18001cf28  jz      loc_18001CFAF
0x18001cf2e  lea     rcx, [rsp+2D0h+pvData]; pszSrc
0x18001cf33  call    cs:__imp_StrToIntW
0x18001cf39  cmp     eax, r14d
0x18001cf3c  jl      short loc_18001CF52
0x18001cf3e  lea     rcx, [rsp+2D0h+pvData]; pszSrc
0x18001cf43  call    cs:__imp_StrToIntW
0x18001cf49  mov     ecx, 270Fh
0x18001cf4e  cmp     eax, ecx
0x18001cf50  jge     short loc_18001CF74
0x18001cf52  lea     rcx, [rsp+2D0h+pvData]; pszSrc
0x18001cf57  call    cs:__imp_StrToIntW
0x18001cf5d  cmp     eax, r14d
0x18001cf60  jge     short loc_18001CF67
0x18001cf62  mov     ecx, r14d
0x18001cf65  jmp     short loc_18001CF74
0x18001cf67  lea     rcx, [rsp+2D0h+pvData]; pszSrc
0x18001cf6c  call    cs:__imp_StrToIntW
0x18001cf72  mov     ecx, eax
0x18001cf74  mov     eax, [rdi+4Ch]
0x18001cf77  mov     [rdi+50h], ecx
0x18001cf7a  imul    ecx, 3Ch ; '<'
0x18001cf7d  cmp     eax, ecx
0x18001cf7f  cmovge  eax, ecx
  ... truncated ...
```
