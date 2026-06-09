# StringCchCopyA(x,x,x)

- ea: `0x10002d80`
- end: `0x10002dd7`
- name: `_StringCchCopyA@12`
- size: `87`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x10002470`
- `0x10002870`
- `0x100083b2`

## callees

- `0x10002d80`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  unsigned int v3; // edx
  _BYTE *v4; // ecx
  _BYTE *v5; // edi
  int v7; // eax
  HRESULT v8; // ebx
  HRESULT result; // eax

  v5 = v4;
  if ( !v3 )
    return -2147024809;
  if ( v3 > 0x7FFFFFFF )
  {
    *v4 = 0;
    return -2147024809;
  }
  v7 = 2147483646;
  v8 = 0;
  while ( v7 && *pszDest )
  {
    *v5++ = *pszDest++;
    --v7;
    if ( !--v3 )
    {
      --v5;
      v8 = -2147024774;
      break;
    }
  }
  result = v8;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x10002d80  mov     edi, edi
0x10002d82  push    ebp
0x10002d83  mov     ebp, esp
0x10002d85  push    edi
0x10002d86  mov     edi, ecx
0x10002d88  test    edx, edx
0x10002d8a  jz      short loc_10002DD0
0x10002d8c  cmp     edx, 7FFFFFFFh
0x10002d92  ja      loc_1000571B
0x10002d98  push    ebx
0x10002d99  push    esi
0x10002d9a  mov     esi, [ebp+pszDest]
0x10002d9d  mov     eax, 7FFFFFFEh
0x10002da2  xor     ebx, ebx
0x10002da4  test    eax, eax
0x10002da6  jz      short loc_10002DC4
0x10002da8  mov     cl, [esi]
0x10002daa  test    cl, cl
0x10002dac  jz      short loc_10002DC0
0x10002dae  mov     [edi], cl
0x10002db0  inc     esi
0x10002db1  inc     edi
0x10002db2  dec     eax
0x10002db3  sub     edx, 1
0x10002db6  jnz     short loc_10002DA4
0x10002db8  dec     edi
0x10002db9  mov     ebx, 8007007Ah
0x10002dbe  jmp     short loc_10002DC4
0x10002dc0  test    edx, edx
0x10002dc2  jz      short loc_10002DB8
0x10002dc4  pop     esi
0x10002dc5  mov     eax, ebx
0x10002dc7  mov     byte ptr [edi], 0
0x10002dca  pop     ebx
0x10002dcb  pop     edi
0x10002dcc  pop     ebp
0x10002dcd  retn    4
0x10002dd0  mov     eax, 80070057h
0x10002dd5  jmp     short loc_10002DCB
0x1000571b  test    edx, edx
0x1000571d  jz      loc_10002DD0
0x10005723  mov     byte ptr [edi], 0
0x10005726  jmp     loc_10002DD0
```
