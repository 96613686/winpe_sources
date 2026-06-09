# BuildCountryListCache

- ea: `0x180002b1c`
- end: `0x18000309d`
- name: `BuildCountryListCache`
- size: `1409`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c8a0`
- `0x18000cd20`

## callees

- `0x180001600`
- `0x180001f50`
- `0x180002b1c`
- `0x1800030a4`
- `0x1800044b0`
- `0x180006208`
- `0x18001c8a4`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003fb7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180002e09`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180002e09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002c5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002c97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002cd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002ce5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002fe3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003021`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000304f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002c5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002c97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002cd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002ce5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002fe3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003021`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000304f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180002d89`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180002d89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002bda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002c18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002c88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002cba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002bda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002c18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002c88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002cba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002c51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002fbe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002c51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002fbe`
- `KERNEL32!HeapAlloc` at `0x180002b89`
- `KERNEL32!HeapAlloc` at `0x180002dc6`
- `KERNEL32!HeapAlloc` at `0x180002e4d`
- `KERNEL32!HeapAlloc` at `0x180002ed1`
- `KERNEL32!HeapAlloc` at `0x180002b89`
- `KERNEL32!HeapAlloc` at `0x180002dc6`
- `KERNEL32!HeapAlloc` at `0x180002e4d`
- `KERNEL32!HeapAlloc` at `0x180002ed1`

## pseudocode

