# SecpRefDllFromCache(_SECP_DLL_BINDING *)

- ea: `0x18000d8ac`
- end: `0x18000e07d`
- name: `?SecpRefDllFromCache@@YAHPEAU_SECP_DLL_BINDING@@@Z`
- size: `2001`
- prototype: `__int64 __fastcall(struct _SECP_DLL_BINDING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d6ec`

## callees

- `0x180007d30`
- `0x18000d8ac`
- `0x18000e084`
- `0x18000e148`
- `0x18001b048`
- `0x18001d478`
- `0x18001d5e4`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000dd37`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000dd37`
- `ntdll!RtlReleaseResource` at `0x18000de10`
- `ntdll!RtlReleaseResource` at `0x18000de10`
- `ntdll!RtlxUnicodeStringToAnsiSize` at `0x18000dc4d`
- `ntdll!RtlxUnicodeStringToAnsiSize` at `0x18000dc9c`
- `ntdll!RtlxUnicodeStringToAnsiSize` at `0x18000dc4d`
- `ntdll!RtlxUnicodeStringToAnsiSize` at `0x18000dc9c`
- `ntdll!RtlEqualUnicodeString` at `0x18000dd96`
- `ntdll!RtlEqualUnicodeString` at `0x18000dd96`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000dc93`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000dce2`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000dc93`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000dce2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d93a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e050`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e05a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d93a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e050`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e05a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000e046`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000e046`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d98c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d9e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000da34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000da87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dadd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dba7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dbe9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d98c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d9e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000da34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000da87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dadd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dba7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dbe9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d908`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d92c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d908`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d92c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d94f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d9ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000da50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dc5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dcae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d94f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d9ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000da50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dc5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dcae`

## string_xrefs

- `0x18000d9fc`: `Comment`
- `0x18000da7b`: `Comment`
- `0x18000df5a`: `Comment`
- `0x18000d8e6`: `System\CurrentControlSet\Control\Lsa\SspiCache`
- `0x18000dbc9`: `TokenSize`
- `0x18000de61`: `TokenSize`

## pseudocode

