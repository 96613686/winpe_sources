# SetAspNetMMCKeys(int)

- ea: `0x18003d288`
- end: `0x18003d856`
- name: `?SetAspNetMMCKeys@@YAJH@Z`
- size: `1486`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c1e8`
- `0x18003c630`
- `0x18003ef38`

## callees

- `0x18003d288`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18003d5ce`
- `KERNEL32!lstrlenW` at `0x18003d607`
- `KERNEL32!lstrlenW` at `0x18003d640`
- `KERNEL32!lstrlenW` at `0x18003d6bc`
- `KERNEL32!lstrlenW` at `0x18003d77b`
- `KERNEL32!lstrlenW` at `0x18003d5ce`
- `KERNEL32!lstrlenW` at `0x18003d607`
- `KERNEL32!lstrlenW` at `0x18003d640`
- `KERNEL32!lstrlenW` at `0x18003d6bc`
- `KERNEL32!lstrlenW` at `0x18003d77b`
- `ADVAPI32!RegCloseKey` at `0x18003d7c2`
- `ADVAPI32!RegCloseKey` at `0x18003d7d2`
- `ADVAPI32!RegCloseKey` at `0x18003d7e2`
- `ADVAPI32!RegCloseKey` at `0x18003d7f2`
- `ADVAPI32!RegCloseKey` at `0x18003d802`
- `ADVAPI32!RegCloseKey` at `0x18003d812`
- `ADVAPI32!RegCloseKey` at `0x18003d821`
- `ADVAPI32!RegCloseKey` at `0x18003d7c2`
- `ADVAPI32!RegCloseKey` at `0x18003d7d2`
- `ADVAPI32!RegCloseKey` at `0x18003d7e2`
- `ADVAPI32!RegCloseKey` at `0x18003d7f2`
- `ADVAPI32!RegCloseKey` at `0x18003d802`
- `ADVAPI32!RegCloseKey` at `0x18003d812`
- `ADVAPI32!RegCloseKey` at `0x18003d821`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d3c4`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d42b`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d48e`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d4ef`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d557`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d3c4`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d42b`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d48e`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d4ef`
- `ADVAPI32!RegCreateKeyExW` at `0x18003d557`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d30b`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d357`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d38f`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d3f3`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d45b`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d4ba`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d522`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d30b`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d357`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d38f`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d3f3`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d45b`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d4ba`
- `ADVAPI32!RegOpenKeyExW` at `0x18003d522`
- `ADVAPI32!RegSetValueExW` at `0x18003d5f5`
- `ADVAPI32!RegSetValueExW` at `0x18003d62e`
- `ADVAPI32!RegSetValueExW` at `0x18003d666`
- `ADVAPI32!RegSetValueExW` at `0x18003d6e3`
- `ADVAPI32!RegSetValueExW` at `0x18003d719`
- `ADVAPI32!RegSetValueExW` at `0x18003d7a7`
- `ADVAPI32!RegSetValueExW` at `0x18003d5f5`
- `ADVAPI32!RegSetValueExW` at `0x18003d62e`
- `ADVAPI32!RegSetValueExW` at `0x18003d666`
- `ADVAPI32!RegSetValueExW` at `0x18003d6e3`
- `ADVAPI32!RegSetValueExW` at `0x18003d719`
- `ADVAPI32!RegSetValueExW` at `0x18003d7a7`
- `ADVAPI32!RegDeleteKeyW` at `0x18003d32f`
- `ADVAPI32!RegDeleteKeyW` at `0x18003d32f`

## string_xrefs

- `0x18003d342`: `CLSID`
- `0x18003d702`: `DllSurrogate`

## pseudocode

