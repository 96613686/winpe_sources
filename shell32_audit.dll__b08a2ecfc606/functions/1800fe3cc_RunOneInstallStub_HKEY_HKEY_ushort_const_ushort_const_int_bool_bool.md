# RunOneInstallStub(HKEY__ *,HKEY__ *,ushort const *,ushort const *,int,bool,bool)

- ea: `0x1800fe3cc`
- end: `0x1800fee46`
- name: `?RunOneInstallStub@@YAHPEAUHKEY__@@0PEBG1H_N2@Z`
- size: `2682`
- prototype: `int(HKEY, HKEY, const unsigned __int16 *, const unsigned __int16 *, int, bool, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800fddc4`

## callees

- `0x1800d1324`
- `0x1800fe3cc`
- `0x1800fefd8`
- `0x180249490`
- `0x18024a53c`
- `0x1802d42f0`
- `0x1802d4440`
- `0x1802d4638`
- `0x1802d46ac`
- `0x18055bab8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800fedc1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800fedc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe62b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe67a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe986`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800feda4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe62b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe67a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fe986`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800feda4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fec5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800feca3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fecea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fec5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800feca3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fecea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fe4ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fe4ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fe42d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fe600`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fe799`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fe42d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fe600`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fe799`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fec08`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fec08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe572`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe6ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe718`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe75e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe7db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe93f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fead9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fed28`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe572`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe6ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe718`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe75e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe7db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fe93f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fead9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fed28`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800feb0c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800feb0c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800fec28`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800fec71`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800fecbc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800fec28`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800fec71`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800fecbc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800fe967`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800fe967`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1800fe527`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1800fe879`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1800fe527`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1800fe879`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x1800fe5cc`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x1800fe5cc`

## string_xrefs

- `0x1800fe51c`: `StubPath`
- `0x1800fe56b`: `IsInstalled`
- `0x1800fea38`: `ShellComponent`
- `0x1800fed1d`: `DontAsk`

## pseudocode

