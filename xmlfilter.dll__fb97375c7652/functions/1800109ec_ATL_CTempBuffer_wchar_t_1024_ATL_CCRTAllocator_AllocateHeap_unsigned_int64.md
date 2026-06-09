# ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1800109ec`
- end: `0x180010a17`
- name: `?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010410`
- `0x180012508`

## callees

- `0x1800109ec`
- `0x180011478`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800109f8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800109f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, size_t a2)
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
0x1800109ec  push    rbx
0x1800109ee  sub     rsp, 20h
0x1800109f2  mov     rbx, rcx
0x1800109f5  mov     rcx, rdx; Size
0x1800109f8  call    cs:__imp_malloc
0x1800109fe  test    rax, rax
0x180010a01  jz      short loc_180010A0C
0x180010a03  mov     [rbx], rax
0x180010a06  add     rsp, 20h
0x180010a0a  pop     rbx
0x180010a0b  retn
0x180010a0c  mov     ecx, 8007000Eh; int
0x180010a11  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
