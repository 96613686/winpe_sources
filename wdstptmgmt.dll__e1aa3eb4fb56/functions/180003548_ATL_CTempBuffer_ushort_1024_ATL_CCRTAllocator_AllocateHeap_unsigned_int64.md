# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180003548`
- end: `0x18000357a`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000304c`
- `0x180004c9c`

## callees

- `0x180003548`
- `0x180003f04`

## import_xrefs

- `msvcrt!malloc` at `0x180003554`
- `msvcrt!malloc` at `0x180003554`

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
0x180003548  push    rbx
0x18000354a  sub     rsp, 20h
0x18000354e  mov     rbx, rcx
0x180003551  mov     rcx, rdx; Size
0x180003554  call    cs:__imp_malloc
0x18000355b  nop     dword ptr [rax+rax+00h]
0x180003560  test    rax, rax
0x180003563  jnz     short loc_180003570
0x180003565  mov     ecx, 8007000Eh; int
0x18000356a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003570  mov     [rbx], rax
0x180003573  add     rsp, 20h
0x180003577  pop     rbx
0x180003578  retn
```
