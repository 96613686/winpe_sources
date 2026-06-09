# PfSvUnattendProcessSubKey

- ea: `0x180084264`
- end: `0x180084637`
- name: `PfSvUnattendProcessSubKey`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180084020`

## callees

- `0x180039f94`
- `0x180084264`
- `0x18009eb8c`
- `0x1800add08`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800845f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084604`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800845f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084604`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800842d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800842d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800845cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800845cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084314`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008436c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800843c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008441c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008446d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084571`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084314`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008436c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800843c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008441c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008446d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084571`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084534`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084534`

## string_xrefs

- `0x180084308`: `CacheSizeMB`
- `0x180084401`: `EnableCompression`

## pseudocode

```c
__int64 __fastcall PfSvUnattendProcessSubKey(HKEY a1, const WCHAR *a2)
{
  unsigned int v2; // ebx
  int v3; // r14d
  unsigned int v4; // esi
  int v5; // ebx
  int v6; // edi
  LSTATUS v7; // eax
  int v8; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v15; // [rsp+68h] [rbp-98h] BYREF
  wchar_t pszDest[264]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pObjectName[264]; // [rsp+280h] [rbp+180h] BYREF

  *(_DWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  v15 = 0;
  v2 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  if ( !v2 )
  {
    cbData = 4;
    v2 = RegQueryValueExW(hKey, L"CacheSizeMB", 0, &Type, Data, &cbData);
    if ( !v2 )
    {
      if ( cbData != 4 || Type != 4 )
        goto LABEL_34;
      v3 = *(_DWORD *)Data;
      cbData = 4;
      v2 = RegQueryValueExW(hKey, L"DiskID", 0, &Type, Data, &cbData);
      if ( v2 )
        goto LABEL_35;
      if ( cbData != 4 || Type != 4 )
        goto LABEL_34;
      v4 = *(_DWORD *)Data;
      cbData = 4;
      v2 = RegQueryValueExW(hKey, L"PartitionID", 0, &Type, Data, &cbData);
      if ( v2 )
        goto LABEL_35;
      if ( cbData == 4 && Type == 4 )
      {
        v5 = *(_DWORD *)Data;
        cbData = 4;
        v6 = 0;
        if ( !RegQueryValueExW(hKey, L"EnableCompression", 0, &Type, Data, &cbData)
          && cbData == 4
          && Type == 4
          && !*(_DWORD *)Data )
        {
          v6 = 2;
        }
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"EnableEncryption", 0, &Type, Data, &cbData)
          && cbData == 4
          && Type == 4
          && !*(_DWORD *)Data )
        {
          v6 |= 4u;
        }
        LODWORD(phkResult) = v5;
        StringCbPrintfW(pszDest, 0x208u, L"\\??\\HardDisk%dPartition%d", v4, phkResult);
        StringCbPrintfW(pObjectName, 0x208u, L"%s\\%s", pszDest, L"EMD.dat");
        v2 = RdbCfCreate(pObjectName, v3, v6);
        if ( !v2 )
        {
          if ( (v6 & 4) != 0 )
          {
            v2 = RegCreateKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"System\\CurrentControlSet\\Control\\Session Manager\\Memory Management\\StoreParameters",
                   0,
                   0,
                   0,
                   0xF003Fu,
                   0,
                   &v15,
                   0);
            if ( v2 )
              goto LABEL_35;
            cbData = 4;
            v7 = RegQueryValueExW(v15, L"EncryptionScope", 0, &Type, Data, &cbData);
            v2 = v7;
            if ( v7 )
            {
              if ( v7 != 2 )
                goto LABEL_35;
LABEL_32:
              *(_DWORD *)Data = 1;
              v2 = RegSetValueExW(v15, L"EncryptionScope", 0, 4u, Data, 4u);
              if ( v2 )
                goto LABEL_35;
              goto LABEL_33;
            }
            if ( cbData == 4 && Type == 4 )
            {
              v8 = *(_DWORD *)Data;
            }
            else
            {
              v8 = 0;
              *(_DWORD *)Data = 0;
            }
            if ( !v8 )
              goto LABEL_32;
          }
LABEL_33:
          RdbDeleteDeviceState(pszDest);
          v2 = 0;
        }
      }
      else
      {
LABEL_34:
        v2 = 11;
      }
    }
  }
