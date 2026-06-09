# StringCchCopyNW

- ea: `0x180014bc4`
- end: `0x180014c41`
- name: `StringCchCopyNW`
- size: `125`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180014a94`
- `0x1800151f0`
- `0x180015668`
- `0x1800156f8`

## callees

- `0x180014bc4`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)
{
  size_t v4; // r10
  STRSAFE_LPWSTR v5; // r11
  HRESULT v6; // edx

  v4 = cchDest;
  v5 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF || cchToCopy > 0x7FFFFFFE )
  {
    v6 = -2147024809;
  }
  else
  {
    do
    {
      if ( !cchToCopy )
        break;
      if ( !*pszSrc )
        break;
      *v5++ = *pszSrc++;
      --cchToCopy;
      --v4;
    }
    while ( v4 );
    pszDest = v5 - 1;
    if ( v4 )
      pszDest = v5;
    v6 = v4 == 0 ? 0x8007007A : 0;
  }
  *pszDest = 0;
  return v6;
}

```

## disassembly

```asm
0x180014bc4  mov     [rsp+arg_0], rbx
0x180014bc9  xor     ebx, ebx
0x180014bcb  mov     r10, rdx
0x180014bce  mov     r11, rcx
0x180014bd1  test    rdx, rdx
0x180014bd4  jz      short loc_180014C2C
0x180014bd6  cmp     rdx, 7FFFFFFFh
0x180014bdd  jbe     short loc_180014BE6
0x180014bdf  mov     edx, 80070057h
0x180014be4  jmp     short loc_180014C36
0x180014be6  cmp     r9, 7FFFFFFEh
0x180014bed  ja      short loc_180014BDF
0x180014bef  test    r9, r9
0x180014bf2  jz      short loc_180014C12
0x180014bf4  movzx   eax, word ptr [r8]
0x180014bf8  test    ax, ax
0x180014bfb  jz      short loc_180014C12
0x180014bfd  mov     [r11], ax
0x180014c01  add     r8, 2
0x180014c05  add     r11, 2
0x180014c09  dec     r9
0x180014c0c  sub     r10, 1
0x180014c10  jnz     short loc_180014BEF
0x180014c12  test    r10, r10
0x180014c15  lea     rcx, [r11-2]
0x180014c19  cmovnz  rcx, r11
0x180014c1d  neg     r10
0x180014c20  sbb     edx, edx
0x180014c22  not     edx
0x180014c24  and     edx, 8007007Ah
0x180014c2a  jmp     short loc_180014C36
0x180014c2c  mov     edx, 80070057h
0x180014c31  test    r10, r10
0x180014c34  jz      short loc_180014C39
0x180014c36  mov     [rcx], bx
0x180014c39  mov     rbx, [rsp+arg_0]
0x180014c3e  mov     eax, edx
0x180014c40  retn
```
