# CreateAreaCodeRule

- ea: `0x18003f10c`
- end: `0x18003f2a9`
- name: `CreateAreaCodeRule`
- size: `413`
- prototype: `__int64(HKEY hKey, int, const BYTE *, const BYTE *, BYTE *lpData, DWORD cbData, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003e9a4`

## callees

- `0x180001600`
- `0x18001c8a4`
- `0x18003f10c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f283`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f283`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f19a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f19a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f1e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f21c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f248`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f272`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f1e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f21c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f248`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f272`

## pseudocode

```c
__int64 CreateAreaCodeRule(HKEY hKey, int a2, const BYTE *a3, const BYTE *a4, BYTE *lpData, DWORD cbData, ...)
{
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // rax
  HKEY hKeya; // [rsp+50h] [rbp-31h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-29h] BYREF
  wchar_t pszDest[20]; // [rsp+60h] [rbp-21h] BYREF
  va_list va; // [rsp+100h] [rbp+7Fh] BYREF

  va_start(va, cbData);
  dwDisposition = 0;
  hKeya = 0;
  StringCbPrintfW(pszDest, 0x22u, L"%s%d", L"Rule", a2);
  v9 = RegCreateKeyExW(hKey, pszDest, 0, 0, 0, 0x20006u, 0, &hKeya, &dwDisposition);
  if ( !v9 )
  {
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&a3[2 * v11] );
    v9 = RegSetValueExW(hKeya, L"AreaCodeToCall", 0, 1u, a3, 2 * v11 + 2);
    if ( !v9 )
    {
      do
        ++v10;
      while ( *(_WORD *)&a4[2 * v10] );
      v9 = RegSetValueExW(hKeya, L"NumberToDial", 0, 1u, a4, 2 * v10 + 2);
      if ( !v9 )
      {
        v9 = RegSetValueExW(hKeya, L"Flags", 0, 4u, (const BYTE *)va, 4u);
        if ( !v9 )
          v9 = RegSetValueExW(hKeya, L"Prefixes", 0, 7u, lpData, cbData);
      }
    }
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  return v9;
}

