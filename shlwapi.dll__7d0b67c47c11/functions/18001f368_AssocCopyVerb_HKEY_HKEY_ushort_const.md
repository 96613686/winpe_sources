# _AssocCopyVerb(HKEY__ *,HKEY__ *,ushort const *)

- ea: `0x18001f368`
- end: `0x18001f44c`
- name: `?_AssocCopyVerb@@YAJPEAUHKEY__@@0PEBG@Z`
- size: `228`
- prototype: `__int64 __fastcall(HKEY hkeySrc, HKEY hKey, LPCWSTR pszSrcSubKey)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001fa90`
- `0x18002094c`

## callees

- `0x180004e64`
- `0x180012550`
- `0x18001f368`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f421`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f3e9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f3e9`
- `api-ms-win-shcore-registry-l1-1-0!SHCopyKeyW` at `0x18001f40c`
- `api-ms-win-shcore-registry-l1-1-0!SHCopyKeyW` at `0x18001f40c`

## pseudocode

```c
__int64 __fastcall _AssocCopyVerb(HKEY hkeySrc, HKEY hKey, LPCWSTR pszSrcSubKey)
{
  unsigned int v6; // edi
  HKEY v7; // rcx
  HKEY hkeyDest; // [rsp+50h] [rbp-248h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-240h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-238h] BYREF

  v6 = 0;
  hkeyDest = 0;
  dwDisposition = 0;
  StringCchPrintfW(SubKey, 0x104u, L"shell\\%s", pszSrcSubKey);
  RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x20006u, 0, &hkeyDest, &dwDisposition);
  v7 = hkeyDest;
  if ( hkeyDest )
  {
    if ( dwDisposition == 1 )
    {
      if ( SHCopyKeyW(hkeySrc, pszSrcSubKey, hkeyDest, 0) )
        v6 = -2147418113;
      v7 = hkeyDest;
    }
    RegCloseKey(v7);
  }
  return v6;
}

```

## disassembly

```asm
0x18001f368  mov     [rsp+arg_18], rbx
0x18001f36d  push    rbp
0x18001f36e  push    rsi
0x18001f36f  push    rdi
0x18001f370  sub     rsp, 280h
0x18001f377  mov     rax, cs:__security_cookie
0x18001f37e  xor     rax, rsp
0x18001f381  mov     [rsp+298h+var_28], rax
0x18001f389  mov     rsi, r8
0x18001f38c  mov     rbx, rdx
0x18001f38f  mov     rbp, rcx
0x18001f392  xor     edi, edi
0x18001f394  mov     r9, r8
0x18001f397  mov     [rsp+298h+hkeyDest], rdi
0x18001f39c  lea     r8, aShellS; "shell\\%s"
0x18001f3a3  mov     [rsp+298h+dwDisposition], edi
0x18001f3a7  mov     edx, 104h; unsigned __int64
0x18001f3ac  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x18001f3b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f3b6  lea     rax, [rsp+298h+dwDisposition]
0x18001f3bb  xor     r9d, r9d; lpClass
0x18001f3be  mov     [rsp+298h+lpdwDisposition], rax; lpdwDisposition
0x18001f3c3  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x18001f3c8  lea     rax, [rsp+298h+hkeyDest]
0x18001f3cd  xor     r8d, r8d; Reserved
0x18001f3d0  mov     [rsp+298h+phkResult], rax; phkResult
0x18001f3d5  mov     rcx, rbx; hKey
0x18001f3d8  mov     [rsp+298h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18001f3dd  mov     [rsp+298h+samDesired], 20006h; samDesired
0x18001f3e5  mov     [rsp+298h+dwOptions], edi; dwOptions
0x18001f3e9  call    cs:__imp_RegCreateKeyExW
0x18001f3ef  mov     rcx, [rsp+298h+hkeyDest]
0x18001f3f4  test    rcx, rcx
0x18001f3f7  jz      short loc_18001F427
0x18001f3f9  cmp     [rsp+298h+dwDisposition], 1
0x18001f3fe  jnz     short loc_18001F421
0x18001f400  mov     r8, rcx; hkeyDest
0x18001f403  xor     r9d, r9d; fReserved
0x18001f406  mov     rcx, rbp; hkeySrc
0x18001f409  mov     rdx, rsi; pszSrcSubKey
0x18001f40c  call    cs:__imp_SHCopyKeyW
0x18001f412  mov     ecx, 8000FFFFh
0x18001f417  test    eax, eax
0x18001f419  cmovnz  edi, ecx
0x18001f41c  mov     rcx, [rsp+298h+hkeyDest]; hKey
0x18001f421  call    cs:__imp_RegCloseKey
0x18001f427  mov     eax, edi
0x18001f429  mov     rcx, [rsp+298h+var_28]
0x18001f431  xor     rcx, rsp; StackCookie
0x18001f434  call    __security_check_cookie
0x18001f439  mov     rbx, [rsp+298h+arg_18]
0x18001f441  add     rsp, 280h
0x18001f448  pop     rdi
0x18001f449  pop     rsi
0x18001f44a  pop     rbp
0x18001f44b  retn
```
