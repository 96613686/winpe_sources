# ATL::CElementTraitsBase<UnBCL::SmartPtr<UnBCL::String>>::RelocateElements(UnBCL::SmartPtr<UnBCL::String> *,UnBCL::SmartPtr<UnBCL::String> *,unsigned __int64)

- ea: `0x18002f6d0`
- end: `0x18002f728`
- name: `?RelocateElements@?$CElementTraitsBase@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@SAXPEAV?$SmartPtr@VString@UnBCL@@@UnBCL@@0_K@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006b863`

## callees

- `0x1800066cc`
- `0x18002f6d0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002f6e4`
- `msvcrt!memmove_s` at `0x18002f6e4`

## pseudocode

```c
errno_t __fastcall ATL::CElementTraitsBase<UnBCL::SmartPtr<UnBCL::String>>::RelocateElements(
        void *a1,
        const void *a2,
        __int64 a3)
{
  errno_t result; // eax

  result = memmove_s(a1, 16 * a3, a2, 16 * a3);
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
0x18002f6d0  sub     rsp, 28h
0x18002f6d4  mov     rax, r8
0x18002f6d7  mov     r8, rdx; Source
0x18002f6da  shl     rax, 4
0x18002f6de  mov     r9, rax; SourceSize
0x18002f6e1  mov     rdx, rax; DestinationSize
0x18002f6e4  call    cs:__imp_memmove_s
0x18002f6ea  test    eax, eax
0x18002f6ec  jz      short loc_18002F702
0x18002f6ee  cmp     eax, 0Ch
0x18002f6f1  jz      short loc_18002F71D
0x18002f6f3  cmp     eax, 16h
0x18002f6f6  jz      short loc_18002F712
0x18002f6f8  cmp     eax, 22h ; '"'
0x18002f6fb  jz      short loc_18002F712
0x18002f6fd  cmp     eax, 50h ; 'P'
0x18002f700  jnz     short loc_18002F707
0x18002f702  add     rsp, 28h
0x18002f706  retn
0x18002f707  mov     ecx, 80004005h; int
0x18002f70c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f712  mov     ecx, 80070057h; int
0x18002f717  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f71d  mov     ecx, 8007000Eh; int
0x18002f722  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
