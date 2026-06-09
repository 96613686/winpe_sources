# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x1800038c8`
- end: `0x1800038d2`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c98`
- `0x1800043c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800038cb`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x1800038c8  mov     rcx, [rcx]
0x1800038cb  jmp     cs:__imp_free
```
