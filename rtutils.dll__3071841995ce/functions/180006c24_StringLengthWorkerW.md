# StringLengthWorkerW

- ea: `0x180006c24`
- end: `0x180006c64`
- name: `StringLengthWorkerW`
- size: `64`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006bf4`
- `0x180007664`
- `0x180007e34`

## callees

- `0x180006c24`

## pseudocode

```c
HRESULT __stdcall StringLengthWorkerW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  __int64 v3; // rdx
  HRESULT result; // eax

  v3 = 260;
  do
  {
    if ( !*psz )
      break;
    ++psz;
    --v3;
  }
  while ( v3 );
  result = v3 == 0 ? 0x80070057 : 0;
  if ( pcchLength )
  {
    if ( v3 )
      *pcchLength = 260 - v3;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006c24  mov     r9d, 104h
0x180006c2a  xor     r10d, r10d
0x180006c2d  mov     edx, r9d
0x180006c30  cmp     [rcx], r10w
0x180006c34  jz      short loc_180006C40
0x180006c36  add     rcx, 2
0x180006c3a  sub     rdx, 1
0x180006c3e  jnz     short loc_180006C30
0x180006c40  mov     rax, rdx
0x180006c43  neg     rax
0x180006c46  sbb     eax, eax
0x180006c48  not     eax
0x180006c4a  and     eax, 80070057h
0x180006c4f  test    r8, r8
0x180006c52  jz      short locret_180006C63
0x180006c54  test    rdx, rdx
0x180006c57  jz      short loc_180006C60
0x180006c59  sub     r9, rdx
0x180006c5c  mov     [r8], r9
0x180006c5f  retn
0x180006c60  mov     [r8], r10
0x180006c63  retn
```
