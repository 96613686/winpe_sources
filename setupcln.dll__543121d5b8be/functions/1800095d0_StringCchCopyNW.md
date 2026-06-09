# StringCchCopyNW

- ea: `0x1800095d0`
- end: `0x18000961b`
- name: `StringCchCopyNW`
- size: `75`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180009528`
- `0x18000a780`
- `0x18000aa40`

## callees

- `0x1800095d0`
- `0x1800096f0`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)
{
  HRESULT v4; // edx

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF && cchToCopy <= 0x7FFFFFFE )
    return StringCopyWorkerW(pszDest, cchDest, (size_t *)pszSrc, pszSrc, cchToCopy);
  v4 = -2147024809;
  *pszDest = 0;
  return v4;
}

```

## disassembly

```asm
0x1800095d0  sub     rsp, 38h
0x1800095d4  mov     rax, rdx
0x1800095d7  test    rdx, rdx
0x1800095da  jz      short loc_180009605
0x1800095dc  cmp     rax, 7FFFFFFFh
0x1800095e2  jbe     short loc_1800095EB
0x1800095e4  mov     edx, 80070057h; cchDest
0x1800095e9  jmp     short loc_18000960F
0x1800095eb  cmp     r9, 7FFFFFFEh
0x1800095f2  ja      short loc_1800095E4
0x1800095f4  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x1800095f9  mov     r9, r8; pszSrc
0x1800095fc  call    StringCopyWorkerW
0x180009601  mov     edx, eax
0x180009603  jmp     short loc_180009614
0x180009605  mov     edx, 80070057h
0x18000960a  test    rax, rax
0x18000960d  jz      short loc_180009614
0x18000960f  xor     eax, eax
0x180009611  mov     [rcx], ax
0x180009614  mov     eax, edx
0x180009616  add     rsp, 38h
0x18000961a  retn
```
