# StringCchCopyW

- ea: `0x180005da4`
- end: `0x180005e0f`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003804`
- `0x1800064e4`
- `0x180007330`
- `0x1800076a4`
- `0x18000859c`
- `0x180008d30`
- `0x180008d8c`
- `0x180009030`

## callees

- `0x180005da4`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  HRESULT result; // eax
  __int64 v5; // rax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v5;
      --cchDest;
    }
    while ( cchDest );
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x180005da4  xor     r10d, r10d
0x180005da7  mov     r9, rcx
0x180005daa  test    rdx, rdx
0x180005dad  jz      short loc_180005E00
0x180005daf  cmp     rdx, 7FFFFFFFh
0x180005db6  jbe     short loc_180005DBF
0x180005db8  mov     eax, 80070057h
0x180005dbd  jmp     short loc_180005E0A
0x180005dbf  mov     eax, 7FFFFFFEh
0x180005dc4  test    rax, rax
0x180005dc7  jz      short loc_180005DE7
0x180005dc9  movzx   ecx, word ptr [r8]
0x180005dcd  test    cx, cx
0x180005dd0  jz      short loc_180005DE7
0x180005dd2  mov     [r9], cx
0x180005dd6  add     r8, 2
0x180005dda  add     r9, 2
0x180005dde  dec     rax
0x180005de1  sub     rdx, 1
0x180005de5  jnz     short loc_180005DC4
0x180005de7  test    rdx, rdx
0x180005dea  lea     rcx, [r9-2]
0x180005dee  cmovnz  rcx, r9
0x180005df2  neg     rdx
0x180005df5  sbb     eax, eax
0x180005df7  not     eax
0x180005df9  and     eax, 8007007Ah
0x180005dfe  jmp     short loc_180005E0A
0x180005e00  mov     eax, 80070057h
0x180005e05  test    rdx, rdx
0x180005e08  jz      short locret_180005E0E
0x180005e0a  mov     [rcx], r10w
0x180005e0e  retn
```
