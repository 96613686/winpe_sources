# RegisterProgID

- ea: `0x18002d9c4`
- end: `0x18002dc9e`
- name: `RegisterProgID`
- size: `730`
- prototype: `__int64 __usercall@<rax>(BYTE *lpData@<rcx>, BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002d5b0`

## callees

- `0x18000d2c0`
- `0x180018460`
- `0x18002d9c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002db07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002db4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dba5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dc0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dc51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002db07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002db4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dba5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dc0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dc51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc69`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002da1d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002da59`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002da1d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002da59`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002da6a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002dc73`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002dc7d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002da6a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002dc73`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002dc7d`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002dac3`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002db1c`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002db72`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002dbd1`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002dc21`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002dac3`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002db1c`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002db72`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002dbd1`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002dc21`

## string_xrefs

- `0x18002db11`: `CLSID`
- `0x18002dc16`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegisterProgID(BYTE *lpData, const BYTE *a2, const unsigned __int16 *a3, const BYTE *a4, BYTE *a5)
{
  __int64 v7; // rbx
  __int64 v8; // rax
  void *v9; // rsi
  __int64 v11; // rcx
  unsigned __int64 v12; // r13
  unsigned __int16 *v13; // r15
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-10h]

  phkResult = 0;
  hKey = 0;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  v20 = (unsigned int)(v8 + 18);
  v9 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v20, 2u));
  if ( !v9 )
    return 2147942414LL;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)&a5[2 * v11] );
  v12 = (unsigned int)(v11 + 18);
  v13 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v12, 2u));
  if ( !v13 )
  {
    CWin32DefaultArena::WbemMemFree(v9);
    return 2147942414LL;
  }
  StringCchCopyW((unsigned __int16 *)v9, v20, L"SOFTWARE\\CLASSES\\");
  StringCchCatW((unsigned __int16 *)v9, v20, a3);
  StringCchCopyW(v13, v12, L"SOFTWARE\\CLASSES\\");
  StringCchCatW(v13, v12, (const unsigned __int16 *)a5);
  if ( !RegCreateKeyW(HKEY_LOCAL_MACHINE, (LPCWSTR)v9, &phkResult) )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&a2[2 * v14] );
    RegSetValueExW(phkResult, 0, 0, 1u, a2, 2 * v14 + 2);
    if ( !RegCreateKeyW(phkResult, L"CLSID", &hKey) )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&lpData[2 * v15] );
      RegSetValueExW(hKey, 0, 0, 1u, lpData, 2 * v15 + 2);
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( !RegCreateKeyW(phkResult, L"CurVer", &hKey) )
    {
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)&a5[2 * v16] );
      RegSetValueExW(hKey, 0, 0, 1u, a5, 2 * v16 + 2);
      RegCloseKey(hKey);
      hKey = 0;
    }
    RegCloseKey(phkResult);
  }
  if ( !RegCreateKeyW(HKEY_LOCAL_MACHINE, v13, &phkResult) )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)&a4[2 * v17] );
    RegSetValueExW(phkResult, 0, 0, 1u, a4, 2 * v17 + 2);
    if ( !RegCreateKeyW(phkResult, L"CLSID", &hKey) )
    {
      do
        ++v7;
      while ( *(_WORD *)&lpData[2 * v7] );
      RegSetValueExW(hKey, 0, 0, 1u, lpData, 2 * v7 + 2);
      RegCloseKey(hKey);
      hKey = 0;
    }
    RegCloseKey(phkResult);
  }
  CWin32DefaultArena::WbemMemFree(v9);
  CWin32DefaultArena::WbemMemFree(v13);
  return 0;
}

```

## disassembly