LABEL_35:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v15 )
    RegCloseKey(v15);
  return v2;
}

```

## disassembly

```asm
0x180084264  mov     [rsp-8+arg_10], rbx
0x180084269  mov     [rsp-8+arg_18], rsi
0x18008426e  push    rbp
0x18008426f  push    rdi
0x180084270  push    r13
0x180084272  push    r14
0x180084274  push    r15
0x180084276  lea     rbp, [rsp-3A0h]
0x18008427e  sub     rsp, 4A0h
0x180084285  mov     rax, cs:__security_cookie
0x18008428c  xor     rax, rsp
0x18008428f  mov     [rbp+3C0h+var_30], rax
0x180084296  lea     rax, [rsp+4C0h+hKey]
0x18008429b  mov     dword ptr [rsp+4C0h+Data], 0
0x1800842a3  mov     r9d, 20019h; samDesired
0x1800842a9  mov     [rsp+4C0h+phkResult], rax; phkResult
0x1800842ae  xor     r8d, r8d; ulOptions
0x1800842b1  mov     [rsp+4C0h+cbData], 0
0x1800842b9  mov     [rsp+4C0h+Type], 0
0x1800842c1  mov     [rsp+4C0h+hKey], 0
0x1800842ca  mov     [rsp+4C0h+var_458], 0
0x1800842d3  call    cs:__imp_RegOpenKeyExW
0x1800842d9  mov     ebx, eax
0x1800842db  test    eax, eax
0x1800842dd  jnz     loc_1800845EA
0x1800842e3  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800842e8  lea     r15d, [rax+4]
0x1800842ec  lea     rax, [rsp+4C0h+cbData]
0x1800842f1  mov     [rsp+4C0h+cbData], r15d
0x1800842f6  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x1800842fb  lea     r9, [rsp+4C0h+Type]; lpType
0x180084300  lea     rax, [rsp+4C0h+Data]
0x180084305  xor     r8d, r8d; lpReserved
0x180084308  lea     rdx, aCachesizemb; "CacheSizeMB"
0x18008430f  mov     [rsp+4C0h+phkResult], rax; lpData
0x180084314  call    cs:__imp_RegQueryValueExW
0x18008431a  mov     ebx, eax
0x18008431c  test    eax, eax
0x18008431e  jnz     loc_1800845EA
0x180084324  cmp     [rsp+4C0h+cbData], r15d
0x180084329  jnz     loc_1800845E5
0x18008432f  cmp     [rsp+4C0h+Type], r15d
0x180084334  jnz     loc_1800845E5
0x18008433a  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18008433f  lea     rax, [rsp+4C0h+cbData]
0x180084344  mov     r14d, dword ptr [rsp+4C0h+Data]
0x180084349  lea     r9, [rsp+4C0h+Type]; lpType
0x18008434e  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x180084353  lea     rdx, aDiskid; "DiskID"
0x18008435a  lea     rax, [rsp+4C0h+Data]
0x18008435f  mov     [rsp+4C0h+cbData], r15d
0x180084364  xor     r8d, r8d; lpReserved
0x180084367  mov     [rsp+4C0h+phkResult], rax; lpData
0x18008436c  call    cs:__imp_RegQueryValueExW
0x180084372  mov     ebx, eax
0x180084374  test    eax, eax
0x180084376  jnz     loc_1800845EA
0x18008437c  cmp     [rsp+4C0h+cbData], r15d
0x180084381  jnz     loc_1800845E5
0x180084387  cmp     [rsp+4C0h+Type], r15d
0x18008438c  jnz     loc_1800845E5
0x180084392  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180084397  lea     rax, [rsp+4C0h+cbData]
0x18008439c  mov     esi, dword ptr [rsp+4C0h+Data]
0x1800843a0  lea     r9, [rsp+4C0h+Type]; lpType
0x1800843a5  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x1800843aa  lea     rdx, aPartitionid; "PartitionID"
0x1800843b1  lea     rax, [rsp+4C0h+Data]
0x1800843b6  mov     [rsp+4C0h+cbData], r15d
0x1800843bb  xor     r8d, r8d; lpReserved
0x1800843be  mov     [rsp+4C0h+phkResult], rax; lpData
0x1800843c3  call    cs:__imp_RegQueryValueExW
0x1800843c9  mov     ebx, eax
0x1800843cb  test    eax, eax
0x1800843cd  jnz     loc_1800845EA
0x1800843d3  cmp     [rsp+4C0h+cbData], r15d
0x1800843d8  jnz     loc_1800845E5
0x1800843de  cmp     [rsp+4C0h+Type], r15d
0x1800843e3  jnz     loc_1800845E5
0x1800843e9  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800843ee  lea     rax, [rsp+4C0h+cbData]
0x1800843f3  mov     ebx, dword ptr [rsp+4C0h+Data]
0x1800843f7  lea     r9, [rsp+4C0h+Type]; lpType
0x1800843fc  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x180084401  lea     rdx, aEnablecompress; "EnableCompression"
0x180084408  lea     rax, [rsp+4C0h+Data]
0x18008440d  mov     [rsp+4C0h+cbData], r15d
0x180084412  xor     r8d, r8d; lpReserved
0x180084415  mov     [rsp+4C0h+phkResult], rax; lpData
0x18008441a  xor     edi, edi
0x18008441c  call    cs:__imp_RegQueryValueExW
0x180084422  lea     r13d, [r15-2]
0x180084426  test    eax, eax
0x180084428  jnz     short loc_180084440
0x18008442a  cmp     [rsp+4C0h+cbData], r15d
0x18008442f  jnz     short loc_180084440
0x180084431  cmp     [rsp+4C0h+Type], r15d
0x180084436  jnz     short loc_180084440
0x180084438  cmp     dword ptr [rsp+4C0h+Data], edi
0x18008443c  cmovz   edi, r13d
0x180084440  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180084445  lea     rax, [rsp+4C0h+cbData]
0x18008444a  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x18008444f  lea     r9, [rsp+4C0h+Type]; lpType
0x180084454  lea     rax, [rsp+4C0h+Data]
0x180084459  mov     [rsp+4C0h+cbData], r15d
0x18008445e  xor     r8d, r8d; lpReserved
0x180084461  mov     [rsp+4C0h+phkResult], rax; lpData
0x180084466  lea     rdx, aEnableencrypti; "EnableEncryption"
0x18008446d  call    cs:__imp_RegQueryValueExW
0x180084473  test    eax, eax
0x180084475  jnz     short loc_18008448E
0x180084477  cmp     [rsp+4C0h+cbData], r15d
0x18008447c  jnz     short loc_18008448E
0x18008447e  cmp     [rsp+4C0h+Type], r15d
0x180084483  jnz     short loc_18008448E
0x180084485  cmp     dword ptr [rsp+4C0h+Data], eax
0x180084489  jnz     short loc_18008448E
0x18008448b  or      edi, r15d
0x18008448e  mov     dword ptr [rsp+4C0h+phkResult], ebx
0x180084492  lea     r8, aHarddiskDparti; "\\??\\HardDisk%dPartition%d"
0x180084499  mov     ebx, 208h
0x18008449e  lea     rcx, [rsp+4C0h+pszDest]; pszDest
0x1800844a3  mov     edx, ebx; cbDest
0x1800844a5  mov     r9d, esi
0x1800844a8  call    StringCbPrintfW
0x1800844ad  lea     rax, aEmdDat; "EMD.dat"
0x1800844b4  mov     edx, ebx; cbDest
0x1800844b6  lea     r9, [rsp+4C0h+pszDest]
0x1800844bb  mov     [rsp+4C0h+phkResult], rax
0x1800844c0  lea     r8, aSS; "%s\\%s"
0x1800844c7  lea     rcx, [rbp+3C0h+pObjectName]; pszDest
0x1800844ce  call    StringCbPrintfW
0x1800844d3  mov     r8d, edi
0x1800844d6  lea     rcx, [rbp+3C0h+pObjectName]; pObjectName
0x1800844dd  mov     edx, r14d
0x1800844e0  call    RdbCfCreate
0x1800844e5  mov     ebx, eax
0x1800844e7  test    eax, eax
0x1800844e9  jnz     loc_1800845EA
0x1800844ef  test    r15b, dil
0x1800844f2  jz      loc_1800845D7
0x1800844f8  mov     [rsp+4C0h+lpdwDisposition], 0; lpdwDisposition
0x180084501  lea     rax, [rsp+4C0h+var_458]
0x180084506  mov     [rsp+4C0h+var_488], rax; phkResult
0x18008450b  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ses"...
0x180084512  mov     [rsp+4C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008451b  xor     r9d, r9d; lpClass
0x18008451e  mov     dword ptr [rsp+4C0h+lpcbData], 0F003Fh; samDesired
0x180084526  xor     r8d, r8d; Reserved
0x180084529  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084530  mov     dword ptr [rsp+4C0h+phkResult], ebx; dwOptions
0x180084534  call    cs:__imp_RegCreateKeyExW
0x18008453a  mov     ebx, eax
0x18008453c  test    eax, eax
0x18008453e  jnz     loc_1800845EA
0x180084544  mov     rcx, [rsp+4C0h+var_458]; hKey
0x180084549  lea     rax, [rsp+4C0h+cbData]
0x18008454e  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x180084553  lea     r9, [rsp+4C0h+Type]; lpType
0x180084558  lea     rax, [rsp+4C0h+Data]
0x18008455d  mov     [rsp+4C0h+cbData], r15d
0x180084562  xor     r8d, r8d; lpReserved
0x180084565  mov     [rsp+4C0h+phkResult], rax; lpData
0x18008456a  lea     rdx, aEncryptionscop; "EncryptionScope"
0x180084571  call    cs:__imp_RegQueryValueExW
0x180084577  mov     ebx, eax
0x180084579  test    eax, eax
0x18008457b  jz      short loc_180084584
0x18008457d  cmp     eax, r13d
0x180084580  jnz     short loc_1800845EA
0x180084582  jmp     short loc_1800845A2
0x180084584  cmp     [rsp+4C0h+cbData], r15d
0x180084589  jnz     short loc_180084598
0x18008458b  cmp     [rsp+4C0h+Type], r15d
0x180084590  jnz     short loc_180084598
0x180084592  mov     eax, dword ptr [rsp+4C0h+Data]
0x180084596  jmp     short loc_18008459E
0x180084598  xor     eax, eax
0x18008459a  mov     dword ptr [rsp+4C0h+Data], eax
0x18008459e  test    eax, eax
0x1800845a0  jnz     short loc_1800845D7
0x1800845a2  mov     rcx, [rsp+4C0h+var_458]; hKey
0x1800845a7  lea     rax, [rsp+4C0h+Data]
0x1800845ac  mov     dword ptr [rsp+4C0h+lpcbData], r15d; cbData
0x1800845b1  lea     rdx, aEncryptionscop; "EncryptionScope"
0x1800845b8  mov     r9d, r15d; dwType
0x1800845bb  mov     [rsp+4C0h+phkResult], rax; lpData
0x1800845c0  xor     r8d, r8d; Reserved
0x1800845c3  mov     dword ptr [rsp+4C0h+Data], 1
0x1800845cb  call    cs:__imp_RegSetValueExW
0x1800845d1  mov     ebx, eax
0x1800845d3  test    eax, eax
0x1800845d5  jnz     short loc_1800845EA
0x1800845d7  lea     rcx, [rsp+4C0h+pszDest]; lpFileName
0x1800845dc  call    RdbDeleteDeviceState
0x1800845e1  xor     ebx, ebx
0x1800845e3  jmp     short loc_1800845EA
0x1800845e5  mov     ebx, 0Bh
0x1800845ea  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800845ef  test    rcx, rcx
0x1800845f2  jz      short loc_1800845FA
0x1800845f4  call    cs:__imp_RegCloseKey
0x1800845fa  mov     rcx, [rsp+4C0h+var_458]; hKey
0x1800845ff  test    rcx, rcx
0x180084602  jz      short loc_18008460A
0x180084604  call    cs:__imp_RegCloseKey
0x18008460a  mov     eax, ebx
0x18008460c  mov     rcx, [rbp+3C0h+var_30]
0x180084613  xor     rcx, rsp; StackCookie
0x180084616  call    __security_check_cookie
0x18008461b  lea     r11, [rsp+4C0h+var_20]
0x180084623  mov     rbx, [r11+40h]
0x180084627  mov     rsi, [r11+48h]
0x18008462b  mov     rsp, r11
0x18008462e  pop     r15
0x180084630  pop     r14
0x180084632  pop     r13
0x180084634  pop     rdi
0x180084635  pop     rbp
0x180084636  retn
```