```c
__int64 BuildCountryListCache()
{
  DWORD v0; // r14d
  unsigned int v1; // edi
  unsigned int v2; // r13d
  char *v3; // rbx
  char *v4; // rsi
  char *v5; // r12
  __int64 v6; // rdx
  __int64 v7; // r8
  char *v8; // rax
  char *v9; // r12
  int v10; // eax
  __int64 v11; // r8
  const char *v12; // rdx
  void *v13; // rax
  unsigned int *v14; // r12
  char *v15; // rsi
  __int64 i; // r15
  char *v17; // rax
  char *v18; // rsi
  int v19; // esi
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v25; // [rsp+60h] [rbp-A0h] BYREF
  char *v26; // [rsp+68h] [rbp-98h]
  DWORD lpcbData[2]; // [rsp+70h] [rbp-90h] BYREF
  DWORD v28[2]; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type[4]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[256]; // [rsp+90h] [rbp-70h] BYREF

  v0 = 0;
  v1 = 1;
  if ( !gpCountryList )
  {
    v2 = 27672;
    cbData = 0;
    *(_DWORD *)Data = 0;
    Type[0] = 0;
    hKey = 0;
    phkResult = 0;
    v3 = (char *)HeapAlloc(ghTapisrvHeap, 8u, 0x6C18u);
    if ( !v3 )
    {
      v1 = 0;
      TRACELogPrint(65538, "Mem alloc failed for country/region list!1 (0x%lx", 27672);
LABEL_40:
      gpCountryList = (__int64)qword_1800510B8;
      ServerFree(gpCountryGroups);
      gpCountryGroups = 0;
      return v1;
    }
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony",
           0,
           0x20019u,
           &hKey) )
    {
      goto LABEL_5;
    }
    *(_DWORD *)Data = 0;
    if ( !RegOpenKeyExW(hKey, L"Country/region List", 0, 0x20019u, &phkResult) )
    {
      cbData = 4;
      RegQueryValueExW(phkResult, L"CountryListVersion", 0, Type, Data, &cbData);
      RegCloseKey(phkResult);
    }
    if ( *(_DWORD *)Data < 0x121u || RegOpenKeyExW(hKey, L"Country/region List\\1", 0, 0x20019u, &phkResult) )
    {
      if ( !RegOpenKeyExW(hKey, L"Country/region List", 0, 0xF003Fu, &phkResult) )
      {
        DeleteAllSubkeys(phkResult, 0);
        RegCloseKey(phkResult);
      }
      BuildCountryRegistryListFromRCW();
    }
    else
    {
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony",
           0,
           0x20019u,
           &phkResult) )
    {
LABEL_5:
      v1 = 0;
      ServerFree(v3);
      goto LABEL_40;
    }
    if ( RegOpenKeyExW(phkResult, L"Country/region List", 0, 0x20019u, &hKey) )
    {
      RegCloseKey(phkResult);
      goto LABEL_5;
    }
    RegCloseKey(phkResult);
    v4 = v3 + 24;
    v5 = v3 + 24;
    v26 = v3 + 24;
    while ( 1 )
    {
      cbData = 256;
      if ( RegEnumKeyExW(hKey, v0, Name, &cbData, 0, 0, 0, 0) )
        break;
      v25 = (HKEY)v2;
      if ( 44 * (unsigned __int64)v0 + 24 > v2 )
      {
        v8 = (char *)HeapAlloc(ghTapisrvHeap, 8u, 108 * v0 + 2724);
        v9 = v8;
        if ( !v8 )
        {
          v11 = 108 * v0 + 2724;
          v12 = "Mem alloc failed for country/region list!2 (0x%lx";
LABEL_39:
          v1 = 0;
          TRACELogPrint(65538, v12, v11);
          ServerFree(v3);
          RegCloseKey(hKey);
          goto LABEL_40;
        }
        v2 = 108 * v0 + 2724;
        memcpy_0(v8, v3, v4 - v3);
        ServerFree(v3);
        v3 = v9;
        v4 = (char *)v25 + (_QWORD)v9;
        *(_QWORD *)lpcbData = v9;
        v5 = v26;
      }
      v10 = _o__wtol(Name, v6, v7);
      *(_DWORD *)v4 = v10;
      *((_DWORD *)v5 + 2) = v10;
      v5 = v4;
      v26 = v4;
      v4 += 44;
      ++v0;
    }
    v13 = HeapAlloc(ghTapisrvHeap, 8u, 4 * v0);
    gpCountryGroups = v13;
    if ( v13 )
      memset_0(v13, 0, 4LL * v0);
    *((_DWORD *)v5 + 2) = 0;
    v14 = (unsigned int *)(v3 + 24);
    LODWORD(v15) = (_DWORD)v3 + 44 * v0 + 24;
    v26 = &v3[44 * v0 + 24];
    for ( i = 0; (unsigned int)i < v0; i = (unsigned int)(i + 1) )
    {
      v25 = 0;
      *(_QWORD *)lpcbData = (unsigned int)((_DWORD)v15 - (_DWORD)v3);
      if ( *(_QWORD *)lpcbData + 1160LL > (unsigned __int64)v2 )
      {
        v2 += 1024;
        v17 = (char *)HeapAlloc(ghTapisrvHeap, 8u, v2);
        *(_QWORD *)v28 = v17;
        v18 = v17;
        if ( !v17 )
        {
          v11 = v2;
          v12 = "Mem alloc failed for country/region list!3 (0x%lx";
          goto LABEL_39;
        }
        memcpy_0(v17, v3, (char *)v14 - v3);
        v15 = &v18[*(_QWORD *)lpcbData];
        v26 = v15;
        ServerFree(v3);
        v3 = *(char **)v28;
        *(_QWORD *)lpcbData = *(_QWORD *)v28;
        v14 = (unsigned int *)(44LL * (unsigned int)i + *(_QWORD *)v28 + 24LL);
      }
      StringCbPrintfW(Name, 0x200u, L"%ld", *v14);
      if ( !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &v25) )
      {
        FillupACountryEntry(v25);
        if ( gpCountryGroups )
        {
          v28[0] = 0;
          lpcbData[0] = 4;
          if ( RegQueryValueExW(v25, L"CountryGroup", 0, v28, (LPBYTE)gpCountryGroups + 4 * i, lpcbData) || v28[0] != 4 )
            *((_DWORD *)gpCountryGroups + i) = 0;
        }
        RegCloseKey(v25);
        LODWORD(v15) = (_DWORD)v26;
      }
      v14 += 11;
    }
    RegCloseKey(hKey);
    v19 = (_DWORD)v15 - (_DWORD)v3;
    *((_DWORD *)v3 + 3) = v0;
    *(_DWORD *)v3 = v19;
    *((_DWORD *)v3 + 1) = v19;
    *((_DWORD *)v3 + 2) = v19;
    *((_DWORD *)v3 + 5) = 24;
    *((_DWORD *)v3 + 4) = 44 * v0;
    gpCountryList = (__int64)v3;
  }
  return v1;
}

```

