# ValidateCopyUnicodeToUnicode

- ea: `0x18000869c`
- end: `0x1800086d1`
- name: `ValidateCopyUnicodeToUnicode`
- size: `53`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, size_t cchDest, STRSAFE_LPWSTR pszDest)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b80`
- `0x18000996c`

## callees

- `0x180004150`
- `0x18000869c`

## pseudocode

```c
__int64 __fastcall ValidateCopyUnicodeToUnicode(STRSAFE_LPCWSTR pszSrc, size_t cchDest, STRSAFE_LPWSTR pszDest)
{
  unsigned __int64 v3; // rax

  v3 = -1;
  do
    ++v3;
  while ( pszSrc[v3] );
  if ( v3 >= (unsigned int)cchDest )
    return 0;
  StringCchCopyW(pszDest, (unsigned int)cchDest, pszSrc);
  return 1;
}

```

## disassembly

```asm
0x18000869c  sub     rsp, 28h
0x1800086a0  mov     r9, r8
0x1800086a3  mov     edx, edx; cchDest
0x1800086a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800086a9  inc     rax
0x1800086ac  cmp     word ptr [rcx+rax*2], 0
0x1800086b1  jnz     short loc_1800086A9
0x1800086b3  cmp     rax, rdx
0x1800086b6  jb      short loc_1800086BC
0x1800086b8  xor     eax, eax
0x1800086ba  jmp     short loc_1800086CC
0x1800086bc  mov     r8, rcx; pszSrc
0x1800086bf  mov     rcx, r9; pszDest
0x1800086c2  call    StringCchCopyW
0x1800086c7  mov     eax, 1
0x1800086cc  add     rsp, 28h
0x1800086d0  retn
```