```c
__int64 __fastcall SecpRefDllFromCache(struct _SECP_DLL_BINDING *a1)
{
  unsigned __int16 *v2; // rcx
  const WCHAR *v3; // r14
  HLOCAL v4; // rsi
  unsigned int v5; // edi
  const WCHAR *v6; // r15
  int v7; // r8d
  BYTE *v8; // rax
  BYTE *v9; // rax
  __int64 v10; // r8
  unsigned int v11; // edx
  bool v12; // zf
  ULONG v13; // eax
  CHAR *v14; // rax
  ULONG v15; // eax
  CHAR *v16; // rax
  PVOID *v17; // rcx
  unsigned int v18; // r14d
  const UNICODE_STRING *i; // r14
  BOOLEAN v20; // al
  unsigned int j; // ebx
  _QWORD *v23; // rcx
  int v24; // edx
  const WCHAR *v25; // rax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  _QWORD *v28; // rcx
  int v29; // edx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  struct _STRING DestinationString; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+48h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+50h] BYREF
  int Data; // [rsp+B0h] [rbp+58h] BYREF
  HKEY phkResult; // [rsp+B8h] [rbp+60h] BYREF

  v2 = (unsigned __int16 *)*((_QWORD *)a1 + 3);
  hKey = 0;
  phkResult = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  v3 = SecpFileNameFromPath(v2);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa\\SspiCache", 0, 0x20019u, &hKey) )
    return 0;
  if ( RegOpenKeyExW(hKey, v3, 0, 0x20019u, &phkResult) )
  {
    RegCloseKey(hKey);
    return 0;
  }
  v4 = LocalAlloc(0x40u, 0xD8u);
  if ( !v4 )
  {
    v5 = 0;
    goto LABEL_55;
  }
  v6 = L"Name";
  cbData = 0;
  v5 = 1;
  if ( RegQueryValueExW(phkResult, L"Name", 0, &Type, 0, &cbData) || Type != 1 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v29 = 19;
LABEL_91:
    WPP_SF_SS(v28[2], v29, v7, (_DWORD)v3, (__int64)v6);
    goto LABEL_92;
  }
  v8 = (BYTE *)LocalAlloc(0, cbData);
  *((_QWORD *)v4 + 13) = v8;
  if ( !v8 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    v27 = 21;
LABEL_87:
    WPP_SF_D(v26[2], v27, &WPP_a2431279d589382153de9f1c7b526408_Traceguids, cbData);
LABEL_93:
    RegCloseKey(hKey);
    RegCloseKey(phkResult);
    SecpFreePackage(v4, 1);
    return 0;
  }
  if ( RegQueryValueExW(phkResult, L"Name", 0, &Type, v8, &cbData) || Type != 1 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v29 = 20;
    goto LABEL_91;
  }
  v6 = L"Comment";
  *((_WORD *)v4 + 49) = cbData;
  *((_WORD *)v4 + 48) = cbData - 2;
  cbData = 0;
  if ( RegQueryValueExW(phkResult, L"Comment", 0, &Type, 0, &cbData) || Type != 1 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v29 = 22;
    goto LABEL_91;
  }
  v9 = (BYTE *)LocalAlloc(0, cbData);
  *((_QWORD *)v4 + 15) = v9;
  if ( !v9 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    v27 = 24;
    goto LABEL_87;
  }
  if ( RegQueryValueExW(phkResult, L"Comment", 0, &Type, v9, &cbData) || Type != 1 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v24 = 23;
    v25 = L"Comment";
LABEL_59:
    WPP_SF_SS(v23[2], v24, v10, (_DWORD)v3, (__int64)v25);
LABEL_92:
    RegDeleteKeyExW(hKey, v3, 0, 0);
    goto LABEL_93;
  }
  *((_WORD *)v4 + 57) = cbData;
  *((_WORD *)v4 + 56) = cbData - 2;
  cbData = 4;
  if ( RegQueryValueExW(phkResult, L"Capabilities", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v24 = 25;
    v25 = L"Capabilities";
    goto LABEL_59;
  }
  *((_DWORD *)v4 + 20) = Data;
  if ( RegQueryValueExW(phkResult, L"RpcId", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v24 = 26;
    v25 = L"RpcId";
    goto LABEL_59;
  }
  *((_WORD *)v4 + 43) = Data;
  if ( RegQueryValueExW(phkResult, L"Version", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v24 = 27;
    v25 = L"Version";
    goto LABEL_59;
  }
  *((_WORD *)v4 + 42) = Data;
  if ( RegQueryValueExW(phkResult, L"Type", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v24 = 28;
    v25 = L"Type";
    goto LABEL_59;
  }
  *((_DWORD *)v4 + 4) = Data;
  if ( RegQueryValueExW(phkResult, L"TokenSize", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v24 = 29;
    v25 = L"TokenSize";
    goto LABEL_59;
  }
  v11 = SecSspiPackageCount;
  *((_DWORD *)v4 + 23) = Data;
  *((_DWORD *)a1 + 9) = 1;
  *((_QWORD *)v4 + 7) = a1;
  *((_DWORD *)v4 + 9) = 4;
  *((_QWORD *)v4 + 3) = v11 + 0x10000;
  v12 = (*((_BYTE *)v4 + 16) & 0x10) == 0;
  SecSspiPackageCount = v11 + 1;
  *((_DWORD *)v4 + 8) = 0;
  *((_QWORD *)v4 + 8) = v4;
  *((_QWORD *)v4 + 9) = 0;
  if ( !v12 )
  {
    v13 = RtlxUnicodeStringToAnsiSize((PCUNICODE_STRING)v4 + 6) + 1;
    *((_DWORD *)v4 + 34) = v13;
    v14 = (CHAR *)LocalAlloc(0, v13);
    *((_QWORD *)v4 + 16) = v14;
    if ( v14 )
    {
      DestinationString.Buffer = v14;
      DestinationString.MaximumLength = *((_WORD *)v4 + 68);
      *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
      DestinationString.Length = 0;
      RtlUnicodeStringToAnsiString(&DestinationString, (PCUNICODE_STRING)v4 + 6, 0);
    }
    v15 = RtlxUnicodeStringToAnsiSize((PCUNICODE_STRING)v4 + 7) + 1;
    *((_DWORD *)v4 + 38) = v15;
    v16 = (CHAR *)LocalAlloc(0, v15);
    *((_QWORD *)v4 + 18) = v16;
    if ( v16 )
    {
      DestinationString.Buffer = v16;
      DestinationString.MaximumLength = *((_WORD *)v4 + 76);
      *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
      DestinationString.Length = 0;
      RtlUnicodeStringToAnsiString(&DestinationString, (PCUNICODE_STRING)v4 + 7, 0);
    }
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_35;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v10, *((_QWORD *)v4 + 13));
  }
  v17 = (PVOID *)WPP_GLOBAL_Control;
LABEL_35:
  v18 = 0;
  if ( SecPackageListLockCount )
  {
    do
      RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * v18++], 1u);
    while ( v18 < SecPackageListLockCount );
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  for ( i = (const UNICODE_STRING *)SecPackageControlList; ; i = *(const UNICODE_STRING **)&i->Length )
  {
    if ( i == (const UNICODE_STRING *)&SecPackageControlList )
      goto LABEL_52;
    if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 )
    {
      WPP_SF_S(v17[2], 11, v10, i[6].Buffer);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 == (HLOCAL)-96LL )
      break;
    v20 = RtlEqualUnicodeString(i + 6, (PCUNICODE_STRING)v4 + 6, 1u);
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( v20 )
      goto LABEL_44;
LABEL_50:
    ;
  }
  if ( i[1].Buffer != (PWSTR)-1LL )
    goto LABEL_50;
LABEL_44:
  if ( !i )
  {
LABEL_52:
    SecpAddDllPackage((struct _DLL_SECURITY_PACKAGE *)v4);
    goto LABEL_53;
  }
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 )
    WPP_SF_S(v17[2], 31, v10, *((_QWORD *)v4 + 13));
  SecpFreePackage(v4, 1);
LABEL_53:
  for ( j = 0; j < SecPackageListLockCount; ++j )
    RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * j]);
LABEL_55:
  RegCloseKey(hKey);
  RegCloseKey(phkResult);
  return v5;
}

```

