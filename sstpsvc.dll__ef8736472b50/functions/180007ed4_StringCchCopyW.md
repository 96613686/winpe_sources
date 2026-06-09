# StringCchCopyW

- ea: `0x180007ed4`
- end: `0x180007f3f`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007dd0`

## callees

- `0x180007ed4`

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
0x180007ed4  xor     r10d, r10d
0x180007ed7  mov     r9, rcx
0x180007eda  test    rdx, rdx
0x180007edd  jz      short loc_180007F30
0x180007edf  cmp     rdx, 7FFFFFFFh
0x180007ee6  jbe     short loc_180007EEF
0x180007ee8  mov     eax, 80070057h
0x180007eed  jmp     short loc_180007F3A
0x180007eef  mov     eax, 7FFFFFFEh
0x180007ef4  test    rax, rax
0x180007ef7  jz      short loc_180007F17
0x180007ef9  movzx   ecx, word ptr [r8]
0x180007efd  test    cx, cx
0x180007f00  jz      short loc_180007F17
0x180007f02  mov     [r9], cx
0x180007f06  add     r8, 2
0x180007f0a  add     r9, 2
0x180007f0e  dec     rax
0x180007f11  sub     rdx, 1
0x180007f15  jnz     short loc_180007EF4
0x180007f17  test    rdx, rdx
0x180007f1a  lea     rcx, [r9-2]
0x180007f1e  cmovnz  rcx, r9
0x180007f22  neg     rdx
0x180007f25  sbb     eax, eax
0x180007f27  not     eax
0x180007f29  and     eax, 8007007Ah
0x180007f2e  jmp     short loc_180007F3A
0x180007f30  mov     eax, 80070057h
0x180007f35  test    rdx, rdx
0x180007f38  jz      short locret_180007F3E
0x180007f3a  mov     [rcx], r10w
0x180007f3e  retn
```
