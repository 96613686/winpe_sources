# ATL::CElementTraitsBase<UnBCL::StringPtr>::RelocateElements(UnBCL::StringPtr *,UnBCL::StringPtr *,unsigned __int64)

- ea: `0x180045a60`
- end: `0x180045ab8`
- name: `?RelocateElements@?$CElementTraitsBase@VStringPtr@UnBCL@@@ATL@@SAXPEAVStringPtr@UnBCL@@0_K@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006cd27`

## callees

- `0x1800066cc`
- `0x180045a60`

## import_xrefs

- `msvcrt!memmove_s` at `0x180045a74`
- `msvcrt!memmove_s` at `0x180045a74`

## pseudocode

```c
errno_t __fastcall ATL::CElementTraitsBase<UnBCL::StringPtr>::RelocateElements(void *a1, const void *a2, __int64 a3)
{
  errno_t result; // eax

  result = memmove_s(a1, 32 * a3, a2, 32 * a3);
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
0x180045a60  sub     rsp, 28h
0x180045a64  mov     rax, r8
0x180045a67  mov     r8, rdx; Source
0x180045a6a  shl     rax, 5
0x180045a6e  mov     r9, rax; SourceSize
0x180045a71  mov     rdx, rax; DestinationSize
0x180045a74  call    cs:__imp_memmove_s
0x180045a7a  test    eax, eax
0x180045a7c  jz      short loc_180045A92
0x180045a7e  cmp     eax, 0Ch
0x180045a81  jz      short loc_180045AAD
0x180045a83  cmp     eax, 16h
0x180045a86  jz      short loc_180045AA2
0x180045a88  cmp     eax, 22h ; '"'
0x180045a8b  jz      short loc_180045AA2
0x180045a8d  cmp     eax, 50h ; 'P'
0x180045a90  jnz     short loc_180045A97
0x180045a92  add     rsp, 28h
0x180045a96  retn
0x180045a97  mov     ecx, 80004005h; int
0x180045a9c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180045aa2  mov     ecx, 80070057h; int
0x180045aa7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180045aad  mov     ecx, 8007000Eh; int
0x180045ab2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
