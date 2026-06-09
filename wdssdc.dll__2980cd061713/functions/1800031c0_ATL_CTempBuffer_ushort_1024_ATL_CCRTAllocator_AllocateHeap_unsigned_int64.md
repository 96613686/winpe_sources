# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1800031c0`
- end: `0x1800031f2`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c98`
- `0x1800043c0`

## callees

- `0x1800031c0`
- `0x18000335c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800031cc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800031cc`

## pseudocode

```c
void *__fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, size_t a2)
{
  void *result; // rax

  result = malloc(a2);
  if ( !result )
    ATL::AtlThrowImpl(-2147024882);
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x1800031c0  push    rbx
0x1800031c2  sub     rsp, 20h
0x1800031c6  mov     rbx, rcx
0x1800031c9  mov     rcx, rdx; Size
0x1800031cc  call    cs:__imp_malloc
0x1800031d3  nop     dword ptr [rax+rax+00h]
0x1800031d8  test    rax, rax
0x1800031db  jz      short loc_1800031E7
0x1800031dd  mov     [rbx], rax
0x1800031e0  add     rsp, 20h
0x1800031e4  pop     rbx
0x1800031e5  retn
0x1800031e7  mov     ecx, 8007000Eh; int
0x1800031ec  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
