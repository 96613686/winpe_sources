# AtCreateSecurityObject(void)

- ea: `0x18002d308`
- end: `0x18002d416`
- name: `?AtCreateSecurityObject@@YAKXZ`
- size: `270`
- prototype: `LSTATUS(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015b7c`

## callees

- `0x180016fa0`
- `0x18002d308`
- `0x18002e1ec`
- `0x18002e28c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d394`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d394`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d388`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d388`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d34f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d34f`

## pseudocode

```c
LSTATUS AtCreateSecurityObject(void)
{
  LSTATUS result; // eax
  LSTATUS v1; // ebx
  int WellKnownSids; // eax
  __int16 v3; // [rsp+30h] [rbp-28h] BYREF
  char v4; // [rsp+32h] [rbp-26h]
  int v5; // [rsp+34h] [rbp-24h]
  __int64 *v6; // [rsp+38h] [rbp-20h]
  __int16 v7; // [rsp+40h] [rbp-18h]
  char v8; // [rsp+42h] [rbp-16h]
  int v9; // [rsp+44h] [rbp-14h]
  __int64 *v10; // [rsp+48h] [rbp-10h]
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF
  DWORD Type; // [rsp+80h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+30h] BYREF

  Data = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x20019u, &hKey);
  if ( !result )
  {
    cbData = 4;
    v1 = RegQueryValueExW(hKey, L"SubmitControl", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
    if ( v1 || Type != 4 || cbData != 4 )
      Data = 0;
    WellKnownSids = NetpCreateWellKnownSids();
    if ( WellKnownSids < 0 )
      return NetpNtStatusToApiStatus((unsigned int)WellKnownSids);
    v6 = &AliasAdminsSid;
    v5 = 0x10000000;
    v9 = 0x10000000;
    v10 = &AliasSystemOpsSid;
    v3 = 0;
    v4 = 0;
    v7 = 0;
    v8 = 0;
    WellKnownSids = NetpCreateSecurityObject(&v3, (Data & 1u) + 1);
    if ( WellKnownSids < 0 )
      return NetpNtStatusToApiStatus((unsigned int)WellKnownSids);
    else
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002d308  push    rbp
0x18002d30a  push    rbx
0x18002d30b  mov     rbp, rsp
0x18002d30e  sub     rsp, 58h
0x18002d312  lea     rax, [rbp+hKey]
0x18002d316  mov     [rbp+Data], 0
0x18002d31d  mov     r9d, 20019h; samDesired
0x18002d323  mov     [rsp+58h+phkResult], rax; phkResult
0x18002d328  xor     r8d, r8d; ulOptions
0x18002d32b  mov     [rbp+Type], 0
0x18002d332  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Lsa"
0x18002d339  mov     [rbp+cbData], 0
0x18002d340  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d347  mov     [rbp+hKey], 0
0x18002d34f  call    cs:__imp_RegOpenKeyExW
0x18002d355  test    eax, eax
0x18002d357  jnz     loc_18002D40F
0x18002d35d  mov     rcx, [rbp+hKey]; hKey
0x18002d361  lea     rax, [rbp+cbData]
0x18002d365  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002d36a  lea     r9, [rbp+Type]; lpType
0x18002d36e  lea     rax, [rbp+Data]
0x18002d372  mov     [rbp+cbData], 4
0x18002d379  xor     r8d, r8d; lpReserved
0x18002d37c  mov     [rsp+58h+phkResult], rax; lpData
0x18002d381  lea     rdx, aSubmitcontrol; "SubmitControl"
0x18002d388  call    cs:__imp_RegQueryValueExW
0x18002d38e  mov     rcx, [rbp+hKey]; hKey
0x18002d392  mov     ebx, eax
0x18002d394  call    cs:__imp_RegCloseKey
0x18002d39a  test    ebx, ebx
0x18002d39c  jnz     short loc_18002D3AA
0x18002d39e  cmp     [rbp+Type], 4
0x18002d3a2  jnz     short loc_18002D3AA
0x18002d3a4  cmp     [rbp+cbData], 4
0x18002d3a8  jz      short loc_18002D3B1
0x18002d3aa  mov     [rbp+Data], 0
0x18002d3b1  call    NetpCreateWellKnownSids
0x18002d3b6  test    eax, eax
0x18002d3b8  jns     short loc_18002D3C3
0x18002d3ba  mov     ecx, eax
0x18002d3bc  call    NetpNtStatusToApiStatus
0x18002d3c1  jmp     short loc_18002D40F
0x18002d3c3  mov     edx, [rbp+Data]
0x18002d3c6  lea     rax, AliasAdminsSid
0x18002d3cd  mov     ecx, 10000000h
0x18002d3d2  mov     [rbp+var_20], rax
0x18002d3d6  and     edx, 1
0x18002d3d9  mov     [rbp+var_24], ecx
0x18002d3dc  lea     rax, AliasSystemOpsSid
0x18002d3e3  mov     [rbp+var_14], ecx
0x18002d3e6  inc     edx
0x18002d3e8  mov     [rbp+var_10], rax
0x18002d3ec  lea     rcx, [rbp+var_28]
0x18002d3f0  mov     [rbp+var_28], 0
0x18002d3f6  mov     [rbp+var_26], 0
0x18002d3fa  mov     [rbp+var_18], 0
0x18002d400  mov     [rbp+var_16], 0
0x18002d404  call    NetpCreateSecurityObject
0x18002d409  test    eax, eax
0x18002d40b  js      short loc_18002D3BA
0x18002d40d  xor     eax, eax
0x18002d40f  add     rsp, 58h
0x18002d413  pop     rbx
0x18002d414  pop     rbp
0x18002d415  retn
```
