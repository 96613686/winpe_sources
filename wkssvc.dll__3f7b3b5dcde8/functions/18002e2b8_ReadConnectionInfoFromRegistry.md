# ReadConnectionInfoFromRegistry

- ea: `0x18002e2b8`
- end: `0x18002e7a2`
- name: `ReadConnectionInfoFromRegistry`
- size: `1258`
- prototype: `__int64 __fastcall(HKEY hKey, STRSAFE_LPCWSTR pszSrc, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d904`
- `0x18002e9c4`

## callees

- `0x18001e420`
- `0x18001ed46`
- `0x180029818`
- `0x18002e2b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002e38e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002e38e`
- `ntdll!DbgPrint` at `0x18002e427`
- `ntdll!DbgPrint` at `0x18002e466`
- `ntdll!DbgPrint` at `0x18002e47c`
- `ntdll!DbgPrint` at `0x18002e5fd`
- `ntdll!DbgPrint` at `0x18002e657`
- `ntdll!DbgPrint` at `0x18002e427`
- `ntdll!DbgPrint` at `0x18002e466`
- `ntdll!DbgPrint` at `0x18002e47c`
- `ntdll!DbgPrint` at `0x18002e5fd`
- `ntdll!DbgPrint` at `0x18002e657`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18002e6cc`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18002e6cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e34d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e3c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e416`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e44c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e4bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e579`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e5ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e637`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e6a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e70b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e747`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e34d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e3c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e416`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e44c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e4bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e579`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e5ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e637`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e6a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e70b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e747`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e500`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e500`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e765`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e765`

## string_xrefs

- `0x18002e3b2`: `RemotePath`
- `0x18002e550`: `RemotePath`
- `0x18002e4a1`: `SecurityDescriptor`
- `0x18002e67f`: `SecurityDescriptor`

## pseudocode

```c
__int64 __fastcall ReadConnectionInfoFromRegistry(HKEY hKey, STRSAFE_LPCWSTR pszSrc, _QWORD *a3)
{
  unsigned int v6; // esi
  __int64 v7; // rax
  unsigned int v8; // ebx
  SIZE_T v9; // rbx
  char *v10; // rax
  char *v11; // rdi
  unsigned int v12; // esi
  BYTE *v13; // rbx
  _DWORD *v14; // rcx
  DWORD v15; // edx
  DWORD Type; // [rsp+30h] [rbp-49h] BYREF
  DWORD SecurityDescriptorLength; // [rsp+34h] [rbp-45h] BYREF
  DWORD lpcbData; // [rsp+38h] [rbp-41h] BYREF
  DWORD v20; // [rsp+3Ch] [rbp-3Dh] BYREF
  DWORD v21; // [rsp+40h] [rbp-39h] BYREF
  DWORD v22; // [rsp+44h] [rbp-35h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-31h] BYREF
  BYTE Data[64]; // [rsp+50h] [rbp-29h] BYREF

  lpcbData = 0;
  v22 = 0;
  v20 = 0;
  v6 = 0;
  v21 = 0;
  Type = 0;
  SecurityDescriptorLength = 0;
  if ( pszSrc )
  {
    v7 = -1;
    do
      ++v7;
    while ( pszSrc[v7] );
    v6 = (2 * v7 + 17) & 0xFFFFFFF0;
  }
  cbData = 64;
  if ( RegQueryValueExW(hKey, L"ProviderName", 0, &Type, Data, &cbData)
    || Type != 1
    || (cbData & 1) != 0
    || cbData > 0xFFFF )
  {
    goto LABEL_52;
  }
  if ( (unsigned int)_o__wcsnicmp(Data, L"Microsoft Windows Network", (unsigned __int64)cbData >> 1) )
  {
    v8 = 1204;
LABEL_53:
    v11 = 0;
    goto LABEL_54;
  }
  v8 = RegQueryValueExW(hKey, L"RemotePath", 0, &Type, 0, &lpcbData);
  if ( v8 )
    goto LABEL_53;
  if ( Type != 1 || (lpcbData & 1) != 0 || lpcbData > 0xFFFF )
    goto LABEL_52;
  lpcbData = (lpcbData + 17) & 0xFFFFFFF0;
  if ( RegQueryValueExW(hKey, L"UseOptions", 0, &Type, 0, &v20) )
  {
    DbgPrint("UseOptions not found. Querying for DeferredParameters...\n");
    v8 = RegQueryValueExW(hKey, L"DeferredParameters", 0, &Type, 0, &v22);
    if ( v8 )
      goto LABEL_53;
    DbgPrint("DeferredParameters: %u\n", v22);
    v20 = v22 + 8;
    DbgPrint("cbUseOptions: %u\n", v22 + 8);
  }
  if ( Type != 3 || v20 > 0xFFFF )
    goto LABEL_52;
  v20 = (v20 + 15) & 0xFFFFFFF0;
  v8 = RegQueryValueExW(hKey, L"SecurityDescriptor", 0, &Type, 0, &v21);
  if ( v8 )
    goto LABEL_53;
  if ( Type != 3 || v21 > 0xFFFF )
  {
LABEL_52:
    v8 = 13;
    goto LABEL_53;
  }
  v21 = (v21 + 15) & 0xFFFFFFF0;
  v9 = v6 + lpcbData + v21 + v20 + 64;
  v10 = (char *)LocalAlloc(0, v9);
  v11 = v10;
  if ( !v10 )
  {
    v8 = 8;
    goto LABEL_53;
  }
  memset_0(v10, 0, v9);
  if ( pszSrc )
  {
    *(_QWORD *)v11 = v11 + 64;
    StringCbCopyW((STRSAFE_LPWSTR)v11 + 32, v6, pszSrc);
  }
  else
  {
    *(_QWORD *)v11 = 0;
  }
  v12 = v6 + 64;
  if ( lpcbData )
  {
    *((_QWORD *)v11 + 1) = &v11[v12];
    SecurityDescriptorLength = lpcbData;
    v8 = RegQueryValueExW(hKey, L"RemotePath", 0, &Type, *((LPBYTE *)v11 + 1), &SecurityDescriptorLength);
    if ( v8 )
      goto LABEL_51;
    if ( Type != 1 || (SecurityDescriptorLength & 1) != 0 )
      goto LABEL_50;
    *(_WORD *)(*((_QWORD *)v11 + 1) + 2 * ((unsigned __int64)lpcbData >> 1) - 2) = 0;
    v12 += lpcbData;
  }
  if ( v20 )
  {
    v13 = (BYTE *)&v11[v12];
    *((_QWORD *)v11 + 3) = v13;
    SecurityDescriptorLength = v20;
    if ( RegQueryValueExW(hKey, L"UseOptions", 0, &Type, *((LPBYTE *)v11 + 3), &SecurityDescriptorLength) )
    {
      DbgPrint(" Restoring DeferredParameters..\n");
      v14 = (_DWORD *)*((_QWORD *)v11 + 3);
      *v14 = 1130784068;
      v14[1] = 124;
      v8 = RegQueryValueExW(hKey, L"DeferredParameters", 0, &Type, v13 + 8, &SecurityDescriptorLength);
      v15 = SecurityDescriptorLength + 8;
      SecurityDescriptorLength += 8;
      if ( v8 )
        goto LABEL_51;
      DbgPrint(" valueLength: %d\n", v15);
    }
    if ( Type != 3 )
    {
LABEL_50:
      v8 = 13;
      goto LABEL_51;
    }
    *((_DWORD *)v11 + 8) = SecurityDescriptorLength;
    v12 += v20;
  }
  if ( v21 )
  {
    *((_QWORD *)v11 + 5) = &v11[v12];
    SecurityDescriptorLength = v21;
    v8 = RegQueryValueExW(hKey, L"SecurityDescriptor", 0, &Type, *((LPBYTE *)v11 + 5), &SecurityDescriptorLength);
    if ( v8 )
      goto LABEL_51;
    if ( Type != 3
      || !RtlValidRelativeSecurityDescriptor(*((PSECURITY_DESCRIPTOR *)v11 + 5), SecurityDescriptorLength, 0) )
    {
      goto LABEL_50;
    }
    *((_DWORD *)v11 + 12) = SecurityDescriptorLength;
  }
  SecurityDescriptorLength = 4;
  v8 = RegQueryValueExW(hKey, L"ProviderFlags", 0, &Type, (LPBYTE)v11 + 16, &SecurityDescriptorLength);
  if ( v8 )
    goto LABEL_51;
  if ( Type != 4 || SecurityDescriptorLength != 4 )
    goto LABEL_50;
  SecurityDescriptorLength = 4;
  v8 = RegQueryValueExW(hKey, L"CredentialType", 0, &Type, (LPBYTE)v11 + 20, &SecurityDescriptorLength);
  if ( v8 )
  {
LABEL_51:
    LocalFree(v11);
    goto LABEL_53;
  }
  if ( Type != 4 || SecurityDescriptorLength != 4 )
    goto LABEL_50;
LABEL_54:
  *a3 = v11;
  return v8;
}

