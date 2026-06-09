# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180008b28`
- end: `0x180008b53`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008624`
- `0x18000a348`

## callees

- `0x180008b28`
- `0x180008c94`

## import_xrefs

- `msvcrt!malloc` at `0x180008b34`
- `msvcrt!malloc` at `0x180008b34`

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
0x180008b28  push    rbx
0x180008b2a  sub     rsp, 20h
0x180008b2e  mov     rbx, rcx
0x180008b31  mov     rcx, rdx; Size
0x180008b34  call    cs:__imp_malloc
0x180008b3a  test    rax, rax
0x180008b3d  jz      short loc_180008B48
0x180008b3f  mov     [rbx], rax
0x180008b42  add     rsp, 20h
0x180008b46  pop     rbx
0x180008b47  retn
0x180008b48  mov     ecx, 8007000Eh; int
0x180008b4d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
