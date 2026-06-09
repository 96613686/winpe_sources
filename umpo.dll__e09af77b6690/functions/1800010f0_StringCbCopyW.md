# StringCbCopyW

- ea: `0x1800010f0`
- end: `0x18000115d`
- name: `StringCbCopyW`
- size: `109`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a00`
- `0x180012748`

## callees

- `0x1800010f0`

## pseudocode

```c
HRESULT __stdcall StringCbCopyW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v3; // rdx
  STRSAFE_LPWSTR v4; // r9
  __int64 v5; // rax
  STRSAFE_LPWSTR v6; // rax
  HRESULT result; // eax

  v3 = cbDest >> 1;
  v4 = pszDest;
  if ( !v3 )
    return -2147024809;
  if ( v3 > 0x7FFFFFFF )
  {
    result = -2147024809;
    *pszDest = 0;
  }
  else
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *v4++ = *pszSrc++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = v4 - 1;
    if ( v3 )
      v6 = v4;
    *v6 = 0;
    result = -2147024774;
    if ( v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800010f0  shr     rdx, 1
0x1800010f3  mov     r9, rcx
0x1800010f6  jz      short loc_18000114C
0x1800010f8  cmp     rdx, 7FFFFFFFh
0x1800010ff  ja      short loc_180001145
0x180001101  mov     eax, 7FFFFFFEh
0x180001106  test    rax, rax
0x180001109  jz      short loc_180001129
0x18000110b  movzx   ecx, word ptr [r8]
0x18000110f  test    cx, cx
0x180001112  jz      short loc_180001129
0x180001114  mov     [r9], cx
0x180001118  add     r8, 2
0x18000111c  add     r9, 2
0x180001120  dec     rax
0x180001123  sub     rdx, 1
0x180001127  jnz     short loc_180001106
0x180001129  test    rdx, rdx
0x18000112c  lea     rax, [r9-2]
0x180001130  cmovnz  rax, r9
0x180001134  xor     ecx, ecx
0x180001136  test    rdx, rdx
0x180001139  mov     [rax], cx
0x18000113c  mov     eax, 8007007Ah
0x180001141  cmovnz  eax, ecx
0x180001144  retn
0x180001145  mov     eax, 80070057h
0x18000114a  jmp     short loc_180001156
0x18000114c  mov     eax, 80070057h
0x180001151  test    rdx, rdx
0x180001154  jz      short locret_180001144
0x180001156  xor     ecx, ecx
0x180001158  mov     [r9], cx
0x18000115c  retn
```