```c
__int64 __fastcall SetAspNetMMCKeys(int a1)
{
  unsigned int LastWin32Error; // ebx
  LSTATUS v3; // eax
  __int64 v4; // rdi
  __int64 v5; // rdx
  WCHAR *v6; // rcx
  WCHAR v7; // ax
  WCHAR *v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  WCHAR v14; // ax
  WCHAR *v15; // rax
  int v16; // eax
  WCHAR *v17; // rcx
  WCHAR v18; // ax
  WCHAR *v19; // rax
  int v20; // eax
  HKEY v22; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v24; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v25; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY v27; // [rsp+78h] [rbp-88h] BYREF
  HKEY v28[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR String[104]; // [rsp+90h] [rbp-70h] BYREF

  phkResult = 0;
  v25 = 0;
  v27 = 0;
  hKey = 0;
  v22 = 0;
  v28[0] = 0;
  v24 = 0;
  LastWin32Error = 0;
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AppID", 0, 0x2001Fu, &hKey) )
  {
    hKey = 0;
LABEL_49:
    LastWin32Error = GetLastWin32Error();
    goto LABEL_50;
  }
  if ( !a1 )
  {
    v3 = RegDeleteKeyW(hKey, L"{F75B6772-91E4-4D2F-9D44-61A447109C2B}");
    goto LABEL_48;
  }
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2001Fu, &phkResult) )
  {
    phkResult = 0;
    goto LABEL_49;
  }
  if ( RegOpenKeyExW(phkResult, L"{5437FDFA-9EC9-4CCC-8531-42F8D9C19AF7}", 0, 0x20006u, &v22)
    && RegCreateKeyExW(phkResult, L"{5437FDFA-9EC9-4CCC-8531-42F8D9C19AF7}", 0, 0, 0, 0x20006u, 0, &v22, 0) )
  {
    v22 = 0;
    goto LABEL_49;
  }
  if ( RegOpenKeyExW(v22, L"ProgId", 0, 0x20006u, v28) && RegCreateKeyExW(v22, L"ProgId", 0, 0, 0, 0x20006u, 0, v28, 0) )
  {
    v28[0] = 0;
    goto LABEL_49;
  }
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Microsoft.Aspnet.Snapin.AspNetManagementUtility.4", 0, 0x20006u, &v25)
    && RegCreateKeyExW(
         HKEY_CLASSES_ROOT,
         L"Microsoft.Aspnet.Snapin.AspNetManagementUtility.4",
         0,
         0,
         0,
         0x20006u,
         0,
         &v25,
         0) )
  {
    v25 = 0;
    goto LABEL_49;
  }
  if ( RegOpenKeyExW(v25, L"CLSID", 0, 0x20006u, &v27) && RegCreateKeyExW(v25, L"CLSID", 0, 0, 0, 0x20006u, 0, &v27, 0) )
  {
    v27 = 0;
    goto LABEL_49;
  }
  if ( RegOpenKeyExW(hKey, L"{F75B6772-91E4-4D2F-9D44-61A447109C2B}", 0, 0x20006u, &v24)
    && RegCreateKeyExW(hKey, L"{F75B6772-91E4-4D2F-9D44-61A447109C2B}", 0, 0, 0, 0x20006u, 0, &v24, 0) )
  {
    v24 = 0;
    goto LABEL_49;
  }
  v4 = 100;
  v5 = 100;
  v6 = String;
  do
  {
    if ( v5 == -2147483546 )
      break;
    v7 = *(WCHAR *)((char *)v6 + (char *)L"Microsoft.Aspnet.Snapin.AspNetManagementUtility.4" - (char *)String);
    if ( !v7 )
      break;
    *v6++ = v7;
    --v5;
  }
  while ( v5 );
  v8 = v6 - 1;
  if ( v5 )
    v8 = v6;
  *v8 = 0;
  LastWin32Error = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
  {
    v9 = lstrlenW(String);
    if ( RegSetValueExW(v24, 0, 0, 1u, (const BYTE *)String, 2 * v9 + 2) )
      goto LABEL_49;
    v10 = lstrlenW(String);
    if ( RegSetValueExW(v22, 0, 0, 1u, (const BYTE *)String, 2 * v10 + 2) )
      goto LABEL_49;
    v11 = lstrlenW(String);
    if ( RegSetValueExW(v28[0], 0, 0, 1u, (const BYTE *)String, 2 * v11 + 2) )
      goto LABEL_49;
    String[0] = 0;
    v12 = String;
    v13 = 100;
    do
    {
      if ( v13 == -2147483546 )
        break;
      v14 = *(WCHAR *)((char *)v12 + (char *)L"{5437FDFA-9EC9-4CCC-8531-42F8D9C19AF7}" - (char *)String);
      if ( !v14 )
        break;
      *v12++ = v14;
      --v13;
    }
    while ( v13 );
    v15 = v12 - 1;
    if ( v13 )
      v15 = v12;
    *v15 = 0;
    v16 = lstrlenW(String);
    if ( RegSetValueExW(v27, 0, 0, 1u, (const BYTE *)String, 2 * v16 + 2) )
      goto LABEL_49;
    String[0] = 0;
    if ( RegSetValueExW(v24, L"DllSurrogate", 0, 1u, (const BYTE *)String, 2u) )
      goto LABEL_49;
    v17 = String;
    do
    {
      if ( v4 == -2147483546 )
        break;
      v18 = *(WCHAR *)((char *)v17 + (char *)L"{F75B6772-91E4-4D2F-9D44-61A447109C2B}" - (char *)String);
      if ( !v18 )
        break;
      *v17++ = v18;
      --v4;
    }
    while ( v4 );
    v19 = v17 - 1;
    if ( v4 )
      v19 = v17;
    *v19 = 0;
    LastWin32Error = v4 == 0 ? 0x8007007A : 0;
    if ( v4 )
    {
      v20 = lstrlenW(String);
      v3 = RegSetValueExW(v22, L"AppId", 0, 1u, (const BYTE *)String, 2 * v20 + 2);
LABEL_48:
      if ( !v3 )
        goto LABEL_50;
      goto LABEL_49;
    }
  }
LABEL_50:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v22 )
    RegCloseKey(v22);
  if ( v24 )
    RegCloseKey(v24);
  if ( v25 )
    RegCloseKey(v25);
  if ( v27 )
    RegCloseKey(v27);
  if ( v28[0] )
    RegCloseKey(v28[0]);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003d288  mov     rax, rsp
0x18003d28b  mov     [rax+8], rbx
0x18003d28f  mov     [rax+10h], rsi
0x18003d293  mov     [rax+18h], rdi
0x18003d297  mov     [rax+20h], r12
0x18003d29b  push    rbp
0x18003d29c  push    r14
0x18003d29e  push    r15
0x18003d2a0  lea     rbp, [rsp-70h]
0x18003d2a5  sub     rsp, 170h
0x18003d2ac  mov     rax, cs:__security_cookie
0x18003d2b3  xor     rax, rsp
0x18003d2b6  mov     [rbp+80h+var_20], rax
0x18003d2ba  xor     r15d, r15d
0x18003d2bd  lea     rax, [rsp+180h+hKey]
0x18003d2c2  mov     edi, ecx
0x18003d2c4  mov     [rsp+180h+var_110], r15
0x18003d2c9  mov     r14d, 2001Fh
0x18003d2cf  mov     [rsp+180h+var_118], r15
0x18003d2d4  mov     rsi, 0FFFFFFFF80000000h
0x18003d2db  mov     [rsp+180h+var_108], r15
0x18003d2e0  mov     r9d, r14d; samDesired
0x18003d2e3  mov     [rsp+180h+hKey], r15
0x18003d2e8  mov     rcx, rsi; hKey
0x18003d2eb  mov     [rsp+180h+var_130], r15
0x18003d2f0  xor     r8d, r8d; ulOptions
0x18003d2f3  mov     [rbp+80h+var_100], r15
0x18003d2f7  lea     rdx, aAppid_0; "AppID"
0x18003d2fe  mov     [rsp+180h+var_120], r15
0x18003d303  mov     ebx, r15d
0x18003d306  mov     [rsp+180h+phkResult], rax; phkResult
0x18003d30b  call    cs:__imp_RegOpenKeyExW
0x18003d311  test    eax, eax
0x18003d313  jz      short loc_18003D31F
0x18003d315  mov     [rsp+180h+hKey], r15
0x18003d31a  jmp     loc_18003D7B1
0x18003d31f  test    edi, edi
0x18003d321  jnz     short loc_18003D33A
0x18003d323  mov     rcx, [rsp+180h+hKey]; hKey
0x18003d328  lea     rdx, aF75b677291e44d; "{F75B6772-91E4-4D2F-9D44-61A447109C2B}"
0x18003d32f  call    cs:__imp_RegDeleteKeyW
0x18003d335  jmp     loc_18003D7AD
0x18003d33a  lea     rax, [rsp+180h+var_110]
0x18003d33f  mov     r9d, r14d; samDesired
0x18003d342  lea     r12, aClsid; "CLSID"
0x18003d349  mov     [rsp+180h+phkResult], rax; phkResult
0x18003d34e  mov     rdx, r12; lpSubKey
0x18003d351  xor     r8d, r8d; ulOptions
0x18003d354  mov     rcx, rsi; hKey
0x18003d357  call    cs:__imp_RegOpenKeyExW
0x18003d35d  test    eax, eax
0x18003d35f  jz      short loc_18003D36B
0x18003d361  mov     [rsp+180h+var_110], r15
0x18003d366  jmp     loc_18003D7B1
0x18003d36b  mov     rcx, [rsp+180h+var_110]; hKey
0x18003d370  lea     rax, [rsp+180h+var_130]
0x18003d375  mov     edi, 20006h
0x18003d37a  mov     [rsp+180h+phkResult], rax; phkResult
0x18003d37f  lea     r14, a5437fdfa9ec94c; "{5437FDFA-9EC9-4CCC-8531-42F8D9C19AF7}"
0x18003d386  mov     r9d, edi; samDesired
0x18003d389  mov     rdx, r14; lpSubKey
0x18003d38c  xor     r8d, r8d; ulOptions
0x18003d38f  call    cs:__imp_RegOpenKeyExW
0x18003d395  test    eax, eax
0x18003d397  jz      short loc_18003D3D8
0x18003d399  mov     rcx, [rsp+180h+var_110]; hKey
0x18003d39e  lea     rax, [rsp+180h+var_130]
0x18003d3a3  mov     [rsp+180h+lpdwDisposition], r15; lpdwDisposition
0x18003d3a8  xor     r9d, r9d; lpClass
0x18003d3ab  mov     [rsp+180h+var_148], rax; phkResult
0x18003d3b0  xor     r8d, r8d; Reserved
0x18003d3b3  mov     [rsp+180h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003d3b8  mov     rdx, r14; lpSubKey
0x18003d3bb  mov     [rsp+180h+samDesired], edi; samDesired
0x18003d3bf  mov     dword ptr [rsp+180h+phkResult], r15d; dwOptions
0x18003d3c4  call    cs:__imp_RegCreateKeyExW
0x18003d3ca  test    eax, eax
0x18003d3cc  jz      short loc_18003D3D8
0x18003d3ce  mov     [rsp+180h+var_130], r15
0x18003d3d3  jmp     loc_18003D7B1
0x18003d3d8  mov     rcx, [rsp+180h+var_130]; hKey
0x18003d3dd  lea     rax, [rbp+80h+var_100]
0x18003d3e1  mov     r9d, edi; samDesired
0x18003d3e4  mov     [rsp+180h+phkResult], rax; phkResult
0x18003d3e9  xor     r8d, r8d; ulOptions
0x18003d3ec  lea     rdx, aProgid; "ProgId"
0x18003d3f3  call    cs:__imp_RegOpenKeyExW
0x18003d3f9  test    eax, eax
0x18003d3fb  jz      short loc_18003D43E
0x18003d3fd  mov     rcx, [rsp+180h+var_130]; hKey
0x18003d402  lea     rax, [rbp+80h+var_100]
0x18003d406  mov     [rsp+180h+lpdwDisposition], r15; lpdwDisposition
0x18003d40b  lea     rdx, aProgid; "ProgId"
0x18003d412  mov     [rsp+180h+var_148], rax; phkResult
0x18003d417  xor     r9d, r9d; lpClass
0x18003d41a  mov     [rsp+180h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003d41f  xor     r8d, r8d; Reserved
0x18003d422  mov     [rsp+180h+samDesired], edi; samDesired
0x18003d426  mov     dword ptr [rsp+180h+phkResult], r15d; dwOptions
0x18003d42b  call    cs:__imp_RegCreateKeyExW
0x18003d431  test    eax, eax
0x18003d433  jz      short loc_18003D43E
0x18003d435  mov     [rbp+80h+var_100], r15
0x18003d439  jmp     loc_18003D7B1
0x18003d43e  lea     rax, [rsp+180h+var_118]
0x18003d443  mov     r9d, edi; samDesired
0x18003d446  lea     rbx, szProgID; "Microsoft.Aspnet.Snapin.AspNetManagemen"...
0x18003d44d  mov     [rsp+180h+phkResult], rax; phkResult
0x18003d452  mov     rdx, rbx; lpSubKey
0x18003d455  xor     r8d, r8d; ulOptions
0x18003d458  mov     rcx, rsi; hKey
0x18003d45b  call    cs:__imp_RegOpenKeyExW
0x18003d461  test    eax, eax
0x18003d463  jz      short loc_18003D4A2
0x18003d465  mov     [rsp+180h+lpdwDisposition], r15; lpdwDisposition
0x18003d46a  lea     rax, [rsp+180h+var_118]
0x18003d46f  mov     [rsp+180h+var_148], rax; phkResult
0x18003d474  xor     r9d, r9d; lpClass
0x18003d477  mov     [rsp+180h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003d47c  xor     r8d, r8d; Reserved
0x18003d47f  mov     [rsp+180h+samDesired], edi; samDesired
0x18003d483  mov     rdx, rbx; lpSubKey
0x18003d486  mov     rcx, rsi; hKey
0x18003d489  mov     dword ptr [rsp+180h+phkResult], r15d; dwOptions
0x18003d48e  call    cs:__imp_RegCreateKeyExW
0x18003d494  test    eax, eax
0x18003d496  jz      short loc_18003D4A2
0x18003d498  mov     [rsp+180h+var_118], r15
0x18003d49d  jmp     loc_18003D7B1
0x18003d4a2  mov     rcx, [rsp+180h+var_118]; hKey
0x18003d4a7  lea     rax, [rsp+180h+var_108]
0x18003d4ac  mov     r9d, edi; samDesired
0x18003d4af  mov     [rsp+180h+phkResult], rax; phkResult
0x18003d4b4  xor     r8d, r8d; ulOptions
0x18003d4b7  mov     rdx, r12; lpSubKey
0x18003d4ba  call    cs:__imp_RegOpenKeyExW
0x18003d4c0  test    eax, eax
0x18003d4c2  jz      short loc_18003D503
0x18003d4c4  mov     rcx, [rsp+180h+var_118]; hKey
0x18003d4c9  lea     rax, [rsp+180h+var_108]
0x18003d4ce  mov     [rsp+180h+lpdwDisposition], r15; lpdwDisposition
0x18003d4d3  xor     r9d, r9d; lpClass
0x18003d4d6  mov     [rsp+180h+var_148], rax; phkResult
0x18003d4db  xor     r8d, r8d; Reserved
0x18003d4de  mov     [rsp+180h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003d4e3  mov     rdx, r12; lpSubKey
0x18003d4e6  mov     [rsp+180h+samDesired], edi; samDesired
0x18003d4ea  mov     dword ptr [rsp+180h+phkResult], r15d; dwOptions
0x18003d4ef  call    cs:__imp_RegCreateKeyExW
0x18003d4f5  test    eax, eax
0x18003d4f7  jz      short loc_18003D503
0x18003d4f9  mov     [rsp+180h+var_108], r15
0x18003d4fe  jmp     loc_18003D7B1
0x18003d503  mov     rcx, [rsp+180h+hKey]; hKey
0x18003d508  lea     rax, [rsp+180h+var_120]
0x18003d50d  lea     rsi, aF75b677291e44d; "{F75B6772-91E4-4D2F-9D44-61A447109C2B}"
0x18003d514  mov     [rsp+180h+phkResult], rax; phkResult
0x18003d519  mov     rdx, rsi; lpSubKey
0x18003d51c  mov     r9d, edi; samDesired
0x18003d51f  xor     r8d, r8d; ulOptions
0x18003d522  call    cs:__imp_RegOpenKeyExW
0x18003d528  test    eax, eax
0x18003d52a  jz      short loc_18003D56B
0x18003d52c  mov     rcx, [rsp+180h+hKey]; hKey
0x18003d531  lea     rax, [rsp+180h+var_120]
0x18003d536  mov     [rsp+180h+lpdwDisposition], r15; lpdwDisposition
0x18003d53b  xor     r9d, r9d; lpClass
0x18003d53e  mov     [rsp+180h+var_148], rax; phkResult
0x18003d543  xor     r8d, r8d; Reserved
0x18003d546  mov     [rsp+180h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003d54b  mov     rdx, rsi; lpSubKey
0x18003d54e  mov     [rsp+180h+samDesired], edi; samDesired
0x18003d552  mov     dword ptr [rsp+180h+phkResult], r15d; dwOptions
0x18003d557  call    cs:__imp_RegCreateKeyExW
0x18003d55d  test    eax, eax
0x18003d55f  jz      short loc_18003D56B
0x18003d561  mov     [rsp+180h+var_120], r15
0x18003d566  jmp     loc_18003D7B1
0x18003d56b  mov     edi, 64h ; 'd'
0x18003d570  lea     rax, [rbp+80h+String]
0x18003d574  mov     edx, edi
0x18003d576  lea     rcx, [rbp+80h+String]
0x18003d57a  sub     rbx, rax
0x18003d57d  lea     r12d, [rdi-63h]
0x18003d581  lea     rax, [rdx+7FFFFF9Ah]
0x18003d588  test    rax, rax
0x18003d58b  jz      short loc_18003D5A2
0x18003d58d  movzx   eax, word ptr [rbx+rcx]
0x18003d591  test    ax, ax
0x18003d594  jz      short loc_18003D5A2
0x18003d596  mov     [rcx], ax
0x18003d599  add     rcx, 2
0x18003d59d  sub     rdx, r12
0x18003d5a0  jnz     short loc_18003D581
0x18003d5a2  test    rdx, rdx
0x18003d5a5  lea     rax, [rcx-2]
0x18003d5a9  cmovnz  rax, rcx
0x18003d5ad  mov     [rax], r15w
0x18003d5b1  mov     rax, rdx
0x18003d5b4  neg     rax
0x18003d5b7  sbb     ebx, ebx
0x18003d5b9  not     ebx
0x18003d5bb  and     ebx, 8007007Ah
0x18003d5c1  test    rdx, rdx
0x18003d5c4  jz      loc_18003D7B8
0x18003d5ca  lea     rcx, [rbp+80h+String]; lpString
0x18003d5ce  call    cs:__imp_lstrlenW
0x18003d5d4  mov     rcx, [rsp+180h+var_120]; hKey
0x18003d5d9  mov     r9d, r12d; dwType
0x18003d5dc  xor     r8d, r8d; Reserved
0x18003d5df  xor     edx, edx; lpValueName
0x18003d5e1  lea     eax, ds:2[rax*2]
0x18003d5e8  mov     [rsp+180h+samDesired], eax; cbData
0x18003d5ec  lea     rax, [rbp+80h+String]
0x18003d5f0  mov     [rsp+180h+phkResult], rax; lpData
0x18003d5f5  call    cs:__imp_RegSetValueExW
0x18003d5fb  test    eax, eax
0x18003d5fd  jnz     loc_18003D7B1
0x18003d603  lea     rcx, [rbp+80h+String]; lpString
0x18003d607  call    cs:__imp_lstrlenW
0x18003d60d  mov     rcx, [rsp+180h+var_130]; hKey
0x18003d612  mov     r9d, r12d; dwType
0x18003d615  xor     r8d, r8d; Reserved
0x18003d618  xor     edx, edx; lpValueName
0x18003d61a  lea     eax, ds:2[rax*2]
0x18003d621  mov     [rsp+180h+samDesired], eax; cbData
0x18003d625  lea     rax, [rbp+80h+String]
0x18003d629  mov     [rsp+180h+phkResult], rax; lpData
0x18003d62e  call    cs:__imp_RegSetValueExW
0x18003d634  test    eax, eax
0x18003d636  jnz     loc_18003D7B1
0x18003d63c  lea     rcx, [rbp+80h+String]; lpString
0x18003d640  call    cs:__imp_lstrlenW
0x18003d646  mov     rcx, [rbp+80h+var_100]; hKey
0x18003d64a  mov     r9d, r12d; dwType
0x18003d64d  xor     r8d, r8d; Reserved
0x18003d650  xor     edx, edx; lpValueName
0x18003d652  lea     eax, ds:2[rax*2]
0x18003d659  mov     [rsp+180h+samDesired], eax; cbData
0x18003d65d  lea     rax, [rbp+80h+String]
0x18003d661  mov     [rsp+180h+phkResult], rax; lpData
0x18003d666  call    cs:__imp_RegSetValueExW
0x18003d66c  test    eax, eax
0x18003d66e  jnz     loc_18003D7B1
0x18003d674  lea     rax, [rbp+80h+String]
0x18003d678  mov     [rbp+80h+String], r15w
0x18003d67d  sub     r14, rax
0x18003d680  lea     rcx, [rbp+80h+String]
0x18003d684  mov     rdx, rdi
0x18003d687  lea     rax, [rdx+7FFFFF9Ah]
0x18003d68e  test    rax, rax
0x18003d691  jz      short loc_18003D6A9
0x18003d693  movzx   eax, word ptr [r14+rcx]
0x18003d698  test    ax, ax
0x18003d69b  jz      short loc_18003D6A9
0x18003d69d  mov     [rcx], ax
0x18003d6a0  add     rcx, 2
0x18003d6a4  sub     rdx, r12
0x18003d6a7  jnz     short loc_18003D687
0x18003d6a9  lea     rax, [rcx-2]
0x18003d6ad  test    rdx, rdx
0x18003d6b0  cmovnz  rax, rcx
0x18003d6b4  lea     rcx, [rbp+80h+String]; lpString
0x18003d6b8  mov     [rax], r15w
0x18003d6bc  call    cs:__imp_lstrlenW
0x18003d6c2  mov     rcx, [rsp+180h+var_108]; hKey
0x18003d6c7  mov     r9d, r12d; dwType
0x18003d6ca  xor     r8d, r8d; Reserved
0x18003d6cd  xor     edx, edx; lpValueName
0x18003d6cf  lea     eax, ds:2[rax*2]
0x18003d6d6  mov     [rsp+180h+samDesired], eax; cbData
0x18003d6da  lea     rax, [rbp+80h+String]
0x18003d6de  mov     [rsp+180h+phkResult], rax; lpData
0x18003d6e3  call    cs:__imp_RegSetValueExW
0x18003d6e9  test    eax, eax
0x18003d6eb  jnz     loc_18003D7B1
0x18003d6f1  mov     rcx, [rsp+180h+var_120]; hKey
0x18003d6f6  lea     rax, [rbp+80h+String]
0x18003d6fa  mov     [rsp+180h+samDesired], 2; cbData
0x18003d702  lea     rdx, aDllsurrogate; "DllSurrogate"
0x18003d709  mov     r9d, r12d; dwType
0x18003d70c  mov     [rsp+180h+phkResult], rax; lpData
0x18003d711  xor     r8d, r8d; Reserved
0x18003d714  mov     [rbp+80h+String], r15w
0x18003d719  call    cs:__imp_RegSetValueExW
0x18003d71f  test    eax, eax
0x18003d721  jnz     loc_18003D7B1
0x18003d727  lea     rax, [rbp+80h+String]
0x18003d72b  sub     rsi, rax
0x18003d72e  lea     rcx, [rbp+80h+String]
0x18003d732  lea     rax, [rdi+7FFFFF9Ah]
0x18003d739  test    rax, rax
0x18003d73c  jz      short loc_18003D753
0x18003d73e  movzx   eax, word ptr [rsi+rcx]
0x18003d742  test    ax, ax
0x18003d745  jz      short loc_18003D753
0x18003d747  mov     [rcx], ax
0x18003d74a  add     rcx, 2
0x18003d74e  sub     rdi, r12
0x18003d751  jnz     short loc_18003D732
  ... truncated ...
```