```c
__int64 __fastcall RunOneInstallStub(
        HKEY a1,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        bool a6,
        char a7)
{
  DWORD v7; // r15d
  char v10; // al
  int v11; // ebx
  LSTATUS ValueW; // eax
  signed int v13; // ecx
  int v14; // ebx
  WCHAR *v15; // r12
  char v16; // bl
  unsigned int v18; // ebx
  unsigned int v19; // r14d
  int v20; // r13d
  DWORD v21; // esi
  const WCHAR *v22; // rsi
  int v23; // eax
  int v24; // eax
  int v25; // eax
  bool v26; // [rsp+50h] [rbp-B0h]
  unsigned int v27; // [rsp+54h] [rbp-ACh]
  unsigned int v28; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v29; // [rsp+5Ch] [rbp-A4h] BYREF
  PCWSTR psz2; // [rsp+60h] [rbp-A0h]
  HKEY hKey; // [rsp+68h] [rbp-98h]
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hkey; // [rsp+78h] [rbp-88h] BYREF
  __int64 Type; // [rsp+80h] [rbp-80h] BYREF
  BYTE pvData[4]; // [rsp+88h] [rbp-78h] BYREF
  DWORD pdwType; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp-70h] BYREF
  BYTE Data[4]; // [rsp+94h] [rbp-6Ch] BYREF
  BYTE v39[2]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR v40[12]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v41[24]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v42[28]; // [rsp+F8h] [rbp-8h] BYREF
  BYTE v43[2]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v44[264]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v45[264]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR String[264]; // [rsp+660h] [rbp+560h] BYREF

  v7 = 0;
  psz2 = a4;
  hKey = a2;
  v27 = 0;
  hkey = 0;
  if ( RegOpenKeyExW(a1, a3, 0, 1u, &hkey) )
    return v27;
  v10 = !a6;
  *(_DWORD *)Data = 0;
  Type = 0x400000000LL;
  phkResult = 0;
  v26 = !a6;
  if ( !a7 )
    goto LABEL_27;
  pdwType = 0;
  pcbData = 4;
  v11 = 0;
  ValueW = RegGetValueW(hkey, 0, L"Enabled", 0x10000012u, &pdwType, pvData, &pcbData);
  v13 = ValueW;
  if ( !ValueW )
  {
    LOWORD(v13) = 13;
    if ( pdwType == 4 )
    {
      if ( *(_DWORD *)pvData <= 1u )
      {
        v13 = 0;
        LOBYTE(v11) = *(_DWORD *)pvData == 1;
        goto LABEL_7;
      }
    }
    else if ( pcbData == 4 && (unsigned __int16)(*(_WORD *)pvData - 48) <= 1u )
    {
      v13 = 0;
      LOBYTE(v11) = *(_WORD *)pvData == 49;
      goto LABEL_7;
    }
    goto LABEL_6;
  }
  if ( ValueW == 234 )
  {
    LOWORD(v13) = 13;
    goto LABEL_6;
  }
  if ( ValueW > 0 )
LABEL_6:
    v13 = (unsigned __int16)v13 | 0x80070000;
LABEL_7:
  if ( v13 < 0 )
  {
    v10 = !a6;
    goto LABEL_9;
  }
  v10 = v11 != 0;
LABEL_27:
  v26 = v10;
LABEL_9:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x100000000LL) != 0 )
    McTemplateU0zttt_EtwEventWriteTransfer(
      (unsigned __int8)a7,
      (unsigned int)&Shell32_ActiveSetup_RunOneInstallStub_Start,
      (_DWORD)a3,
      a6,
      a7,
      v10);
  HIDWORD(Type) = 520;
  if ( !SHQueryValueExW(hkey, L"StubPath", 0, (DWORD *)&Type, v45, (DWORD *)&Type + 1) && (unsigned int)(Type - 1) <= 1 )
  {
    HIDWORD(Type) = 4;
    if ( !RegQueryValueExW(hkey, L"IsInstalled", 0, (LPDWORD)&Type, Data, (LPDWORD)&Type + 1)
      && ((_DWORD)Type == 4 || Type == 0x400000003LL) )
    {
      v14 = *(_DWORD *)Data;
    }
    else
    {
      v14 = 1;
      *(_DWORD *)Data = 1;
    }
    memset_0(v44, 0, 0x208u);
    if ( v14 )
      SHRegGetStringEx(hkey, 0, L"ShellComponent", 2, v44, 0x104u);
    v15 = String;
    if ( (int)SHLoadRegUIStringW(hkey, L"LocalizedName", String, 260) < 0 )
    {
      HIDWORD(Type) = 520;
      if ( SHQueryValueExW(hkey, &pszStart, 0, (DWORD *)&Type, String, (DWORD *)&Type + 1) || (_DWORD)Type != 1 )
      {
        v15 = v44;
        if ( !v44[0] )
          v15 = v45;
      }
    }
    if ( !*(_DWORD *)Data )
    {
      if ( RegOpenKeyExW(a2, a3, 0, 1u, &phkResult) )
        goto LABEL_21;
      *(_DWORD *)pvData = 0;
      HIDWORD(Type) = 4;
      if ( !RegQueryValueExW(hkey, L"DontAsk", 0, (LPDWORD)&Type, pvData, (LPDWORD)&Type + 1)
        && ((_DWORD)Type == 4 || Type == 0x400000003LL)
        && *(_DWORD *)pvData == 1 )
      {
        goto LABEL_21;
      }
      if ( a5 == -1 )
      {
LABEL_114:
        if ( *(_DWORD *)pvData == 2 || ConfirmUninstall(v15) == 6 )
        {
          IndicateProgress(v15, 0);
          ShellExecuteRegApp(v45, 10);
          RegCloseKey(phkResult);
          phkResult = 0;
          RegDeleteKeyExW(a2, a3, 0, 0);
        }
        goto LABEL_21;
      }
      if ( !a5 )
      {
        if ( *a3 == 62 )
          goto LABEL_114;
LABEL_124:
        if ( a5 == 2 )
        {
          if ( *a3 == 60 )
            goto LABEL_114;
LABEL_21:
          v16 = v26;
          goto LABEL_22;
        }
        goto LABEL_120;
      }
      if ( a5 != 1 )
        goto LABEL_124;
      if ( *a3 != 60 )
      {
        if ( *a3 != 62 )
          goto LABEL_114;
LABEL_120:
        if ( a5 && (a5 != 1 || *a3 != 60) )
          goto LABEL_21;
      }
LABEL_123:
      v27 = 1;
      goto LABEL_21;
    }
    pcbData = 0;
    v18 = 0;
    pdwType = 0;
    v28 = 0;
    v19 = 0;
    v29 = 0;
    *(_DWORD *)pvData = 0;
    HIDWORD(Type) = 4;
    if ( RegQueryValueExW(hkey, L"CloneUser", 0, (LPDWORD)&Type, pvData, (LPDWORD)&Type + 1)
      || (_DWORD)Type != 4 && Type != 0x400000003LL )
    {
      *(_DWORD *)pvData = 0;
    }
    HIDWORD(Type) = 48;
    if ( RegQueryValueExW(hkey, L"Version", 0, (LPDWORD)&Type, (LPBYTE)v41, (LPDWORD)&Type + 1)
      || (_DWORD)Type != 1
      || (int)GetVersionFromString(v41, &pcbData, &pdwType) < 0 )
    {
      v20 = 0;
      v21 = 0;
    }
    else
    {
      v21 = pcbData;
      v20 = 1;
      v7 = pdwType;
    }
    HIDWORD(Type) = 20;
    if ( RegQueryValueExW(hkey, L"Locale", 0, (LPDWORD)&Type, v39, (LPDWORD)&Type + 1) || (_DWORD)Type != 1 )
      *(_WORD *)v39 = 0;
    if ( RegOpenKeyExW(hKey, a3, 0, 3u, &phkResult) )
    {
      phkResult = 0;
    }
    else
    {
      HIDWORD(Type) = 48;
      if ( !RegQueryValueExW(phkResult, L"Version", 0, (LPDWORD)&Type, (LPBYTE)v42, (LPDWORD)&Type + 1)
        && (_DWORD)Type == 1
        && (int)GetVersionFromString(v42, &v28, &v29) >= 0 )
      {
        v18 = v28;
        v19 = v29;
      }
      if ( *(_WORD *)v39 )
      {
        HIDWORD(Type) = 20;
        if ( !RegQueryValueExW(phkResult, L"Locale", 0, (LPDWORD)&Type, (LPBYTE)v40, (LPDWORD)&Type + 1)
          && (_DWORD)Type == 1
          && !lstrcmpW((LPCWSTR)v39, v40) )
        {
          *(_WORD *)v39 = 0;
        }
      }
      if ( *(_DWORD *)pvData )
      {
        HIDWORD(Type) = 258;
        if ( RegQueryValueExW(phkResult, L"Username", 0, (LPDWORD)&Type, v43, (LPDWORD)&Type + 1) || (_DWORD)Type != 1 )
          *(_WORD *)v43 = 0;
      }
    }
    if ( !phkResult || v20 && (v21 > v18 || v21 == v18 && v7 > v19) || *(_WORD *)v39 )
    {
      v22 = psz2;
    }
    else
    {
      if ( !*(_DWORD *)pvData )
        goto LABEL_21;
      v22 = psz2;
      if ( !StrCmpIW((PCWSTR)v43, psz2) )
        goto LABEL_21;
    }
    if ( a5 == -1 )
    {
LABEL_85:
      IndicateProgress(v15, 1);
      v16 = v26;
      if ( v26 )
      {
        if ( v44[0] )
          ShellComponentSetup(v44, v45);
        else
          ShellExecuteRegApp(v45, 10);
      }
      if ( !phkResult )
      {
        RegCreateKeyExW(hKey, a3, 0, 0, 0, 2u, 0, &phkResult, 0);
        if ( !phkResult )
          goto LABEL_24;
      }
      if ( v20 )
      {
        v23 = lstrlenW(v41);
        RegSetValueExW(phkResult, L"Version", 0, 1u, (const BYTE *)v41, 2 * v23 + 2);
      }
      if ( *(_WORD *)v39 )
      {
        v24 = lstrlenW((LPCWSTR)v39);
        RegSetValueExW(phkResult, L"Locale", 0, 1u, v39, 2 * v24 + 2);
      }
      if ( *(_DWORD *)pvData )
      {
        v25 = lstrlenW(v22);
        RegSetValueExW(phkResult, L"Username", 0, 1u, (const BYTE *)v22, 2 * v25 + 2);
      }
LABEL_22:
      if ( phkResult )
        RegCloseKey(phkResult);
LABEL_24:
      RegCloseKey(hkey);
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x100000000LL) != 0 )
        McTemplateU0zttt_EtwEventWriteTransfer(
          (unsigned __int8)a7,
          (unsigned int)&Shell32_ActiveSetup_RunOneInstallStub_Stop,
          (_DWORD)a3,
          a6,
          a7,
          v16);
      return v27;
    }
    if ( a5 )
    {
      if ( a5 == 1 )
      {
        if ( *a3 == 60 )
          goto LABEL_93;
        if ( *a3 != 62 )
          goto LABEL_85;
LABEL_91:
        if ( !a5 )
          goto LABEL_123;
        if ( a5 != 1 )
          goto LABEL_21;
LABEL_93:
        v16 = v26;
        if ( *a3 == 62 )
          v27 = 1;
        goto LABEL_22;
      }
    }
    else if ( *a3 == 60 )
    {
      goto LABEL_85;
    }
    if ( a5 == 2 )
    {
      if ( *a3 != 62 )
        goto LABEL_21;
      goto LABEL_85;
    }
    goto LABEL_91;
  }
  RegCloseKey(hkey);
  return 0;
}

```

