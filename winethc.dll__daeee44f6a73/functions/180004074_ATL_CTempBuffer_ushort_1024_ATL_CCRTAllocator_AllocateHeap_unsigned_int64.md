# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180004074`
- end: `0x1800040a6`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b40`
- `0x18000b518`

## callees

- `0x180004074`
- `0x1800041f8`

## import_xrefs

- `msvcrt!malloc` at `0x180004080`
- `msvcrt!malloc` at `0x180004080`

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
0x180004074  push    rbx
0x180004076  sub     rsp, 20h
0x18000407a  mov     rbx, rcx
0x18000407d  mov     rcx, rdx; Size
0x180004080  call    cs:__imp_malloc
0x180004087  nop     dword ptr [rax+rax+00h]
0x18000408c  test    rax, rax
0x18000408f  jz      short loc_18000409B
0x180004091  mov     [rbx], rax
0x180004094  add     rsp, 20h
0x180004098  pop     rbx
0x180004099  retn
0x18000409b  mov     ecx, 8007000Eh; int
0x1800040a0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
