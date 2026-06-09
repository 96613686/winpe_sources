# ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x140002e98`
- end: `0x140002ec3`
- name: `?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400028bc`
- `0x140003fac`
- `0x140006fe8`
- `0x140007258`

## callees

- `0x140002e98`
- `0x140003004`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140002ea4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140002ea4`

## pseudocode

```c
void *__fastcall ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, size_t a2)
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
0x140002e98  push    rbx
0x140002e9a  sub     rsp, 20h
0x140002e9e  mov     rbx, rcx
0x140002ea1  mov     rcx, rdx; Size
0x140002ea4  call    cs:__imp_malloc
0x140002eaa  test    rax, rax
0x140002ead  jz      short loc_140002EB8
0x140002eaf  mov     [rbx], rax
0x140002eb2  add     rsp, 20h
0x140002eb6  pop     rbx
0x140002eb7  retn
0x140002eb8  mov     ecx, 8007000Eh; int
0x140002ebd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
