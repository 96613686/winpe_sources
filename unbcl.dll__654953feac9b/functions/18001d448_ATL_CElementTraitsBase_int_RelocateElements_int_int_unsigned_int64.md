# ATL::CElementTraitsBase<int>::RelocateElements(int *,int *,unsigned __int64)

- ea: `0x18001d448`
- end: `0x18001d4a1`
- name: `?RelocateElements@?$CElementTraitsBase@H@ATL@@SAXPEAH0_K@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180069f41`

## callees

- `0x1800066cc`
- `0x18001d448`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001d45d`
- `msvcrt!memmove_s` at `0x18001d45d`

## pseudocode

```c
errno_t __fastcall ATL::CElementTraitsBase<int>::RelocateElements(void *a1, const void *a2, __int64 a3)
{
  errno_t result; // eax

  result = memmove_s(a1, 4 * a3, a2, 4 * a3);
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
0x18001d448  sub     rsp, 28h
0x18001d44c  mov     rax, rdx
0x18001d44f  lea     rdx, ds:0[r8*4]; DestinationSize
0x18001d457  mov     r9, rdx; SourceSize
0x18001d45a  mov     r8, rax; Source
0x18001d45d  call    cs:__imp_memmove_s
0x18001d463  test    eax, eax
0x18001d465  jz      short loc_18001D47B
0x18001d467  cmp     eax, 0Ch
0x18001d46a  jz      short loc_18001D496
0x18001d46c  cmp     eax, 16h
0x18001d46f  jz      short loc_18001D48B
0x18001d471  cmp     eax, 22h ; '"'
0x18001d474  jz      short loc_18001D48B
0x18001d476  cmp     eax, 50h ; 'P'
0x18001d479  jnz     short loc_18001D480
0x18001d47b  add     rsp, 28h
0x18001d47f  retn
0x18001d480  mov     ecx, 80004005h; int
0x18001d485  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d48b  mov     ecx, 80070057h; int
0x18001d490  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d496  mov     ecx, 8007000Eh; int
0x18001d49b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
