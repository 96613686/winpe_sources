# StringCchCopyW

- ea: `0x18000b6b4`
- end: `0x18000b71f`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000235c`
- `0x18000298c`
- `0x1800031d0`
- `0x180006d20`
- `0x180008f00`
- `0x1800196d0`
- `0x180029134`
- `0x18002a964`
- `0x18002b3bc`
- `0x18002b8f8`

## callees

- `0x18000b6b4`

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
0x18000b6b4  xor     r10d, r10d
0x18000b6b7  mov     r9, rcx
0x18000b6ba  test    rdx, rdx
0x18000b6bd  jz      short loc_18000B710
0x18000b6bf  cmp     rdx, 7FFFFFFFh
0x18000b6c6  jbe     short loc_18000B6CF
0x18000b6c8  mov     eax, 80070057h
0x18000b6cd  jmp     short loc_18000B71A
0x18000b6cf  mov     eax, 7FFFFFFEh
0x18000b6d4  test    rax, rax
0x18000b6d7  jz      short loc_18000B6F7
0x18000b6d9  movzx   ecx, word ptr [r8]
0x18000b6dd  test    cx, cx
0x18000b6e0  jz      short loc_18000B6F7
0x18000b6e2  mov     [r9], cx
0x18000b6e6  add     r8, 2
0x18000b6ea  add     r9, 2
0x18000b6ee  dec     rax
0x18000b6f1  sub     rdx, 1
0x18000b6f5  jnz     short loc_18000B6D4
0x18000b6f7  test    rdx, rdx
0x18000b6fa  lea     rcx, [r9-2]
0x18000b6fe  cmovnz  rcx, r9
0x18000b702  neg     rdx
0x18000b705  sbb     eax, eax
0x18000b707  not     eax
0x18000b709  and     eax, 8007007Ah
0x18000b70e  jmp     short loc_18000B71A
0x18000b710  mov     eax, 80070057h
0x18000b715  test    rdx, rdx
0x18000b718  jz      short locret_18000B71E
0x18000b71a  mov     [rcx], r10w
0x18000b71e  retn
```
