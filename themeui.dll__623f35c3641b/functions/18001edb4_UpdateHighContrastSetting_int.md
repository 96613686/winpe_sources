# UpdateHighContrastSetting(int)

- ea: `0x18001edb4`
- end: `0x18001f239`
- name: `?UpdateHighContrastSetting@@YA_NH@Z`
- size: `1157`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18004fb2c`

## callees

- `0x180007d20`
- `0x1800089c0`
- `0x18001987c`
- `0x18001edb4`
- `0x1800206ac`
- `0x1800358c0`
- `0x18003633c`
- `0x18004cc7c`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x18001f1ec`
- `SHELL32!SHChangeNotify` at `0x18001f1ec`
- `SHLWAPI!StrCmpIW` at `0x18001f09c`
- `SHLWAPI!StrCmpIW` at `0x18001f09c`
- `SHLWAPI!__imp_SHSendMessageBroadcastW` at `0x18001f0eb`
- `SHLWAPI!__imp_SHSendMessageBroadcastW` at `0x18001f0eb`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18001ef5a`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18001ef5a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001efb7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f034`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001efb7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f034`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eff8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f077`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eff8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f077`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001efe4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f063`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001efe4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f063`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ee40`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f1a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ee40`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f1a8`
- `USER32!SystemParametersInfoW` at `0x18001ee97`
- `USER32!SystemParametersInfoW` at `0x18001f0dd`
- `USER32!SystemParametersInfoW` at `0x18001ee97`
- `USER32!SystemParametersInfoW` at `0x18001f0dd`

## string_xrefs

- `0x18001eee7`: `@themeui.dll,-%d`
- `0x18001f173`: `LastUpdatedThemeId`
- `0x18001f1f5`: `LastUpdatedThemeId`
- `0x18001f18c`: `Control Panel\Accessibility\HighContrast`
- `0x18001f1fc`: `Control Panel\Accessibility\HighContrast`

## pseudocode

