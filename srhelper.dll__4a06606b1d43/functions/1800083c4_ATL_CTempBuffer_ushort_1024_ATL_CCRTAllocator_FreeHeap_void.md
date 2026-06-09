# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x1800083c4`
- end: `0x1800083ce`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180007534`
- `0x180008e78`

## import_xrefs

- `msvcrt!free` at `0x1800083c7`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x1800083c4  mov     rcx, [rcx]
0x1800083c7  jmp     cs:__imp_free
```