## disassembly

```asm
0x180002b1c  push    rbp
0x180002b1e  push    rbx
0x180002b1f  push    rsi
0x180002b20  push    rdi
0x180002b21  push    r12
0x180002b23  push    r13
0x180002b25  push    r14
0x180002b27  push    r15
0x180002b29  lea     rbp, [rsp-1A8h]
0x180002b31  sub     rsp, 2A8h
0x180002b38  mov     rax, cs:__security_cookie
0x180002b3f  xor     rax, rsp
0x180002b42  mov     [rbp+1E0h+var_50], rax
0x180002b49  xor     r14d, r14d
0x180002b4c  mov     edi, 1
0x180002b51  cmp     cs:gpCountryList, r14
0x180002b58  jnz     loc_180003078
0x180002b5e  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180002b65  lea     edx, [rdi+7]; dwFlags
0x180002b68  mov     r13d, 6C18h
0x180002b6e  mov     [rsp+2E0h+cbData], r14d
0x180002b73  mov     r8d, r13d; dwBytes
0x180002b76  mov     dword ptr [rsp+2E0h+Data], r14d
0x180002b7b  mov     [rbp+1E0h+Type], r14d
0x180002b7f  mov     [rsp+2E0h+hKey], r14
0x180002b84  mov     [rsp+2E0h+var_2A0], r14
0x180002b89  call    cs:__imp_HeapAlloc
0x180002b8f  mov     rbx, rax
0x180002b92  test    rax, rax
0x180002b95  jnz     short loc_180002BB3
0x180002b97  mov     r8d, r13d
0x180002b9a  lea     rdx, aMemAllocFailed_0; "Mem alloc failed for country/region lis"...
0x180002ba1  mov     ecx, 10002h
0x180002ba6  mov     edi, r14d
0x180002ba9  call    TRACELogPrint
0x180002bae  jmp     loc_180003027
0x180002bb3  lea     rax, [rsp+2E0h+hKey]
0x180002bb8  mov     r15d, 20019h
0x180002bbe  mov     r12, 0FFFFFFFF80000002h
0x180002bc5  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180002bca  mov     r9d, r15d; samDesired
0x180002bcd  lea     rdx, gszRegKeyTelephony; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180002bd4  mov     rcx, r12; hKey
0x180002bd7  xor     r8d, r8d; ulOptions
0x180002bda  call    cs:__imp_RegOpenKeyExW
0x180002be0  test    eax, eax
0x180002be2  jz      short loc_180002BF4
0x180002be4  mov     rcx, rbx; lpMem
0x180002be7  mov     edi, r14d
0x180002bea  call    ServerFree
0x180002bef  jmp     loc_180003027
0x180002bf4  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180002bf9  lea     rax, [rsp+2E0h+var_2A0]
0x180002bfe  lea     rsi, SubKey; "Country/region List"
0x180002c05  mov     dword ptr [rsp+2E0h+Data], r14d
0x180002c0a  mov     rdx, rsi; lpSubKey
0x180002c0d  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180002c12  mov     r9d, r15d; samDesired
0x180002c15  xor     r8d, r8d; ulOptions
0x180002c18  call    cs:__imp_RegOpenKeyExW
0x180002c1e  test    eax, eax
0x180002c20  jnz     short loc_180002C62
0x180002c22  mov     rcx, [rsp+2E0h+var_2A0]; hKey
0x180002c27  lea     rax, [rsp+2E0h+cbData]
0x180002c2c  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180002c31  lea     r9, [rbp+1E0h+Type]; lpType
0x180002c35  lea     rax, [rsp+2E0h+Data]
0x180002c3a  mov     [rsp+2E0h+cbData], 4
0x180002c42  xor     r8d, r8d; lpReserved
0x180002c45  mov     [rsp+2E0h+phkResult], rax; lpData
0x180002c4a  lea     rdx, gszCountryListVersionW; "CountryListVersion"
0x180002c51  call    cs:__imp_RegQueryValueExW
0x180002c57  mov     rcx, [rsp+2E0h+var_2A0]; hKey
0x180002c5c  call    cs:__imp_RegCloseKey
0x180002c62  cmp     dword ptr [rsp+2E0h+Data], 121h
0x180002c6a  jb      short loc_180002C9F
0x180002c6c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180002c71  lea     rax, [rsp+2E0h+var_2A0]
0x180002c76  mov     r9d, r15d; samDesired
0x180002c79  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180002c7e  xor     r8d, r8d; ulOptions
0x180002c81  lea     rdx, aCountryRegionL_0; "Country/region List\\1"
0x180002c88  call    cs:__imp_RegOpenKeyExW
0x180002c8e  test    eax, eax
0x180002c90  jnz     short loc_180002C9F
0x180002c92  mov     rcx, [rsp+2E0h+var_2A0]; hKey
0x180002c97  call    cs:__imp_RegCloseKey
0x180002c9d  jmp     short loc_180002CE0
0x180002c9f  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180002ca4  lea     rax, [rsp+2E0h+var_2A0]
0x180002ca9  mov     r9d, 0F003Fh; samDesired
0x180002caf  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180002cb4  xor     r8d, r8d; ulOptions
0x180002cb7  mov     rdx, rsi; lpSubKey
0x180002cba  call    cs:__imp_RegOpenKeyExW
0x180002cc0  test    eax, eax
0x180002cc2  jnz     short loc_180002CDB
0x180002cc4  mov     rcx, [rsp+2E0h+var_2A0]
0x180002cc9  xor     edx, edx
0x180002ccb  call    DeleteAllSubkeys
0x180002cd0  mov     rcx, [rsp+2E0h+var_2A0]; hKey
0x180002cd5  call    cs:__imp_RegCloseKey
0x180002cdb  call    BuildCountryRegistryListFromRCW
0x180002ce0  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180002ce5  call    cs:__imp_RegCloseKey
0x180002ceb  lea     rax, [rsp+2E0h+var_2A0]
0x180002cf0  mov     r9d, r15d; samDesired
0x180002cf3  xor     r8d, r8d; ulOptions
0x180002cf6  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180002cfb  lea     rdx, gszRegKeyTelephony; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180002d02  mov     rcx, r12; hKey
0x180002d05  call    cs:__imp_RegOpenKeyExW
0x180002d0b  test    eax, eax
0x180002d0d  jnz     loc_180002BE4
0x180002d13  mov     rcx, [rsp+2E0h+var_2A0]; hKey
0x180002d18  lea     rax, [rsp+2E0h+hKey]
0x180002d1d  mov     r9d, r15d; samDesired
0x180002d20  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180002d25  xor     r8d, r8d; ulOptions
0x180002d28  mov     rdx, rsi; lpSubKey
0x180002d2b  call    cs:__imp_RegOpenKeyExW
0x180002d31  mov     rcx, [rsp+2E0h+var_2A0]; hKey
0x180002d36  test    eax, eax
0x180002d38  jz      short loc_180002D45
0x180002d3a  call    cs:__imp_RegCloseKey
0x180002d40  jmp     loc_180002BE4
0x180002d45  call    cs:__imp_RegCloseKey
0x180002d4b  lea     rsi, [rbx+18h]
0x180002d4f  mov     r12, rsi
0x180002d52  mov     [rsp+2E0h+var_278], rsi
0x180002d57  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180002d5c  lea     r9, [rsp+2E0h+cbData]; lpcchName
0x180002d61  xor     eax, eax
0x180002d63  mov     [rsp+2E0h+cbData], 100h
0x180002d6b  mov     [rsp+2E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180002d70  lea     r8, [rbp+1E0h+Name]; lpName
0x180002d74  mov     [rsp+2E0h+lpcchClass], rax; lpcchClass
0x180002d79  mov     edx, r14d; dwIndex
0x180002d7c  mov     [rsp+2E0h+lpcbData], rax; lpClass
0x180002d81  mov     [rsp+2E0h+phkResult], rax; lpReserved
0x180002d86  mov     r15d, r14d
0x180002d89  call    cs:__imp_RegEnumKeyExW
0x180002d8f  test    eax, eax
0x180002d91  jnz     loc_180002E39
0x180002d97  imul    rax, r15, 2Ch ; ','
0x180002d9b  mov     ecx, r13d
0x180002d9e  add     rax, 18h
0x180002da2  mov     [rsp+2E0h+var_280], rcx
0x180002da7  cmp     rax, rcx
0x180002daa  jbe     short loc_180002E05
0x180002dac  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180002db3  mov     edx, 8; dwFlags
0x180002db8  imul    r15d, r14d, 6Ch ; 'l'
0x180002dbc  add     r15d, 0AA4h
0x180002dc3  mov     r8d, r15d; dwBytes
0x180002dc6  call    cs:__imp_HeapAlloc
0x180002dcc  mov     r12, rax
0x180002dcf  test    rax, rax
0x180002dd2  jz      short loc_180002E2A
0x180002dd4  sub     rsi, rbx
0x180002dd7  mov     rdx, rbx; Src
0x180002dda  mov     r8, rsi; Size
0x180002ddd  mov     rcx, rax; void *
0x180002de0  mov     r13d, r15d
0x180002de3  call    memcpy_0
0x180002de8  mov     rcx, rbx; lpMem
0x180002deb  call    ServerFree
0x180002df0  mov     rsi, [rsp+2E0h+var_280]
0x180002df5  mov     rbx, r12
0x180002df8  add     rsi, r12
0x180002dfb  mov     qword ptr [rsp+2E0h+var_270], r12
0x180002e00  mov     r12, [rsp+2E0h+var_278]
0x180002e05  lea     rcx, [rbp+1E0h+Name]
0x180002e09  call    cs:__imp__o__wtol
0x180002e0f  mov     [rsi], eax
0x180002e11  mov     [r12+8], eax
0x180002e16  mov     r12, rsi
0x180002e19  mov     [rsp+2E0h+var_278], rsi
0x180002e1e  add     rsi, 2Ch ; ','
0x180002e22  add     r14d, edi
0x180002e25  jmp     loc_180002D57
0x180002e2a  mov     r8d, r15d
0x180002e2d  lea     rdx, aMemAllocFailed; "Mem alloc failed for country/region lis"...
0x180002e34  jmp     loc_180003004
0x180002e39  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180002e40  lea     r8d, ds:0[r14*4]; dwBytes
0x180002e48  mov     edx, 8; dwFlags
0x180002e4d  call    cs:__imp_HeapAlloc
0x180002e53  mov     cs:gpCountryGroups, rax
0x180002e5a  test    rax, rax
0x180002e5d  jz      short loc_180002E71
0x180002e5f  lea     r8, ds:0[r15*4]; Size
0x180002e67  xor     edx, edx; Val
0x180002e69  mov     rcx, rax; void *
0x180002e6c  call    memset_0
0x180002e71  imul    rsi, r15, 2Ch ; ','
0x180002e75  mov     dword ptr [r12+8], 0
0x180002e7e  lea     r12, [rbx+18h]
0x180002e82  add     rsi, 18h
0x180002e86  add     rsi, rbx
0x180002e89  mov     [rsp+2E0h+var_278], rsi
0x180002e8e  xor     r15d, r15d
0x180002e91  cmp     r15d, r14d
0x180002e94  jnb     loc_18000304A
0x180002e9a  mov     eax, esi
0x180002e9c  mov     [rsp+2E0h+var_280], 0
0x180002ea5  sub     eax, ebx
0x180002ea7  mov     qword ptr [rsp+2E0h+var_270], rax
0x180002eac  lea     rcx, [rax+488h]
0x180002eb3  mov     eax, r13d
0x180002eb6  cmp     rcx, rax
0x180002eb9  jbe     short loc_180002F23
0x180002ebb  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180002ec2  add     r13d, 400h
0x180002ec9  mov     r8d, r13d; dwBytes
0x180002ecc  mov     edx, 8; dwFlags
0x180002ed1  call    cs:__imp_HeapAlloc
0x180002ed7  mov     qword ptr [rsp+2E0h+var_268], rax
0x180002edc  mov     rsi, rax
0x180002edf  test    rax, rax
0x180002ee2  jz      loc_180002FFA
0x180002ee8  sub     r12, rbx
0x180002eeb  mov     rdx, rbx; Src
0x180002eee  mov     r8, r12; Size
0x180002ef1  mov     rcx, rax; void *
0x180002ef4  call    memcpy_0
0x180002ef9  add     rsi, qword ptr [rsp+2E0h+var_270]
0x180002efe  mov     rcx, rbx; lpMem
0x180002f01  mov     [rsp+2E0h+var_278], rsi
0x180002f06  call    ServerFree
0x180002f0b  mov     rbx, qword ptr [rsp+2E0h+var_268]
0x180002f10  mov     eax, r15d
0x180002f13  imul    rax, 2Ch ; ','
0x180002f17  lea     r12, [rbx+18h]
0x180002f1b  mov     qword ptr [rsp+2E0h+var_270], rbx
0x180002f20  add     r12, rax
0x180002f23  mov     r9d, [r12]
0x180002f27  lea     r8, aLd; "%ld"
0x180002f2e  mov     edx, 200h; cbDest
0x180002f33  lea     rcx, [rbp+1E0h+Name]; pszDest
0x180002f37  call    StringCbPrintfW
0x180002f3c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180002f41  lea     rax, [rsp+2E0h+var_280]
0x180002f46  mov     r9d, 20019h; samDesired
0x180002f4c  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180002f51  xor     r8d, r8d; ulOptions
0x180002f54  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x180002f58  call    cs:__imp_RegOpenKeyExW
0x180002f5e  test    eax, eax
0x180002f60  jnz     loc_180002FEE
0x180002f66  mov     rcx, [rsp+2E0h+var_280]; hKey
0x180002f6b  lea     r9, [rsp+2E0h+var_278]
0x180002f70  mov     r8, r12
0x180002f73  mov     rdx, rbx
0x180002f76  call    FillupACountryEntry
0x180002f7b  mov     rax, cs:gpCountryGroups
0x180002f82  test    rax, rax
0x180002f85  jz      short loc_180002FDE
0x180002f87  lea     rcx, [rsp+2E0h+var_270]
0x180002f8c  mov     [rsp+2E0h+var_268], 0
0x180002f94  mov     [rsp+2E0h+lpcbData], rcx; lpcbData
0x180002f99  lea     rax, [rax+r15*4]
0x180002f9d  mov     rcx, [rsp+2E0h+var_280]; hKey
0x180002fa2  lea     r9, [rsp+2E0h+var_268]; lpType
0x180002fa7  xor     r8d, r8d; lpReserved
0x180002faa  mov     [rsp+2E0h+var_270], 4
0x180002fb2  lea     rdx, gszCountryGroupW; "CountryGroup"
0x180002fb9  mov     [rsp+2E0h+phkResult], rax; lpData
0x180002fbe  call    cs:__imp_RegQueryValueExW
0x180002fc4  test    eax, eax
0x180002fc6  jnz     short loc_180002FCF
0x180002fc8  cmp     [rsp+2E0h+var_268], 4
0x180002fcd  jz      short loc_180002FDE
0x180002fcf  mov     rax, cs:gpCountryGroups
0x180002fd6  mov     dword ptr [rax+r15*4], 0
0x180002fde  mov     rcx, [rsp+2E0h+var_280]; hKey
0x180002fe3  call    cs:__imp_RegCloseKey
0x180002fe9  mov     rsi, [rsp+2E0h+var_278]
0x180002fee  add     r12, 2Ch ; ','
0x180002ff2  add     r15d, edi
0x180002ff5  jmp     loc_180002E91
0x180002ffa  mov     r8d, r13d
0x180002ffd  lea     rdx, aMemAllocFailed_1; "Mem alloc failed for country/region lis"...
0x180003004  xor     r14d, r14d
0x180003007  mov     ecx, 10002h
0x18000300c  mov     edi, r14d
0x18000300f  call    TRACELogPrint
0x180003014  mov     rcx, rbx; lpMem
0x180003017  call    ServerFree
0x18000301c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180003021  call    cs:__imp_RegCloseKey
0x180003027  mov     rcx, cs:gpCountryGroups; lpMem
0x18000302e  lea     rax, qword_1800510B8
0x180003035  mov     cs:gpCountryList, rax
0x18000303c  call    ServerFree
0x180003041  mov     cs:gpCountryGroups, r14
0x180003048  jmp     short loc_180003078
0x18000304a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000304f  call    cs:__imp_RegCloseKey
0x180003055  sub     esi, ebx
  ... truncated ...
```
