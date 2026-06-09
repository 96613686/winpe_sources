# GetWhqlEnforcementDateTime(_CRYPT_PROVIDER_DATA *)

- ea: `0x180027714`
- end: `0x180027883`
- name: `?GetWhqlEnforcementDateTime@@YAJPEAU_CRYPT_PROVIDER_DATA@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(struct _CRYPT_PROVIDER_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e1c0`

## callees

- `0x180027714`
- `0x18004deb0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800277b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800277b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027779`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027779`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027863`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027863`

## pseudocode

```c
__int64 __fastcall GetWhqlEnforcementDateTime(struct _CRYPT_PROVIDER_DATA *a1)
{
  unsigned int v2; // esi
  unsigned __int64 v3; // rbx
  _QWORD *v4; // rax
  DWORD *padwTrustStepErrors; // rax
  struct _CRYPT_PROVIDER_FUNCTIONS *psPfns; // rax
  DWORD Type; // [rsp+30h] [rbp-19h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-15h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-11h] BYREF
  unsigned __int64 v11; // [rsp+40h] [rbp-9h]
  HKEY hKey; // [rsp+48h] [rbp-1h] BYREF
  __int128 v13; // [rsp+50h] [rbp+7h] BYREF
  __int128 v14; // [rsp+60h] [rbp+17h]

  hKey = 0;
  v11 = 130826016000000000LL;
  v2 = 1;
  v13 = 0;
  v14 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\CI\\Policy", 0, 1u, &hKey)
    || (Type = 0,
        *(_QWORD *)Data = 0,
        cbData = 8,
        RegQueryValueExW(hKey, L"WhqlEnforcementDateTime", 0, &Type, Data, &cbData))
    || Type != 3
    || !*(_QWORD *)Data )
  {
    v3 = v11;
  }
  else
  {
    v3 = v11;
    if ( *(_QWORD *)Data < v11 )
      v3 = *(_QWORD *)Data;
  }
  v4 = (_QWORD *)((__int64 (__fastcall *)(__int64))a1->psPfns->pfnAlloc)(16);
  if ( v4 )
  {
    *v4 = 16;
    v4[1] = v3;
    v2 = 0;
    *((_QWORD *)&v14 + 1) = v4;
    psPfns = a1->psPfns;
    *(_QWORD *)&v13 = 0xAAC56B00000020LL;
    *((_QWORD *)&v13 + 1) = 0xC000C28C11D0CD44uLL;
    *(_QWORD *)&v14 = 0x10EE95C24FLL;
    ((void (__fastcall *)(struct _CRYPT_PROVIDER_DATA *, __int128 *))psPfns->pfnAddPrivData2Chain)(a1, &v13);
  }
  else
  {
    padwTrustStepErrors = a1->padwTrustStepErrors;
    a1->dwError = -2146762751;
    padwTrustStepErrors[31] = -2146762751;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180027714  push    rbp
0x180027716  push    rbx
0x180027717  push    rsi
0x180027718  push    rdi
0x180027719  lea     rbp, [rsp-3Fh]
0x18002771e  sub     rsp, 88h
0x180027725  mov     rax, cs:__security_cookie
0x18002772c  xor     rax, rsp
0x18002772f  mov     [rbp+57h+var_30], rax
0x180027733  xorps   xmm0, xmm0
0x180027736  mov     [rbp+57h+hKey], 0
0x18002773e  mov     rdi, rcx
0x180027741  mov     dword ptr [rbp+57h+var_60], 830F4000h
0x180027748  lea     rax, [rbp+57h+hKey]
0x18002774c  mov     dword ptr [rbp+57h+var_60+4], 1D0C991h
0x180027753  mov     esi, 1
0x180027758  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18002775d  mov     r9d, esi; samDesired
0x180027760  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\CI"...
0x180027767  xor     r8d, r8d; ulOptions
0x18002776a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027771  movups  [rbp+57h+var_50], xmm0
0x180027775  movups  [rbp+57h+var_40], xmm0
0x180027779  call    cs:__imp_RegOpenKeyExW
0x18002777f  test    eax, eax
0x180027781  jnz     short loc_1800277DF
0x180027783  mov     rcx, [rbp+57h+hKey]; hKey
0x180027787  lea     r9, [rbp+57h+Type]; lpType
0x18002778b  mov     [rbp+57h+Type], eax
0x18002778e  lea     rdx, aWhqlenforcemen; "WhqlEnforcementDateTime"
0x180027795  lea     rax, [rbp+57h+cbData]
0x180027799  mov     qword ptr [rbp+57h+Data], 0
0x1800277a1  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x1800277a6  xor     r8d, r8d; lpReserved
0x1800277a9  lea     rax, [rbp+57h+Data]
0x1800277ad  mov     [rbp+57h+cbData], 8
0x1800277b4  mov     [rsp+0A0h+phkResult], rax; lpData
0x1800277b9  call    cs:__imp_RegQueryValueExW
0x1800277bf  test    eax, eax
0x1800277c1  jnz     short loc_1800277DF
0x1800277c3  cmp     [rbp+57h+Type], 3
0x1800277c7  jnz     short loc_1800277DF
0x1800277c9  mov     rax, qword ptr [rbp+57h+Data]
0x1800277cd  test    rax, rax
0x1800277d0  jz      short loc_1800277DF
0x1800277d2  mov     rbx, [rbp+57h+var_60]
0x1800277d6  cmp     rax, rbx
0x1800277d9  cmovb   rbx, rax
0x1800277dd  jmp     short loc_1800277E3
0x1800277df  mov     rbx, [rbp+57h+var_60]
0x1800277e3  mov     rax, [rdi+40h]
0x1800277e7  mov     ecx, 10h
0x1800277ec  mov     rax, [rax+8]
0x1800277f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277f5  test    rax, rax
0x1800277f8  jnz     short loc_18002780B
0x1800277fa  mov     rax, [rdi+50h]
0x1800277fe  mov     ecx, 800B0001h
0x180027803  mov     [rdi+30h], ecx
0x180027806  mov     [rax+7Ch], ecx
0x180027809  jmp     short loc_18002785A
0x18002780b  mov     qword ptr [rax], 10h
0x180027812  lea     rdx, [rbp+57h+var_50]
0x180027816  mov     [rax+8], rbx
0x18002781a  xor     esi, esi
0x18002781c  mov     qword ptr [rbp+57h+var_40+8], rax
0x180027820  mov     rcx, rdi
0x180027823  mov     rax, [rdi+40h]
0x180027827  mov     dword ptr [rbp+57h+var_50], 20h ; ' '
0x18002782e  mov     dword ptr [rbp+57h+var_50+4], 0AAC56Bh
0x180027835  mov     dword ptr [rbp+57h+var_50+8], 11D0CD44h
0x18002783c  mov     dword ptr [rbp+57h+var_50+0Ch], 0C000C28Ch
0x180027843  mov     dword ptr [rbp+57h+var_40], 0EE95C24Fh
0x18002784a  mov     dword ptr [rbp+57h+var_40+4], 10h
0x180027851  mov     rax, [rax+30h]
0x180027855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002785a  mov     rcx, [rbp+57h+hKey]; hKey
0x18002785e  test    rcx, rcx
0x180027861  jz      short loc_180027869
0x180027863  call    cs:__imp_RegCloseKey
0x180027869  mov     eax, esi
0x18002786b  mov     rcx, [rbp+57h+var_30]
0x18002786f  xor     rcx, rsp; StackCookie
0x180027872  call    __security_check_cookie
0x180027877  add     rsp, 88h
0x18002787e  pop     rdi
0x18002787f  pop     rsi
0x180027880  pop     rbx
0x180027881  pop     rbp
0x180027882  retn
```
