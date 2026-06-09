# StringCchCopyW

- ea: `0x180004150`
- end: `0x1800041bd`
- name: `StringCchCopyW`
- size: `109`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800057f0`
- `0x180007ed0`
- `0x180008300`
- `0x18000869c`
- `0x1800097d4`
- `0x18000a580`
- `0x18000adf0`

## callees

- `0x180004150`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  __int64 v4; // rax
  STRSAFE_LPWSTR v5; // rax
  HRESULT result; // eax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF )
  {
    result = -2147024809;
    *pszDest = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    v5 = v3 - 1;
    if ( cchDest )
      v5 = v3;
    *v5 = 0;
    result = -2147024774;
    if ( cchDest )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004150  mov     r9, rcx
0x180004153  test    rdx, rdx
0x180004156  jz      short loc_1800041AC
0x180004158  cmp     rdx, 7FFFFFFFh
0x18000415f  ja      short loc_1800041A5
0x180004161  mov     eax, 7FFFFFFEh
0x180004166  test    rax, rax
0x180004169  jz      short loc_180004189
0x18000416b  movzx   ecx, word ptr [r8]
0x18000416f  test    cx, cx
0x180004172  jz      short loc_180004189
0x180004174  mov     [r9], cx
0x180004178  add     r8, 2
0x18000417c  add     r9, 2
0x180004180  dec     rax
0x180004183  sub     rdx, 1
0x180004187  jnz     short loc_180004166
0x180004189  test    rdx, rdx
0x18000418c  lea     rax, [r9-2]
0x180004190  cmovnz  rax, r9
0x180004194  xor     ecx, ecx
0x180004196  test    rdx, rdx
0x180004199  mov     [rax], cx
0x18000419c  mov     eax, 8007007Ah
0x1800041a1  cmovnz  eax, ecx
0x1800041a4  retn
0x1800041a5  mov     eax, 80070057h
0x1800041aa  jmp     short loc_1800041B6
0x1800041ac  mov     eax, 80070057h
0x1800041b1  test    rdx, rdx
0x1800041b4  jz      short locret_1800041A4
0x1800041b6  xor     ecx, ecx
0x1800041b8  mov     [r9], cx
0x1800041bc  retn
```
