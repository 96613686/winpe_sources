# ATL::CElementTraitsBase<ushort>::RelocateElements(ushort *,ushort *,unsigned __int64)

- ea: `0x18001d3ec`
- end: `0x18001d441`
- name: `?RelocateElements@?$CElementTraitsBase@G@ATL@@SAXPEAG0_K@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180069ef0`

## callees

- `0x1800066cc`
- `0x18001d3ec`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001d3fd`
- `msvcrt!memmove_s` at `0x18001d3fd`

## pseudocode

```c
errno_t __fastcall ATL::CElementTraitsBase<unsigned short>::RelocateElements(void *a1, const void *a2, __int64 a3)
{
  errno_t result; // eax

  result = memmove_s(a1, 2 * a3, a2, 2 * a3);
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
0x18001d3ec  sub     rsp, 28h
0x18001d3f0  mov     rax, rdx
0x18001d3f3  lea     rdx, [r8+r8]; DestinationSize
0x18001d3f7  mov     r9, rdx; SourceSize
0x18001d3fa  mov     r8, rax; Source
0x18001d3fd  call    cs:__imp_memmove_s
0x18001d403  test    eax, eax
0x18001d405  jz      short loc_18001D41B
0x18001d407  cmp     eax, 0Ch
0x18001d40a  jz      short loc_18001D436
0x18001d40c  cmp     eax, 16h
0x18001d40f  jz      short loc_18001D42B
0x18001d411  cmp     eax, 22h ; '"'
0x18001d414  jz      short loc_18001D42B
0x18001d416  cmp     eax, 50h ; 'P'
0x18001d419  jnz     short loc_18001D420
0x18001d41b  add     rsp, 28h
0x18001d41f  retn
0x18001d420  mov     ecx, 80004005h; int
0x18001d425  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d42b  mov     ecx, 80070057h; int
0x18001d430  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d436  mov     ecx, 8007000Eh; int
0x18001d43b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
