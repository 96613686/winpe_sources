# StringCchCopyW

- ea: `0x180017d24`
- end: `0x180017d61`
- name: `StringCchCopyW`
- size: `61`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18001792c`
- `0x1800179f4`
- `0x180017dd0`
- `0x18001831c`
- `0x180018b00`
- `0x180019468`
- `0x180019758`
- `0x180019fd0`
- `0x18001a218`
- `0x18001a354`

## callees

- `0x18000909c`
- `0x180017d24`

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
0x180017d24  sub     rsp, 38h
0x180017d28  mov     rax, rdx
0x180017d2b  test    rdx, rdx
0x180017d2e  jz      short loc_180017D4B
0x180017d30  cmp     rax, 7FFFFFFFh
0x180017d36  jbe     short loc_180017D3F
0x180017d38  mov     edx, 80070057h; cchDest
0x180017d3d  jmp     short loc_180017D55
0x180017d3f  mov     r9, r8; pszSrc
0x180017d42  call    StringCopyWorkerW
0x180017d47  mov     edx, eax
0x180017d49  jmp     short loc_180017D5A
0x180017d4b  mov     edx, 80070057h
0x180017d50  test    rax, rax
0x180017d53  jz      short loc_180017D5A
0x180017d55  xor     eax, eax
0x180017d57  mov     [rcx], ax
0x180017d5a  mov     eax, edx
0x180017d5c  add     rsp, 38h
0x180017d60  retn
```