## disassembly

```asm
0x18000d8ac  push    rbp
0x18000d8ae  push    rbx
0x18000d8af  push    rsi
0x18000d8b0  push    rdi
0x18000d8b1  push    r12
0x18000d8b3  push    r13
0x18000d8b5  push    r14
0x18000d8b7  push    r15
0x18000d8b9  mov     rbp, rsp
0x18000d8bc  sub     rsp, 58h
0x18000d8c0  xor     r13d, r13d
0x18000d8c3  mov     rbx, rcx
0x18000d8c6  mov     rcx, [rcx+18h]; unsigned __int16 *
0x18000d8ca  mov     [rbp+hKey], r13
0x18000d8ce  mov     [rbp+arg_18], r13
0x18000d8d2  mov     [rbp+Type], r13d
0x18000d8d6  mov     [rbp+cbData], r13d
0x18000d8da  mov     [rbp+Data], r13d
0x18000d8de  call    ?SecpFileNameFromPath@@YAPEAGPEAG@Z; SecpFileNameFromPath(ushort *)
0x18000d8e3  mov     r14, rax
0x18000d8e6  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Lsa"...
0x18000d8ed  lea     rax, [rbp+hKey]
0x18000d8f1  mov     edi, 20019h
0x18000d8f6  mov     r9d, edi; samDesired
0x18000d8f9  mov     [rsp+58h+phkResult], rax; phkResult
0x18000d8fe  xor     r8d, r8d; ulOptions
0x18000d901  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d908  call    cs:__imp_RegOpenKeyExW
0x18000d90e  test    eax, eax
0x18000d910  jnz     loc_18000E06A
0x18000d916  mov     rcx, [rbp+hKey]; hKey
0x18000d91a  lea     rax, [rbp+arg_18]
0x18000d91e  mov     r9d, edi; samDesired
0x18000d921  mov     [rsp+58h+phkResult], rax; phkResult
0x18000d926  xor     r8d, r8d; ulOptions
0x18000d929  mov     rdx, r14; lpSubKey
0x18000d92c  call    cs:__imp_RegOpenKeyExW
0x18000d932  test    eax, eax
0x18000d934  jz      short loc_18000D945
0x18000d936  mov     rcx, [rbp+hKey]; hKey
0x18000d93a  call    cs:__imp_RegCloseKey
0x18000d940  jmp     loc_18000E06A
0x18000d945  mov     edx, 0D8h; uBytes
0x18000d94a  mov     ecx, 40h ; '@'; uFlags
0x18000d94f  call    cs:__imp_LocalAlloc
0x18000d955  mov     rsi, rax
0x18000d958  test    rax, rax
0x18000d95b  jnz     short loc_18000D965
0x18000d95d  mov     edi, r13d
0x18000d960  jmp     loc_18000DE20
0x18000d965  mov     rcx, [rbp+arg_18]; hKey
0x18000d969  lea     rax, [rbp+cbData]
0x18000d96d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000d972  lea     r15, ValueName; "Name"
0x18000d979  mov     rdx, r15; lpValueName
0x18000d97c  mov     [rsp+58h+phkResult], r13; lpData
0x18000d981  lea     r9, [rbp+Type]; lpType
0x18000d985  mov     [rbp+cbData], r13d
0x18000d989  xor     r8d, r8d; lpReserved
0x18000d98c  call    cs:__imp_RegQueryValueExW
0x18000d992  mov     edi, 1
0x18000d997  test    eax, eax
0x18000d999  jnz     loc_18000E00A
0x18000d99f  cmp     [rbp+Type], edi
0x18000d9a2  jnz     loc_18000E00A
0x18000d9a8  mov     edx, [rbp+cbData]; uBytes
0x18000d9ab  xor     ecx, ecx; uFlags
0x18000d9ad  call    cs:__imp_LocalAlloc
0x18000d9b3  lea     r12, [rsi+60h]
0x18000d9b7  mov     [r12+8], rax
0x18000d9bc  test    rax, rax
0x18000d9bf  jz      loc_18000DFD6
0x18000d9c5  lea     rcx, [rbp+cbData]
0x18000d9c9  xor     r8d, r8d; lpReserved
0x18000d9cc  mov     [rsp+58h+lpcbData], rcx; lpcbData
0x18000d9d1  lea     r9, [rbp+Type]; lpType
0x18000d9d5  mov     rcx, [rbp+arg_18]; hKey
0x18000d9d9  mov     rdx, r15; lpValueName
0x18000d9dc  mov     [rsp+58h+phkResult], rax; lpData
0x18000d9e1  call    cs:__imp_RegQueryValueExW
0x18000d9e7  test    eax, eax
0x18000d9e9  jnz     loc_18000DFB6
0x18000d9ef  cmp     [rbp+Type], edi
0x18000d9f2  jnz     loc_18000DFB6
0x18000d9f8  movzx   eax, word ptr [rbp+cbData]
0x18000d9fc  lea     r15, aComment; "Comment"
0x18000da03  mov     [rsi+62h], ax
0x18000da07  lea     r9, [rbp+Type]; lpType
0x18000da0b  movzx   eax, word ptr [rbp+cbData]
0x18000da0f  xor     r8d, r8d; lpReserved
0x18000da12  sub     ax, 2
0x18000da16  mov     rdx, r15; lpValueName
0x18000da19  mov     [r12], ax
0x18000da1e  lea     rax, [rbp+cbData]
0x18000da22  mov     rcx, [rbp+arg_18]; hKey
0x18000da26  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000da2b  mov     [rsp+58h+phkResult], r13; lpData
0x18000da30  mov     [rbp+cbData], r13d
0x18000da34  call    cs:__imp_RegQueryValueExW
0x18000da3a  test    eax, eax
0x18000da3c  jnz     loc_18000DF8E
0x18000da42  cmp     [rbp+Type], edi
0x18000da45  jnz     loc_18000DF8E
0x18000da4b  mov     edx, [rbp+cbData]; uBytes
0x18000da4e  xor     ecx, ecx; uFlags
0x18000da50  call    cs:__imp_LocalAlloc
0x18000da56  lea     r15, [rsi+70h]
0x18000da5a  mov     [r15+8], rax
0x18000da5e  test    rax, rax
0x18000da61  jz      loc_18000DF66
0x18000da67  lea     rcx, [rbp+cbData]
0x18000da6b  xor     r8d, r8d; lpReserved
0x18000da6e  mov     [rsp+58h+lpcbData], rcx; lpcbData
0x18000da73  lea     r9, [rbp+Type]; lpType
0x18000da77  mov     rcx, [rbp+arg_18]; hKey
0x18000da7b  lea     rdx, aComment; "Comment"
0x18000da82  mov     [rsp+58h+phkResult], rax; lpData
0x18000da87  call    cs:__imp_RegQueryValueExW
0x18000da8d  test    eax, eax
0x18000da8f  jnz     loc_18000DF34
0x18000da95  cmp     [rbp+Type], edi
0x18000da98  jnz     loc_18000DF34
0x18000da9e  movzx   eax, word ptr [rbp+cbData]
0x18000daa2  lea     r9, [rbp+Type]; lpType
0x18000daa6  mov     [rsi+72h], ax
0x18000daaa  lea     rdx, aCapabilities; "Capabilities"
0x18000dab1  movzx   eax, word ptr [rbp+cbData]
0x18000dab5  xor     r8d, r8d; lpReserved
0x18000dab8  sub     ax, 2
0x18000dabc  mov     [r15], ax
0x18000dac0  lea     rax, [rbp+cbData]
0x18000dac4  mov     rcx, [rbp+arg_18]; hKey
0x18000dac8  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000dacd  lea     rax, [rbp+Data]
0x18000dad1  mov     [rsp+58h+phkResult], rax; lpData
0x18000dad6  mov     [rbp+cbData], 4
0x18000dadd  call    cs:__imp_RegQueryValueExW
0x18000dae3  test    eax, eax
0x18000dae5  jnz     loc_18000DF02
0x18000daeb  cmp     [rbp+Type], 4
0x18000daef  jnz     loc_18000DF02
0x18000daf5  mov     eax, [rbp+Data]
0x18000daf8  lea     r9, [rbp+Type]; lpType
0x18000dafc  mov     [rsi+50h], eax
0x18000daff  lea     rdx, aRpcid; "RpcId"
0x18000db06  mov     rcx, [rbp+arg_18]; hKey
0x18000db0a  lea     rax, [rbp+cbData]
0x18000db0e  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000db13  xor     r8d, r8d; lpReserved
0x18000db16  lea     rax, [rbp+Data]
0x18000db1a  mov     [rsp+58h+phkResult], rax; lpData
0x18000db1f  call    cs:__imp_RegQueryValueExW
0x18000db25  test    eax, eax
0x18000db27  jnz     loc_18000DED0
0x18000db2d  cmp     [rbp+Type], 4
0x18000db31  jnz     loc_18000DED0
0x18000db37  movzx   eax, word ptr [rbp+Data]
0x18000db3b  lea     r9, [rbp+Type]; lpType
0x18000db3f  mov     [rsi+56h], ax
0x18000db43  lea     rdx, aVersion; "Version"
0x18000db4a  mov     rcx, [rbp+arg_18]; hKey
0x18000db4e  lea     rax, [rbp+cbData]
0x18000db52  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000db57  xor     r8d, r8d; lpReserved
0x18000db5a  lea     rax, [rbp+Data]
0x18000db5e  mov     [rsp+58h+phkResult], rax; lpData
0x18000db63  call    cs:__imp_RegQueryValueExW
0x18000db69  test    eax, eax
0x18000db6b  jnz     loc_18000DEA1
0x18000db71  cmp     [rbp+Type], 4
0x18000db75  jnz     loc_18000DEA1
0x18000db7b  movzx   eax, word ptr [rbp+Data]
0x18000db7f  lea     r9, [rbp+Type]; lpType
0x18000db83  mov     [rsi+54h], ax
0x18000db87  lea     rdx, aType; "Type"
0x18000db8e  mov     rcx, [rbp+arg_18]; hKey
0x18000db92  lea     rax, [rbp+cbData]
0x18000db96  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000db9b  xor     r8d, r8d; lpReserved
0x18000db9e  lea     rax, [rbp+Data]
0x18000dba2  mov     [rsp+58h+phkResult], rax; lpData
0x18000dba7  call    cs:__imp_RegQueryValueExW
0x18000dbad  test    eax, eax
0x18000dbaf  jnz     loc_18000DE72
0x18000dbb5  cmp     [rbp+Type], 4
0x18000dbb9  jnz     loc_18000DE72
0x18000dbbf  mov     eax, [rbp+Data]
0x18000dbc2  lea     r9, [rbp+Type]; lpType
0x18000dbc6  mov     [rsi+10h], eax
0x18000dbc9  lea     rdx, aTokensize; "TokenSize"
0x18000dbd0  mov     rcx, [rbp+arg_18]; hKey
0x18000dbd4  lea     rax, [rbp+cbData]
0x18000dbd8  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000dbdd  xor     r8d, r8d; lpReserved
0x18000dbe0  lea     rax, [rbp+Data]
0x18000dbe4  mov     [rsp+58h+phkResult], rax; lpData
0x18000dbe9  call    cs:__imp_RegQueryValueExW
0x18000dbef  test    eax, eax
0x18000dbf1  jnz     loc_18000DE3B
0x18000dbf7  cmp     [rbp+Type], 4
0x18000dbfb  jnz     loc_18000DE3B
0x18000dc01  mov     eax, [rbp+Data]
0x18000dc04  mov     edx, cs:?SecSspiPackageCount@@3KA; ulong SecSspiPackageCount
0x18000dc0a  mov     [rsi+5Ch], eax
0x18000dc0d  mov     [rbx+24h], edi
0x18000dc10  mov     [rsi+38h], rbx
0x18000dc14  lea     rbx, WPP_GLOBAL_Control
0x18000dc1b  lea     ecx, [rdx+10000h]
0x18000dc21  mov     dword ptr [rsi+24h], 4
0x18000dc28  add     edx, edi
0x18000dc2a  mov     [rsi+18h], rcx
0x18000dc2e  test    byte ptr [rsi+10h], 10h
0x18000dc32  mov     cs:?SecSspiPackageCount@@3KA, edx; ulong SecSspiPackageCount
0x18000dc38  mov     [rsi+20h], r13d
0x18000dc3c  mov     [rsi+40h], rsi
0x18000dc40  mov     [rsi+48h], r13
0x18000dc44  jz      loc_18000DD0C
0x18000dc4a  mov     rcx, r12; UnicodeString
0x18000dc4d  call    cs:__imp_RtlxUnicodeStringToAnsiSize
0x18000dc53  inc     eax
0x18000dc55  xor     ecx, ecx; uFlags
0x18000dc57  mov     edx, eax; uBytes
0x18000dc59  mov     [rsi+88h], eax
0x18000dc5f  call    cs:__imp_LocalAlloc
0x18000dc65  mov     [rsi+80h], rax
0x18000dc6c  test    rax, rax
0x18000dc6f  jz      short loc_18000DC99
0x18000dc71  mov     [rbp+DestinationString.Buffer], rax
0x18000dc75  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000dc79  movzx   eax, word ptr [rsi+88h]
0x18000dc80  xor     r8d, r8d; AllocateDestinationString
0x18000dc83  mov     rdx, r12; SourceString
0x18000dc86  mov     [rbp+DestinationString.MaximumLength], ax
0x18000dc8a  mov     dword ptr [rbp+DestinationString+4], r13d
0x18000dc8e  mov     [rbp+DestinationString.Length], r13w
0x18000dc93  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18000dc99  mov     rcx, r15; UnicodeString
0x18000dc9c  call    cs:__imp_RtlxUnicodeStringToAnsiSize
0x18000dca2  inc     eax
0x18000dca4  xor     ecx, ecx; uFlags
0x18000dca6  mov     edx, eax; uBytes
0x18000dca8  mov     [rsi+98h], eax
0x18000dcae  call    cs:__imp_LocalAlloc
0x18000dcb4  mov     [rsi+90h], rax
0x18000dcbb  test    rax, rax
0x18000dcbe  jz      short loc_18000DCE8
0x18000dcc0  mov     [rbp+DestinationString.Buffer], rax
0x18000dcc4  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000dcc8  movzx   eax, word ptr [rsi+98h]
0x18000dccf  xor     r8d, r8d; AllocateDestinationString
0x18000dcd2  mov     rdx, r15; SourceString
0x18000dcd5  mov     [rbp+DestinationString.MaximumLength], ax
0x18000dcd9  mov     dword ptr [rbp+DestinationString+4], r13d
0x18000dcdd  mov     [rbp+DestinationString.Length], r13w
0x18000dce2  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18000dce8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcef  cmp     rcx, rbx
0x18000dcf2  jz      short loc_18000DD13
0x18000dcf4  test    byte ptr [rcx+1Ch], 4
0x18000dcf8  jz      short loc_18000DD13
0x18000dcfa  mov     r9, [rsi+68h]
0x18000dcfe  mov     edx, 1Eh
0x18000dd03  mov     rcx, [rcx+10h]
0x18000dd07  call    WPP_SF_S
0x18000dd0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd13  cmp     cs:SecPackageListLockCount, r13d
0x18000dd1a  mov     r14d, r13d
0x18000dd1d  jbe     short loc_18000DD53
0x18000dd1f  lea     r13, SecPackageListLock
0x18000dd26  mov     eax, r14d
0x18000dd29  mov     dl, dil; Wait
0x18000dd2c  lea     rcx, [rax+rax*2]
0x18000dd30  shl     rcx, 5
0x18000dd34  add     rcx, r13; Resource
0x18000dd37  call    cs:__imp_RtlAcquireResourceExclusive
0x18000dd3d  add     r14d, edi
0x18000dd40  cmp     r14d, cs:SecPackageListLockCount
0x18000dd47  jb      short loc_18000DD26
0x18000dd49  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd50  xor     r13d, r13d
0x18000dd53  mov     r14, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x18000dd5a  lea     r15, ?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x18000dd61  jmp     short loc_18000DDDF
0x18000dd63  cmp     rcx, rbx
0x18000dd66  jz      short loc_18000DD87
0x18000dd68  test    byte ptr [rcx+1Ch], 4
0x18000dd6c  jz      short loc_18000DD87
0x18000dd6e  mov     r9, [r14+68h]
0x18000dd72  mov     edx, 0Bh
0x18000dd77  mov     rcx, [rcx+10h]
0x18000dd7b  call    WPP_SF_S
0x18000dd80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd87  test    r12, r12
0x18000dd8a  jz      short loc_18000DDD5
0x18000dd8c  lea     rcx, [r14+60h]; String1
0x18000dd90  mov     r8b, dil; CaseInsensitive
0x18000dd93  mov     rdx, r12; String2
0x18000dd96  call    cs:__imp_RtlEqualUnicodeString
0x18000dd9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dda3  test    al, al
  ... truncated ...
```
