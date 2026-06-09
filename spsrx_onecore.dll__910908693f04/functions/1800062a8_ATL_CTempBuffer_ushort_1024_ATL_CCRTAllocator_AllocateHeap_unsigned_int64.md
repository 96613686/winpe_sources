# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1800062a8`
- end: `0x1800062d3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e28`
- `0x18000764c`

## callees

- `0x1800062a8`
- `0x1800068ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800062b4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800062b4`

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
0x1800062a8  push    rbx
0x1800062aa  sub     rsp, 20h
0x1800062ae  mov     rbx, rcx
0x1800062b1  mov     rcx, rdx; Size
0x1800062b4  call    cs:__imp_malloc
0x1800062ba  test    rax, rax
0x1800062bd  jz      short loc_1800062C8
0x1800062bf  mov     [rbx], rax
0x1800062c2  add     rsp, 20h
0x1800062c6  pop     rbx
0x1800062c7  retn
0x1800062c8  mov     ecx, 8007000Eh; int
0x1800062cd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
