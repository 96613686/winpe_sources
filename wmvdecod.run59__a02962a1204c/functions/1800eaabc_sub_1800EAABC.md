# sub_1800EAABC

- ea: `0x1800eaabc`
- end: `0x1800eac63`
- name: `sub_1800EAABC`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800eb724`

## callees

- `0x1800eaabc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eabb3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eabfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eabb3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eabfb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eab06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eab3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eab76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eab06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eab3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eab76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac47`

## string_xrefs

- `0x1800eabac`: `NumThreads`

## pseudocode

```c
__int64 __fastcall sub_1800EAABC(int a1, BYTE *a2)
{
  unsigned int v2; // ebx
  HKEY v6; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD Type; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  cbData = 4;
  Type = 0;
  v6 = 0;
  phkResult = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE", 0, 1u, &hKey)
    || !hKey
    || RegOpenKeyExW(hKey, L"Microsoft", 0, 1u, &phkResult)
    || !phkResult
    || RegOpenKeyExW(phkResult, L"Scrunch", 0, 1u, &v6) )
  {
    goto LABEL_15;
  }
  if ( !a1 )
  {
    if ( !RegQueryValueExW(v6, L"CPU Downgrade Level", 0, &Type, a2, &cbData) && Type == 4 )
      goto LABEL_15;
LABEL_14:
    v2 = -1;
    goto LABEL_15;
  }
  if ( a1 != 1 || RegQueryValueExW(v6, L"NumThreads", 0, &Type, a2, &cbData) || Type != 4 )
    goto LABEL_14;
  if ( (unsigned int)(*(_DWORD *)a2 - 65) <= 0xFFFFFFBD )
    *(_DWORD *)a2 = 64;
LABEL_15:
  if ( v6 )
    RegCloseKey(v6);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1800eaabc  mov     [rsp-18h+arg_0], rbx
