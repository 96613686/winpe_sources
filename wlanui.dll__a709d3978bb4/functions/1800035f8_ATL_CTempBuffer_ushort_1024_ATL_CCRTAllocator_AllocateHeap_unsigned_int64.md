# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1800035f8`
- end: `0x180003623`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030f4`
- `0x180004828`

## callees

- `0x1800035f8`
- `0x180003870`

## import_xrefs

- `msvcrt!malloc` at `0x180003604`
- `msvcrt!malloc` at `0x180003604`

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
0x1800035f8  push    rbx
0x1800035fa  sub     rsp, 20h
0x1800035fe  mov     rbx, rcx
0x180003601  mov     rcx, rdx; Size
0x180003604  call    cs:__imp_malloc
0x18000360a  test    rax, rax
0x18000360d  jz      short loc_180003618
0x18000360f  mov     [rbx], rax
0x180003612  add     rsp, 20h
0x180003616  pop     rbx
0x180003617  retn
0x180003618  mov     ecx, 8007000Eh; int
0x18000361d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
