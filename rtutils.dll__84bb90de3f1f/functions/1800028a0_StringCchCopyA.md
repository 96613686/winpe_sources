# StringCchCopyA

- ea: `0x1800028a0`
- end: `0x180002906`
- name: `StringCchCopyA`
- size: `102`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a68`

## callees

- `0x1800028a0`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  STRSAFE_LPSTR v3; // r9
  __int64 v4; // rcx
  STRSAFE_LPSTR v5; // rax
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
0x1800028a0  mov     r9, rcx
0x1800028a3  test    rdx, rdx
0x1800028a6  jz      short loc_1800028F8
0x1800028a8  cmp     rdx, 7FFFFFFFh
0x1800028af  ja      short loc_1800028F1
0x1800028b1  mov     ecx, 7FFFFFFEh
0x1800028b6  test    rcx, rcx
0x1800028b9  jz      short loc_1800028D5
0x1800028bb  movzx   eax, byte ptr [r8]
0x1800028bf  test    al, al
0x1800028c1  jz      short loc_1800028D5
0x1800028c3  mov     [r9], al
0x1800028c6  inc     r8
0x1800028c9  inc     r9
0x1800028cc  dec     rcx
0x1800028cf  sub     rdx, 1
0x1800028d3  jnz     short loc_1800028B6
0x1800028d5  test    rdx, rdx
0x1800028d8  lea     rax, [r9-1]
0x1800028dc  cmovnz  rax, r9
0x1800028e0  xor     ecx, ecx
0x1800028e2  test    rdx, rdx
0x1800028e5  mov     byte ptr [rax], 0
0x1800028e8  mov     eax, 8007007Ah
0x1800028ed  cmovnz  eax, ecx
0x1800028f0  retn
0x1800028f1  mov     eax, 80070057h
0x1800028f6  jmp     short loc_180002902
0x1800028f8  mov     eax, 80070057h
0x1800028fd  test    rdx, rdx
0x180002900  jz      short locret_1800028F0
0x180002902  mov     byte ptr [rcx], 0
0x180002905  retn
```