0x1800eaac1  push    rbp
0x1800eaac2  push    rsi
0x1800eaac3  push    rdi
0x1800eaac4  mov     rbp, rsp
0x1800eaac7  sub     rsp, 50h
0x1800eaacb  xor     ebx, ebx
0x1800eaacd  mov     [rbp+cbData], 4
0x1800eaad4  mov     rsi, rdx
0x1800eaad7  mov     [rbp+Type], ebx
0x1800eaada  mov     edi, ecx
0x1800eaadc  mov     [rbp+var_20], rbx
0x1800eaae0  lea     rax, [rbp+hKey]
0x1800eaae4  mov     [rbp+var_18], rbx
0x1800eaae8  lea     r9d, [rbx+1]; samDesired
0x1800eaaec  mov     [rbp+hKey], rbx
0x1800eaaf0  xor     r8d, r8d; ulOptions
0x1800eaaf3  mov     [rsp+50h+phkResult], rax; phkResult
0x1800eaaf8  lea     rdx, aSoftware; "SOFTWARE"
0x1800eaaff  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800eab06  call    cs:RegOpenKeyExW
0x1800eab0d  nop     dword ptr [rax+rax+00h]
0x1800eab12  test    eax, eax
0x1800eab14  jnz     loc_1800EAC14
0x1800eab1a  mov     rcx, [rbp+hKey]; hKey
0x1800eab1e  test    rcx, rcx
0x1800eab21  jz      loc_1800EAC14
0x1800eab27  lea     rax, [rbp+var_18]
0x1800eab2b  xor     r8d, r8d; ulOptions
0x1800eab2e  lea     r9d, [rbx+1]; samDesired
0x1800eab32  mov     [rsp+50h+phkResult], rax; phkResult
0x1800eab37  lea     rdx, aMicrosoft; "Microsoft"
0x1800eab3e  call    cs:RegOpenKeyExW
0x1800eab45  nop     dword ptr [rax+rax+00h]
0x1800eab4a  test    eax, eax
0x1800eab4c  jnz     loc_1800EAC14
0x1800eab52  mov     rcx, [rbp+var_18]; hKey
0x1800eab56  test    rcx, rcx
0x1800eab59  jz      loc_1800EAC14
0x1800eab5f  lea     rax, [rbp+var_20]
0x1800eab63  xor     r8d, r8d; ulOptions
0x1800eab66  lea     r9d, [rbx+1]; samDesired
0x1800eab6a  mov     [rsp+50h+phkResult], rax; phkResult
0x1800eab6f  lea     rdx, aScrunch; "Scrunch"
0x1800eab76  call    cs:RegOpenKeyExW
0x1800eab7d  nop     dword ptr [rax+rax+00h]
0x1800eab82  test    eax, eax
0x1800eab84  jnz     loc_1800EAC14
0x1800eab8a  test    edi, edi
0x1800eab8c  jz      short loc_1800EABDB
0x1800eab8e  cmp     edi, 1
0x1800eab91  jnz     short loc_1800EAC11
0x1800eab93  mov     rcx, [rbp+var_20]; hKey
0x1800eab97  lea     rax, [rbp+cbData]
0x1800eab9b  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800eaba0  lea     r9, [rbp+Type]; lpType
0x1800eaba4  xor     r8d, r8d; lpReserved
0x1800eaba7  mov     [rsp+50h+phkResult], rsi; lpData
0x1800eabac  lea     rdx, aNumthreads; "NumThreads"
0x1800eabb3  call    cs:RegQueryValueExW
0x1800eabba  nop     dword ptr [rax+rax+00h]
0x1800eabbf  test    eax, eax
0x1800eabc1  jnz     short loc_1800EAC11
0x1800eabc3  cmp     [rbp+Type], 4
0x1800eabc7  jnz     short loc_1800EAC11
0x1800eabc9  mov     eax, [rsi]
0x1800eabcb  sub     eax, 41h ; 'A'
0x1800eabce  cmp     eax, 0FFFFFFBDh
0x1800eabd1  ja      short loc_1800EAC14
0x1800eabd3  mov     dword ptr [rsi], 40h ; '@'
0x1800eabd9  jmp     short loc_1800EAC14
0x1800eabdb  mov     rcx, [rbp+var_20]; hKey
0x1800eabdf  lea     rax, [rbp+cbData]
0x1800eabe3  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800eabe8  lea     r9, [rbp+Type]; lpType
0x1800eabec  xor     r8d, r8d; lpReserved
0x1800eabef  mov     [rsp+50h+phkResult], rsi; lpData
0x1800eabf4  lea     rdx, aCpuDowngradeLe; "CPU Downgrade Level"
0x1800eabfb  call    cs:RegQueryValueExW
0x1800eac02  nop     dword ptr [rax+rax+00h]
0x1800eac07  test    eax, eax
0x1800eac09  jnz     short loc_1800EAC11
0x1800eac0b  cmp     [rbp+Type], 4
0x1800eac0f  jz      short loc_1800EAC14
0x1800eac11  or      ebx, 0FFFFFFFFh
0x1800eac14  mov     rcx, [rbp+var_20]; hKey
0x1800eac18  test    rcx, rcx
0x1800eac1b  jz      short loc_1800EAC29
0x1800eac1d  call    cs:RegCloseKey
0x1800eac24  nop     dword ptr [rax+rax+00h]
0x1800eac29  mov     rcx, [rbp+var_18]; hKey
0x1800eac2d  test    rcx, rcx
0x1800eac30  jz      short loc_1800EAC3E
0x1800eac32  call    cs:RegCloseKey
0x1800eac39  nop     dword ptr [rax+rax+00h]
0x1800eac3e  mov     rcx, [rbp+hKey]; hKey
0x1800eac42  test    rcx, rcx
0x1800eac45  jz      short loc_1800EAC53
0x1800eac47  call    cs:RegCloseKey
0x1800eac4e  nop     dword ptr [rax+rax+00h]
0x1800eac53  mov     eax, ebx
0x1800eac55  mov     rbx, [rsp+50h+arg_0]
0x1800eac5a  add     rsp, 50h
0x1800eac5e  pop     rdi
0x1800eac5f  pop     rsi
0x1800eac60  pop     rbp
0x1800eac61  retn
```
