# StringCchCopyA

- ea: `0x180017d24`
- end: `0x180017d86`
- name: `StringCchCopyA`
- size: `98`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000df10`
- `0x18000e3f0`
- `0x18000e540`

## callees

- `0x180017d24`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax
  __int64 v4; // rax
  STRSAFE_LPSTR v5; // rax

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    v5 = pszDest - 1;
    if ( cchDest )
      v5 = pszDest;
    *v5 = 0;
    return cchDest == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180017d24  test    rdx, rdx
0x180017d27  jz      short loc_180017D78
0x180017d29  cmp     rdx, 7FFFFFFFh
0x180017d30  jbe     short loc_180017D39
0x180017d32  mov     eax, 80070057h
0x180017d37  jmp     short loc_180017D82
0x180017d39  mov     eax, 7FFFFFFEh
0x180017d3e  test    rax, rax
0x180017d41  jz      short loc_180017D5D
0x180017d43  mov     r9b, [r8]
0x180017d46  test    r9b, r9b
0x180017d49  jz      short loc_180017D5D
0x180017d4b  mov     [rcx], r9b
0x180017d4e  inc     r8
0x180017d51  inc     rcx
0x180017d54  dec     rax
0x180017d57  sub     rdx, 1
0x180017d5b  jnz     short loc_180017D3E
0x180017d5d  test    rdx, rdx
0x180017d60  lea     rax, [rcx-1]
0x180017d64  cmovnz  rax, rcx
0x180017d68  neg     rdx
0x180017d6b  mov     byte ptr [rax], 0
0x180017d6e  sbb     eax, eax
0x180017d70  not     eax
0x180017d72  and     eax, 8007007Ah
0x180017d77  retn
0x180017d78  mov     eax, 80070057h
0x180017d7d  test    rdx, rdx
0x180017d80  jz      short locret_180017D85
0x180017d82  mov     byte ptr [rcx], 0
0x180017d85  retn
```
