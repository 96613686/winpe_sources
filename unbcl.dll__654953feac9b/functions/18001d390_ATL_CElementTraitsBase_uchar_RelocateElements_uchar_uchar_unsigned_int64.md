# ATL::CElementTraitsBase<uchar>::RelocateElements(uchar *,uchar *,unsigned __int64)

- ea: `0x18001d390`
- end: `0x18001d3e4`
- name: `?RelocateElements@?$CElementTraitsBase@E@ATL@@SAXPEAE0_K@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180069ea1`

## callees

- `0x1800066cc`
- `0x18001d390`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001d3a0`
- `msvcrt!memmove_s` at `0x18001d3a0`

## pseudocode

```c
errno_t __fastcall ATL::CElementTraitsBase<unsigned char>::RelocateElements(void *a1, const void *a2, rsize_t a3)
{
  errno_t result; // eax

  result = memmove_s(a1, a3, a2, a3);
  if ( result )
  {
    if ( result == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( result == 22 || result == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( result != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  return result;
}

```

## disassembly

```asm
0x18001d390  sub     rsp, 28h
0x18001d394  mov     rax, r8
0x18001d397  mov     r9, r8; SourceSize
0x18001d39a  mov     r8, rdx; Source
0x18001d39d  mov     rdx, rax; DestinationSize
0x18001d3a0  call    cs:__imp_memmove_s
0x18001d3a6  test    eax, eax
0x18001d3a8  jz      short loc_18001D3BE
0x18001d3aa  cmp     eax, 0Ch
0x18001d3ad  jz      short loc_18001D3D9
0x18001d3af  cmp     eax, 16h
0x18001d3b2  jz      short loc_18001D3CE
0x18001d3b4  cmp     eax, 22h ; '"'
0x18001d3b7  jz      short loc_18001D3CE
0x18001d3b9  cmp     eax, 50h ; 'P'
0x18001d3bc  jnz     short loc_18001D3C3
0x18001d3be  add     rsp, 28h
0x18001d3c2  retn
0x18001d3c3  mov     ecx, 80004005h; int
0x18001d3c8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d3ce  mov     ecx, 80070057h; int
0x18001d3d3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d3d9  mov     ecx, 8007000Eh; int
0x18001d3de  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
