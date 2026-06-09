# TraceRegCreateDefaultsW

- ea: `0x180008260`
- end: `0x180008626`
- name: `TraceRegCreateDefaultsW`
- size: `966`
- prototype: `int __fastcall(LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007e34`

## callees

- `0x180003bb0`
- `0x180004456`
- `0x180004ab8`
- `0x180008260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000830e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000838e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000830e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000838e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008485`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800084b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800084ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008525`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000855a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008592`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800085fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008485`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800084b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800084ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008525`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000855a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008592`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800085fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800083ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800083ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000845d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000845d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008348`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008400`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008438`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008348`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008400`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008438`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800085c9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800085c9`

## string_xrefs

- `0x180008341`: `FileDirectory`
- `0x1800085d2`: `FileDirectory`

## pseudocode

```c
int __fastcall TraceRegCreateDefaultsW(LPCWSTR lpSubKey, PHKEY phkResult)
{
  int result; // eax
  HKEY v5; // rcx
  LSTATUS v6; // esi
  HKEY v7; // rcx
  HKEY v8; // rcx
  HKEY v9; // rcx
  HKEY v10; // rcx
  const wchar_t *v11; // r8
  int v12; // eax
  HKEY v13; // rcx
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v15[4]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v17[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v19[4]; // [rsp+64h] [rbp-9Ch] BYREF
  BYTE v20[8]; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest[264]; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[528]; // [rsp+290h] [rbp+190h] BYREF

  cbData = 0;
  *(_DWORD *)v15 = 0;
  *(_DWORD *)v17 = 0;
  dwDisposition = 0;
  memset_0(Data, 0, 0x208u);
  hKey = 0;
  Type = 0;
  *(_DWORD *)v20 = 0;
  *(_DWORD *)v19 = 0;
  *phkResult = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Tracing",
             0,
             0,
             0,
             0x2001Fu,
             0,
             phkResult,
             &dwDisposition);
  if ( !result )
  {
    v5 = *phkResult;
    cbData = 520;
    v6 = RegQueryValueExW(v5, L"FileDirectory", 0, &Type, Data, &cbData);
    if ( *phkResult )
    {
      RegCloseKey(*phkResult);
      *phkResult = 0;
    }
    result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Bu, 0, phkResult, &dwDisposition);
    if ( !result )
    {
      *(_DWORD *)v15 = 0;
      cbData = 4;
      *(_DWORD *)v17 = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Tracing", 0, 0x20119u, &hKey) )
      {
        if ( !RegQueryValueExW(hKey, L"EnableFileTracing", 0, &Type, v20, &cbData) && Type == 4 )
        {
          if ( !RegQueryValueExW(hKey, L"EnableAutoFileTracing", 0, &Type, v19, &cbData) && Type == 4 )
            *(_DWORD *)v17 = *(_DWORD *)v19;
          *(_DWORD *)v15 = *(_DWORD *)v20;
        }
        RegCloseKey(hKey);
      }
      result = RegSetValueExW(*phkResult, L"EnableFileTracing", 0, 4u, v15, cbData);
      if ( !result )
      {
        result = RegSetValueExW(*phkResult, L"EnableAutoFileTracing", 0, 4u, v17, cbData);
        if ( !result )
        {
          v7 = *phkResult;
          *(_DWORD *)v15 = 0;
          result = RegSetValueExW(v7, L"EnableConsoleTracing", 0, 4u, v15, cbData);
          if ( !result )
          {
            v8 = *phkResult;
            *(_DWORD *)v15 = -65536;
            result = RegSetValueExW(v8, L"FileTracingMask", 0, 4u, v15, cbData);
            if ( !result )
            {
              v9 = *phkResult;
              *(_DWORD *)v15 = -65536;
              result = RegSetValueExW(v9, L"ConsoleTracingMask", 0, 4u, v15, cbData);
              if ( !result )
              {
                v10 = *phkResult;
                *(_DWORD *)v15 = 0x100000;
                result = RegSetValueExW(v10, L"MaxFileSize", 0, 4u, v15, cbData);
                if ( !result )
                {
                  v11 = (const wchar_t *)Data;
                  if ( v6 )
                    v11 = L"%windir%\\tracing";
                  result = StringCchCopyW(pszDest, 0x104u, v11);
                  if ( result >= 0 )
                  {
                    v12 = lstrlenW(pszDest);
                    v13 = *phkResult;
                    cbData = 2 * v12 + 2;
                    return RegSetValueExW(v13, L"FileDirectory", 0, 2u, (const BYTE *)pszDest, cbData);
                  }
                  else
                  {
                    return (unsigned __int16)result;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008260  mov     [rsp-8+arg_10], rbx
0x180008265  push    rbp
0x180008266  push    rsi
0x180008267  push    rdi
0x180008268  push    r14
0x18000826a  push    r15
0x18000826c  lea     rbp, [rsp-3B0h]
0x180008274  sub     rsp, 4B0h
0x18000827b  mov     rax, cs:__security_cookie
0x180008282  xor     rax, rsp
0x180008285  mov     [rbp+3D0h+var_30], rax
0x18000828c  xor     r14d, r14d
0x18000828f  mov     rbx, rdx
0x180008292  mov     rdi, rcx
0x180008295  mov     [rsp+4D0h+cbData], r14d
0x18000829a  mov     esi, 208h
0x18000829f  mov     dword ptr [rsp+4D0h+var_47C], r14d
0x1800082a4  mov     r8d, esi; Size
0x1800082a7  mov     dword ptr [rsp+4D0h+var_474], r14d
0x1800082ac  xor     edx, edx; Val
0x1800082ae  mov     [rsp+4D0h+dwDisposition], r14d
0x1800082b3  lea     rcx, [rbp+3D0h+Data]; void *
0x1800082ba  call    memset_0
0x1800082bf  lea     rax, [rsp+4D0h+dwDisposition]
0x1800082c4  mov     [rsp+4D0h+hKey], r14
0x1800082c9  mov     [rsp+4D0h+lpdwDisposition], rax; lpdwDisposition
0x1800082ce  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Tracing"
0x1800082d5  mov     [rsp+4D0h+phkResult], rbx; phkResult
0x1800082da  mov     r15, 0FFFFFFFF80000002h
0x1800082e1  mov     [rsp+4D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800082e6  xor     r9d, r9d; lpClass
0x1800082e9  mov     [rsp+4D0h+samDesired], 2001Fh; samDesired
0x1800082f1  xor     r8d, r8d; Reserved
0x1800082f4  mov     rcx, r15; hKey
0x1800082f7  mov     [rsp+4D0h+dwOptions], r14d; dwOptions
0x1800082fc  mov     [rsp+4D0h+Type], r14d
0x180008301  mov     dword ptr [rsp+4D0h+var_468], r14d
0x180008306  mov     dword ptr [rsp+4D0h+var_46C], r14d
0x18000830b  mov     [rbx], r14
0x18000830e  call    cs:__imp_RegCreateKeyExW
0x180008314  test    eax, eax
0x180008316  jnz     loc_180008600
0x18000831c  mov     rcx, [rbx]; hKey
0x18000831f  lea     rax, [rsp+4D0h+cbData]
0x180008324  mov     qword ptr [rsp+4D0h+samDesired], rax; lpcbData
0x180008329  lea     r9, [rsp+4D0h+Type]; lpType
0x18000832e  lea     rax, [rbp+3D0h+Data]
0x180008335  mov     [rsp+4D0h+cbData], esi
0x180008339  xor     r8d, r8d; lpReserved
0x18000833c  mov     qword ptr [rsp+4D0h+dwOptions], rax; lpData
0x180008341  lea     rdx, aFiledirectory; "FileDirectory"
0x180008348  call    cs:__imp_RegQueryValueExW
0x18000834e  mov     rcx, [rbx]; hKey
0x180008351  mov     esi, eax
0x180008353  test    rcx, rcx
0x180008356  jz      short loc_180008361
0x180008358  call    cs:__imp_RegCloseKey
0x18000835e  mov     [rbx], r14
0x180008361  lea     rax, [rsp+4D0h+dwDisposition]
0x180008366  xor     r9d, r9d; lpClass
0x180008369  mov     [rsp+4D0h+lpdwDisposition], rax; lpdwDisposition
0x18000836e  xor     r8d, r8d; Reserved
0x180008371  mov     [rsp+4D0h+phkResult], rbx; phkResult
0x180008376  mov     rdx, rdi; lpSubKey
0x180008379  mov     [rsp+4D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000837e  mov     rcx, r15; hKey
0x180008381  mov     [rsp+4D0h+samDesired], 2001Bh; samDesired
0x180008389  mov     [rsp+4D0h+dwOptions], r14d; dwOptions
0x18000838e  call    cs:__imp_RegCreateKeyExW
0x180008394  test    eax, eax
0x180008396  jnz     loc_180008600
0x18000839c  lea     edi, [rax+4]
0x18000839f  mov     dword ptr [rsp+4D0h+var_47C], r14d
0x1800083a4  lea     rax, [rsp+4D0h+hKey]
0x1800083a9  mov     [rsp+4D0h+cbData], edi
0x1800083ad  mov     r9d, 20119h; samDesired
0x1800083b3  mov     qword ptr [rsp+4D0h+dwOptions], rax; phkResult
0x1800083b8  xor     r8d, r8d; ulOptions
0x1800083bb  mov     dword ptr [rsp+4D0h+var_474], r14d
0x1800083c0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Tracing"
0x1800083c7  mov     rcx, r15; hKey
0x1800083ca  call    cs:__imp_RegOpenKeyExW
0x1800083d0  test    eax, eax
0x1800083d2  jnz     loc_180008463
0x1800083d8  mov     rcx, [rsp+4D0h+hKey]; hKey
0x1800083dd  lea     rax, [rsp+4D0h+cbData]
0x1800083e2  mov     qword ptr [rsp+4D0h+samDesired], rax; lpcbData
0x1800083e7  lea     r9, [rsp+4D0h+Type]; lpType
0x1800083ec  lea     rax, [rsp+4D0h+var_468]
0x1800083f1  xor     r8d, r8d; lpReserved
0x1800083f4  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800083fb  mov     qword ptr [rsp+4D0h+dwOptions], rax; lpData
0x180008400  call    cs:__imp_RegQueryValueExW
0x180008406  test    eax, eax
0x180008408  jnz     short loc_180008458
0x18000840a  cmp     [rsp+4D0h+Type], edi
0x18000840e  jnz     short loc_180008458
0x180008410  mov     rcx, [rsp+4D0h+hKey]; hKey
0x180008415  lea     rax, [rsp+4D0h+cbData]
0x18000841a  mov     qword ptr [rsp+4D0h+samDesired], rax; lpcbData
0x18000841f  lea     r9, [rsp+4D0h+Type]; lpType
0x180008424  lea     rax, [rsp+4D0h+var_46C]
0x180008429  xor     r8d, r8d; lpReserved
0x18000842c  lea     rdx, aEnableautofile_0; "EnableAutoFileTracing"
0x180008433  mov     qword ptr [rsp+4D0h+dwOptions], rax; lpData
0x180008438  call    cs:__imp_RegQueryValueExW
0x18000843e  test    eax, eax
0x180008440  jnz     short loc_180008450
0x180008442  cmp     [rsp+4D0h+Type], edi
0x180008446  jnz     short loc_180008450
0x180008448  mov     eax, dword ptr [rsp+4D0h+var_46C]
0x18000844c  mov     dword ptr [rsp+4D0h+var_474], eax
0x180008450  mov     eax, dword ptr [rsp+4D0h+var_468]
0x180008454  mov     dword ptr [rsp+4D0h+var_47C], eax
0x180008458  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18000845d  call    cs:__imp_RegCloseKey
0x180008463  mov     eax, [rsp+4D0h+cbData]
0x180008467  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x18000846e  mov     rcx, [rbx]; hKey
0x180008471  mov     r9d, edi; dwType
0x180008474  mov     [rsp+4D0h+samDesired], eax; cbData
0x180008478  xor     r8d, r8d; Reserved
0x18000847b  lea     rax, [rsp+4D0h+var_47C]
0x180008480  mov     qword ptr [rsp+4D0h+dwOptions], rax; lpData
0x180008485  call    cs:__imp_RegSetValueExW
0x18000848b  test    eax, eax
0x18000848d  jnz     loc_180008600
0x180008493  mov     eax, [rsp+4D0h+cbData]
0x180008497  lea     rdx, aEnableautofile_0; "EnableAutoFileTracing"
0x18000849e  mov     rcx, [rbx]; hKey
0x1800084a1  mov     r9d, edi; dwType
0x1800084a4  mov     [rsp+4D0h+samDesired], eax; cbData
0x1800084a8  xor     r8d, r8d; Reserved
0x1800084ab  lea     rax, [rsp+4D0h+var_474]
0x1800084b0  mov     qword ptr [rsp+4D0h+dwOptions], rax; lpData
0x1800084b5  call    cs:__imp_RegSetValueExW
0x1800084bb  test    eax, eax
0x1800084bd  jnz     loc_180008600
0x1800084c3  mov     eax, [rsp+4D0h+cbData]
0x1800084c7  lea     rdx, aEnableconsolet; "EnableConsoleTracing"
0x1800084ce  mov     rcx, [rbx]; hKey
0x1800084d1  mov     r9d, edi; dwType
0x1800084d4  mov     [rsp+4D0h+samDesired], eax; cbData
0x1800084d8  xor     r8d, r8d; Reserved
0x1800084db  lea     rax, [rsp+4D0h+var_47C]
0x1800084e0  mov     dword ptr [rsp+4D0h+var_47C], r14d
0x1800084e5  mov     qword ptr [rsp+4D0h+dwOptions], rax; lpData
0x1800084ea  call    cs:__imp_RegSetValueExW
0x1800084f0  test    eax, eax
0x1800084f2  jnz     loc_180008600
0x1800084f8  mov     eax, [rsp+4D0h+cbData]
0x1800084fc  lea     rdx, aFiletracingmas; "FileTracingMask"
0x180008503  mov     rcx, [rbx]; hKey
0x180008506  mov     r15d, 0FFFF0000h
0x18000850c  mov     [rsp+4D0h+samDesired], eax; cbData
0x180008510  mov     r9d, edi; dwType
0x180008513  lea     rax, [rsp+4D0h+var_47C]
0x180008518  mov     dword ptr [rsp+4D0h+var_47C], r15d
0x18000851d  xor     r8d, r8d; Reserved
0x180008520  mov     qword ptr [rsp+4D0h+dwOptions], rax; lpData
0x180008525  call    cs:__imp_RegSetValueExW
0x18000852b  test    eax, eax
0x18000852d  jnz     loc_180008600
0x180008533  mov     eax, [rsp+4D0h+cbData]
0x180008537  lea     rdx, aConsoletracing_0; "ConsoleTracingMask"
0x18000853e  mov     rcx, [rbx]; hKey
0x180008541  mov     r9d, edi; dwType
0x180008544  mov     [rsp+4D0h+samDesired], eax; cbData
0x180008548  xor     r8d, r8d; Reserved
0x18000854b  lea     rax, [rsp+4D0h+var_47C]
0x180008550  mov     dword ptr [rsp+4D0h+var_47C], r15d
0x180008555  mov     qword ptr [rsp+4D0h+dwOptions], rax; lpData
0x18000855a  call    cs:__imp_RegSetValueExW
0x180008560  test    eax, eax
0x180008562  jnz     loc_180008600
0x180008568  mov     eax, [rsp+4D0h+cbData]
0x18000856c  lea     rdx, aMaxfilesize_0; "MaxFileSize"
0x180008573  mov     rcx, [rbx]; hKey
0x180008576  mov     r9d, edi; dwType
0x180008579  mov     [rsp+4D0h+samDesired], eax; cbData
0x18000857d  xor     r8d, r8d; Reserved
0x180008580  lea     rax, [rsp+4D0h+var_47C]
0x180008585  mov     dword ptr [rsp+4D0h+var_47C], 100000h
0x18000858d  mov     qword ptr [rsp+4D0h+dwOptions], rax; lpData
0x180008592  call    cs:__imp_RegSetValueExW
0x180008598  test    eax, eax
0x18000859a  jnz     short loc_180008600
0x18000859c  lea     rcx, [rbp+3D0h+pszDest]; pszDest
0x1800085a0  mov     edx, 104h; cchDest
0x1800085a5  lea     r8, [rbp+3D0h+Data]
0x1800085ac  test    esi, esi
0x1800085ae  jz      short loc_1800085B7
0x1800085b0  lea     r8, aWindirTracing; "%windir%\\tracing"
0x1800085b7  call    StringCchCopyW
0x1800085bc  test    eax, eax
0x1800085be  jns     short loc_1800085C5
0x1800085c0  movzx   eax, ax
0x1800085c3  jmp     short loc_180008600
0x1800085c5  lea     rcx, [rbp+3D0h+pszDest]; lpString
0x1800085c9  call    cs:__imp_lstrlenW
0x1800085cf  mov     rcx, [rbx]; hKey
0x1800085d2  lea     rdx, aFiledirectory; "FileDirectory"
0x1800085d9  mov     r9d, 2; dwType
0x1800085df  xor     r8d, r8d; Reserved
0x1800085e2  lea     eax, ds:2[rax*2]
0x1800085e9  mov     [rsp+4D0h+samDesired], eax; cbData
0x1800085ed  mov     [rsp+4D0h+cbData], eax
0x1800085f1  lea     rax, [rbp+3D0h+pszDest]
0x1800085f5  mov     qword ptr [rsp+4D0h+dwOptions], rax; lpData
0x1800085fa  call    cs:__imp_RegSetValueExW
0x180008600  mov     rcx, [rbp+3D0h+var_30]
0x180008607  xor     rcx, rsp; StackCookie
0x18000860a  call    __security_check_cookie
0x18000860f  mov     rbx, [rsp+4D0h+arg_10]
0x180008617  add     rsp, 4B0h
0x18000861e  pop     r15
0x180008620  pop     r14
0x180008622  pop     rdi
0x180008623  pop     rsi
0x180008624  pop     rbp
0x180008625  retn
```
