# ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::ReAllocateHeap(unsigned __int64)

- ea: `0x140007224`
- end: `0x14000724f`
- name: `?ReAllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007258`

## callees

- `0x140003004`
- `0x140007224`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140007230`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140007230`

## pseudocode

```c
__int64 __fastcall ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::ReAllocateHeap(__int64 *a1)
{
  __int64 result; // rax

  result = _o_realloc(*a1);
  if ( !result )
    ATL::AtlThrowImpl(-2147024882);
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x140007224  push    rbx
0x140007226  sub     rsp, 20h
0x14000722a  mov     rbx, rcx
0x14000722d  mov     rcx, [rcx]
0x140007230  call    cs:__imp__o_realloc
0x140007236  test    rax, rax
0x140007239  jz      short loc_140007244
0x14000723b  mov     [rbx], rax
0x14000723e  add     rsp, 20h
0x140007242  pop     rbx
0x140007243  retn
0x140007244  mov     ecx, 8007000Eh; int
0x140007249  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
