# ReadConnectionInfoFromRegistry

- ea: `0x180030d6c`
- end: `0x1800312cf`
- name: `ReadConnectionInfoFromRegistry`
- size: `1379`
- prototype: `__int64 __fastcall(HKEY hKey, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e57c`
- `0x180031538`

## callees

- `0x18001fbd0`
- `0x1800204f6`
- `0x18002bce8`
- `0x180030d6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030e48`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030e48`
- `ntdll!DbgPrint` at `0x180030ef3`
- `ntdll!DbgPrint` at `0x180030f3e`
- `ntdll!DbgPrint` at `0x180030f5a`
- `ntdll!DbgPrint` at `0x1800310f9`
- `ntdll!DbgPrint` at `0x18003115f`
- `ntdll!DbgPrint` at `0x180030ef3`
- `ntdll!DbgPrint` at `0x180030f3e`
- `ntdll!DbgPrint` at `0x180030f5a`
- `ntdll!DbgPrint` at `0x1800310f9`
- `ntdll!DbgPrint` at `0x18003115f`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800311e0`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800311e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030e01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030e81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030edc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030f1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030fa3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031069`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800310e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031139`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800311b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031225`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031267`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030e01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030e81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030edc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030f1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030fa3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031069`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800310e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031139`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800311b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031225`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031267`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030fea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030fea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003128b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003128b`

## string_xrefs

- `0x180030e72`: `RemotePath`
- `0x180031040`: `RemotePath`
- `0x180030f85`: `SecurityDescriptor`
- `0x18003118d`: `SecurityDescriptor`

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
0x180030d6c  mov     [rsp-8+arg_18], rbx
0x180030d71  push    rbp
0x180030d72  push    rsi
0x180030d73  push    rdi
0x180030d74  push    r12
0x180030d76  push    r13
0x180030d78  push    r14
0x180030d7a  push    r15
0x180030d7c  lea     rbp, [rsp-27h]
0x180030d81  sub     rsp, 0A0h
0x180030d88  mov     rax, cs:__security_cookie
0x180030d8f  xor     rax, rsp
0x180030d92  mov     [rbp+57h+var_40], rax
0x180030d96  xor     r13d, r13d
0x180030d99  mov     r12, r8
0x180030d9c  mov     [rbp+57h+var_98], r13d
0x180030da0  mov     r15, rdx
0x180030da3  mov     [rbp+57h+var_8C], r13d
0x180030da7  mov     r14, rcx
0x180030daa  mov     [rbp+57h+var_94], r13d
0x180030dae  mov     esi, r13d
0x180030db1  mov     [rbp+57h+var_90], r13d
0x180030db5  mov     [rbp+57h+Type], r13d
0x180030db9  mov     [rbp+57h+SecurityDescriptorLength], r13d
0x180030dbd  test    rdx, rdx
0x180030dc0  jz      short loc_180030DDA
0x180030dc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030dc6  inc     rax
0x180030dc9  cmp     [rdx+rax*2], r13w
0x180030dce  jnz     short loc_180030DC6
0x180030dd0  lea     esi, ds:11h[rax*2]
0x180030dd7  and     esi, 0FFFFFFF0h
0x180030dda  lea     rax, [rbp+57h+cbData]
0x180030dde  mov     [rbp+57h+cbData], 40h ; '@'
0x180030de5  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180030dea  lea     r9, [rbp+57h+Type]; lpType
0x180030dee  lea     rax, [rbp+57h+Data]
0x180030df2  xor     r8d, r8d; lpReserved
0x180030df5  lea     rdx, aProvidername; "ProviderName"
0x180030dfc  mov     [rsp+0D0h+lpData], rax; lpData
0x180030e01  call    cs:__imp_RegQueryValueExW
0x180030e08  nop     dword ptr [rax+rax+00h]
0x180030e0d  test    eax, eax
0x180030e0f  jnz     loc_180031299
0x180030e15  cmp     [rbp+57h+Type], 1
0x180030e19  jnz     loc_180031299
0x180030e1f  mov     eax, [rbp+57h+cbData]
0x180030e22  test    al, 1
0x180030e24  jnz     loc_180031299
0x180030e2a  mov     edi, 0FFFFh
0x180030e2f  cmp     eax, edi
0x180030e31  ja      loc_180031299
0x180030e37  mov     r8d, eax
0x180030e3a  lea     rdx, Data; "Microsoft Windows Network"
0x180030e41  shr     r8, 1
0x180030e44  lea     rcx, [rbp+57h+Data]
0x180030e48  call    cs:__imp__o__wcsnicmp
0x180030e4f  nop     dword ptr [rax+rax+00h]
0x180030e54  test    eax, eax
0x180030e56  jz      short loc_180030E62
0x180030e58  mov     ebx, 4B4h
0x180030e5d  jmp     loc_18003129E
0x180030e62  lea     rax, [rbp+57h+var_98]
0x180030e66  xor     r8d, r8d; lpReserved
0x180030e69  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180030e6e  lea     r9, [rbp+57h+Type]; lpType
0x180030e72  lea     rdx, aRemotepath; "RemotePath"
0x180030e79  mov     [rsp+0D0h+lpData], r13; lpData
0x180030e7e  mov     rcx, r14; hKey
0x180030e81  call    cs:__imp_RegQueryValueExW
0x180030e88  nop     dword ptr [rax+rax+00h]
0x180030e8d  mov     ebx, eax
0x180030e8f  test    eax, eax
0x180030e91  jnz     loc_18003129E
0x180030e97  cmp     [rbp+57h+Type], 1
0x180030e9b  jnz     loc_180031299
0x180030ea1  mov     eax, [rbp+57h+var_98]
0x180030ea4  test    al, 1
0x180030ea6  jnz     loc_180031299
0x180030eac  cmp     eax, edi
0x180030eae  ja      loc_180031299
0x180030eb4  add     eax, 11h
0x180030eb7  lea     r9, [rbp+57h+Type]; lpType
0x180030ebb  and     eax, 0FFFFFFF0h
0x180030ebe  lea     rdx, aUseoptions; "UseOptions"
0x180030ec5  mov     [rbp+57h+var_98], eax
0x180030ec8  xor     r8d, r8d; lpReserved
0x180030ecb  lea     rax, [rbp+57h+var_94]
0x180030ecf  mov     rcx, r14; hKey
0x180030ed2  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180030ed7  mov     [rsp+0D0h+lpData], r13; lpData
0x180030edc  call    cs:__imp_RegQueryValueExW
0x180030ee3  nop     dword ptr [rax+rax+00h]
0x180030ee8  test    eax, eax
0x180030eea  jz      short loc_180030F66
0x180030eec  lea     rcx, aUseoptionsNotF; "UseOptions not found. Querying for Defe"...
0x180030ef3  call    cs:__imp_DbgPrint
0x180030efa  nop     dword ptr [rax+rax+00h]
0x180030eff  lea     rax, [rbp+57h+var_8C]
0x180030f03  xor     r8d, r8d; lpReserved
0x180030f06  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180030f0b  lea     r9, [rbp+57h+Type]; lpType
0x180030f0f  lea     rdx, aDeferredparame; "DeferredParameters"
0x180030f16  mov     [rsp+0D0h+lpData], r13; lpData
0x180030f1b  mov     rcx, r14; hKey
0x180030f1e  call    cs:__imp_RegQueryValueExW
0x180030f25  nop     dword ptr [rax+rax+00h]
0x180030f2a  mov     ebx, eax
0x180030f2c  test    eax, eax
0x180030f2e  jnz     loc_18003129E
0x180030f34  mov     edx, [rbp+57h+var_8C]
0x180030f37  lea     rcx, aDeferredparame_0; "DeferredParameters: %u\n"
0x180030f3e  call    cs:__imp_DbgPrint
0x180030f45  nop     dword ptr [rax+rax+00h]
0x180030f4a  mov     edx, [rbp+57h+var_8C]
0x180030f4d  lea     rcx, aCbuseoptionsU; "cbUseOptions: %u\n"
0x180030f54  add     edx, 8
0x180030f57  mov     [rbp+57h+var_94], edx
0x180030f5a  call    cs:__imp_DbgPrint
0x180030f61  nop     dword ptr [rax+rax+00h]
0x180030f66  cmp     [rbp+57h+Type], 3
0x180030f6a  jnz     loc_180031299
0x180030f70  mov     eax, [rbp+57h+var_94]
0x180030f73  cmp     eax, edi
0x180030f75  ja      loc_180031299
0x180030f7b  add     eax, 0Fh
0x180030f7e  lea     r9, [rbp+57h+Type]; lpType
0x180030f82  and     eax, 0FFFFFFF0h
0x180030f85  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x180030f8c  mov     [rbp+57h+var_94], eax
0x180030f8f  xor     r8d, r8d; lpReserved
0x180030f92  lea     rax, [rbp+57h+var_90]
0x180030f96  mov     rcx, r14; hKey
0x180030f99  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180030f9e  mov     [rsp+0D0h+lpData], r13; lpData
0x180030fa3  call    cs:__imp_RegQueryValueExW
0x180030faa  nop     dword ptr [rax+rax+00h]
0x180030faf  mov     ebx, eax
0x180030fb1  test    eax, eax
0x180030fb3  jnz     loc_18003129E
0x180030fb9  cmp     [rbp+57h+Type], 3
0x180030fbd  jnz     loc_180031299
0x180030fc3  mov     ecx, [rbp+57h+var_90]
0x180030fc6  cmp     ecx, edi
0x180030fc8  ja      loc_180031299
0x180030fce  mov     eax, [rbp+57h+var_94]
0x180030fd1  add     ecx, 0Fh
0x180030fd4  and     ecx, 0FFFFFFF0h
0x180030fd7  add     eax, 40h ; '@'
0x180030fda  add     eax, ecx
0x180030fdc  mov     [rbp+57h+var_90], ecx
0x180030fdf  add     eax, [rbp+57h+var_98]
0x180030fe2  xor     ecx, ecx; uFlags
0x180030fe4  add     eax, esi
0x180030fe6  mov     edx, eax; uBytes
0x180030fe8  mov     ebx, eax
0x180030fea  call    cs:__imp_LocalAlloc
0x180030ff1  nop     dword ptr [rax+rax+00h]
0x180030ff6  mov     rdi, rax
0x180030ff9  test    rax, rax
0x180030ffc  jnz     short loc_180031006
0x180030ffe  lea     ebx, [rax+8]
0x180031001  jmp     loc_18003129E
0x180031006  mov     r8, rbx; Size
0x180031009  xor     edx, edx; Val
0x18003100b  mov     rcx, rdi; void *
0x18003100e  call    memset_0
0x180031013  test    r15, r15
0x180031016  jz      short loc_18003102B
0x180031018  lea     rcx, [rdi+40h]; pszDest
0x18003101c  mov     edx, esi; cbDest
0x18003101e  mov     r8, r15; pszSrc
0x180031021  mov     [rdi], rcx
0x180031024  call    StringCbCopyW
0x180031029  jmp     short loc_18003102E
0x18003102b  mov     [rdi], r13
0x18003102e  add     esi, 40h ; '@'
0x180031031  cmp     [rbp+57h+var_98], r13d
0x180031035  jz      short loc_1800310A6
0x180031037  mov     eax, esi
0x180031039  lea     r9, [rbp+57h+Type]; lpType
0x18003103d  add     rax, rdi
0x180031040  lea     rdx, aRemotepath; "RemotePath"
0x180031047  mov     [rdi+8], rax
0x18003104b  xor     r8d, r8d; lpReserved
0x18003104e  mov     eax, [rbp+57h+var_98]
0x180031051  mov     rcx, r14; hKey
0x180031054  mov     [rbp+57h+SecurityDescriptorLength], eax
0x180031057  lea     rax, [rbp+57h+SecurityDescriptorLength]
0x18003105b  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180031060  mov     rax, [rdi+8]
0x180031064  mov     [rsp+0D0h+lpData], rax; lpData
0x180031069  call    cs:__imp_RegQueryValueExW
0x180031070  nop     dword ptr [rax+rax+00h]
0x180031075  mov     ebx, eax
0x180031077  test    eax, eax
0x180031079  jnz     loc_180031288
0x18003107f  cmp     [rbp+57h+Type], 1
0x180031083  jnz     loc_180031283
0x180031089  test    byte ptr [rbp+57h+SecurityDescriptorLength], 1
0x18003108d  jnz     loc_180031283
0x180031093  mov     edx, [rbp+57h+var_98]
0x180031096  mov     rcx, [rdi+8]
0x18003109a  shr     rdx, 1
0x18003109d  mov     [rcx+rdx*2-2], r13w
0x1800310a3  add     esi, [rbp+57h+var_98]
0x1800310a6  cmp     [rbp+57h+var_94], r13d
0x1800310aa  jz      loc_18003117E
0x1800310b0  mov     ebx, esi
0x1800310b2  lea     r9, [rbp+57h+Type]; lpType
0x1800310b6  add     rbx, rdi
0x1800310b9  lea     rdx, aUseoptions; "UseOptions"
0x1800310c0  mov     [rdi+18h], rbx
0x1800310c4  xor     r8d, r8d; lpReserved
0x1800310c7  mov     eax, [rbp+57h+var_94]
0x1800310ca  mov     rcx, r14; hKey
0x1800310cd  mov     [rbp+57h+SecurityDescriptorLength], eax
0x1800310d0  lea     rax, [rbp+57h+SecurityDescriptorLength]
0x1800310d4  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800310d9  mov     rax, [rdi+18h]
0x1800310dd  mov     [rsp+0D0h+lpData], rax; lpData
0x1800310e2  call    cs:__imp_RegQueryValueExW
0x1800310e9  nop     dword ptr [rax+rax+00h]
0x1800310ee  test    eax, eax
0x1800310f0  jz      short loc_18003116B
0x1800310f2  lea     rcx, aRestoringDefer; " Restoring DeferredParameters..\n"
0x1800310f9  call    cs:__imp_DbgPrint
0x180031100  nop     dword ptr [rax+rax+00h]
0x180031105  mov     rcx, [rdi+18h]
0x180031109  lea     rax, [rbx+8]
0x18003110d  lea     r9, [rbp+57h+Type]; lpType
0x180031111  xor     r8d, r8d; lpReserved
0x180031114  lea     rdx, aDeferredparame; "DeferredParameters"
0x18003111b  mov     dword ptr [rcx], 43666544h
0x180031121  mov     dword ptr [rcx+4], 7Ch ; '|'
0x180031128  lea     rcx, [rbp+57h+SecurityDescriptorLength]
0x18003112c  mov     [rsp+0D0h+lpcbData], rcx; lpcbData
0x180031131  mov     rcx, r14; hKey
0x180031134  mov     [rsp+0D0h+lpData], rax; lpData
0x180031139  call    cs:__imp_RegQueryValueExW
0x180031140  nop     dword ptr [rax+rax+00h]
0x180031145  mov     edx, [rbp+57h+SecurityDescriptorLength]
0x180031148  mov     ebx, eax
0x18003114a  add     edx, 8
0x18003114d  mov     [rbp+57h+SecurityDescriptorLength], edx
0x180031150  test    eax, eax
0x180031152  jnz     loc_180031288
0x180031158  lea     rcx, aValuelengthD; " valueLength: %d\n"
0x18003115f  call    cs:__imp_DbgPrint
0x180031166  nop     dword ptr [rax+rax+00h]
0x18003116b  cmp     [rbp+57h+Type], 3
0x18003116f  jnz     loc_180031283
0x180031175  mov     eax, [rbp+57h+SecurityDescriptorLength]
0x180031178  mov     [rdi+20h], eax
0x18003117b  add     esi, [rbp+57h+var_94]
0x18003117e  cmp     [rbp+57h+var_90], r13d
0x180031182  jz      short loc_1800311FA
0x180031184  mov     eax, esi
0x180031186  lea     r9, [rbp+57h+Type]; lpType
0x18003118a  add     rax, rdi
0x18003118d  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x180031194  mov     [rdi+28h], rax
0x180031198  xor     r8d, r8d; lpReserved
0x18003119b  mov     eax, [rbp+57h+var_90]
0x18003119e  mov     rcx, r14; hKey
0x1800311a1  mov     [rbp+57h+SecurityDescriptorLength], eax
0x1800311a4  lea     rax, [rbp+57h+SecurityDescriptorLength]
0x1800311a8  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800311ad  mov     rax, [rdi+28h]
0x1800311b1  mov     [rsp+0D0h+lpData], rax; lpData
0x1800311b6  call    cs:__imp_RegQueryValueExW
0x1800311bd  nop     dword ptr [rax+rax+00h]
0x1800311c2  mov     ebx, eax
0x1800311c4  test    eax, eax
0x1800311c6  jnz     loc_180031288
0x1800311cc  cmp     [rbp+57h+Type], 3
0x1800311d0  jnz     loc_180031283
0x1800311d6  mov     edx, [rbp+57h+SecurityDescriptorLength]; SecurityDescriptorLength
0x1800311d9  xor     r8d, r8d; RequiredInformation
0x1800311dc  mov     rcx, [rdi+28h]; SecurityDescriptorInput
0x1800311e0  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800311e7  nop     dword ptr [rax+rax+00h]
0x1800311ec  test    al, al
0x1800311ee  jz      loc_180031283
0x1800311f4  mov     eax, [rbp+57h+SecurityDescriptorLength]
0x1800311f7  mov     [rdi+30h], eax
0x1800311fa  lea     rcx, [rbp+57h+SecurityDescriptorLength]
0x1800311fe  mov     esi, 4
0x180031203  mov     [rsp+0D0h+lpcbData], rcx; lpcbData
0x180031208  lea     rax, [rdi+10h]
0x18003120c  mov     rcx, r14; hKey
0x18003120f  mov     [rbp+57h+SecurityDescriptorLength], esi
0x180031212  lea     r9, [rbp+57h+Type]; lpType
0x180031216  mov     [rsp+0D0h+lpData], rax; lpData
0x18003121b  xor     r8d, r8d; lpReserved
0x18003121e  lea     rdx, aProviderflags; "ProviderFlags"
0x180031225  call    cs:__imp_RegQueryValueExW
0x18003122c  nop     dword ptr [rax+rax+00h]
0x180031231  mov     ebx, eax
0x180031233  test    eax, eax
  ... truncated ...
```