```

## disassembly

```asm
0x18002e2b8  mov     [rsp-8+arg_18], rbx
0x18002e2bd  push    rbp
0x18002e2be  push    rsi
0x18002e2bf  push    rdi
0x18002e2c0  push    r12
0x18002e2c2  push    r13
0x18002e2c4  push    r14
0x18002e2c6  push    r15
0x18002e2c8  lea     rbp, [rsp-27h]
0x18002e2cd  sub     rsp, 0A0h
0x18002e2d4  mov     rax, cs:__security_cookie
0x18002e2db  xor     rax, rsp
0x18002e2de  mov     [rbp+57h+var_40], rax
0x18002e2e2  xor     r13d, r13d
0x18002e2e5  mov     r12, r8
0x18002e2e8  mov     [rbp+57h+var_98], r13d
0x18002e2ec  mov     r15, rdx
0x18002e2ef  mov     [rbp+57h+var_8C], r13d
0x18002e2f3  mov     r14, rcx
0x18002e2f6  mov     [rbp+57h+var_94], r13d
0x18002e2fa  mov     esi, r13d
0x18002e2fd  mov     [rbp+57h+var_90], r13d
0x18002e301  mov     [rbp+57h+Type], r13d
0x18002e305  mov     [rbp+57h+SecurityDescriptorLength], r13d
0x18002e309  test    rdx, rdx
0x18002e30c  jz      short loc_18002E326
0x18002e30e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e312  inc     rax
0x18002e315  cmp     [rdx+rax*2], r13w
0x18002e31a  jnz     short loc_18002E312
0x18002e31c  lea     esi, ds:11h[rax*2]
0x18002e323  and     esi, 0FFFFFFF0h
0x18002e326  lea     rax, [rbp+57h+cbData]
0x18002e32a  mov     [rbp+57h+cbData], 40h ; '@'
0x18002e331  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18002e336  lea     r9, [rbp+57h+Type]; lpType
0x18002e33a  lea     rax, [rbp+57h+Data]
0x18002e33e  xor     r8d, r8d; lpReserved
0x18002e341  lea     rdx, aProvidername; "ProviderName"
0x18002e348  mov     [rsp+0D0h+lpData], rax; lpData
0x18002e34d  call    cs:__imp_RegQueryValueExW
0x18002e353  test    eax, eax
0x18002e355  jnz     loc_18002E76D
0x18002e35b  cmp     [rbp+57h+Type], 1
0x18002e35f  jnz     loc_18002E76D
0x18002e365  mov     eax, [rbp+57h+cbData]
0x18002e368  test    al, 1
0x18002e36a  jnz     loc_18002E76D
0x18002e370  mov     edi, 0FFFFh
0x18002e375  cmp     eax, edi
0x18002e377  ja      loc_18002E76D
0x18002e37d  mov     r8d, eax
0x18002e380  lea     rdx, Data; "Microsoft Windows Network"
0x18002e387  shr     r8, 1
0x18002e38a  lea     rcx, [rbp+57h+Data]
0x18002e38e  call    cs:__imp__o__wcsnicmp
0x18002e394  test    eax, eax
0x18002e396  jz      short loc_18002E3A2
0x18002e398  mov     ebx, 4B4h
0x18002e39d  jmp     loc_18002E772
0x18002e3a2  lea     rax, [rbp+57h+var_98]
0x18002e3a6  xor     r8d, r8d; lpReserved
0x18002e3a9  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18002e3ae  lea     r9, [rbp+57h+Type]; lpType
0x18002e3b2  lea     rdx, aRemotepath; "RemotePath"
0x18002e3b9  mov     [rsp+0D0h+lpData], r13; lpData
0x18002e3be  mov     rcx, r14; hKey
0x18002e3c1  call    cs:__imp_RegQueryValueExW
0x18002e3c7  mov     ebx, eax
0x18002e3c9  test    eax, eax
0x18002e3cb  jnz     loc_18002E772
0x18002e3d1  cmp     [rbp+57h+Type], 1
0x18002e3d5  jnz     loc_18002E76D
0x18002e3db  mov     eax, [rbp+57h+var_98]
0x18002e3de  test    al, 1
0x18002e3e0  jnz     loc_18002E76D
0x18002e3e6  cmp     eax, edi
0x18002e3e8  ja      loc_18002E76D
0x18002e3ee  add     eax, 11h
0x18002e3f1  lea     r9, [rbp+57h+Type]; lpType
0x18002e3f5  and     eax, 0FFFFFFF0h
0x18002e3f8  lea     rdx, aUseoptions; "UseOptions"
0x18002e3ff  mov     [rbp+57h+var_98], eax
0x18002e402  xor     r8d, r8d; lpReserved
0x18002e405  lea     rax, [rbp+57h+var_94]
0x18002e409  mov     rcx, r14; hKey
0x18002e40c  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18002e411  mov     [rsp+0D0h+lpData], r13; lpData
0x18002e416  call    cs:__imp_RegQueryValueExW
0x18002e41c  test    eax, eax
0x18002e41e  jz      short loc_18002E482
0x18002e420  lea     rcx, aUseoptionsNotF; "UseOptions not found. Querying for Defe"...
0x18002e427  call    cs:__imp_DbgPrint
0x18002e42d  lea     rax, [rbp+57h+var_8C]
0x18002e431  xor     r8d, r8d; lpReserved
0x18002e434  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18002e439  lea     r9, [rbp+57h+Type]; lpType
0x18002e43d  lea     rdx, aDeferredparame; "DeferredParameters"
0x18002e444  mov     [rsp+0D0h+lpData], r13; lpData
0x18002e449  mov     rcx, r14; hKey
0x18002e44c  call    cs:__imp_RegQueryValueExW
0x18002e452  mov     ebx, eax
0x18002e454  test    eax, eax
0x18002e456  jnz     loc_18002E772
0x18002e45c  mov     edx, [rbp+57h+var_8C]
0x18002e45f  lea     rcx, aDeferredparame_0; "DeferredParameters: %u\n"
0x18002e466  call    cs:__imp_DbgPrint
0x18002e46c  mov     edx, [rbp+57h+var_8C]
0x18002e46f  lea     rcx, aCbuseoptionsU; "cbUseOptions: %u\n"
0x18002e476  add     edx, 8
0x18002e479  mov     [rbp+57h+var_94], edx
0x18002e47c  call    cs:__imp_DbgPrint
0x18002e482  cmp     [rbp+57h+Type], 3
0x18002e486  jnz     loc_18002E76D
0x18002e48c  mov     eax, [rbp+57h+var_94]
0x18002e48f  cmp     eax, edi
0x18002e491  ja      loc_18002E76D
0x18002e497  add     eax, 0Fh
0x18002e49a  lea     r9, [rbp+57h+Type]; lpType
0x18002e49e  and     eax, 0FFFFFFF0h
0x18002e4a1  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x18002e4a8  mov     [rbp+57h+var_94], eax
0x18002e4ab  xor     r8d, r8d; lpReserved
0x18002e4ae  lea     rax, [rbp+57h+var_90]
0x18002e4b2  mov     rcx, r14; hKey
0x18002e4b5  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18002e4ba  mov     [rsp+0D0h+lpData], r13; lpData
0x18002e4bf  call    cs:__imp_RegQueryValueExW
0x18002e4c5  mov     ebx, eax
0x18002e4c7  test    eax, eax
0x18002e4c9  jnz     loc_18002E772
0x18002e4cf  cmp     [rbp+57h+Type], 3
0x18002e4d3  jnz     loc_18002E76D
0x18002e4d9  mov     ecx, [rbp+57h+var_90]
0x18002e4dc  cmp     ecx, edi
0x18002e4de  ja      loc_18002E76D
0x18002e4e4  mov     eax, [rbp+57h+var_94]
0x18002e4e7  add     ecx, 0Fh
0x18002e4ea  and     ecx, 0FFFFFFF0h
0x18002e4ed  add     eax, 40h ; '@'
0x18002e4f0  add     eax, ecx
0x18002e4f2  mov     [rbp+57h+var_90], ecx
0x18002e4f5  add     eax, [rbp+57h+var_98]
0x18002e4f8  xor     ecx, ecx; uFlags
0x18002e4fa  add     eax, esi
0x18002e4fc  mov     edx, eax; uBytes
0x18002e4fe  mov     ebx, eax
0x18002e500  call    cs:__imp_LocalAlloc
0x18002e506  mov     rdi, rax
0x18002e509  test    rax, rax
0x18002e50c  jnz     short loc_18002E516
0x18002e50e  lea     ebx, [rax+8]
0x18002e511  jmp     loc_18002E772
0x18002e516  mov     r8, rbx; Size
0x18002e519  xor     edx, edx; Val
0x18002e51b  mov     rcx, rdi; void *
0x18002e51e  call    memset_0
0x18002e523  test    r15, r15
0x18002e526  jz      short loc_18002E53B
0x18002e528  lea     rcx, [rdi+40h]; pszDest
0x18002e52c  mov     edx, esi; cbDest
0x18002e52e  mov     r8, r15; pszSrc
0x18002e531  mov     [rdi], rcx
0x18002e534  call    StringCbCopyW
0x18002e539  jmp     short loc_18002E53E
0x18002e53b  mov     [rdi], r13
0x18002e53e  add     esi, 40h ; '@'
0x18002e541  cmp     [rbp+57h+var_98], r13d
0x18002e545  jz      short loc_18002E5B0
0x18002e547  mov     eax, esi
0x18002e549  lea     r9, [rbp+57h+Type]; lpType
0x18002e54d  add     rax, rdi
0x18002e550  lea     rdx, aRemotepath; "RemotePath"
0x18002e557  mov     [rdi+8], rax
0x18002e55b  xor     r8d, r8d; lpReserved
0x18002e55e  mov     eax, [rbp+57h+var_98]
0x18002e561  mov     rcx, r14; hKey
0x18002e564  mov     [rbp+57h+SecurityDescriptorLength], eax
0x18002e567  lea     rax, [rbp+57h+SecurityDescriptorLength]
0x18002e56b  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18002e570  mov     rax, [rdi+8]
0x18002e574  mov     [rsp+0D0h+lpData], rax; lpData
0x18002e579  call    cs:__imp_RegQueryValueExW
0x18002e57f  mov     ebx, eax
0x18002e581  test    eax, eax
0x18002e583  jnz     loc_18002E762
0x18002e589  cmp     [rbp+57h+Type], 1
0x18002e58d  jnz     loc_18002E75D
0x18002e593  test    byte ptr [rbp+57h+SecurityDescriptorLength], 1
0x18002e597  jnz     loc_18002E75D
0x18002e59d  mov     edx, [rbp+57h+var_98]
0x18002e5a0  mov     rcx, [rdi+8]
0x18002e5a4  shr     rdx, 1
0x18002e5a7  mov     [rcx+rdx*2-2], r13w
0x18002e5ad  add     esi, [rbp+57h+var_98]
0x18002e5b0  cmp     [rbp+57h+var_94], r13d
0x18002e5b4  jz      loc_18002E670
0x18002e5ba  mov     ebx, esi
0x18002e5bc  lea     r9, [rbp+57h+Type]; lpType
0x18002e5c0  add     rbx, rdi
0x18002e5c3  lea     rdx, aUseoptions; "UseOptions"
0x18002e5ca  mov     [rdi+18h], rbx
0x18002e5ce  xor     r8d, r8d; lpReserved
0x18002e5d1  mov     eax, [rbp+57h+var_94]
0x18002e5d4  mov     rcx, r14; hKey
0x18002e5d7  mov     [rbp+57h+SecurityDescriptorLength], eax
0x18002e5da  lea     rax, [rbp+57h+SecurityDescriptorLength]
0x18002e5de  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18002e5e3  mov     rax, [rdi+18h]
0x18002e5e7  mov     [rsp+0D0h+lpData], rax; lpData
0x18002e5ec  call    cs:__imp_RegQueryValueExW
0x18002e5f2  test    eax, eax
0x18002e5f4  jz      short loc_18002E65D
0x18002e5f6  lea     rcx, aRestoringDefer; " Restoring DeferredParameters..\n"
0x18002e5fd  call    cs:__imp_DbgPrint
0x18002e603  mov     rcx, [rdi+18h]
0x18002e607  lea     rax, [rbx+8]
0x18002e60b  lea     r9, [rbp+57h+Type]; lpType
0x18002e60f  xor     r8d, r8d; lpReserved
0x18002e612  lea     rdx, aDeferredparame; "DeferredParameters"
0x18002e619  mov     dword ptr [rcx], 43666544h
0x18002e61f  mov     dword ptr [rcx+4], 7Ch ; '|'
0x18002e626  lea     rcx, [rbp+57h+SecurityDescriptorLength]
0x18002e62a  mov     [rsp+0D0h+lpcbData], rcx; lpcbData
0x18002e62f  mov     rcx, r14; hKey
0x18002e632  mov     [rsp+0D0h+lpData], rax; lpData
0x18002e637  call    cs:__imp_RegQueryValueExW
0x18002e63d  mov     edx, [rbp+57h+SecurityDescriptorLength]
0x18002e640  mov     ebx, eax
0x18002e642  add     edx, 8
0x18002e645  mov     [rbp+57h+SecurityDescriptorLength], edx
0x18002e648  test    eax, eax
0x18002e64a  jnz     loc_18002E762
0x18002e650  lea     rcx, aValuelengthD; " valueLength: %d\n"
0x18002e657  call    cs:__imp_DbgPrint
0x18002e65d  cmp     [rbp+57h+Type], 3
0x18002e661  jnz     loc_18002E75D
0x18002e667  mov     eax, [rbp+57h+SecurityDescriptorLength]
0x18002e66a  mov     [rdi+20h], eax
0x18002e66d  add     esi, [rbp+57h+var_94]
0x18002e670  cmp     [rbp+57h+var_90], r13d
0x18002e674  jz      short loc_18002E6E0
0x18002e676  mov     eax, esi
0x18002e678  lea     r9, [rbp+57h+Type]; lpType
0x18002e67c  add     rax, rdi
0x18002e67f  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x18002e686  mov     [rdi+28h], rax
0x18002e68a  xor     r8d, r8d; lpReserved
0x18002e68d  mov     eax, [rbp+57h+var_90]
0x18002e690  mov     rcx, r14; hKey
0x18002e693  mov     [rbp+57h+SecurityDescriptorLength], eax
0x18002e696  lea     rax, [rbp+57h+SecurityDescriptorLength]
0x18002e69a  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18002e69f  mov     rax, [rdi+28h]
0x18002e6a3  mov     [rsp+0D0h+lpData], rax; lpData
0x18002e6a8  call    cs:__imp_RegQueryValueExW
0x18002e6ae  mov     ebx, eax
0x18002e6b0  test    eax, eax
0x18002e6b2  jnz     loc_18002E762
0x18002e6b8  cmp     [rbp+57h+Type], 3
0x18002e6bc  jnz     loc_18002E75D
0x18002e6c2  mov     edx, [rbp+57h+SecurityDescriptorLength]; SecurityDescriptorLength
0x18002e6c5  xor     r8d, r8d; RequiredInformation
0x18002e6c8  mov     rcx, [rdi+28h]; SecurityDescriptorInput
0x18002e6cc  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18002e6d2  test    al, al
0x18002e6d4  jz      loc_18002E75D
0x18002e6da  mov     eax, [rbp+57h+SecurityDescriptorLength]
0x18002e6dd  mov     [rdi+30h], eax
0x18002e6e0  lea     rcx, [rbp+57h+SecurityDescriptorLength]
0x18002e6e4  mov     esi, 4
0x18002e6e9  mov     [rsp+0D0h+lpcbData], rcx; lpcbData
0x18002e6ee  lea     rax, [rdi+10h]
0x18002e6f2  mov     rcx, r14; hKey
0x18002e6f5  mov     [rbp+57h+SecurityDescriptorLength], esi
0x18002e6f8  lea     r9, [rbp+57h+Type]; lpType
0x18002e6fc  mov     [rsp+0D0h+lpData], rax; lpData
0x18002e701  xor     r8d, r8d; lpReserved
0x18002e704  lea     rdx, aProviderflags; "ProviderFlags"
0x18002e70b  call    cs:__imp_RegQueryValueExW
0x18002e711  mov     ebx, eax
0x18002e713  test    eax, eax
0x18002e715  jnz     short loc_18002E762
0x18002e717  cmp     [rbp+57h+Type], esi
0x18002e71a  jnz     short loc_18002E75D
0x18002e71c  cmp     [rbp+57h+SecurityDescriptorLength], esi
0x18002e71f  jnz     short loc_18002E75D
0x18002e721  lea     rcx, [rbp+57h+SecurityDescriptorLength]
0x18002e725  mov     [rbp+57h+SecurityDescriptorLength], esi
0x18002e728  mov     [rsp+0D0h+lpcbData], rcx; lpcbData
0x18002e72d  lea     rax, [rdi+14h]
0x18002e731  mov     rcx, r14; hKey
0x18002e734  mov     [rsp+0D0h+lpData], rax; lpData
0x18002e739  lea     r9, [rbp+57h+Type]; lpType
0x18002e73d  xor     r8d, r8d; lpReserved
0x18002e740  lea     rdx, aCredentialtype; "CredentialType"
0x18002e747  call    cs:__imp_RegQueryValueExW
0x18002e74d  mov     ebx, eax
0x18002e74f  test    eax, eax
0x18002e751  jnz     short loc_18002E762
  ... truncated ...
```
