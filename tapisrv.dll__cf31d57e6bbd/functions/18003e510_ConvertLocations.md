# ConvertLocations

- ea: `0x18003e510`
- end: `0x18003e99b`
- name: `ConvertLocations`
- size: `1163`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cb10`

## callees

- `0x180001600`
- `0x18001c740`
- `0x18001c8a4`
- `0x18003e510`
- `0x18003e9a4`
- `0x18003f3c0`
- `0x18003f91c`
- `0x18003f958`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003e8c9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003e8db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003e8c9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003e8db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e5b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e740`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e7d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e952`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e962`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e5b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e740`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e7d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e952`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e962`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e907`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e940`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e907`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e940`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e584`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e6da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e79d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e584`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e6da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e79d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e640`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e723`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e640`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e723`
- `KERNEL32!GlobalAlloc` at `0x18003e670`
- `KERNEL32!GlobalAlloc` at `0x18003e670`
- `KERNEL32!GlobalFree` at `0x18003e970`
- `KERNEL32!GlobalFree` at `0x18003e970`
- `KERNEL32!GetWindowsDirectoryW` at `0x18003e5c7`
- `KERNEL32!GetWindowsDirectoryW` at `0x18003e5c7`

## string_xrefs

- `0x18003e8f2`: `KeyRenameHistory`

## pseudocode

```c
__int64 ConvertLocations()
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  BYTE *v3; // rsi
  int v4; // eax
  _DWORD *v5; // rdi
  int v6; // r14d
  unsigned int v7; // r15d
  LSTATUS v8; // eax
  int v9; // r12d
  unsigned int v10; // eax
  BYTE *v11; // r14
  unsigned int i; // r12d
  int v13; // r13d
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE v17[4]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v20; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v22[4]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v23; // [rsp+58h] [rbp-A8h]
  wchar_t SubKey[24]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[24]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  v20 = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  *(_DWORD *)v17 = 0;
  *(_DWORD *)v22 = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Locations",
         0,
         0x2001Fu,
         &hKey);
  v1 = v0;
  if ( v0 == 2 )
    return 0;
  v3 = 0;
  if ( !v0 )
  {
    if ( !(unsigned int)IsLocationListInOldFormat(hKey) )
    {
      RegCloseKey(hKey);
      return 0;
    }
    if ( GetWindowsDirectoryW(Buffer, 0xF8u) )
    {
      if ( Buffer[3] )
        StringCbCatW(Buffer, 0x20Au, L"\\");
      StringCbCatW(Buffer, 0x20Au, L"REGLOCS.OLD");
      SaveKey(hKey, Buffer);
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"NumEntries", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v4 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v4 = *(_DWORD *)Data;
    }
    if ( v4 )
    {
      v3 = (BYTE *)GlobalAlloc(0x40u, 4LL * (unsigned int)(4 * v4));
      if ( !v3 )
      {
        v1 = 14;
        goto LABEL_39;
      }
      v4 = *(_DWORD *)Data;
    }
    v5 = v3;
    v6 = v4 - 1;
    v7 = 0;
    while ( v6 >= 0 )
    {
      LODWORD(phkResult) = v6;
      StringCbPrintfW(pszDest, 0x2Au, L"%s%d", L"Location", phkResult);
      v8 = RegOpenKeyExW(hKey, pszDest, 0, 0x2001Fu, &v20);
      v1 = v8;
      if ( v8 != 2 )
      {
        if ( v8 )
          goto LABEL_39;
        cbData = 4;
        if ( !RegQueryValueExW(v20, L"ID", 0, &Type, v17, &cbData) )
        {
          ConvertOneLocation(v20);
          RegCloseKey(v20);
          v20 = 0;
          if ( *(_DWORD *)v17 != v6 )
          {
            LODWORD(phkResult) = *(_DWORD *)v17;
            StringCbPrintfW(SubKey, 0x2Au, L"%s%d", L"Location", phkResult);
            v9 = *(_DWORD *)v17;
            if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &v20) )
            {
              v9 |= 0x80000000;
              LODWORD(phkResult) = v9;
              StringCbPrintfW(SubKey, 0x2Au, L"%s%d", L"Location", phkResult);
            }
            if ( v20 )
            {
              RegCloseKey(v20);
              v20 = 0;
            }
            v1 = RegRenameKey(hKey, pszDest, SubKey);
            if ( v1 )
              goto LABEL_39;
            *v5 = v6;
            v5[1] = v9;
            v5 += 2;
            ++v7;
          }
        }
      }
      --v6;
    }
    v10 = v7;
    v11 = v3;
    v23 = v7;
    for ( i = 0; i < v10; ++i )
    {
      v13 = *((_DWORD *)v11 + 1);
      if ( v13 < 0 )
      {
        LODWORD(phkResult) = *((_DWORD *)v11 + 1);
        StringCbPrintfW(pszDest, 0x2Au, L"%s%d", L"Location", phkResult);
        *(_DWORD *)v17 = v13 & 0x7FFFFFFF;
        LODWORD(phkResulta) = v13 & 0x7FFFFFFF;
        StringCbPrintfW(SubKey, 0x2Au, L"%s%d", L"Location", phkResulta);
        v1 = RegRenameKey(hKey, pszDest, SubKey);
        if ( v1 )
          goto LABEL_39;
        *v5 = v13;
        v5[1] = *(_DWORD *)v17;
        v5 += 2;
        v10 = v23;
        ++v7;
      }
      v11 += 8;
    }
    RegDeleteValueW(hKey, L"DisableCallWaiting");
    RegDeleteValueW(hKey, L"NumEntries");
    v1 = RegSetValueExW(hKey, L"KeyRenameHistory", 0, 3u, v3, 8 * v7);
    if ( !v1 )
    {
      *(_DWORD *)v22 = 2;
      v1 = RegSetValueExW(hKey, L"LocationListVersion", 0, 4u, v22, 4u);
    }
  }
