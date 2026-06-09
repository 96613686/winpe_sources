# ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](unsigned __int64)

- ea: `0x18000c24c`
- end: `0x18000c270`
- name: `??A?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAAAEAUINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@1@_K@Z`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c278`
- `0x18000c2d8`
- `0x18000c848`
- `0x18000cf44`
- `0x18000d09c`
- `0x18000d288`
- `0x18000d424`
- `0x18000d564`
- `0x18000d974`
- `0x18000da1c`
- `0x18000dc64`

## callees

- `0x18000c24c`
- `0x18000c404`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](
        _QWORD *a1,
        unsigned __int64 a2)
{
  if ( a2 >= a1[1] )
    ATL::AtlThrowImpl(-2147024809);
  return *a1 + 16 * a2;
}

```

## disassembly

```asm
0x18000c24c  sub     rsp, 28h
0x18000c250  cmp     rdx, [rcx+8]
0x18000c254  jb      short loc_18000C261
0x18000c256  mov     ecx, 80070057h; int
0x18000c25b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c261  shl     rdx, 4
0x18000c265  add     rdx, [rcx]
0x18000c268  mov     rax, rdx
0x18000c26b  add     rsp, 28h
0x18000c26f  retn
```
