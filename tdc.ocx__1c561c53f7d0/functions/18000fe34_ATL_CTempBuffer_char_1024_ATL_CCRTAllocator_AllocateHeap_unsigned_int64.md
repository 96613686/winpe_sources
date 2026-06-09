# ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000fe34`
- end: `0x18000fe5f`
- name: `?AllocateHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f804`
- `0x180011800`

## callees

- `0x180003b70`
- `0x18000fe34`

## import_xrefs

- `msvcrt!malloc` at `0x18000fe40`
- `msvcrt!malloc` at `0x18000fe40`

## pseudocode

```c
void *__fastcall ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, size_t a2)
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
0x18000fe34  push    rbx
0x18000fe36  sub     rsp, 20h
0x18000fe3a  mov     rbx, rcx
0x18000fe3d  mov     rcx, rdx; Size
0x18000fe40  call    cs:__imp_malloc
0x18000fe46  test    rax, rax
0x18000fe49  jz      short loc_18000FE54
0x18000fe4b  mov     [rbx], rax
0x18000fe4e  add     rsp, 20h
0x18000fe52  pop     rbx
0x18000fe53  retn
0x18000fe54  mov     ecx, 8007000Eh; int
0x18000fe59  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
