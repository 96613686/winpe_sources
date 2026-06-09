# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180002cf8`
- end: `0x180002d23`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000271c`
- `0x180003978`

## callees

- `0x180002cf8`
- `0x180002f30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180002d04`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180002d04`

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
0x180002cf8  push    rbx
0x180002cfa  sub     rsp, 20h
0x180002cfe  mov     rbx, rcx
0x180002d01  mov     rcx, rdx; Size
0x180002d04  call    cs:__imp_malloc
0x180002d0a  test    rax, rax
0x180002d0d  jz      short loc_180002D18
0x180002d0f  mov     [rbx], rax
0x180002d12  add     rsp, 20h
0x180002d16  pop     rbx
0x180002d17  retn
0x180002d18  mov     ecx, 8007000Eh; int
0x180002d1d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
