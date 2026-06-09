# StringCchCopyW

- ea: `0x180009624`
- end: `0x18000966a`
- name: `StringCchCopyW`
- size: `70`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000946c`

## callees

- `0x180009624`
- `0x1800096f0`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT v3; // edx

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringCopyWorkerW(pszDest, cchDest, (size_t *)pszSrc, pszSrc, 0x7FFFFFFEu);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x180009624  sub     rsp, 38h
0x180009628  mov     rax, rdx
0x18000962b  test    rdx, rdx
0x18000962e  jz      short loc_180009654
0x180009630  cmp     rax, 7FFFFFFFh
0x180009636  jbe     short loc_18000963F
0x180009638  mov     edx, 80070057h; cchDest
0x18000963d  jmp     short loc_18000965E
0x18000963f  mov     r9, r8; pszSrc
0x180009642  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x18000964b  call    StringCopyWorkerW
0x180009650  mov     edx, eax
0x180009652  jmp     short loc_180009663
0x180009654  mov     edx, 80070057h
0x180009659  test    rax, rax
0x18000965c  jz      short loc_180009663
0x18000965e  xor     eax, eax
0x180009660  mov     [rcx], ax
0x180009663  mov     eax, edx
0x180009665  add     rsp, 38h
0x180009669  retn
```
