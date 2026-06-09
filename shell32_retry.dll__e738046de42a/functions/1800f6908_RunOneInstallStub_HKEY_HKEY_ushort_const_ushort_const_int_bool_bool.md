# RunOneInstallStub(HKEY__ *,HKEY__ *,ushort const *,ushort const *,int,bool,bool)

- ea: `0x1800f6908`
- end: `0x1800f72d3`
- name: `?RunOneInstallStub@@YAHPEAUHKEY__@@0PEBG1H_N2@Z`
- size: `2507`
- prototype: `int(HKEY, HKEY, const unsigned __int16 *, const unsigned __int16 *, int, bool, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f6380`

## callees

- `0x1800cacd0`
- `0x1800f6908`
- `0x1800f7468`
- `0x180233280`
- `0x1802342fc`
- `0x1802b8010`
- `0x1802b8130`
- `0x1802b82d8`
- `0x1802b8338`
- `0x18051dc80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f6969`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f6b1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f6c92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f6969`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f6b1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f6c92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f6b43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f6b8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f6e61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f723d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f6b43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f6b8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f6e61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f723d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800f7254`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800f7254`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f69e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f69e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6a9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6bd9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6c1d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6c5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6cce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6e26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6fae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f71c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6a9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6bd9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6c1d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6c5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6cce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6e26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f6fae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f71c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800f70d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800f70d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f7117`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f7154`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f718f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f7117`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f7154`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f718f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800f6fdb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800f6fdb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800f6e48`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800f6e48`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800f70eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800f7128`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800f7167`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800f70eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800f7128`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800f7167`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1800f6a57`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1800f6d66`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1800f6a57`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1800f6d66`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x1800f6af0`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x1800f6af0`

## string_xrefs

- `0x1800f6a4c`: `StubPath`
- `0x1800f6a95`: `IsInstalled`
- `0x1800f71bc`: `DontAsk`
- `0x1800f6f0d`: `ShellComponent`

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
      if ( SHQueryValueExW(hkey, (LPCWSTR)&pszStart, 0, (DWORD *)&Type, String, (DWORD *)&Type + 1) || (_DWORD)Type != 1 )
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
0x1800f6908  push    rbp
0x1800f690a  push    rbx
0x1800f690b  push    rsi
0x1800f690c  push    rdi
0x1800f690d  push    r12
0x1800f690f  push    r13
0x1800f6911  push    r14
0x1800f6913  push    r15
0x1800f6915  lea     rbp, [rsp-788h]
0x1800f691d  sub     rsp, 888h
0x1800f6924  mov     rax, cs:__security_cookie
0x1800f692b  xor     rax, rsp
0x1800f692e  mov     [rbp+7C0h+var_50], rax
0x1800f6935  xor     r15d, r15d
0x1800f6938  mov     [rsp+8C0h+psz2], r9
0x1800f693d  mov     rdi, r8
0x1800f6940  mov     [rsp+8C0h+hKey], rdx
0x1800f6945  mov     rsi, rdx
0x1800f6948  mov     [rsp+8C0h+var_86C], r15d
0x1800f694d  lea     rax, [rsp+8C0h+hkey]
0x1800f6952  mov     [rsp+8C0h+hkey], r15
0x1800f6957  lea     r14d, [r15+1]
0x1800f695b  mov     [rsp+8C0h+phkResult], rax; phkResult
0x1800f6960  mov     r9d, r14d; samDesired
0x1800f6963  xor     r8d, r8d; ulOptions
0x1800f6966  mov     rdx, rdi; lpSubKey
0x1800f6969  call    cs:__imp_RegOpenKeyExW
0x1800f696f  test    eax, eax
0x1800f6971  jnz     loc_1800F6B56
0x1800f6977  mov     al, [rbp+7C0h+arg_28]
0x1800f697d  lea     r13d, [r15+4]
0x1800f6981  xor     al, r14b
0x1800f6984  mov     dword ptr [rbp+7C0h+Data], r15d
0x1800f6988  lea     r12d, [r15+30h]
0x1800f698c  mov     dword ptr [rbp+7C0h+Type], r15d
0x1800f6990  mov     dword ptr [rbp+7C0h+Type+4], r13d
0x1800f6994  mov     [rsp+8C0h+var_850], r15
0x1800f6999  mov     [rsp+8C0h+var_870], al
0x1800f699d  cmp     [rbp+7C0h+arg_30], r15b
0x1800f69a4  jz      loc_1800F6B7D
0x1800f69aa  mov     rcx, [rsp+8C0h+hkey]; hkey
0x1800f69af  lea     rax, [rbp+7C0h+var_830]
0x1800f69b3  mov     [rsp+8C0h+pcbData], rax; pcbData
0x1800f69b8  lea     r8, aEnabled; "Enabled"
0x1800f69bf  lea     rax, [rbp+7C0h+var_838]
0x1800f69c3  mov     [rbp+7C0h+pdwType], r15d
0x1800f69c7  mov     [rsp+8C0h+pvData], rax; pvData
0x1800f69cc  mov     r9d, 10000012h; dwFlags
0x1800f69d2  lea     rax, [rbp+7C0h+pdwType]
0x1800f69d6  mov     [rbp+7C0h+var_830], r13d
0x1800f69da  xor     edx, edx; lpSubKey
0x1800f69dc  mov     [rsp+8C0h+phkResult], rax; pdwType
0x1800f69e1  mov     ebx, r15d
0x1800f69e4  call    cs:__imp_RegGetValueW
0x1800f69ea  mov     ecx, eax
0x1800f69ec  test    eax, eax
0x1800f69ee  jz      loc_1800F6D99
0x1800f69f4  cmp     eax, 0EAh
0x1800f69f9  jz      loc_1800F6E9C
0x1800f69ff  test    eax, eax
0x1800f6a01  jle     short loc_1800F6A0C
0x1800f6a03  movzx   ecx, cx
0x1800f6a06  or      ecx, 80070000h
0x1800f6a0c  test    ecx, ecx
0x1800f6a0e  jns     loc_1800F6EA6
0x1800f6a14  mov     al, [rsp+8C0h+var_870]
0x1800f6a18  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+4, r14b
0x1800f6a1f  jnz     loc_1800F6EB0
0x1800f6a25  mov     rcx, [rsp+8C0h+hkey]; hkey
0x1800f6a2a  lea     rax, [rbp+7C0h+Type+4]
0x1800f6a2e  mov     [rsp+8C0h+pvData], rax; pcbData
0x1800f6a33  lea     r9, [rbp+7C0h+Type]; pdwType
0x1800f6a37  lea     rax, [rbp+7C0h+var_470]
0x1800f6a3e  mov     r12d, 208h
0x1800f6a44  xor     r8d, r8d; pdwReserved
0x1800f6a47  mov     [rsp+8C0h+phkResult], rax; pvData
0x1800f6a4c  lea     rdx, aStubpath; "StubPath"
0x1800f6a53  mov     dword ptr [rbp+7C0h+Type+4], r12d
0x1800f6a57  call    cs:__imp_SHQueryValueExW
0x1800f6a5d  test    eax, eax
0x1800f6a5f  jnz     loc_1800F6B86
0x1800f6a65  mov     eax, dword ptr [rbp+7C0h+Type]
0x1800f6a68  dec     eax
0x1800f6a6a  cmp     eax, r14d
0x1800f6a6d  ja      loc_1800F6B86
0x1800f6a73  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800f6a78  lea     rax, [rbp+7C0h+Type+4]
0x1800f6a7c  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800f6a81  lea     r9, [rbp+7C0h+Type]; lpType
0x1800f6a85  lea     rax, [rbp+7C0h+Data]
0x1800f6a89  mov     dword ptr [rbp+7C0h+Type+4], r13d
0x1800f6a8d  xor     r8d, r8d; lpReserved
0x1800f6a90  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800f6a95  lea     rdx, aIsinstalled; "IsInstalled"
0x1800f6a9c  call    cs:__imp_RegQueryValueExW
0x1800f6aa2  test    eax, eax
0x1800f6aa4  jnz     loc_1800F6EEE
0x1800f6aaa  cmp     dword ptr [rbp+7C0h+Type], r13d
0x1800f6aae  jnz     loc_1800F6EDE
0x1800f6ab4  mov     ebx, dword ptr [rbp+7C0h+Data]
0x1800f6ab7  mov     r8, r12; Size
0x1800f6aba  lea     rcx, [rbp+7C0h+var_680]; void *
0x1800f6ac1  xor     edx, edx; Val
0x1800f6ac3  call    memset_0
0x1800f6ac8  test    ebx, ebx
0x1800f6aca  jnz     loc_1800F6EF9
0x1800f6ad0  mov     rcx, [rsp+8C0h+hkey]
0x1800f6ad5  lea     r8, [rbp+7C0h+String]
0x1800f6adc  mov     r9d, 104h
0x1800f6ae2  lea     rdx, aLocalizedname; "LocalizedName"
0x1800f6ae9  lea     r12, [rbp+7C0h+String]
0x1800f6af0  call    cs:__imp_SHLoadRegUIStringW
0x1800f6af6  test    eax, eax
0x1800f6af8  js      loc_1800F6D37
0x1800f6afe  cmp     dword ptr [rbp+7C0h+Data], r15d
0x1800f6b02  jnz     loc_1800F6B95
0x1800f6b08  lea     rax, [rsp+8C0h+var_850]
0x1800f6b0d  mov     r9d, r14d; samDesired
0x1800f6b10  xor     r8d, r8d; ulOptions
0x1800f6b13  mov     [rsp+8C0h+phkResult], rax; phkResult
0x1800f6b18  mov     rdx, rdi; lpSubKey
0x1800f6b1b  mov     rcx, rsi; hKey
0x1800f6b1e  call    cs:__imp_RegOpenKeyExW
0x1800f6b24  test    eax, eax
0x1800f6b26  jz      loc_1800F719A
0x1800f6b2c  mov     bl, [rsp+8C0h+var_870]
0x1800f6b30  mov     rcx, [rsp+8C0h+var_850]; hKey
0x1800f6b35  test    rcx, rcx
0x1800f6b38  jnz     loc_1800F6E61
0x1800f6b3e  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800f6b43  call    cs:__imp_RegCloseKey
0x1800f6b49  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+4, r14b
0x1800f6b50  jnz     loc_1800F72A5
0x1800f6b56  mov     eax, [rsp+8C0h+var_86C]
0x1800f6b5a  mov     rcx, [rbp+7C0h+var_50]
0x1800f6b61  xor     rcx, rsp; StackCookie
0x1800f6b64  call    __security_check_cookie
0x1800f6b69  add     rsp, 888h
0x1800f6b70  pop     r15
0x1800f6b72  pop     r14
0x1800f6b74  pop     r13
0x1800f6b76  pop     r12
0x1800f6b78  pop     rdi
0x1800f6b79  pop     rsi
0x1800f6b7a  pop     rbx
0x1800f6b7b  pop     rbp
0x1800f6b7c  retn
0x1800f6b7d  mov     [rsp+8C0h+var_870], al
0x1800f6b81  jmp     loc_1800F6A18
0x1800f6b86  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800f6b8b  call    cs:__imp_RegCloseKey
0x1800f6b91  xor     eax, eax
0x1800f6b93  jmp     short loc_1800F6B5A
0x1800f6b95  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800f6b9a  lea     rax, [rbp+7C0h+Type+4]
0x1800f6b9e  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800f6ba3  lea     r9, [rbp+7C0h+Type]; lpType
0x1800f6ba7  lea     rax, [rbp+7C0h+var_838]
0x1800f6bab  mov     [rbp+7C0h+var_830], r15d
0x1800f6baf  mov     ebx, r15d
0x1800f6bb2  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800f6bb7  xor     r8d, r8d; lpReserved
0x1800f6bba  mov     [rbp+7C0h+pdwType], r15d
0x1800f6bbe  lea     rdx, aCloneuser; "CloneUser"
0x1800f6bc5  mov     [rsp+8C0h+var_868], ebx
0x1800f6bc9  mov     r14d, r15d
0x1800f6bcc  mov     [rsp+8C0h+var_864], r15d
0x1800f6bd1  mov     dword ptr [rbp+7C0h+var_838], r15d
0x1800f6bd5  mov     dword ptr [rbp+7C0h+Type+4], r13d
0x1800f6bd9  call    cs:__imp_RegQueryValueExW
0x1800f6bdf  test    eax, eax
0x1800f6be1  jnz     loc_1800F6F3B
0x1800f6be7  cmp     dword ptr [rbp+7C0h+Type], r13d
0x1800f6beb  jnz     loc_1800F6F2B
0x1800f6bf1  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800f6bf6  lea     rax, [rbp+7C0h+Type+4]
0x1800f6bfa  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800f6bff  lea     r9, [rbp+7C0h+Type]; lpType
0x1800f6c03  lea     rax, [rbp+7C0h+var_7F8]
0x1800f6c07  mov     dword ptr [rbp+7C0h+Type+4], 30h ; '0'
0x1800f6c0e  xor     r8d, r8d; lpReserved
0x1800f6c11  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800f6c16  lea     rdx, aVersion_1; "Version"
0x1800f6c1d  call    cs:__imp_RegQueryValueExW
0x1800f6c23  test    eax, eax
0x1800f6c25  jz      loc_1800F6F44
0x1800f6c2b  mov     r13d, r15d
0x1800f6c2e  mov     esi, r15d
0x1800f6c31  mov     rcx, [rsp+8C0h+hkey]; hKey
0x1800f6c36  lea     rax, [rbp+7C0h+Type+4]
0x1800f6c3a  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800f6c3f  lea     r9, [rbp+7C0h+Type]; lpType
0x1800f6c43  lea     rax, [rbp+7C0h+var_828]
0x1800f6c47  mov     dword ptr [rbp+7C0h+Type+4], 14h
0x1800f6c4e  xor     r8d, r8d; lpReserved
0x1800f6c51  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800f6c56  lea     rdx, aLocale; "Locale"
0x1800f6c5d  call    cs:__imp_RegQueryValueExW
0x1800f6c63  xor     ecx, ecx
0x1800f6c65  test    eax, eax
0x1800f6c67  jnz     loc_1800F6F79
0x1800f6c6d  cmp     dword ptr [rbp+7C0h+Type], 1
0x1800f6c71  jnz     loc_1800F6F79
0x1800f6c77  mov     rcx, [rsp+8C0h+hKey]; hKey
0x1800f6c7c  lea     rax, [rsp+8C0h+var_850]
0x1800f6c81  mov     r9d, 3; samDesired
0x1800f6c87  mov     [rsp+8C0h+phkResult], rax; phkResult
0x1800f6c8c  xor     r8d, r8d; ulOptions
0x1800f6c8f  mov     rdx, rdi; lpSubKey
0x1800f6c92  call    cs:__imp_RegOpenKeyExW
0x1800f6c98  xor     ecx, ecx
0x1800f6c9a  test    eax, eax
0x1800f6c9c  jnz     loc_1800F6DBD
0x1800f6ca2  mov     rcx, [rsp+8C0h+var_850]; hKey
0x1800f6ca7  lea     rax, [rbp+7C0h+Type+4]
0x1800f6cab  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800f6cb0  lea     r9, [rbp+7C0h+Type]; lpType
0x1800f6cb4  lea     rax, [rbp+7C0h+var_7C8]
0x1800f6cb8  mov     dword ptr [rbp+7C0h+Type+4], 30h ; '0'
0x1800f6cbf  xor     r8d, r8d; lpReserved
0x1800f6cc2  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800f6cc7  lea     rdx, aVersion_1; "Version"
0x1800f6cce  call    cs:__imp_RegQueryValueExW
0x1800f6cd4  test    eax, eax
0x1800f6cd6  jz      loc_1800F6DC7
0x1800f6cdc  xor     ecx, ecx
0x1800f6cde  cmp     word ptr [rbp+7C0h+var_828], cx
0x1800f6ce2  jnz     loc_1800F6DFA
0x1800f6ce8  cmp     dword ptr [rbp+7C0h+var_838], ecx
0x1800f6ceb  jnz     loc_1800F6F82
0x1800f6cf1  cmp     [rsp+8C0h+var_850], rcx
0x1800f6cf6  jz      loc_1800F6FEB
0x1800f6cfc  test    r13d, r13d
0x1800f6cff  jz      short loc_1800F6D14
0x1800f6d01  cmp     esi, ebx
0x1800f6d03  ja      loc_1800F6FEB
0x1800f6d09  jnz     short loc_1800F6D14
0x1800f6d0b  cmp     r15d, r14d
0x1800f6d0e  ja      loc_1800F6FEB
0x1800f6d14  xor     r15d, r15d
0x1800f6d17  cmp     word ptr [rbp+7C0h+var_828], r15w
0x1800f6d1c  jnz     loc_1800F6FEE
0x1800f6d22  cmp     dword ptr [rbp+7C0h+var_838], r15d
0x1800f6d26  jnz     loc_1800F6FCF
0x1800f6d2c  mov     r14d, 1
0x1800f6d32  jmp     loc_1800F6B2C
0x1800f6d37  mov     rcx, [rsp+8C0h+hkey]; hkey
0x1800f6d3c  lea     rax, [rbp+7C0h+Type+4]
0x1800f6d40  mov     [rsp+8C0h+pvData], rax; pcbData
0x1800f6d45  lea     r9, [rbp+7C0h+Type]; pdwType
0x1800f6d49  lea     rax, [rbp+7C0h+String]
0x1800f6d50  mov     dword ptr [rbp+7C0h+Type+4], 208h
0x1800f6d57  xor     r8d, r8d; pdwReserved
0x1800f6d5a  mov     [rsp+8C0h+phkResult], rax; pvData
0x1800f6d5f  lea     rdx, pszStart; pszValue
0x1800f6d66  call    cs:__imp_SHQueryValueExW
0x1800f6d6c  test    eax, eax
0x1800f6d6e  jnz     short loc_1800F6D7A
0x1800f6d70  cmp     dword ptr [rbp+7C0h+Type], r14d
0x1800f6d74  jz      loc_1800F6AFE
0x1800f6d7a  cmp     [rbp+7C0h+var_680], r15w
0x1800f6d82  lea     r12, [rbp+7C0h+var_680]
0x1800f6d89  lea     rax, [rbp+7C0h+var_470]
0x1800f6d90  cmovz   r12, rax
0x1800f6d94  jmp     loc_1800F6AFE
0x1800f6d99  mov     ecx, 0Dh
0x1800f6d9e  cmp     [rbp+7C0h+pdwType], r13d
0x1800f6da2  jnz     loc_1800F6E6C
0x1800f6da8  cmp     dword ptr [rbp+7C0h+var_838], r14d
0x1800f6dac  ja      loc_1800F6A03
0x1800f6db2  mov     ecx, r15d
0x1800f6db5  setz    bl
0x1800f6db8  jmp     loc_1800F6A0C
0x1800f6dbd  mov     [rsp+8C0h+var_850], rcx
0x1800f6dc2  jmp     loc_1800F6CF1
0x1800f6dc7  cmp     dword ptr [rbp+7C0h+Type], 1
0x1800f6dcb  jnz     loc_1800F6CDC
0x1800f6dd1  lea     r8, [rsp+8C0h+var_864]; unsigned int *
0x1800f6dd6  lea     rdx, [rsp+8C0h+var_868]; unsigned int *
0x1800f6ddb  lea     rcx, [rbp+7C0h+var_7C8]; unsigned __int16 *
0x1800f6ddf  call    ?GetVersionFromString@@YAJPEBGPEAK1@Z; GetVersionFromString(ushort const *,ulong *,ulong *)
0x1800f6de4  test    eax, eax
0x1800f6de6  js      loc_1800F6CDC
0x1800f6dec  mov     ebx, [rsp+8C0h+var_868]
0x1800f6df0  mov     r14d, [rsp+8C0h+var_864]
0x1800f6df5  jmp     loc_1800F6CDC
0x1800f6dfa  mov     rcx, [rsp+8C0h+var_850]; hKey
0x1800f6dff  lea     rax, [rbp+7C0h+Type+4]
0x1800f6e03  mov     [rsp+8C0h+pvData], rax; lpcbData
0x1800f6e08  lea     r9, [rbp+7C0h+Type]; lpType
0x1800f6e0c  lea     rax, [rbp+7C0h+var_810]
0x1800f6e10  mov     dword ptr [rbp+7C0h+Type+4], 14h
0x1800f6e17  xor     r8d, r8d; lpReserved
0x1800f6e1a  mov     [rsp+8C0h+phkResult], rax; lpData
0x1800f6e1f  lea     rdx, aLocale; "Locale"
0x1800f6e26  call    cs:__imp_RegQueryValueExW
0x1800f6e2c  xor     ecx, ecx
0x1800f6e2e  test    eax, eax
0x1800f6e30  jnz     loc_1800F6CE8
0x1800f6e36  cmp     dword ptr [rbp+7C0h+Type], 1
  ... truncated ...
```
