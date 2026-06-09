# StringCbCopyW

- ea: `0x1800044e8`
- end: `0x180004528`
- name: `StringCbCopyW`
- size: `64`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003fec`

## callees

- `0x1800044e8`
- `0x180004574`

## pseudocode

```c
HRESULT __stdcall StringCbCopyW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( !(cbDest >> 1) )
    return -2147024809;
  if ( cbDest >> 1 <= 0x7FFFFFFF )
    return StringCopyWorkerW(pszDest, cbDest >> 1, (size_t *)pszSrc, pszSrc, v5);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x1800044e8  sub     rsp, 38h
0x1800044ec  mov     rax, rdx
0x1800044ef  shr     rax, 1
0x1800044f2  jz      short loc_180004512
0x1800044f4  cmp     rax, 7FFFFFFFh
0x1800044fa  jbe     short loc_180004503
0x1800044fc  mov     edx, 80070057h
0x180004501  jmp     short loc_18000451C
0x180004503  mov     r9, r8; pszSrc
0x180004506  mov     rdx, rax; cchDest
0x180004509  call    StringCopyWorkerW
0x18000450e  mov     edx, eax
0x180004510  jmp     short loc_180004521
0x180004512  mov     edx, 80070057h
0x180004517  test    rax, rax
0x18000451a  jz      short loc_180004521
0x18000451c  xor     eax, eax
0x18000451e  mov     [rcx], ax
0x180004521  mov     eax, edx
0x180004523  add     rsp, 38h
0x180004527  retn
```