```c
char __fastcall UpdateHighContrastSetting(signed int a1)
{
  char v2; // r15
  LSTATUS ValueW; // eax
  signed int v4; // ecx
  char v5; // si
  int v6; // ebx
  char v7; // r14
  int v8; // ebx
  WCHAR *v9; // rcx
  WCHAR *v10; // rax
  __int64 v11; // r9
  const unsigned __int16 *v12; // rdx
  HKEY v13; // rcx
  const unsigned __int16 *v14; // rdx
  HKEY v15; // rcx
  LSTATUS v16; // eax
  bool v17; // sf
  DWORD v18; // ecx
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int128 pvParam; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v23[16]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszSource[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 pvData[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v2 = a1 > 0;
  memset_0(pvData, 0, 0x208u);
  pcbData = 520;
  ValueW = RegGetValueW(HKEY_CURRENT_USER, L"Control Panel\\Appearance", L"NewCurrent", 2u, 0, pvData, &pcbData);
  v4 = ValueW;
  if ( ValueW )
  {
    pvData[0] = 0;
    if ( ValueW > 0 )
      v4 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( v4 < 0 || (v5 = 1, a1 == (unsigned int)HighContrastNumberFromSchemeName(pvData)) )
    v5 = 0;
  pvParam = 0;
  LODWORD(pvParam) = 16;
  if ( SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) )
  {
    v6 = DWORD1(pvParam);
    v7 = BYTE4(pvParam) & 1;
    memset_0(pszSource, 0, 0x208u);
    memset_0(pszOutBuf, 0, 0x208u);
    if ( a1 <= 0 )
    {
      DWORD1(pvParam) = v6 & 0xFFFFFFFE;
      hKey = 0;
      if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Appearance", 0, 0, 0, 2u, 0, &hKey, 0) )
      {
        RegSetValueExW(hKey, L"NewCurrent", 0, 1u, (const BYTE *)&Default, 2u);
        if ( hKey != HKEY_CURRENT_USER )
          RegCloseKey(hKey);
      }
      hKey = 0;
      if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Appearance", 0, 0, 0, 2u, 0, &hKey, 0) )
      {
        RegSetValueExW(hKey, L"Current", 0, 1u, (const BYTE *)&Default, 2u);
        if ( hKey != HKEY_CURRENT_USER )
          RegCloseKey(hKey);
      }
    }
    else
    {
      DWORD1(pvParam) = v6 | 1;
      v8 = StringCchPrintfW(pszSource, 0x104u, L"@themeui.dll,-%d", (unsigned int)(a1 + 849));
      SHRegSetString(HKEY_CURRENT_USER, L"Control Panel\\Appearance", L"NewCurrent", pszSource);
      SHRegSetString(HKEY_CURRENT_USER, L"Control Panel\\Appearance", L"Current", pszSource);
      if ( v8 >= 0 && SHLoadIndirectString(pszSource, pszOutBuf, 0x104u, 0) < 0 )
        pszOutBuf[0] = 0;
    }
    if ( v5 || v7 != v2 )
      goto LABEL_23;
    if ( a1 > 0 )
    {
      v9 = (WCHAR *)*((_QWORD *)&pvParam + 1);
      if ( !*((_QWORD *)&pvParam + 1) )
      {
LABEL_24:
        v10 = pszOutBuf;
        v2 = 1;
        if ( !pszOutBuf[0] )
          v10 = v9;
        DWORD1(pvParam) |= 0x1000u;
        *((_QWORD *)&pvParam + 1) = v10;
        SystemParametersInfoW(0x43u, 0x10u, &pvParam, 0);
        SHSendMessageBroadcastW(0x1Au, 0x43u, 0);
        goto LABEL_27;
      }
      if ( StrCmpIW(*((PCWSTR *)&pvParam + 1), pszOutBuf) )
      {
LABEL_23:
        v9 = (WCHAR *)*((_QWORD *)&pvParam + 1);
        goto LABEL_24;
      }
    }
LABEL_27:
    v11 = DWORD1(pvParam);
    LODWORD(v11) = DWORD1(pvParam) & 0xFFFFEFFF;
    if ( (int)StringCchPrintfW(v23, 0xAu, L"%d", v11) >= 0 )
      SetRegValueString(v13, v12, L"Flags", v23);
    if ( *((_QWORD *)&pvParam + 1) )
    {
      SetRegValueString(v13, v12, L"High Contrast Scheme", *((const unsigned __int16 **)&pvParam + 1));
      SetRegValueString(
        v15,
        v14,
        L"Previous High Contrast Scheme MUI Value",
        *((const unsigned __int16 **)&pvParam + 1));
    }
    if ( pszSource[0] )
      SetRegValueString(v13, v12, L"Previous High Contrast Scheme MUI Ptr", pszSource);
    pcbData = 0;
    LODWORD(hKey) = 4;
    v16 = RegGetValueW(
            HKEY_CURRENT_USER,
            L"Control Panel\\Accessibility\\HighContrast",
            L"LastUpdatedThemeId",
            0x10u,
            0,
            &pcbData,
            (LPDWORD)&hKey);
    v17 = v16 < 0;
    if ( v16 > 0 )
      v17 = 1;
    if ( v17 )
    {
      v18 = 0;
      pcbData = 0;
    }
    else
    {
      v18 = pcbData;
    }
    if ( a1 != v18 && ((unsigned int)(a1 - 1) > 2 || v18 - 1 > 2) )
    {
      SHChangeNotify(0x8000000, 0, 0, 0);
      SHRegSetDWORD(HKEY_CURRENT_USER, L"Control Panel\\Accessibility\\HighContrast", L"LastUpdatedThemeId", a1);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001edb4  mov     [rsp-8+arg_8], rbx
0x18001edb9  mov     [rsp-8+arg_10], rsi
0x18001edbe  push    rbp
0x18001edbf  push    rdi
0x18001edc0  push    r12
0x18001edc2  push    r14
0x18001edc4  push    r15
0x18001edc6  lea     rbp, [rsp-5D0h]
0x18001edce  sub     rsp, 6D0h
0x18001edd5  mov     rax, cs:__security_cookie
0x18001eddc  xor     rax, rsp
0x18001eddf  mov     [rbp+5F0h+var_30], rax
0x18001ede6  mov     edi, ecx
0x18001ede8  xor     r12d, r12d
0x18001edeb  test    ecx, ecx
0x18001eded  mov     ebx, 208h
0x18001edf2  mov     r8d, ebx; Size
0x18001edf5  lea     rcx, [rbp+5F0h+var_240]; void *
0x18001edfc  setnle  r15b
0x18001ee00  xor     edx, edx; Val
0x18001ee02  call    memset_0
0x18001ee07  lea     rax, [rsp+6F0h+var_6A0]
0x18001ee0c  mov     [rsp+6F0h+var_6A0], ebx
0x18001ee10  mov     [rsp+6F0h+pcbData], rax; pcbData
0x18001ee15  lea     r9d, [r12+2]; dwFlags
0x18001ee1a  lea     rax, [rbp+5F0h+var_240]
0x18001ee21  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001ee28  mov     [rsp+6F0h+pvData], rax; pvData
0x18001ee2d  lea     r8, aNewcurrent; "NewCurrent"
0x18001ee34  lea     rdx, aControlPanelAp_0; "Control Panel\\Appearance"
0x18001ee3b  mov     [rsp+6F0h+pdwType], r12; pdwType
0x18001ee40  call    cs:__imp_RegGetValueW
0x18001ee46  mov     ecx, eax
0x18001ee48  test    eax, eax
0x18001ee4a  jz      short loc_18001EE5F
0x18001ee4c  mov     [rbp+5F0h+var_240], r12w
0x18001ee54  jle     short loc_18001EE5F
0x18001ee56  movzx   ecx, ax
0x18001ee59  or      ecx, 80070000h
0x18001ee5f  test    ecx, ecx
0x18001ee61  js      short loc_18001EE76
0x18001ee63  lea     rcx, [rbp+5F0h+var_240]; unsigned __int16 *
0x18001ee6a  call    ?HighContrastNumberFromSchemeName@@YAHPEBG@Z; HighContrastNumberFromSchemeName(ushort const *)
0x18001ee6f  mov     sil, 1
0x18001ee72  cmp     edi, eax
0x18001ee74  jnz     short loc_18001EE79
0x18001ee76  mov     sil, r12b
0x18001ee79  mov     eax, 10h
0x18001ee7e  lea     r8, [rsp+6F0h+pvParam]; pvParam
0x18001ee83  xorps   xmm0, xmm0
0x18001ee86  xor     r9d, r9d; fWinIni
0x18001ee89  movups  [rsp+6F0h+pvParam], xmm0
0x18001ee8e  mov     edx, eax; uiParam
0x18001ee90  mov     dword ptr [rsp+6F0h+pvParam], eax
0x18001ee94  lea     ecx, [rax+32h]; uiAction
0x18001ee97  call    cs:__imp_SystemParametersInfoW
0x18001ee9d  test    eax, eax
0x18001ee9f  jz      loc_18001F20B
0x18001eea5  mov     ebx, dword ptr [rsp+6F0h+pvParam+4]
0x18001eea9  lea     rcx, [rbp+5F0h+pszSource]; void *
0x18001eead  mov     r14d, ebx
0x18001eeb0  xor     edx, edx; Val
0x18001eeb2  mov     r8d, 208h; Size
0x18001eeb8  and     r14d, 1
0x18001eebc  call    memset_0
0x18001eec1  xor     edx, edx; Val
0x18001eec3  lea     rcx, [rbp+5F0h+pszOutBuf]; void *
0x18001eeca  mov     r8d, 208h; Size
0x18001eed0  call    memset_0
0x18001eed5  test    edi, edi
0x18001eed7  jle     loc_18001EF75
0x18001eedd  or      ebx, 1
0x18001eee0  lea     r9d, [rdi+351h]
0x18001eee7  lea     r8, aThemeuiDllD; "@themeui.dll,-%d"
0x18001eeee  mov     dword ptr [rsp+6F0h+pvParam+4], ebx
0x18001eef2  mov     edx, 104h; unsigned __int64
0x18001eef7  lea     rcx, [rbp+5F0h+pszSource]; unsigned __int16 *
0x18001eefb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ef00  lea     r9, [rbp+5F0h+pszSource]; unsigned __int16 *
0x18001ef04  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18001ef0b  lea     r8, aNewcurrent; "NewCurrent"
0x18001ef12  mov     ebx, eax
0x18001ef14  lea     rdx, aControlPanelAp_0; "Control Panel\\Appearance"
0x18001ef1b  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001ef20  lea     r9, [rbp+5F0h+pszSource]; unsigned __int16 *
0x18001ef24  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18001ef2b  lea     r8, aCurrent_0; "Current"
0x18001ef32  lea     rdx, aControlPanelAp_0; "Control Panel\\Appearance"
0x18001ef39  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001ef3e  test    ebx, ebx
0x18001ef40  js      loc_18001F07D
0x18001ef46  xor     r9d, r9d; ppvReserved
0x18001ef49  lea     rdx, [rbp+5F0h+pszOutBuf]; pszOutBuf
0x18001ef50  mov     r8d, 104h; cchOutBuf
0x18001ef56  lea     rcx, [rbp+5F0h+pszSource]; pszSource
0x18001ef5a  call    cs:__imp_SHLoadIndirectString
0x18001ef60  test    eax, eax
0x18001ef62  jns     loc_18001F07D
0x18001ef68  mov     [rbp+5F0h+pszOutBuf], r12w
0x18001ef70  jmp     loc_18001F07D
0x18001ef75  mov     [rsp+6F0h+lpdwDisposition], r12; lpdwDisposition
0x18001ef7a  lea     rax, [rsp+6F0h+hKey]
0x18001ef7f  mov     [rsp+6F0h+phkResult], rax; phkResult
0x18001ef84  lea     rdx, aControlPanelAp_0; "Control Panel\\Appearance"
0x18001ef8b  and     ebx, 0FFFFFFFEh
0x18001ef8e  mov     [rsp+6F0h+pcbData], r12; lpSecurityAttributes
0x18001ef93  mov     dword ptr [rsp+6F0h+pvParam+4], ebx
0x18001ef97  xor     r9d, r9d; lpClass
0x18001ef9a  mov     ebx, 2
0x18001ef9f  mov     [rsp+6F0h+hKey], r12
0x18001efa4  mov     dword ptr [rsp+6F0h+pvData], ebx; samDesired
0x18001efa8  xor     r8d, r8d; Reserved
0x18001efab  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001efb2  mov     dword ptr [rsp+6F0h+pdwType], r12d; dwOptions
0x18001efb7  call    cs:__imp_RegCreateKeyExW
0x18001efbd  lea     rcx, Default
0x18001efc4  test    eax, eax
0x18001efc6  jnz     short loc_18001EFFE
0x18001efc8  mov     dword ptr [rsp+6F0h+pvData], ebx; cbData
0x18001efcc  lea     r9d, [rbx-1]; dwType
0x18001efd0  mov     [rsp+6F0h+pdwType], rcx; lpData
0x18001efd5  lea     rdx, aNewcurrent; "NewCurrent"
0x18001efdc  mov     rcx, [rsp+6F0h+hKey]; hKey
0x18001efe1  xor     r8d, r8d; Reserved
0x18001efe4  call    cs:__imp_RegSetValueExW
0x18001efea  mov     rcx, [rsp+6F0h+hKey]; hKey
0x18001efef  cmp     rcx, 0FFFFFFFF80000001h
0x18001eff6  jz      short loc_18001EFFE
0x18001eff8  call    cs:__imp_RegCloseKey
0x18001effe  mov     [rsp+6F0h+lpdwDisposition], r12; lpdwDisposition
0x18001f003  lea     rax, [rsp+6F0h+hKey]
0x18001f008  mov     [rsp+6F0h+phkResult], rax; phkResult
0x18001f00d  lea     rdx, aControlPanelAp_0; "Control Panel\\Appearance"
0x18001f014  mov     [rsp+6F0h+pcbData], r12; lpSecurityAttributes
0x18001f019  xor     r9d, r9d; lpClass
0x18001f01c  mov     dword ptr [rsp+6F0h+pvData], ebx; samDesired
0x18001f020  xor     r8d, r8d; Reserved
0x18001f023  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001f02a  mov     dword ptr [rsp+6F0h+pdwType], r12d; dwOptions
0x18001f02f  mov     [rsp+6F0h+hKey], r12
0x18001f034  call    cs:__imp_RegCreateKeyExW
0x18001f03a  test    eax, eax
0x18001f03c  jnz     short loc_18001F07D
0x18001f03e  mov     rcx, [rsp+6F0h+hKey]; hKey
0x18001f043  lea     rax, Default
0x18001f04a  mov     dword ptr [rsp+6F0h+pvData], ebx; cbData
0x18001f04e  lea     rdx, aCurrent_0; "Current"
0x18001f055  mov     r9d, 1; dwType
0x18001f05b  mov     [rsp+6F0h+pdwType], rax; lpData
0x18001f060  xor     r8d, r8d; Reserved
0x18001f063  call    cs:__imp_RegSetValueExW
0x18001f069  mov     rcx, [rsp+6F0h+hKey]; hKey
0x18001f06e  cmp     rcx, 0FFFFFFFF80000001h
0x18001f075  jz      short loc_18001F07D
0x18001f077  call    cs:__imp_RegCloseKey
0x18001f07d  test    sil, sil
0x18001f080  jnz     short loc_18001F0A6
0x18001f082  cmp     r14b, r15b
0x18001f085  jnz     short loc_18001F0A6
0x18001f087  test    edi, edi
0x18001f089  jle     short loc_18001F0F1
0x18001f08b  mov     rcx, qword ptr [rsp+6F0h+pvParam+8]; psz1
0x18001f090  test    rcx, rcx
0x18001f093  jz      short loc_18001F0AB
0x18001f095  lea     rdx, [rbp+5F0h+pszOutBuf]; psz2
0x18001f09c  call    cs:__imp_StrCmpIW
0x18001f0a2  test    eax, eax
0x18001f0a4  jz      short loc_18001F0F1
0x18001f0a6  mov     rcx, qword ptr [rsp+6F0h+pvParam+8]
0x18001f0ab  cmp     [rbp+5F0h+pszOutBuf], r12w
0x18001f0b3  lea     rax, [rbp+5F0h+pszOutBuf]
0x18001f0ba  lea     r8, [rsp+6F0h+pvParam]; pvParam
0x18001f0bf  mov     r15b, 1
0x18001f0c2  cmovz   rax, rcx
0x18001f0c6  bts     dword ptr [rsp+6F0h+pvParam+4], 0Ch
0x18001f0cc  xor     r9d, r9d; fWinIni
0x18001f0cf  mov     qword ptr [rsp+6F0h+pvParam+8], rax
0x18001f0d4  lea     edx, [r9+10h]; uiParam
0x18001f0d8  lea     ebx, [rdx+33h]
0x18001f0db  mov     ecx, ebx; uiAction
0x18001f0dd  call    cs:__imp_SystemParametersInfoW
0x18001f0e3  xor     r8d, r8d; lParam
0x18001f0e6  lea     ecx, [rbx-29h]; uMsg
0x18001f0e9  mov     edx, ebx; wParam
0x18001f0eb  call    cs:__imp_SHSendMessageBroadcastW
0x18001f0f1  mov     r9d, dword ptr [rsp+6F0h+pvParam+4]
0x18001f0f6  lea     r8, aD; "%d"
0x18001f0fd  btr     r9d, 0Ch
0x18001f102  lea     rcx, [rsp+6F0h+var_680]; unsigned __int16 *
0x18001f107  mov     edx, 0Ah; unsigned __int64
0x18001f10c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f111  test    eax, eax
0x18001f113  js      short loc_18001F126
0x18001f115  lea     r9, [rsp+6F0h+var_680]; unsigned __int16 *
0x18001f11a  lea     r8, aFlags; "Flags"
0x18001f121  call    ?SetRegValueString@@YAHPEAUHKEY__@@PEBG11@Z; SetRegValueString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001f126  mov     r9, qword ptr [rsp+6F0h+pvParam+8]; unsigned __int16 *
0x18001f12b  test    r9, r9
0x18001f12e  jz      short loc_18001F14D
0x18001f130  lea     r8, aHighContrastSc; "High Contrast Scheme"
0x18001f137  call    ?SetRegValueString@@YAHPEAUHKEY__@@PEBG11@Z; SetRegValueString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001f13c  mov     r9, qword ptr [rsp+6F0h+pvParam+8]; unsigned __int16 *
0x18001f141  lea     r8, aPreviousHighCo; "Previous High Contrast Scheme MUI Value"
0x18001f148  call    ?SetRegValueString@@YAHPEAUHKEY__@@PEBG11@Z; SetRegValueString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001f14d  cmp     [rbp+5F0h+pszSource], r12w
0x18001f152  jz      short loc_18001F164
0x18001f154  lea     r9, [rbp+5F0h+pszSource]; unsigned __int16 *
0x18001f158  lea     r8, aPreviousHighCo_0; "Previous High Contrast Scheme MUI Ptr"
0x18001f15f  call    ?SetRegValueString@@YAHPEAUHKEY__@@PEBG11@Z; SetRegValueString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001f164  lea     rax, [rsp+6F0h+hKey]
0x18001f169  mov     [rsp+6F0h+var_6A0], r12d
0x18001f16e  mov     [rsp+6F0h+pcbData], rax; pcbData
0x18001f173  lea     r8, aLastupdatedthe; "LastUpdatedThemeId"
0x18001f17a  lea     rax, [rsp+6F0h+var_6A0]
0x18001f17f  mov     dword ptr [rsp+6F0h+hKey], 4
0x18001f187  mov     [rsp+6F0h+pvData], rax; pvData
0x18001f18c  lea     rdx, aControlPanelAc; "Control Panel\\Accessibility\\HighContr"...
0x18001f193  mov     rbx, 0FFFFFFFF80000001h
0x18001f19a  mov     [rsp+6F0h+pdwType], r12; pdwType
0x18001f19f  mov     r9d, 10h; dwFlags
0x18001f1a5  mov     rcx, rbx; hkey
0x18001f1a8  call    cs:__imp_RegGetValueW
0x18001f1ae  test    eax, eax
0x18001f1b0  jle     short loc_18001F1BC
0x18001f1b2  movzx   eax, ax
0x18001f1b5  or      eax, 80070000h
0x18001f1ba  test    eax, eax
0x18001f1bc  jns     short loc_18001F1C7
0x18001f1be  mov     ecx, r12d
0x18001f1c1  mov     [rsp+6F0h+var_6A0], ecx
0x18001f1c5  jmp     short loc_18001F1CB
0x18001f1c7  mov     ecx, [rsp+6F0h+var_6A0]
0x18001f1cb  cmp     edi, ecx
0x18001f1cd  jz      short loc_18001F20B
0x18001f1cf  lea     eax, [rdi-1]
0x18001f1d2  cmp     eax, 2
0x18001f1d5  ja      short loc_18001F1DF
0x18001f1d7  lea     eax, [rcx-1]
0x18001f1da  cmp     eax, 2
0x18001f1dd  jbe     short loc_18001F20B
0x18001f1df  xor     r9d, r9d; dwItem2
0x18001f1e2  xor     r8d, r8d; dwItem1
0x18001f1e5  xor     edx, edx; uFlags
0x18001f1e7  mov     ecx, 8000000h; wEventId
0x18001f1ec  call    cs:__imp_SHChangeNotify
0x18001f1f2  mov     r9d, edi; unsigned int
0x18001f1f5  lea     r8, aLastupdatedthe; "LastUpdatedThemeId"
0x18001f1fc  lea     rdx, aControlPanelAc; "Control Panel\\Accessibility\\HighContr"...
0x18001f203  mov     rcx, rbx; HKEY
0x18001f206  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001f20b  mov     al, r15b
0x18001f20e  mov     rcx, [rbp+5F0h+var_30]
0x18001f215  xor     rcx, rsp; StackCookie
0x18001f218  call    __security_check_cookie
0x18001f21d  lea     r11, [rsp+6F0h+var_20]
0x18001f225  mov     rbx, [r11+38h]
0x18001f229  mov     rsi, [r11+40h]
0x18001f22d  mov     rsp, r11
0x18001f230  pop     r15
0x18001f232  pop     r14
0x18001f234  pop     r12
0x18001f236  pop     rdi
0x18001f237  pop     rbp
0x18001f238  retn
```
