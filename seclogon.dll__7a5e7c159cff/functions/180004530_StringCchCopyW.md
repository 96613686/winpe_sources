# StringCchCopyW

- ea: `0x180004530`
- end: `0x18000456d`
- name: `StringCchCopyW`
- size: `61`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002110`

## callees

- `0x180004530`
- `0x180004574`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringCopyWorkerW(pszDest, cchDest, (size_t *)pszSrc, pszSrc, v5);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x180004530  sub     rsp, 38h
0x180004534  mov     rax, rdx
0x180004537  test    rdx, rdx
0x18000453a  jz      short loc_180004557
0x18000453c  cmp     rax, 7FFFFFFFh
0x180004542  jbe     short loc_18000454B
0x180004544  mov     edx, 80070057h; cchDest
0x180004549  jmp     short loc_180004561
0x18000454b  mov     r9, r8; pszSrc
0x18000454e  call    StringCopyWorkerW
0x180004553  mov     edx, eax
0x180004555  jmp     short loc_180004566
0x180004557  mov     edx, 80070057h
0x18000455c  test    rax, rax
0x18000455f  jz      short loc_180004566
0x180004561  xor     eax, eax
0x180004563  mov     [rcx], ax
0x180004566  mov     eax, edx
0x180004568  add     rsp, 38h
0x18000456c  retn
```
