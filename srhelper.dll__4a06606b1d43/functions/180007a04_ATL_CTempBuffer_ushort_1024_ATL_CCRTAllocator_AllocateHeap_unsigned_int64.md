# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180007a04`
- end: `0x180007a1f`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `27`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180007534`
- `0x180008e78`

## import_xrefs

- `msvcrt!malloc` at `0x180007a10`
- `msvcrt!malloc` at `0x180007a10`

## pseudocode

```c
void *__fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, size_t a2)
{
  void *result; // rax

  result = malloc(a2);
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180007a04  push    rbx
0x180007a06  sub     rsp, 20h
0x180007a0a  mov     rbx, rcx
0x180007a0d  mov     rcx, rdx; Size
0x180007a10  call    cs:__imp_malloc
0x180007a16  mov     [rbx], rax
0x180007a19  add     rsp, 20h
0x180007a1d  pop     rbx
0x180007a1e  retn
```
