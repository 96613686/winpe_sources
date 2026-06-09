# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180012cec`
- end: `0x180012d17`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800126ec`
- `0x180014950`

## callees

- `0x1800065bc`
- `0x180012cec`

## import_xrefs

- `msvcrt!malloc` at `0x180012cf8`
- `msvcrt!malloc` at `0x180012cf8`

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
0x180012cec  push    rbx
0x180012cee  sub     rsp, 20h
0x180012cf2  mov     rbx, rcx
0x180012cf5  mov     rcx, rdx; Size
0x180012cf8  call    cs:__imp_malloc
0x180012cfe  test    rax, rax
0x180012d01  jz      short loc_180012D0C
0x180012d03  mov     [rbx], rax
0x180012d06  add     rsp, 20h
0x180012d0a  pop     rbx
0x180012d0b  retn
0x180012d0c  mov     ecx, 8007000Eh; int
0x180012d11  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
