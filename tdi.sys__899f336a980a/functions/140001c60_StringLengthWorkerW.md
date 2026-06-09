# StringLengthWorkerW

- ea: `0x140001c60`
- end: `0x140001c9d`
- name: `StringLengthWorkerW`
- size: `61`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001340`
- `0x140001540`

## callees

- `0x140001c60`

## pseudocode

```c
HRESULT __stdcall StringLengthWorkerW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  size_t i; // r9
  HRESULT result; // eax

  for ( i = cchMax; cchMax; --cchMax )
  {
    if ( !*psz )
      break;
    ++psz;
  }
  result = -2147024809;
  if ( cchMax )
    result = 0;
  if ( pcchLength )
  {
    if ( cchMax )
      *pcchLength = i - cchMax;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001c60  mov     r9, rdx
0x140001c63  test    rdx, rdx
0x140001c66  jz      short loc_140001C78
0x140001c68  cmp     word ptr [rcx], 0
0x140001c6c  jz      short loc_140001C78
0x140001c6e  add     rcx, 2
0x140001c72  sub     rdx, 1
0x140001c76  jnz     short loc_140001C68
0x140001c78  xor     ecx, ecx
0x140001c7a  mov     eax, 80070057h
0x140001c7f  test    rdx, rdx
0x140001c82  cmovnz  eax, ecx
0x140001c85  test    r8, r8
0x140001c88  jnz     short loc_140001C8C
0x140001c8a  retn
0x140001c8c  test    rdx, rdx
0x140001c8f  jz      short loc_140001C99
0x140001c91  sub     r9, rdx
0x140001c94  mov     [r8], r9
0x140001c97  retn
0x140001c99  mov     [r8], rcx
0x140001c9c  retn
```
