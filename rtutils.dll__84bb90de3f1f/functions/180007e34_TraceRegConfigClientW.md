# TraceRegConfigClientW

- ea: `0x180007e34`
- end: `0x180008259`
- name: `TraceRegConfigClientW`
- size: `1061`
- prototype: `LSTATUS __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005450`

## callees

- `0x180003bb0`
- `0x180003bf0`
- `0x180004a2c`
- `0x180004ab8`
- `0x180006c24`
- `0x180007e34`
- `0x180008260`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800081f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800081f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000820d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000820d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800081c7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800081c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d1`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180008237`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180008237`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007f04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007f04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007f2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007f2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007f7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007fda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008030`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000808a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800080e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000813e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007f7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007fda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008030`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000808a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800080e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000813e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800081dc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800081dc`

## string_xrefs

- `0x18000810f`: `FileDirectory`

## pseudocode

```c
LSTATUS __fastcall TraceRegConfigClientW(__int64 a1)
{
  LSTATUS result; // eax
  int v3; // edi
  HKEY v4; // rcx
  int v5; // ecx
  int v6; // eax
  unsigned int v7; // eax
  HKEY v8; // rcx
  int v9; // eax
  HKEY v10; // rcx
  int v11; // ecx
  int v12; // eax
  unsigned int v13; // eax
  int v14; // eax
  HKEY v15; // rcx
  int v16; // eax
  HKEY v17; // rcx
  unsigned __int64 v18; // rcx
  size_t v19; // rdx
  HRESULT v20; // eax
  int v21; // edx
  int v22; // eax
  HANDLE EventW; // rax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  size_t pcchLength; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v30; // [rsp+258h] [rbp+158h]
  wchar_t pszDest[264]; // [rsp+260h] [rbp+160h] BYREF

  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  pcchLength = 0;
  result = StringCchCopyW(pszDest, 0x104u, L"Software\\Microsoft\\Tracing");
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatW(pszDest, 0x104u, L"\\");
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatW(pszDest, 0x104u, (STRSAFE_LPCWSTR)(a1 + 128));
  if ( result < 0 )
    return (unsigned __int16)result;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &hKey) )
  {
    v3 = TraceRegCreateDefaultsW(pszDest, &hKey);
    if ( v3 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      *(_QWORD *)(a1 + 1072) = 0;
      return v3;
    }
  }
  v4 = hKey;
  *(_QWORD *)(a1 + 1072) = hKey;
  cbData = 4;
  if ( RegQueryValueExW(v4, L"EnableFileTracing", 0, &Type, Data, &cbData) || Type != 4 )
  {
    v5 = 0;
    *(_DWORD *)Data = 0;
  }
  else
  {
    v5 = *(_DWORD *)Data;
  }
  v6 = *(_DWORD *)(a1 + 56);
  if ( v5 == 1 )
    v7 = v6 | 2;
  else
    v7 = v6 & 0xFFFFFFFD;
  v8 = hKey;
  *(_DWORD *)(a1 + 56) = v7;
  cbData = 4;
  if ( RegQueryValueExW(v8, L"FileTracingMask", 0, &Type, Data, &cbData) || Type != 4 )
  {
    v9 = -65536;
    *(_DWORD *)Data = -65536;
  }
  else
  {
    v9 = *(_DWORD *)Data;
  }
  v10 = hKey;
  cbData = 4;
  *(_DWORD *)(a1 + 272) = v9 & 0xFFFF0000;
  if ( RegQueryValueExW(v10, L"EnableConsoleTracing", 0, &Type, Data, &cbData) || Type != 4 )
  {
    v11 = 0;
    *(_DWORD *)Data = 0;
  }
  else
  {
    v11 = *(_DWORD *)Data;
  }
  v12 = *(_DWORD *)(a1 + 56);
  if ( v11 == 1 )
    v13 = v12 | 4;
  else
    v13 = v12 & 0xFFFFFFFB;
  *(_DWORD *)(a1 + 56) = v13;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"ConsoleTracingMask", 0, &Type, Data, &cbData) || Type != 4 )
  {
    v14 = -65536;
    *(_DWORD *)Data = -65536;
  }
  else
  {
    v14 = *(_DWORD *)Data;
  }
  v15 = hKey;
  cbData = 4;
  *(_DWORD *)(a1 + 276) = v14 & 0xFFFF0000;
  if ( RegQueryValueExW(v15, L"MaxFileSize", 0, &Type, Data, &cbData) || Type != 4 )
  {
    v16 = 0x100000;
    *(_DWORD *)Data = 0x100000;
  }
  else
  {
    v16 = *(_DWORD *)Data;
  }
  v17 = hKey;
  *(_DWORD *)(a1 + 280) = v16;
  cbData = 520;
  v30 = 0;
  if ( RegQueryValueExW(v17, L"FileDirectory", 0, &Type, v29, &cbData) || Type - 1 > 1 )
  {
    result = StringCchCopyW((STRSAFE_LPWSTR)v29, 0x104u, L"%windir%\\tracing");
    if ( result >= 0 )
    {
      v20 = StringLengthWorkerW((STRSAFE_PCNZWCH)v29, v19, &pcchLength);
      v21 = pcchLength;
      if ( v20 < 0 )
        v21 = 0;
      cbData = 2 * (v21 + 1);
      goto LABEL_45;
    }
    return (unsigned __int16)result;
  }
  v18 = cbData & 0xFFFFFFFE;
  if ( v18 >= 0x20A )
    _report_rangecheckfailure();
  *(_WORD *)&v29[v18] = 0;
LABEL_45:
  if ( ExpandEnvironmentStringsW((LPCWSTR)v29, (LPWSTR)(a1 + 546), 0x104u)
    && ((v22 = lstrlenW((LPCWSTR)(a1 + 546)),
         _o_wcstombs(a1 + 284, a1 + 546, v22 + 1),
         (EventW = *(HANDLE *)(a1 + 1080)) != 0)
     || (EventW = CreateEventW(0, 0, 0, 0), (*(_QWORD *)(a1 + 1080) = EventW) != 0)) )
  {
    return RegNotifyChangeKeyValue(*(HKEY *)(a1 + 1072), 0, 0xEu, EventW, 1);
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x180007e34  push    rbp
0x180007e36  push    rbx
0x180007e37  push    rdi
0x180007e38  push    r14
0x180007e3a  lea     rbp, [rsp-388h]
0x180007e42  sub     rsp, 488h
0x180007e49  mov     rax, cs:__security_cookie
0x180007e50  xor     rax, rsp
0x180007e53  mov     [rbp+3A0h+var_30], rax
0x180007e5a  mov     rbx, rcx
0x180007e5d  mov     [rsp+4A0h+hKey], 0
0x180007e66  mov     r14d, 104h
0x180007e6c  mov     [rsp+4A0h+Type], 0
0x180007e74  mov     edx, r14d; cchDest
0x180007e77  mov     dword ptr [rsp+4A0h+Data], 0
0x180007e7f  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Tracing"
0x180007e86  mov     [rsp+4A0h+cbData], 0
0x180007e8e  lea     rcx, [rbp+3A0h+pszDest]; pszDest
0x180007e95  mov     [rsp+4A0h+pcchLength], 0
0x180007e9e  call    StringCchCopyW
0x180007ea3  test    eax, eax
0x180007ea5  jns     short loc_180007EAF
0x180007ea7  movzx   eax, ax
0x180007eaa  jmp     loc_18000823D
0x180007eaf  lea     r8, asc_18000C888; "\\"
0x180007eb6  mov     rdx, r14; cchDest
0x180007eb9  lea     rcx, [rbp+3A0h+pszDest]; pszDest
0x180007ec0  call    StringCchCatW
0x180007ec5  test    eax, eax
0x180007ec7  js      short loc_180007EA7
0x180007ec9  lea     r8, [rbx+80h]; pszSrc
0x180007ed0  mov     rdx, r14; cchDest
0x180007ed3  lea     rcx, [rbp+3A0h+pszDest]; pszDest
0x180007eda  call    StringCchCatW
0x180007edf  test    eax, eax
0x180007ee1  js      short loc_180007EA7
0x180007ee3  lea     rax, [rsp+4A0h+hKey]
0x180007ee8  mov     r9d, 20019h; samDesired
0x180007eee  xor     r8d, r8d; ulOptions
0x180007ef1  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180007ef6  lea     rdx, [rbp+3A0h+pszDest]; lpSubKey
0x180007efd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007f04  call    cs:__imp_RegOpenKeyExW
0x180007f0a  test    eax, eax
0x180007f0c  jz      short loc_180007F47
0x180007f0e  lea     rdx, [rsp+4A0h+hKey]; phkResult
0x180007f13  lea     rcx, [rbp+3A0h+pszDest]; lpSubKey
0x180007f1a  call    TraceRegCreateDefaultsW
0x180007f1f  mov     edi, eax
0x180007f21  test    eax, eax
0x180007f23  jz      short loc_180007F47
0x180007f25  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180007f2a  test    rcx, rcx
0x180007f2d  jz      short loc_180007F35
0x180007f2f  call    cs:__imp_RegCloseKey
0x180007f35  mov     qword ptr [rbx+430h], 0
0x180007f40  mov     eax, edi
0x180007f42  jmp     loc_18000823D
0x180007f47  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180007f4c  lea     rax, [rsp+4A0h+cbData]
0x180007f51  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180007f56  lea     r9, [rsp+4A0h+Type]; lpType
0x180007f5b  lea     rax, [rsp+4A0h+Data]
0x180007f60  mov     [rbx+430h], rcx
0x180007f67  mov     edi, 4
0x180007f6c  mov     [rsp+4A0h+phkResult], rax; lpData
0x180007f71  xor     r8d, r8d; lpReserved
0x180007f74  mov     [rsp+4A0h+cbData], edi
0x180007f78  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x180007f7f  call    cs:__imp_RegQueryValueExW
0x180007f85  test    eax, eax
0x180007f87  jnz     short loc_180007F95
0x180007f89  cmp     [rsp+4A0h+Type], edi
0x180007f8d  jnz     short loc_180007F95
0x180007f8f  mov     ecx, dword ptr [rsp+4A0h+Data]
0x180007f93  jmp     short loc_180007F9B
0x180007f95  xor     ecx, ecx
0x180007f97  mov     dword ptr [rsp+4A0h+Data], ecx
0x180007f9b  mov     eax, [rbx+38h]
0x180007f9e  cmp     ecx, 1
0x180007fa1  jnz     short loc_180007FA8
0x180007fa3  or      eax, 2
0x180007fa6  jmp     short loc_180007FAB
0x180007fa8  and     eax, 0FFFFFFFDh
0x180007fab  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180007fb0  lea     r9, [rsp+4A0h+Type]; lpType
0x180007fb5  mov     [rbx+38h], eax
0x180007fb8  lea     rdx, aFiletracingmas; "FileTracingMask"
0x180007fbf  lea     rax, [rsp+4A0h+cbData]
0x180007fc4  mov     [rsp+4A0h+cbData], edi
0x180007fc8  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180007fcd  xor     r8d, r8d; lpReserved
0x180007fd0  lea     rax, [rsp+4A0h+Data]
0x180007fd5  mov     [rsp+4A0h+phkResult], rax; lpData
0x180007fda  call    cs:__imp_RegQueryValueExW
0x180007fe0  test    eax, eax
0x180007fe2  jnz     short loc_180007FF0
0x180007fe4  cmp     [rsp+4A0h+Type], edi
0x180007fe8  jnz     short loc_180007FF0
0x180007fea  mov     eax, dword ptr [rsp+4A0h+Data]
0x180007fee  jmp     short loc_180007FF9
0x180007ff0  mov     eax, 0FFFF0000h
0x180007ff5  mov     dword ptr [rsp+4A0h+Data], eax
0x180007ff9  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180007ffe  lea     r9, [rsp+4A0h+Type]; lpType
0x180008003  and     eax, 0FFFF0000h
0x180008008  mov     [rsp+4A0h+cbData], edi
0x18000800c  mov     [rbx+110h], eax
0x180008012  lea     rdx, aEnableconsolet; "EnableConsoleTracing"
0x180008019  lea     rax, [rsp+4A0h+cbData]
0x18000801e  xor     r8d, r8d; lpReserved
0x180008021  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180008026  lea     rax, [rsp+4A0h+Data]
0x18000802b  mov     [rsp+4A0h+phkResult], rax; lpData
0x180008030  call    cs:__imp_RegQueryValueExW
0x180008036  test    eax, eax
0x180008038  jnz     short loc_180008046
0x18000803a  cmp     [rsp+4A0h+Type], edi
0x18000803e  jnz     short loc_180008046
0x180008040  mov     ecx, dword ptr [rsp+4A0h+Data]
0x180008044  jmp     short loc_18000804C
0x180008046  xor     ecx, ecx
0x180008048  mov     dword ptr [rsp+4A0h+Data], ecx
0x18000804c  mov     eax, [rbx+38h]
0x18000804f  cmp     ecx, 1
0x180008052  jnz     short loc_180008058
0x180008054  or      eax, edi
0x180008056  jmp     short loc_18000805B
0x180008058  and     eax, 0FFFFFFFBh
0x18000805b  mov     [rbx+38h], eax
0x18000805e  lea     r9, [rsp+4A0h+Type]; lpType
0x180008063  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180008068  lea     rax, [rsp+4A0h+cbData]
0x18000806d  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180008072  lea     rdx, aConsoletracing_0; "ConsoleTracingMask"
0x180008079  lea     rax, [rsp+4A0h+Data]
0x18000807e  mov     [rsp+4A0h+cbData], edi
0x180008082  xor     r8d, r8d; lpReserved
0x180008085  mov     [rsp+4A0h+phkResult], rax; lpData
0x18000808a  call    cs:__imp_RegQueryValueExW
0x180008090  test    eax, eax
0x180008092  jnz     short loc_1800080A0
0x180008094  cmp     [rsp+4A0h+Type], edi
0x180008098  jnz     short loc_1800080A0
0x18000809a  mov     eax, dword ptr [rsp+4A0h+Data]
0x18000809e  jmp     short loc_1800080A9
0x1800080a0  mov     eax, 0FFFF0000h
0x1800080a5  mov     dword ptr [rsp+4A0h+Data], eax
0x1800080a9  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800080ae  lea     r9, [rsp+4A0h+Type]; lpType
0x1800080b3  and     eax, 0FFFF0000h
0x1800080b8  mov     [rsp+4A0h+cbData], edi
0x1800080bc  mov     [rbx+114h], eax
0x1800080c2  lea     rdx, aMaxfilesize_0; "MaxFileSize"
0x1800080c9  lea     rax, [rsp+4A0h+cbData]
0x1800080ce  xor     r8d, r8d; lpReserved
0x1800080d1  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x1800080d6  lea     rax, [rsp+4A0h+Data]
0x1800080db  mov     [rsp+4A0h+phkResult], rax; lpData
0x1800080e0  call    cs:__imp_RegQueryValueExW
0x1800080e6  test    eax, eax
0x1800080e8  jnz     short loc_1800080F6
0x1800080ea  cmp     [rsp+4A0h+Type], edi
0x1800080ee  jnz     short loc_1800080F6
0x1800080f0  mov     eax, dword ptr [rsp+4A0h+Data]
0x1800080f4  jmp     short loc_1800080FF
0x1800080f6  mov     eax, 100000h
0x1800080fb  mov     dword ptr [rsp+4A0h+Data], eax
0x1800080ff  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180008104  lea     r9, [rsp+4A0h+Type]; lpType
0x180008109  mov     [rbx+118h], eax
0x18000810f  lea     rdx, aFiledirectory; "FileDirectory"
0x180008116  xor     eax, eax
0x180008118  mov     [rsp+4A0h+cbData], 208h
0x180008120  mov     [rbp+3A0h+var_248], ax
0x180008127  xor     r8d, r8d; lpReserved
0x18000812a  lea     rax, [rsp+4A0h+cbData]
0x18000812f  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180008134  lea     rax, [rsp+4A0h+var_450]
0x180008139  mov     [rsp+4A0h+phkResult], rax; lpData
0x18000813e  call    cs:__imp_RegQueryValueExW
0x180008144  test    eax, eax
0x180008146  jnz     short loc_180008173
0x180008148  mov     eax, [rsp+4A0h+Type]
0x18000814c  dec     eax
0x18000814e  cmp     eax, 1
0x180008151  ja      short loc_180008173
0x180008153  mov     ecx, [rsp+4A0h+cbData]
0x180008157  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000815b  cmp     rcx, 20Ah
0x180008162  jnb     short loc_18000816D
0x180008164  xor     eax, eax
0x180008166  mov     word ptr [rsp+rcx+4A0h+var_450], ax
0x18000816b  jmp     short loc_1800081B5
0x18000816d  call    __report_rangecheckfailure
0x180008173  lea     r8, aWindirTracing; "%windir%\\tracing"
0x18000817a  mov     rdx, r14; cchDest
0x18000817d  lea     rcx, [rsp+4A0h+var_450]; pszDest
0x180008182  call    StringCchCopyW
0x180008187  test    eax, eax
0x180008189  js      loc_180007EA7
0x18000818f  lea     r8, [rsp+4A0h+pcchLength]; pcchLength
0x180008194  lea     rcx, [rsp+4A0h+var_450]; psz
0x180008199  call    StringLengthWorkerW
0x18000819e  mov     rdx, [rsp+4A0h+pcchLength]
0x1800081a3  xor     ecx, ecx
0x1800081a5  test    eax, eax
0x1800081a7  cmovs   rdx, rcx
0x1800081ab  inc     rdx
0x1800081ae  lea     eax, [rdx+rdx]
0x1800081b1  mov     [rsp+4A0h+cbData], eax
0x1800081b5  lea     rdi, [rbx+222h]
0x1800081bc  mov     r8d, r14d; nSize
0x1800081bf  mov     rdx, rdi; lpDst
0x1800081c2  lea     rcx, [rsp+4A0h+var_450]; lpSrc
0x1800081c7  call    cs:__imp_ExpandEnvironmentStringsW
0x1800081cd  test    eax, eax
0x1800081cf  jnz     short loc_1800081D9
0x1800081d1  call    cs:__imp_GetLastError
0x1800081d7  jmp     short loc_18000823D
0x1800081d9  mov     rcx, rdi; lpString
0x1800081dc  call    cs:__imp_lstrlenW
0x1800081e2  lea     rcx, [rbx+11Ch]
0x1800081e9  mov     rdx, rdi
0x1800081ec  inc     eax
0x1800081ee  movsxd  r8, eax
0x1800081f1  call    cs:__imp__o_wcstombs
0x1800081f7  mov     rax, [rbx+438h]
0x1800081fe  test    rax, rax
0x180008201  jnz     short loc_18000821F
0x180008203  xor     r9d, r9d; lpName
0x180008206  xor     r8d, r8d; bInitialState
0x180008209  xor     edx, edx; bManualReset
0x18000820b  xor     ecx, ecx; lpEventAttributes
0x18000820d  call    cs:__imp_CreateEventW
0x180008213  mov     [rbx+438h], rax
0x18000821a  test    rax, rax
0x18000821d  jz      short loc_1800081D1
0x18000821f  mov     rcx, [rbx+430h]; hKey
0x180008226  xor     edx, edx; bWatchSubtree
0x180008228  mov     r9, rax; hEvent
0x18000822b  mov     dword ptr [rsp+4A0h+phkResult], 1; fAsynchronous
0x180008233  lea     r8d, [rdx+0Eh]; dwNotifyFilter
0x180008237  call    cs:__imp_RegNotifyChangeKeyValue
0x18000823d  mov     rcx, [rbp+3A0h+var_30]
0x180008244  xor     rcx, rsp; StackCookie
0x180008247  call    __security_check_cookie
0x18000824c  add     rsp, 488h
0x180008253  pop     r14
0x180008255  pop     rdi
0x180008256  pop     rbx
0x180008257  pop     rbp
0x180008258  retn
```
