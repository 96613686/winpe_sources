# IsValidThemepackItemPath(ushort const *)

- ea: `0x18001a3e8`
- end: `0x18001a492`
- name: `?IsValidThemepackItemPath@@YA_NPEBG@Z`
- size: `170`
- prototype: `bool __fastcall(LPCWCH lpString2)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180067e40`
- `0x180067fb0`

## callees

- `0x18001a3e8`
- `0x18001a498`
- `0x1800358c0`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x18001a44c`
- `SHLWAPI!PathIsRelativeW` at `0x18001a44c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a484`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a484`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001a463`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001a463`

## pseudocode

```c
bool __fastcall IsValidThemepackItemPath(LPCWCH lpString2)
{
  char v2; // di
  WCHAR pszPathOut[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = 0;
  if ( *lpString2
    && ValidatePathChars(lpString2)
    && PathIsRelativeW(lpString2)
    && PathCchCanonicalize(pszPathOut, 0x104u, lpString2) >= 0 )
  {
    return CompareStringOrdinal(pszPathOut, -1, lpString2, -1, 1) == 2;
  }
  return v2;
}

```

## disassembly

```asm
0x18001a3e8  mov     [rsp+arg_8], rbx
0x18001a3ed  mov     [rsp+arg_10], rsi
0x18001a3f2  push    rdi
0x18001a3f3  sub     rsp, 250h
0x18001a3fa  mov     rax, cs:__security_cookie
0x18001a401  xor     rax, rsp
0x18001a404  mov     [rsp+258h+var_18], rax
0x18001a40c  xor     esi, esi
0x18001a40e  mov     rbx, rcx
0x18001a411  mov     edi, esi
0x18001a413  cmp     [rcx], si
0x18001a416  jz      short loc_18001A421
0x18001a418  call    ?ValidatePathChars@@YA_NPEBG@Z; ValidatePathChars(ushort const *)
0x18001a41d  test    al, al
0x18001a41f  jnz     short loc_18001A449
0x18001a421  mov     al, dil
0x18001a424  mov     rcx, [rsp+258h+var_18]
0x18001a42c  xor     rcx, rsp; StackCookie
0x18001a42f  call    __security_check_cookie
0x18001a434  lea     r11, [rsp+258h+var_8]
0x18001a43c  mov     rbx, [r11+18h]
0x18001a440  mov     rsi, [r11+20h]
0x18001a444  mov     rsp, r11
0x18001a447  pop     rdi
0x18001a448  retn
0x18001a449  mov     rcx, rbx; pszPath
0x18001a44c  call    cs:__imp_PathIsRelativeW
0x18001a452  test    eax, eax
0x18001a454  jz      short loc_18001A421
0x18001a456  mov     r8, rbx; pszPathIn
0x18001a459  lea     rcx, [rsp+258h+pszPathOut]; pszPathOut
0x18001a45e  mov     edx, 104h; cchPathOut
0x18001a463  call    cs:__imp_PathCchCanonicalize
0x18001a469  test    eax, eax
0x18001a46b  js      short loc_18001A421
0x18001a46d  or      edx, 0FFFFFFFFh; cchCount1
0x18001a470  lea     rcx, [rsp+258h+pszPathOut]; lpString1
0x18001a475  mov     esi, 1
0x18001a47a  mov     r9d, edx; cchCount2
0x18001a47d  mov     r8, rbx; lpString2
0x18001a480  mov     [rsp+258h+bIgnoreCase], esi; bIgnoreCase
0x18001a484  call    cs:__imp_CompareStringOrdinal
0x18001a48a  cmp     eax, 2
0x18001a48d  cmovz   edi, esi
0x18001a490  jmp     short loc_18001A421
```
