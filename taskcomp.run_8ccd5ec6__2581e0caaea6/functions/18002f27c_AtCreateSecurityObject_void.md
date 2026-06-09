# AtCreateSecurityObject(void)

- ea: `0x18002f27c`
- end: `0x18002f39d`
- name: `?AtCreateSecurityObject@@YAKXZ`
- size: `289`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800169d8`

## callees

- `0x180017f64`
- `0x18002f27c`
- `0x1800302e4`
- `0x180030394`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f314`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f314`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f302`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f302`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f2c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f2c3`

## pseudocode

```c
LSTATUS AtCreateSecurityObject(void)
{
  LSTATUS result; // eax
  LSTATUS v1; // ebx
  __int64 v2; // rcx
  int WellKnownSids; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  __int16 v6; // [rsp+30h] [rbp-28h] BYREF
  char v7; // [rsp+32h] [rbp-26h]
  int v8; // [rsp+34h] [rbp-24h]
  __int64 *v9; // [rsp+38h] [rbp-20h]
  __int16 v10; // [rsp+40h] [rbp-18h]
  char v11; // [rsp+42h] [rbp-16h]
  int v12; // [rsp+44h] [rbp-14h]
  __int64 *v13; // [rsp+48h] [rbp-10h]
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
    WellKnownSids = NetpCreateWellKnownSids(v2);
    if ( WellKnownSids < 0 )
      return NetpNtStatusToApiStatus((unsigned int)WellKnownSids);
    v9 = &AliasAdminsSid;
    v8 = 0x10000000;
    v12 = 0x10000000;
    v13 = &AliasSystemOpsSid;
    v6 = 0;
    v7 = 0;
    v10 = 0;
    v11 = 0;
    WellKnownSids = NetpCreateSecurityObject((__int64)&v6, (Data & 1u) + 1, v4, v5);
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
0x18002f27c  push    rbp
0x18002f27e  push    rbx
0x18002f27f  mov     rbp, rsp
0x18002f282  sub     rsp, 58h
0x18002f286  lea     rax, [rbp+hKey]
0x18002f28a  mov     [rbp+Data], 0
0x18002f291  mov     r9d, 20019h; samDesired
0x18002f297  mov     [rsp+58h+phkResult], rax; phkResult
0x18002f29c  xor     r8d, r8d; ulOptions
0x18002f29f  mov     [rbp+Type], 0
0x18002f2a6  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Lsa"
0x18002f2ad  mov     [rbp+cbData], 0
0x18002f2b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f2bb  mov     [rbp+hKey], 0
0x18002f2c3  call    cs:__imp_RegOpenKeyExW
0x18002f2ca  nop     dword ptr [rax+rax+00h]
0x18002f2cf  test    eax, eax
0x18002f2d1  jnz     loc_18002F395
0x18002f2d7  mov     rcx, [rbp+hKey]; hKey
0x18002f2db  lea     rax, [rbp+cbData]
0x18002f2df  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002f2e4  lea     r9, [rbp+Type]; lpType
0x18002f2e8  lea     rax, [rbp+Data]
0x18002f2ec  mov     [rbp+cbData], 4
0x18002f2f3  xor     r8d, r8d; lpReserved
0x18002f2f6  mov     [rsp+58h+phkResult], rax; lpData
0x18002f2fb  lea     rdx, aSubmitcontrol; "SubmitControl"
0x18002f302  call    cs:__imp_RegQueryValueExW
0x18002f309  nop     dword ptr [rax+rax+00h]
0x18002f30e  mov     rcx, [rbp+hKey]; hKey
0x18002f312  mov     ebx, eax
0x18002f314  call    cs:__imp_RegCloseKey
0x18002f31b  nop     dword ptr [rax+rax+00h]
0x18002f320  test    ebx, ebx
0x18002f322  jnz     short loc_18002F330
0x18002f324  cmp     [rbp+Type], 4
0x18002f328  jnz     short loc_18002F330
0x18002f32a  cmp     [rbp+cbData], 4
0x18002f32e  jz      short loc_18002F337
0x18002f330  mov     [rbp+Data], 0
0x18002f337  call    NetpCreateWellKnownSids
0x18002f33c  test    eax, eax
0x18002f33e  jns     short loc_18002F349
0x18002f340  mov     ecx, eax
0x18002f342  call    NetpNtStatusToApiStatus
0x18002f347  jmp     short loc_18002F395
0x18002f349  mov     edx, [rbp+Data]
0x18002f34c  lea     rax, AliasAdminsSid
0x18002f353  mov     ecx, 10000000h
0x18002f358  mov     [rbp+var_20], rax
0x18002f35c  and     edx, 1
0x18002f35f  mov     [rbp+var_24], ecx
0x18002f362  lea     rax, AliasSystemOpsSid
0x18002f369  mov     [rbp+var_14], ecx
0x18002f36c  inc     edx
0x18002f36e  mov     [rbp+var_10], rax
0x18002f372  lea     rcx, [rbp+var_28]
0x18002f376  mov     [rbp+var_28], 0
0x18002f37c  mov     [rbp+var_26], 0
0x18002f380  mov     [rbp+var_18], 0
0x18002f386  mov     [rbp+var_16], 0
0x18002f38a  call    NetpCreateSecurityObject
0x18002f38f  test    eax, eax
0x18002f391  js      short loc_18002F340
0x18002f393  xor     eax, eax
0x18002f395  add     rsp, 58h
0x18002f399  pop     rbx
0x18002f39a  pop     rbp
0x18002f39b  retn
```