## disassembly

```asm
0x1800fe3cc  push    rbp
0x1800fe3ce  push    rbx
0x1800fe3cf  push    rsi
0x1800fe3d0  push    rdi
0x1800fe3d1  push    r12
0x1800fe3d3  push    r13
0x1800fe3d5  push    r14
0x1800fe3d7  push    r15
0x1800fe3d9  lea     rbp, [rsp-788h]
0x1800fe3e1  sub     rsp, 888h
0x1800fe3e8  mov     rax, cs:__security_cookie
0x1800fe3ef  xor     rax, rsp
0x1800fe3f2  mov     [rbp+7C0h+var_50], rax
0x1800fe3f9  xor     r15d, r15d
0x1800fe3fc  mov     [rsp+8C0h+psz2], r9
0x1800fe401  mov     rdi, r8
0x1800fe404  mov     [rsp+8C0h+hKey], rdx
0x1800fe409  mov     rsi, rdx
0x1800fe40c  mov     [rsp+8C0h+var_86C], r15d
0x1800fe411  lea     rax, [rsp+8C0h+hkey]
0x1800fe416  mov     [rsp+8C0h+hkey], r15
0x1800fe41b  lea     r14d, [r15+1]
0x1800fe41f  mov     [rsp+8C0h+phkResult], rax; phkResult
0x1800fe424  mov     r9d, r14d; samDesired
0x1800fe427  xor     r8d, r8d; ulOptions
0x1800fe42a  mov     rdx, rdi; lpSubKey
0x1800fe42d  call    cs:__imp_RegOpenKeyExW
0x1800fe434  nop     dword ptr [rax+rax+00h]
0x1800fe439  test    eax, eax
0x1800fe43b  jnz     loc_1800FE644
0x1800fe441  mov     al, [rbp+7C0h+arg_28]
0x1800fe447  lea     r13d, [r15+4]
0x1800fe44b  xor     al, r14b
0x1800fe44e  mov     dword ptr [rbp+7C0h+Data], r15d
0x1800fe452  lea     r12d, [r15+30h]
0x1800fe456  mov     dword ptr [rbp+7C0h+Type], r15d
0x1800fe45a  mov     dword ptr [rbp+7C0h+Type+4], r13d
0x1800fe45e  mov     [rsp+8C0h+var_850], r15
0x1800fe463  mov     [rsp+8C0h+var_870], al
0x1800fe467  cmp     [rbp+7C0h+arg_30], r15b
0x1800fe46e  jz      loc_1800FE66C
0x1800fe474  mov     rcx, [rsp+8C0h+hkey]; hkey
0x1800fe479  lea     rax, [rbp+7C0h+var_830]
0x1800fe47d  mov     [rsp+8C0h+pcbData], rax; pcbData
0x1800fe482  lea     r8, aEnabled; "Enabled"
0x1800fe489  lea     rax, [rbp+7C0h+var_838]
0x1800fe48d  mov     [rbp+7C0h+pdwType], r15d
0x1800fe491  mov     [rsp+8C0h+pvData], rax; pvData
0x1800fe496  mov     r9d, 10000012h; dwFlags
0x1800fe49c  lea     rax, [rbp+7C0h+pdwType]
0x1800fe4a0  mov     [rbp+7C0h+var_830], r13d
0x1800fe4a4  xor     edx, edx; lpSubKey
0x1800fe4a6  mov     [rsp+8C0h+phkResult], rax; pdwType
0x1800fe4ab  mov     ebx, r15d
0x1800fe4ae  call    cs:__imp_RegGetValueW
0x1800fe4b5  nop     dword ptr [rax+rax+00h]
0x1800fe4ba  mov     ecx, eax
0x1800fe4bc  test    eax, eax
0x1800fe4be  jz      loc_1800FE8B2
0x1800fe4c4  cmp     eax, 0EAh
0x1800fe4c9  jz      loc_1800FE9C7
0x1800fe4cf  test    eax, eax
0x1800fe4d1  jle     short loc_1800FE4DC
0x1800fe4d3  movzx   ecx, cx
0x1800fe4d6  or      ecx, 80070000h
0x1800fe4dc  test    ecx, ecx
0x1800fe4de  jns     loc_1800FE9D1
0x1800fe4e4  mov     al, [rsp+8C0h+var_870]
0x1800fe4e8  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+4, r14b
0x1800fe4ef  jnz     loc_1800FE9DB
0x1800fe4f5  mov     rcx, [rsp+8C0h+hkey]; hkey
0x1800fe4fa  lea     rax, [rbp+7C0h+Type+4]
0x1800fe4fe  mov     [rsp+8C0h+pvData], rax; pcbData
0x1800fe503  lea     r9, [rbp+7C0h+Type]; pdwType
0x1800fe507  lea     rax, [rbp+7C0h+var_470]
0x1800fe50e  mov     r12d, 208h
0x1800fe514  xor     r8d, r8d; pdwReserved
0x1800fe517  mov     [rsp+8C0h+phkResult], rax; pvData
0x1800fe51c  lea     rdx, aStubpath; "StubPath"
0x1800fe523  mov     dword ptr [rbp+7C0h+Type+4], r12d
0x1800fe527  call    cs:__imp_SHQueryValueExW
0x1800fe52e  nop     dword ptr [rax+rax+00h]
0x1800fe533  test    eax, eax
0x1800fe535  jnz     loc_1800FE675
0x1800fe53b  mov     eax, dword ptr [rbp+7C0h+Type]
0x1800fe53e  dec     eax
0x1800fe540  cmp     eax, r14d
0x1800fe543  ja      loc_1800FE675
0x1800fe549  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800fe54e  lea     rax, [rbp+7C0h+Type+4]
0x1800fe552  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800fe557  lea     r9, [rbp+7C0h+Type]; lpType
0x1800fe55b  lea     rax, [rbp+7C0h+Data]
0x1800fe55f  mov     dword ptr [rbp+7C0h+Type+4], r13d
0x1800fe563  xor     r8d, r8d; lpReserved
0x1800fe566  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800fe56b  lea     rdx, aIsinstalled; "IsInstalled"
0x1800fe572  call    cs:__imp_RegQueryValueExW
0x1800fe579  nop     dword ptr [rax+rax+00h]
0x1800fe57e  test    eax, eax
0x1800fe580  jnz     loc_1800FEA19
0x1800fe586  cmp     dword ptr [rbp+7C0h+Type], r13d
0x1800fe58a  jnz     loc_1800FEA09
0x1800fe590  mov     ebx, dword ptr [rbp+7C0h+Data]
0x1800fe593  mov     r8, r12; Size
0x1800fe596  lea     rcx, [rbp+7C0h+var_680]; void *
0x1800fe59d  xor     edx, edx; Val
0x1800fe59f  call    memset_0
0x1800fe5a4  test    ebx, ebx
0x1800fe5a6  jnz     loc_1800FEA24
0x1800fe5ac  mov     rcx, [rsp+8C0h+hkey]
0x1800fe5b1  lea     r8, [rbp+7C0h+String]
0x1800fe5b8  mov     r9d, 104h
0x1800fe5be  lea     rdx, aLocalizedname; "LocalizedName"
0x1800fe5c5  lea     r12, [rbp+7C0h+String]
0x1800fe5cc  call    cs:__imp_SHLoadRegUIStringW
0x1800fe5d3  nop     dword ptr [rax+rax+00h]
0x1800fe5d8  test    eax, eax
0x1800fe5da  js      loc_1800FE84A
0x1800fe5e0  cmp     dword ptr [rbp+7C0h+Data], r15d
0x1800fe5e4  jnz     loc_1800FE68A
0x1800fe5ea  lea     rax, [rsp+8C0h+var_850]
0x1800fe5ef  mov     r9d, r14d; samDesired
0x1800fe5f2  xor     r8d, r8d; ulOptions
0x1800fe5f5  mov     [rsp+8C0h+phkResult], rax; phkResult
0x1800fe5fa  mov     rdx, rdi; lpSubKey
0x1800fe5fd  mov     rcx, rsi; hKey
0x1800fe600  call    cs:__imp_RegOpenKeyExW
0x1800fe607  nop     dword ptr [rax+rax+00h]
0x1800fe60c  test    eax, eax
0x1800fe60e  jz      loc_1800FECFB
0x1800fe614  mov     bl, [rsp+8C0h+var_870]
0x1800fe618  mov     rcx, [rsp+8C0h+var_850]; hKey
0x1800fe61d  test    rcx, rcx
0x1800fe620  jnz     loc_1800FE986
0x1800fe626  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800fe62b  call    cs:__imp_RegCloseKey
0x1800fe632  nop     dword ptr [rax+rax+00h]
0x1800fe637  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+4, r14b
0x1800fe63e  jnz     loc_1800FEE18
0x1800fe644  mov     eax, [rsp+8C0h+var_86C]
0x1800fe648  mov     rcx, [rbp+7C0h+var_50]
0x1800fe64f  xor     rcx, rsp; StackCookie
0x1800fe652  call    __security_check_cookie
0x1800fe657  add     rsp, 888h
0x1800fe65e  pop     r15
0x1800fe660  pop     r14
0x1800fe662  pop     r13
0x1800fe664  pop     r12
0x1800fe666  pop     rdi
0x1800fe667  pop     rsi
0x1800fe668  pop     rbx
0x1800fe669  pop     rbp
0x1800fe66a  retn
0x1800fe66c  mov     [rsp+8C0h+var_870], al
0x1800fe670  jmp     loc_1800FE4E8
0x1800fe675  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800fe67a  call    cs:__imp_RegCloseKey
0x1800fe681  nop     dword ptr [rax+rax+00h]
0x1800fe686  xor     eax, eax
0x1800fe688  jmp     short loc_1800FE648
0x1800fe68a  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800fe68f  lea     rax, [rbp+7C0h+Type+4]
0x1800fe693  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800fe698  lea     r9, [rbp+7C0h+Type]; lpType
0x1800fe69c  lea     rax, [rbp+7C0h+var_838]
0x1800fe6a0  mov     [rbp+7C0h+var_830], r15d
0x1800fe6a4  mov     ebx, r15d
0x1800fe6a7  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800fe6ac  xor     r8d, r8d; lpReserved
0x1800fe6af  mov     [rbp+7C0h+pdwType], r15d
0x1800fe6b3  lea     rdx, aCloneuser; "CloneUser"
0x1800fe6ba  mov     [rsp+8C0h+var_868], ebx
0x1800fe6be  mov     r14d, r15d
0x1800fe6c1  mov     [rsp+8C0h+var_864], r15d
0x1800fe6c6  mov     dword ptr [rbp+7C0h+var_838], r15d
0x1800fe6ca  mov     dword ptr [rbp+7C0h+Type+4], r13d
0x1800fe6ce  call    cs:__imp_RegQueryValueExW
0x1800fe6d5  nop     dword ptr [rax+rax+00h]
0x1800fe6da  test    eax, eax
0x1800fe6dc  jnz     loc_1800FEA66
0x1800fe6e2  cmp     dword ptr [rbp+7C0h+Type], r13d
0x1800fe6e6  jnz     loc_1800FEA56
0x1800fe6ec  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800fe6f1  lea     rax, [rbp+7C0h+Type+4]
0x1800fe6f5  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800fe6fa  lea     r9, [rbp+7C0h+Type]; lpType
0x1800fe6fe  lea     rax, [rbp+7C0h+var_7F8]
0x1800fe702  mov     dword ptr [rbp+7C0h+Type+4], 30h ; '0'
0x1800fe709  xor     r8d, r8d; lpReserved
0x1800fe70c  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800fe711  lea     rdx, aVersion_1; "Version"
0x1800fe718  call    cs:__imp_RegQueryValueExW
0x1800fe71f  nop     dword ptr [rax+rax+00h]
0x1800fe724  test    eax, eax
0x1800fe726  jz      loc_1800FEA6F
0x1800fe72c  mov     r13d, r15d
0x1800fe72f  mov     esi, r15d
0x1800fe732  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800fe737  lea     rax, [rbp+7C0h+Type+4]
0x1800fe73b  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800fe740  lea     r9, [rbp+7C0h+Type]; lpType
0x1800fe744  lea     rax, [rbp+7C0h+var_828]
0x1800fe748  mov     dword ptr [rbp+7C0h+Type+4], 14h
0x1800fe74f  xor     r8d, r8d; lpReserved
0x1800fe752  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800fe757  lea     rdx, aLocale; "Locale"
0x1800fe75e  call    cs:__imp_RegQueryValueExW
0x1800fe765  nop     dword ptr [rax+rax+00h]
0x1800fe76a  xor     ecx, ecx
0x1800fe76c  test    eax, eax
0x1800fe76e  jnz     loc_1800FEAA4
0x1800fe774  cmp     dword ptr [rbp+7C0h+Type], 1
0x1800fe778  jnz     loc_1800FEAA4
0x1800fe77e  mov     rcx, [rsp+8C0h+hKey]; hKey
0x1800fe783  lea     rax, [rsp+8C0h+var_850]
0x1800fe788  mov     r9d, 3; samDesired
0x1800fe78e  mov     [rsp+8C0h+phkResult], rax; phkResult
0x1800fe793  xor     r8d, r8d; ulOptions
0x1800fe796  mov     rdx, rdi; lpSubKey
0x1800fe799  call    cs:__imp_RegOpenKeyExW
0x1800fe7a0  nop     dword ptr [rax+rax+00h]
0x1800fe7a5  xor     ecx, ecx
0x1800fe7a7  test    eax, eax
0x1800fe7a9  jnz     loc_1800FE8D6
0x1800fe7af  mov     rcx, [rsp+8C0h+var_850]; hKey
0x1800fe7b4  lea     rax, [rbp+7C0h+Type+4]
0x1800fe7b8  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800fe7bd  lea     r9, [rbp+7C0h+Type]; lpType
0x1800fe7c1  lea     rax, [rbp+7C0h+var_7C8]
0x1800fe7c5  mov     dword ptr [rbp+7C0h+Type+4], 30h ; '0'
0x1800fe7cc  xor     r8d, r8d; lpReserved
0x1800fe7cf  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800fe7d4  lea     rdx, aVersion_1; "Version"
0x1800fe7db  call    cs:__imp_RegQueryValueExW
0x1800fe7e2  nop     dword ptr [rax+rax+00h]
0x1800fe7e7  test    eax, eax
0x1800fe7e9  jz      loc_1800FE8E0
0x1800fe7ef  xor     ecx, ecx
0x1800fe7f1  cmp     word ptr [rbp+7C0h+var_828], cx
0x1800fe7f5  jnz     loc_1800FE913
0x1800fe7fb  cmp     dword ptr [rbp+7C0h+var_838], ecx
0x1800fe7fe  jnz     loc_1800FEAAD
0x1800fe804  cmp     [rsp+8C0h+var_850], rcx
0x1800fe809  jz      loc_1800FEB22
0x1800fe80f  test    r13d, r13d
0x1800fe812  jz      short loc_1800FE827
0x1800fe814  cmp     esi, ebx
0x1800fe816  ja      loc_1800FEB22
0x1800fe81c  jnz     short loc_1800FE827
0x1800fe81e  cmp     r15d, r14d
0x1800fe821  ja      loc_1800FEB22
0x1800fe827  xor     r15d, r15d
0x1800fe82a  cmp     word ptr [rbp+7C0h+var_828], r15w
0x1800fe82f  jnz     loc_1800FEB25
0x1800fe835  cmp     dword ptr [rbp+7C0h+var_838], r15d
0x1800fe839  jnz     loc_1800FEB00
0x1800fe83f  mov     r14d, 1
0x1800fe845  jmp     loc_1800FE614
0x1800fe84a  mov     rcx, [rsp+8C0h+hkey]; hkey
0x1800fe84f  lea     rax, [rbp+7C0h+Type+4]
0x1800fe853  mov     [rsp+8C0h+pvData], rax; pcbData
0x1800fe858  lea     r9, [rbp+7C0h+Type]; pdwType
0x1800fe85c  lea     rax, [rbp+7C0h+String]
0x1800fe863  mov     dword ptr [rbp+7C0h+Type+4], 208h
0x1800fe86a  xor     r8d, r8d; pdwReserved
0x1800fe86d  mov     [rsp+8C0h+phkResult], rax; pvData
0x1800fe872  lea     rdx, pszStart; pszValue
0x1800fe879  call    cs:__imp_SHQueryValueExW
0x1800fe880  nop     dword ptr [rax+rax+00h]
0x1800fe885  test    eax, eax
0x1800fe887  jnz     short loc_1800FE893
0x1800fe889  cmp     dword ptr [rbp+7C0h+Type], r14d
0x1800fe88d  jz      loc_1800FE5E0
0x1800fe893  cmp     [rbp+7C0h+var_680], r15w
0x1800fe89b  lea     r12, [rbp+7C0h+var_680]
0x1800fe8a2  lea     rax, [rbp+7C0h+var_470]
0x1800fe8a9  cmovz   r12, rax
0x1800fe8ad  jmp     loc_1800FE5E0
0x1800fe8b2  mov     ecx, 0Dh
0x1800fe8b7  cmp     [rbp+7C0h+pdwType], r13d
0x1800fe8bb  jnz     loc_1800FE997
0x1800fe8c1  cmp     dword ptr [rbp+7C0h+var_838], r14d
0x1800fe8c5  ja      loc_1800FE4D3
0x1800fe8cb  mov     ecx, r15d
0x1800fe8ce  setz    bl
0x1800fe8d1  jmp     loc_1800FE4DC
0x1800fe8d6  mov     [rsp+8C0h+var_850], rcx
0x1800fe8db  jmp     loc_1800FE804
0x1800fe8e0  cmp     dword ptr [rbp+7C0h+Type], 1
0x1800fe8e4  jnz     loc_1800FE7EF
0x1800fe8ea  lea     r8, [rsp+8C0h+var_864]; unsigned int *
0x1800fe8ef  lea     rdx, [rsp+8C0h+var_868]; unsigned int *
0x1800fe8f4  lea     rcx, [rbp+7C0h+var_7C8]; unsigned __int16 *
0x1800fe8f8  call    ?GetVersionFromString@@YAJPEBGPEAK1@Z; GetVersionFromString(ushort const *,ulong *,ulong *)
0x1800fe8fd  test    eax, eax
0x1800fe8ff  js      loc_1800FE7EF
0x1800fe905  mov     ebx, [rsp+8C0h+var_868]
0x1800fe909  mov     r14d, [rsp+8C0h+var_864]
0x1800fe90e  jmp     loc_1800FE7EF
  ... truncated ...
```
