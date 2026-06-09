# ATL::CElementTraitsBase<UnBCL::String *>::RelocateElements(UnBCL::String * *,UnBCL::String * *,unsigned __int64)

- ea: `0x18001d4a8`
- end: `0x18001d501`
- name: `?RelocateElements@?$CElementTraitsBase@PEAVString@UnBCL@@@ATL@@SAXPEAPEAVString@UnBCL@@0_K@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180069f92`

## callees

- `0x1800066cc`
- `0x18001d4a8`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001d4bd`
- `msvcrt!memmove_s` at `0x18001d4bd`

## pseudocode

```c
errno_t __fastcall ATL::CElementTraitsBase<UnBCL::String *>::RelocateElements(void *a1, const void *a2, __int64 a3)
{
  errno_t result; // eax

  result = memmove_s(a1, 8 * a3, a2, 8 * a3);
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
0x18001d4a8  sub     rsp, 28h
0x18001d4ac  mov     rax, rdx
0x18001d4af  lea     rdx, ds:0[r8*8]; DestinationSize
0x18001d4b7  mov     r9, rdx; SourceSize
0x18001d4ba  mov     r8, rax; Source
0x18001d4bd  call    cs:__imp_memmove_s
0x18001d4c3  test    eax, eax
0x18001d4c5  jz      short loc_18001D4DB
0x18001d4c7  cmp     eax, 0Ch
0x18001d4ca  jz      short loc_18001D4F6
0x18001d4cc  cmp     eax, 16h
0x18001d4cf  jz      short loc_18001D4EB
0x18001d4d1  cmp     eax, 22h ; '"'
0x18001d4d4  jz      short loc_18001D4EB
0x18001d4d6  cmp     eax, 50h ; 'P'
0x18001d4d9  jnz     short loc_18001D4E0
0x18001d4db  add     rsp, 28h
0x18001d4df  retn
0x18001d4e0  mov     ecx, 80004005h; int
0x18001d4e5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d4eb  mov     ecx, 80070057h; int
0x18001d4f0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d4f6  mov     ecx, 8007000Eh; int
0x18001d4fb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