LABEL_39:
  if ( v20 )
    RegCloseKey(v20);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
    GlobalFree(v3);
  return v1;
}

```

## disassembly

```asm
0x18003e510  push    rbp
0x18003e512  push    rbx
0x18003e513  push    rsi
0x18003e514  push    rdi
0x18003e515  push    r12
0x18003e517  push    r13
0x18003e519  push    r14
0x18003e51b  push    r15
0x18003e51d  lea     rbp, [rsp-1E8h]
0x18003e525  sub     rsp, 2E8h
0x18003e52c  mov     rax, cs:__security_cookie
0x18003e533  xor     rax, rsp
0x18003e536  mov     [rbp+220h+var_50], rax
0x18003e53d  xor     r13d, r13d
0x18003e540  lea     rax, [rsp+320h+hKey]
0x18003e545  mov     r9d, 2001Fh; samDesired
0x18003e54b  mov     [rsp+320h+hKey], r13
0x18003e550  xor     r8d, r8d; ulOptions
0x18003e553  mov     [rsp+320h+var_2D8], r13
0x18003e558  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003e55f  mov     dword ptr [rsp+320h+Data], r13d
0x18003e564  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e56b  mov     [rsp+320h+cbData], r13d
0x18003e570  mov     [rsp+320h+Type], r13d
0x18003e575  mov     dword ptr [rsp+320h+var_2E8], r13d
0x18003e57a  mov     dword ptr [rsp+320h+var_2CC], r13d
0x18003e57f  mov     [rsp+320h+phkResult], rax; phkResult
0x18003e584  call    cs:__imp_RegOpenKeyExW
0x18003e58a  mov     ebx, eax
0x18003e58c  cmp     eax, 2
0x18003e58f  jnz     short loc_18003E598
0x18003e591  xor     eax, eax
0x18003e593  jmp     loc_18003E978
0x18003e598  mov     rsi, r13
0x18003e59b  test    eax, eax
0x18003e59d  jnz     loc_18003E948
0x18003e5a3  mov     rcx, [rsp+320h+hKey]
0x18003e5a8  call    IsLocationListInOldFormat
0x18003e5ad  test    eax, eax
0x18003e5af  jnz     short loc_18003E5BE
0x18003e5b1  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e5b6  call    cs:__imp_RegCloseKey
0x18003e5bc  jmp     short loc_18003E591
0x18003e5be  mov     edx, 0F8h; uSize
0x18003e5c3  lea     rcx, [rbp+220h+Buffer]; lpBuffer
0x18003e5c7  call    cs:__imp_GetWindowsDirectoryW
0x18003e5cd  test    eax, eax
0x18003e5cf  jz      short loc_18003E610
0x18003e5d1  mov     ebx, 20Ah
0x18003e5d6  cmp     [rbp+220h+var_25A], r13w
0x18003e5db  jz      short loc_18003E5EF
0x18003e5dd  lea     r8, pszSrc; "\\"
0x18003e5e4  mov     edx, ebx; cbDest
0x18003e5e6  lea     rcx, [rbp+220h+Buffer]; pszDest
0x18003e5ea  call    StringCbCatW
0x18003e5ef  lea     r8, aReglocsOld; "REGLOCS.OLD"
0x18003e5f6  mov     rdx, rbx; cbDest
0x18003e5f9  lea     rcx, [rbp+220h+Buffer]; pszDest
0x18003e5fd  call    StringCbCatW
0x18003e602  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e607  lea     rdx, [rbp+220h+Buffer]; lpFile
0x18003e60b  call    SaveKey
0x18003e610  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e615  lea     rax, [rsp+320h+cbData]
0x18003e61a  mov     [rsp+320h+lpcbData], rax; lpcbData
0x18003e61f  lea     r9, [rsp+320h+Type]; lpType
0x18003e624  lea     rax, [rsp+320h+Data]
0x18003e629  mov     [rsp+320h+cbData], 4
0x18003e631  xor     r8d, r8d; lpReserved
0x18003e634  mov     [rsp+320h+phkResult], rax; lpData
0x18003e639  lea     rdx, aNumentries; "NumEntries"
0x18003e640  call    cs:__imp_RegQueryValueExW
0x18003e646  test    eax, eax
0x18003e648  jnz     short loc_18003E657
0x18003e64a  cmp     [rsp+320h+Type], 4
0x18003e64f  jnz     short loc_18003E657
0x18003e651  mov     eax, dword ptr [rsp+320h+Data]
0x18003e655  jmp     short loc_18003E65E
0x18003e657  mov     eax, r13d
0x18003e65a  mov     dword ptr [rsp+320h+Data], eax
0x18003e65e  test    eax, eax
0x18003e660  jz      short loc_18003E68A
0x18003e662  shl     eax, 2
0x18003e665  mov     ecx, 40h ; '@'; uFlags
0x18003e66a  mov     edx, eax
0x18003e66c  shl     rdx, 2; dwBytes
0x18003e670  call    cs:__imp_GlobalAlloc
0x18003e676  mov     rsi, rax
0x18003e679  test    rax, rax
0x18003e67c  jnz     short loc_18003E686
0x18003e67e  lea     ebx, [rax+0Eh]
0x18003e681  jmp     loc_18003E948
0x18003e686  mov     eax, dword ptr [rsp+320h+Data]
0x18003e68a  mov     rdi, rsi
0x18003e68d  lea     r14d, [rax-1]
0x18003e691  mov     r15d, r13d
0x18003e694  test    r14d, r14d
0x18003e697  js      loc_18003E813
0x18003e69d  lea     r9, aLocation; "Location"
0x18003e6a4  mov     dword ptr [rsp+320h+phkResult], r14d
0x18003e6a9  lea     r8, aSD; "%s%d"
0x18003e6b0  mov     edx, 2Ah ; '*'; cbDest
0x18003e6b5  lea     rcx, [rbp+220h+pszDest]; pszDest
0x18003e6b9  call    StringCbPrintfW
0x18003e6be  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e6c3  lea     rax, [rsp+320h+var_2D8]
0x18003e6c8  mov     r9d, 2001Fh; samDesired
0x18003e6ce  mov     [rsp+320h+phkResult], rax; phkResult
0x18003e6d3  xor     r8d, r8d; ulOptions
0x18003e6d6  lea     rdx, [rbp+220h+pszDest]; lpSubKey
0x18003e6da  call    cs:__imp_RegOpenKeyExW
0x18003e6e0  mov     ebx, eax
0x18003e6e2  cmp     eax, 2
0x18003e6e5  jz      loc_18003E80B
0x18003e6eb  test    eax, eax
0x18003e6ed  jnz     loc_18003E948
0x18003e6f3  mov     rcx, [rsp+320h+var_2D8]; hKey
0x18003e6f8  lea     rax, [rsp+320h+cbData]
0x18003e6fd  mov     [rsp+320h+lpcbData], rax; lpcbData
0x18003e702  lea     r9, [rsp+320h+Type]; lpType
0x18003e707  lea     rax, [rsp+320h+var_2E8]
0x18003e70c  mov     [rsp+320h+cbData], 4
0x18003e714  xor     r8d, r8d; lpReserved
0x18003e717  mov     [rsp+320h+phkResult], rax; lpData
0x18003e71c  lea     rdx, aId; "ID"
0x18003e723  call    cs:__imp_RegQueryValueExW
0x18003e729  test    eax, eax
0x18003e72b  jnz     loc_18003E80B
0x18003e731  mov     rcx, [rsp+320h+var_2D8]; hKey
0x18003e736  call    ConvertOneLocation
0x18003e73b  mov     rcx, [rsp+320h+var_2D8]; hKey
0x18003e740  call    cs:__imp_RegCloseKey
0x18003e746  mov     eax, dword ptr [rsp+320h+var_2E8]
0x18003e74a  mov     [rsp+320h+var_2D8], r13
0x18003e74f  cmp     eax, r14d
0x18003e752  jz      loc_18003E80B
0x18003e758  mov     ebx, 2Ah ; '*'
0x18003e75d  mov     dword ptr [rsp+320h+phkResult], eax
0x18003e761  mov     edx, ebx; cbDest
0x18003e763  lea     r9, aLocation; "Location"
0x18003e76a  lea     r8, aSD; "%s%d"
0x18003e771  lea     rcx, [rsp+320h+SubKey]; pszDest
0x18003e776  call    StringCbPrintfW
0x18003e77b  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e780  lea     rax, [rsp+320h+var_2D8]
0x18003e785  mov     r12d, dword ptr [rsp+320h+var_2E8]
0x18003e78a  lea     rdx, [rsp+320h+SubKey]; lpSubKey
0x18003e78f  mov     r9d, 20019h; samDesired
0x18003e795  mov     [rsp+320h+phkResult], rax; phkResult
0x18003e79a  xor     r8d, r8d; ulOptions
0x18003e79d  call    cs:__imp_RegOpenKeyExW
0x18003e7a3  test    eax, eax
0x18003e7a5  jnz     short loc_18003E7CB
0x18003e7a7  bts     r12d, 1Fh
0x18003e7ac  lea     r9, aLocation; "Location"
0x18003e7b3  lea     r8, aSD; "%s%d"
0x18003e7ba  mov     dword ptr [rsp+320h+phkResult], r12d
0x18003e7bf  mov     edx, ebx; cbDest
0x18003e7c1  lea     rcx, [rsp+320h+SubKey]; pszDest
0x18003e7c6  call    StringCbPrintfW
0x18003e7cb  mov     rcx, [rsp+320h+var_2D8]; hKey
0x18003e7d0  test    rcx, rcx
0x18003e7d3  jz      short loc_18003E7E0
0x18003e7d5  call    cs:__imp_RegCloseKey
0x18003e7db  mov     [rsp+320h+var_2D8], r13
0x18003e7e0  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e7e5  lea     r8, [rsp+320h+SubKey]; lpNewKeyName
0x18003e7ea  lea     rdx, [rbp+220h+pszDest]; lpSubKeyName
0x18003e7ee  call    RegRenameKey
0x18003e7f3  mov     ebx, eax
0x18003e7f5  test    eax, eax
0x18003e7f7  jnz     loc_18003E948
0x18003e7fd  mov     [rdi], r14d
0x18003e800  mov     [rdi+4], r12d
0x18003e804  add     rdi, 8
0x18003e808  inc     r15d
0x18003e80b  dec     r14d
0x18003e80e  jmp     loc_18003E694
0x18003e813  mov     eax, r15d
0x18003e816  mov     r14, rsi
0x18003e819  mov     [rsp+320h+var_2C8], eax
0x18003e81d  mov     r12d, r13d
0x18003e820  cmp     r12d, eax
0x18003e823  jnb     loc_18003E8BD
0x18003e829  mov     r13d, [r14+4]
0x18003e82d  test    r13d, r13d
0x18003e830  jns     short loc_18003E8B1
0x18003e832  lea     r9, aLocation; "Location"
0x18003e839  mov     dword ptr [rsp+320h+phkResult], r13d
0x18003e83e  lea     r8, aSD; "%s%d"
0x18003e845  mov     edx, 2Ah ; '*'; cbDest
0x18003e84a  lea     rcx, [rbp+220h+pszDest]; pszDest
0x18003e84e  call    StringCbPrintfW
0x18003e853  mov     eax, r13d
0x18003e856  lea     r9, aLocation; "Location"
0x18003e85d  btr     eax, 1Fh
0x18003e861  lea     r8, aSD; "%s%d"
0x18003e868  mov     edx, 2Ah ; '*'; cbDest
0x18003e86d  mov     dword ptr [rsp+320h+var_2E8], eax
0x18003e871  lea     rcx, [rsp+320h+SubKey]; pszDest
0x18003e876  mov     dword ptr [rsp+320h+phkResult], eax
0x18003e87a  call    StringCbPrintfW
0x18003e87f  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e884  lea     r8, [rsp+320h+SubKey]; lpNewKeyName
0x18003e889  lea     rdx, [rbp+220h+pszDest]; lpSubKeyName
0x18003e88d  call    RegRenameKey
0x18003e892  mov     ebx, eax
0x18003e894  test    eax, eax
0x18003e896  jnz     loc_18003E948
0x18003e89c  mov     [rdi], r13d
0x18003e89f  mov     eax, dword ptr [rsp+320h+var_2E8]
0x18003e8a3  mov     [rdi+4], eax
0x18003e8a6  add     rdi, 8
0x18003e8aa  mov     eax, [rsp+320h+var_2C8]
0x18003e8ae  inc     r15d
0x18003e8b1  add     r14, 8
0x18003e8b5  inc     r12d
0x18003e8b8  jmp     loc_18003E820
0x18003e8bd  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e8c2  lea     rdx, aDisablecallwai; "DisableCallWaiting"
0x18003e8c9  call    cs:__imp_RegDeleteValueW
0x18003e8cf  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e8d4  lea     rdx, aNumentries; "NumEntries"
0x18003e8db  call    cs:__imp_RegDeleteValueW
0x18003e8e1  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e8e6  lea     eax, ds:0[r15*8]
0x18003e8ee  mov     dword ptr [rsp+320h+lpcbData], eax; cbData
0x18003e8f2  lea     rdx, aKeyrenamehisto; "KeyRenameHistory"
0x18003e8f9  mov     r9d, 3; dwType
0x18003e8ff  mov     [rsp+320h+phkResult], rsi; lpData
0x18003e904  xor     r8d, r8d; Reserved
0x18003e907  call    cs:__imp_RegSetValueExW
0x18003e90d  mov     ebx, eax
0x18003e90f  test    eax, eax
0x18003e911  jnz     short loc_18003E948
0x18003e913  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e918  lea     rax, [rsp+320h+var_2CC]
0x18003e91d  mov     dword ptr [rsp+320h+lpcbData], 4; cbData
0x18003e925  lea     r9d, [rbx+4]; dwType
0x18003e929  xor     r8d, r8d; Reserved
0x18003e92c  mov     [rsp+320h+phkResult], rax; lpData
0x18003e931  lea     rdx, aLocationlistve; "LocationListVersion"
0x18003e938  mov     dword ptr [rsp+320h+var_2CC], 2
0x18003e940  call    cs:__imp_RegSetValueExW
0x18003e946  mov     ebx, eax
0x18003e948  mov     rcx, [rsp+320h+var_2D8]; hKey
0x18003e94d  test    rcx, rcx
0x18003e950  jz      short loc_18003E958
0x18003e952  call    cs:__imp_RegCloseKey
0x18003e958  mov     rcx, [rsp+320h+hKey]; hKey
0x18003e95d  test    rcx, rcx
0x18003e960  jz      short loc_18003E968
0x18003e962  call    cs:__imp_RegCloseKey
0x18003e968  test    rsi, rsi
0x18003e96b  jz      short loc_18003E976
0x18003e96d  mov     rcx, rsi; hMem
0x18003e970  call    cs:__imp_GlobalFree
0x18003e976  mov     eax, ebx
0x18003e978  mov     rcx, [rbp+220h+var_50]
0x18003e97f  xor     rcx, rsp; StackCookie
0x18003e982  call    __security_check_cookie
0x18003e987  add     rsp, 2E8h
0x18003e98e  pop     r15
0x18003e990  pop     r14
0x18003e992  pop     r13
0x18003e994  pop     r12
0x18003e996  pop     rdi
0x18003e997  pop     rsi
0x18003e998  pop     rbx
0x18003e999  pop     rbp
0x18003e99a  retn
```