```asm
0x18002d9c4  mov     [rsp-38h+arg_0], rbx
0x18002d9c9  mov     [rsp-38h+arg_18], r9
0x18002d9ce  mov     [rsp-38h+arg_8], rdx
0x18002d9d3  push    rbp
0x18002d9d4  push    rsi
0x18002d9d5  push    rdi
0x18002d9d6  push    r12
0x18002d9d8  push    r13
0x18002d9da  push    r14
0x18002d9dc  push    r15
0x18002d9de  mov     rbp, rsp
0x18002d9e1  sub     rsp, 50h
0x18002d9e5  mov     r12, r8
0x18002d9e8  mov     r14, rcx
0x18002d9eb  xor     r15d, r15d
0x18002d9ee  mov     [rbp+phkResult], r15
0x18002d9f2  mov     [rbp+hKey], r15
0x18002d9f6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002d9fa  mov     rax, rbx
0x18002d9fd  inc     rax
0x18002da00  cmp     [r8+rax*2], r15w
0x18002da05  jnz     short loc_18002D9FD
0x18002da07  lea     ecx, [rax+12h]
0x18002da0a  mov     [rbp+var_10], rcx
0x18002da0e  mov     eax, 2
0x18002da13  mul     rcx
0x18002da16  cmovb   rax, rbx
0x18002da1a  mov     rcx, rax
0x18002da1d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002da23  mov     rsi, rax
0x18002da26  test    rax, rax
0x18002da29  jnz     short loc_18002DA35
0x18002da2b  mov     eax, 8007000Eh
0x18002da30  jmp     loc_18002DC86
0x18002da35  mov     rdi, [rbp+arg_20]
0x18002da39  mov     rcx, rbx
0x18002da3c  inc     rcx
0x18002da3f  cmp     [rdi+rcx*2], r15w
0x18002da44  jnz     short loc_18002DA3C
0x18002da46  lea     r13d, [rcx+12h]
0x18002da4a  mov     eax, 2
0x18002da4f  mul     r13
0x18002da52  cmovb   rax, rbx
0x18002da56  mov     rcx, rax
0x18002da59  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002da5f  mov     r15, rax
0x18002da62  test    rax, rax
0x18002da65  jnz     short loc_18002DA73
0x18002da67  mov     rcx, rsi
0x18002da6a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002da70  nop
0x18002da71  jmp     short loc_18002DA2B
0x18002da73  lea     r8, aSoftwareClasse_0; "SOFTWARE\\CLASSES\\"
0x18002da7a  mov     rdx, [rbp+var_10]; unsigned __int64
0x18002da7e  mov     rcx, rsi; unsigned __int16 *
0x18002da81  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002da86  mov     r8, r12; unsigned __int16 *
0x18002da89  mov     rdx, [rbp+var_10]; unsigned __int64
0x18002da8d  mov     rcx, rsi; unsigned __int16 *
0x18002da90  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002da95  lea     r8, aSoftwareClasse_0; "SOFTWARE\\CLASSES\\"
0x18002da9c  mov     rdx, r13; unsigned __int64
0x18002da9f  mov     rcx, r15; unsigned __int16 *
0x18002daa2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002daa7  mov     r8, rdi; unsigned __int16 *
0x18002daaa  mov     rdx, r13; unsigned __int64
0x18002daad  mov     rcx, r15; unsigned __int16 *
0x18002dab0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002dab5  lea     r8, [rbp+phkResult]; phkResult
0x18002dab9  mov     rdx, rsi; lpSubKey
0x18002dabc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dac3  call    cs:__imp_RegCreateKeyW
0x18002dac9  mov     r13d, 1
0x18002dacf  xor     r12d, r12d
0x18002dad2  test    eax, eax
0x18002dad4  jnz     loc_18002DBC3
0x18002dada  mov     rax, rbx
0x18002dadd  mov     rcx, [rbp+arg_8]
0x18002dae1  inc     rax
0x18002dae4  cmp     [rcx+rax*2], r12w
0x18002dae9  jnz     short loc_18002DAE1
0x18002daeb  lea     eax, ds:2[rax*2]
0x18002daf2  mov     [rsp+50h+cbData], eax; cbData
0x18002daf6  mov     [rsp+50h+lpData], rcx; lpData
0x18002dafb  mov     r9d, r13d; dwType
0x18002dafe  xor     r8d, r8d; Reserved
0x18002db01  xor     edx, edx; lpValueName
0x18002db03  mov     rcx, [rbp+phkResult]; hKey
0x18002db07  call    cs:__imp_RegSetValueExW
0x18002db0d  lea     r8, [rbp+hKey]; phkResult
0x18002db11  lea     rdx, aClsid; "CLSID"
0x18002db18  mov     rcx, [rbp+phkResult]; hKey
0x18002db1c  call    cs:__imp_RegCreateKeyW
0x18002db22  test    eax, eax
0x18002db24  jnz     short loc_18002DB63
0x18002db26  mov     rax, rbx
0x18002db29  inc     rax
0x18002db2c  cmp     [r14+rax*2], r12w
0x18002db31  jnz     short loc_18002DB29
0x18002db33  lea     eax, ds:2[rax*2]
0x18002db3a  mov     [rsp+50h+cbData], eax; cbData
0x18002db3e  mov     [rsp+50h+lpData], r14; lpData
0x18002db43  mov     r9d, r13d; dwType
0x18002db46  xor     r8d, r8d; Reserved
0x18002db49  xor     edx, edx; lpValueName
0x18002db4b  mov     rcx, [rbp+hKey]; hKey
0x18002db4f  call    cs:__imp_RegSetValueExW
0x18002db55  mov     rcx, [rbp+hKey]; hKey
0x18002db59  call    cs:__imp_RegCloseKey
0x18002db5f  mov     [rbp+hKey], r12
0x18002db63  lea     r8, [rbp+hKey]; phkResult
0x18002db67  lea     rdx, aCurver; "CurVer"
0x18002db6e  mov     rcx, [rbp+phkResult]; hKey
0x18002db72  call    cs:__imp_RegCreateKeyW
0x18002db78  test    eax, eax
0x18002db7a  jnz     short loc_18002DBB9
0x18002db7c  mov     rax, rbx
0x18002db7f  inc     rax
0x18002db82  cmp     [rdi+rax*2], r12w
0x18002db87  jnz     short loc_18002DB7F
0x18002db89  lea     eax, ds:2[rax*2]
0x18002db90  mov     [rsp+50h+cbData], eax; cbData
0x18002db94  mov     [rsp+50h+lpData], rdi; lpData
0x18002db99  mov     r9d, r13d; dwType
0x18002db9c  xor     r8d, r8d; Reserved
0x18002db9f  xor     edx, edx; lpValueName
0x18002dba1  mov     rcx, [rbp+hKey]; hKey
0x18002dba5  call    cs:__imp_RegSetValueExW
0x18002dbab  mov     rcx, [rbp+hKey]; hKey
0x18002dbaf  call    cs:__imp_RegCloseKey
0x18002dbb5  mov     [rbp+hKey], r12
0x18002dbb9  mov     rcx, [rbp+phkResult]; hKey
0x18002dbbd  call    cs:__imp_RegCloseKey
0x18002dbc3  lea     r8, [rbp+phkResult]; phkResult
0x18002dbc7  mov     rdx, r15; lpSubKey
0x18002dbca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dbd1  call    cs:__imp_RegCreateKeyW
0x18002dbd7  test    eax, eax
0x18002dbd9  jnz     loc_18002DC70
0x18002dbdf  mov     rax, rbx
0x18002dbe2  mov     rcx, [rbp+arg_18]
0x18002dbe6  inc     rax
0x18002dbe9  cmp     [rcx+rax*2], r12w
0x18002dbee  jnz     short loc_18002DBE6
0x18002dbf0  lea     eax, ds:2[rax*2]
0x18002dbf7  mov     [rsp+50h+cbData], eax; cbData
0x18002dbfb  mov     [rsp+50h+lpData], rcx; lpData
0x18002dc00  mov     r9d, r13d; dwType
0x18002dc03  xor     r8d, r8d; Reserved
0x18002dc06  xor     edx, edx; lpValueName
0x18002dc08  mov     rcx, [rbp+phkResult]; hKey
0x18002dc0c  call    cs:__imp_RegSetValueExW
0x18002dc12  lea     r8, [rbp+hKey]; phkResult
0x18002dc16  lea     rdx, aClsid; "CLSID"
0x18002dc1d  mov     rcx, [rbp+phkResult]; hKey
0x18002dc21  call    cs:__imp_RegCreateKeyW
0x18002dc27  test    eax, eax
0x18002dc29  jnz     short loc_18002DC65
0x18002dc2b  inc     rbx
0x18002dc2e  cmp     [r14+rbx*2], r12w
0x18002dc33  jnz     short loc_18002DC2B
0x18002dc35  lea     eax, ds:2[rbx*2]
0x18002dc3c  mov     [rsp+50h+cbData], eax; cbData
0x18002dc40  mov     [rsp+50h+lpData], r14; lpData
0x18002dc45  mov     r9d, r13d; dwType
0x18002dc48  xor     r8d, r8d; Reserved
0x18002dc4b  xor     edx, edx; lpValueName
0x18002dc4d  mov     rcx, [rbp+hKey]; hKey
0x18002dc51  call    cs:__imp_RegSetValueExW
0x18002dc57  mov     rcx, [rbp+hKey]; hKey
0x18002dc5b  call    cs:__imp_RegCloseKey
0x18002dc61  mov     [rbp+hKey], r12
0x18002dc65  mov     rcx, [rbp+phkResult]; hKey
0x18002dc69  call    cs:__imp_RegCloseKey
0x18002dc6f  nop
0x18002dc70  mov     rcx, rsi
0x18002dc73  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002dc79  nop
0x18002dc7a  mov     rcx, r15
0x18002dc7d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002dc83  nop
0x18002dc84  xor     eax, eax
0x18002dc86  mov     rbx, [rsp+50h+arg_0]
0x18002dc8e  add     rsp, 50h
0x18002dc92  pop     r15
0x18002dc94  pop     r14
0x18002dc96  pop     r13
0x18002dc98  pop     r12
0x18002dc9a  pop     rdi
0x18002dc9b  pop     rsi
0x18002dc9c  pop     rbp
0x18002dc9d  retn
```