```

## disassembly

```asm
0x18003f10c  push    rbp
0x18003f10e  push    rbx
0x18003f10f  push    rsi
0x18003f110  push    rdi
0x18003f111  push    r12
0x18003f113  push    r14
0x18003f115  push    r15
0x18003f117  lea     rbp, [rsp-0Fh]
0x18003f11c  sub     rsp, 90h
0x18003f123  mov     rax, cs:__security_cookie
0x18003f12a  xor     rax, rsp
0x18003f12d  mov     [rbp+3Fh+var_38], rax
0x18003f131  mov     r15, [rbp+3Fh+lpData]
0x18003f135  xor     r12d, r12d
0x18003f138  mov     r14, r9
0x18003f13b  mov     [rsp+0C0h+dwOptions], edx
0x18003f13f  mov     rsi, r8
0x18003f142  mov     [rbp+3Fh+dwDisposition], r12d
0x18003f146  mov     rbx, rcx
0x18003f149  mov     [rbp+3Fh+hKey], r12
0x18003f14d  lea     edx, [r12+22h]; cbDest
0x18003f152  lea     r9, aRule; "Rule"
0x18003f159  lea     r8, aSD; "%s%d"
0x18003f160  lea     rcx, [rbp+3Fh+pszDest]; pszDest
0x18003f164  call    StringCbPrintfW
0x18003f169  lea     rax, [rbp+3Fh+dwDisposition]
0x18003f16d  xor     r9d, r9d; lpClass
0x18003f170  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18003f175  lea     rdx, [rbp+3Fh+pszDest]; lpSubKey
0x18003f179  lea     rax, [rbp+3Fh+hKey]
0x18003f17d  xor     r8d, r8d; Reserved
0x18003f180  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18003f185  mov     rcx, rbx; hKey
0x18003f188  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18003f18d  mov     [rsp+0C0h+samDesired], 20006h; samDesired
0x18003f195  mov     [rsp+0C0h+dwOptions], r12d; dwOptions
0x18003f19a  call    cs:__imp_RegCreateKeyExW
0x18003f1a0  mov     ebx, eax
0x18003f1a2  test    eax, eax
0x18003f1a4  jnz     loc_18003F27A
0x18003f1aa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003f1ae  mov     rax, rdi
0x18003f1b1  inc     rax
0x18003f1b4  cmp     [rsi+rax*2], r12w
0x18003f1b9  jnz     short loc_18003F1B1
0x18003f1bb  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18003f1bf  lea     eax, ds:2[rax*2]
0x18003f1c6  mov     [rsp+0C0h+samDesired], eax; cbData
0x18003f1ca  lea     rdx, aAreacodetocall; "AreaCodeToCall"
0x18003f1d1  mov     qword ptr [rsp+0C0h+dwOptions], rsi; lpData
0x18003f1d6  xor     r8d, r8d; Reserved
0x18003f1d9  mov     esi, 1
0x18003f1de  mov     r9d, esi; dwType
0x18003f1e1  call    cs:__imp_RegSetValueExW
0x18003f1e7  mov     ebx, eax
0x18003f1e9  test    eax, eax
0x18003f1eb  jnz     loc_18003F27A
0x18003f1f1  inc     rdi
0x18003f1f4  cmp     [r14+rdi*2], r12w
0x18003f1f9  jnz     short loc_18003F1F1
0x18003f1fb  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18003f1ff  lea     eax, ds:2[rdi*2]
0x18003f206  mov     [rsp+0C0h+samDesired], eax; cbData
0x18003f20a  lea     rdx, aNumbertodial; "NumberToDial"
0x18003f211  mov     r9d, esi; dwType
0x18003f214  mov     qword ptr [rsp+0C0h+dwOptions], r14; lpData
0x18003f219  xor     r8d, r8d; Reserved
0x18003f21c  call    cs:__imp_RegSetValueExW
0x18003f222  mov     ebx, eax
0x18003f224  test    eax, eax
0x18003f226  jnz     short loc_18003F27A
0x18003f228  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18003f22c  lea     r9d, [rax+4]; dwType
0x18003f230  lea     rax, [rbp+3Fh+Data]
0x18003f234  mov     [rsp+0C0h+samDesired], r9d; cbData
0x18003f239  xor     r8d, r8d; Reserved
0x18003f23c  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x18003f241  lea     rdx, aFlags; "Flags"
0x18003f248  call    cs:__imp_RegSetValueExW
0x18003f24e  mov     ebx, eax
0x18003f250  test    eax, eax
0x18003f252  jnz     short loc_18003F27A
0x18003f254  mov     eax, [rbp+3Fh+cbData]
0x18003f257  lea     r9d, [rbx+7]; dwType
0x18003f25b  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18003f25f  lea     rdx, aPrefixes; "Prefixes"
0x18003f266  mov     [rsp+0C0h+samDesired], eax; cbData
0x18003f26a  xor     r8d, r8d; Reserved
0x18003f26d  mov     qword ptr [rsp+0C0h+dwOptions], r15; lpData
0x18003f272  call    cs:__imp_RegSetValueExW
0x18003f278  mov     ebx, eax
0x18003f27a  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18003f27e  test    rcx, rcx
0x18003f281  jz      short loc_18003F289
0x18003f283  call    cs:__imp_RegCloseKey
0x18003f289  mov     eax, ebx
0x18003f28b  mov     rcx, [rbp+3Fh+var_38]
0x18003f28f  xor     rcx, rsp; StackCookie
0x18003f292  call    __security_check_cookie
0x18003f297  add     rsp, 90h
0x18003f29e  pop     r15
0x18003f2a0  pop     r14
0x18003f2a2  pop     r12
0x18003f2a4  pop     rdi
0x18003f2a5  pop     rsi
0x18003f2a6  pop     rbx
0x18003f2a7  pop     rbp
0x18003f2a8  retn
```
