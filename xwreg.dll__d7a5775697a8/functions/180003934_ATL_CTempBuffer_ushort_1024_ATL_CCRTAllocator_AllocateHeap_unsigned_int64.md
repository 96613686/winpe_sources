# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180003934`
- end: `0x18000395f`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800033ac`
- `0x1800053f0`

## callees

- `0x180003934`
- `0x180003ca8`

## import_xrefs

- `msvcrt!malloc` at `0x180003940`
- `msvcrt!malloc` at `0x180003940`

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
0x180003934  push    rbx
0x180003936  sub     rsp, 20h
0x18000393a  mov     rbx, rcx
0x18000393d  mov     rcx, rdx; Size
0x180003940  call    cs:__imp_malloc
0x180003946  test    rax, rax
0x180003949  jnz     short loc_180003956
0x18000394b  mov     ecx, 8007000Eh; int
0x180003950  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003956  mov     [rbx], rax
0x180003959  add     rsp, 20h
0x18000395d  pop     rbx
0x18000395e  retn
```
